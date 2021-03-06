---
title: Application Gateway-Integration mit Dienstendpunkten – Azure App Service | Microsoft-Dokumentation
description: Hier finden Sie Informationen zur Application Gateway-Integration in Azure App Service mit Schutz durch Dienstendpunkte.
services: app-service
documentationcenter: ''
author: madsd
manager: ccompy
editor: ''
ms.assetid: 073eb49c-efa1-4760-9f0c-1fecd5c251cc
ms.service: app-service
ms.workload: web
ms.tgt_pltfrm: na
ms.topic: article
ms.date: 12/09/2019
ms.author: madsd
ms.custom: seodec18
ms.openlocfilehash: 5e32baa10e98f0f57a861f8cebfb7506ad615631
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "74979923"
---
# <a name="application-gateway-integration-with-service-endpoints"></a>Application Gateway-Integration mit Dienstendpunkten
Es gibt drei Varianten von App Service, die jeweils eine etwas andere Konfiguration der Integration mit Azure Application Gateway erfordern. Zu diesen Varianten zählen die reguläre App Service-Instanz (mehrinstanzenfähig) sowie ILB-ASE (Internal Load Balancer App Service Environment, App Service-Umgebung mit internem Lastenausgleich) und die externe ASE. In diesem Artikel erfahren Sie Schritt für Schritt, wie Sie die Konfiguration mit App Service (mehrinstanzenfähig) durchführen, und Sie finden Informationen zu ILB und externer ASE.

## <a name="integration-with-app-service-multi-tenant"></a>Integration mit App Service (mehrinstanzenfähig)
App Service (mehrinstanzenfähig) verfügt über einen öffentlichen Endpunkt mit Internetzugriff. Mithilfe von [Dienstendpunkten](../../virtual-network/virtual-network-service-endpoints-overview.md) können Sie dafür sorgen, dass nur Datenverkehr von einem bestimmten Subnetz innerhalb eines virtuellen Azure-Netzwerks zugelassen und alles andere blockiert wird. Im folgenden Szenario verwenden wir diese Funktion, um sicherzustellen, dass eine App Service-Instanz nur Datenverkehr von einer bestimmten Application Gateway-Instanz empfangen kann.

![Application Gateway-Integration mit App Service](./media/app-gateway-with-service-endpoints/service-endpoints-appgw.png)

Diese Konfiguration umfasst zwei Teile (neben der Erstellung der App Service- und der Application Gateway-Instanz): Der erste Teil besteht darin, Dienstendpunkte im Subnetz des virtuellen Netzwerks zu aktivieren, in dem die Application Gateway-Instanz bereitgestellt wird. Dienstendpunkte sorgen dafür, dass der gesamte Netzwerkdatenverkehr, der das Subnetz in Richtung App Service verlässt, mit der spezifischen Subnetz-ID gekennzeichnet wird. Der zweite Teil besteht darin, eine Zugriffseinschränkung der spezifischen Web-App festzulegen, um sicherzustellen, dass nur Datenverkehr zugelassen wird, der mit dieser spezifischen Subnetz-ID gekennzeichnet ist. Diese Konfiguration kann mit verschiedenen Tools durchgeführt werden.

## <a name="using-azure-portal"></a>Verwenden des Azure-Portals
Im Azure-Portal müssen vier Schritte ausgeführt werden, um das Setup bereitzustellen und zu konfigurieren. Wenn Sie bereits über Ressourcen verfügen, können Sie die ersten Schritte überspringen.
1. Erstellen Sie mithilfe einer der Schnellstartanleitungen aus der App Service-Dokumentation (beispielsweise [Erstellen von ASP.NET Core-Web-Apps in Azure](../../app-service/app-service-web-get-started-dotnet.md)) eine App Service-Instanz.
2. Erstellen Sie gemäß der Schnellstartanleitung [Weiterleiten von Webdatenverkehr per Azure Application Gateway – Azure-Portal](../../application-gateway/quick-create-portal.md) eine Application Gateway-Instanz, überspringen Sie dabei aber den Abschnitt „Hinzufügen von Back-End-Zielen“.
3. Konfigurieren Sie [App Service als Back-End in Application Gateway](../../application-gateway/configure-web-app-portal.md), überspringen Sie dabei aber den Abschnitt „Beschränken des Zugriffs“.
4. Erstellen Sie abschließend die [Zugriffseinschränkung mithilfe von Dienstendpunkten](../../app-service/app-service-ip-restrictions.md#service-endpoints).

Nun können Sie über die Application Gateway-Instanz auf die App Service-Instanz zugreifen. Wenn Sie jedoch versuchen, direkt auf die App Service-Instanz zuzugreifen, erhalten Sie einen HTTP-Fehler vom Typ 403, der angibt, dass die Website beendet wurde.

![Application Gateway-Integration mit App Service](./media/app-gateway-with-service-endpoints/web-site-stopped.png)

## <a name="using-azure-resource-manager-template"></a>Verwenden von Azure Resource Manager-Vorlagen
Die [Resource Manager-Bereitstellungsvorlage][template-app-gateway-app-service-complete] stellt ein vollständiges Szenario bereit. Das Szenario besteht aus einer App Service-Instanz, die durch eine Kombination aus Dienstendpunkten und Zugriffseinschränkung gesperrt wurde, um nur Datenverkehr von Application Gateway zu empfangen. Die Vorlage enthält der Einfachheit halber viele intelligente Standardwerte sowie eindeutige Postfixes für die Ressourcennamen. Wenn Sie diese überschreiben möchten, müssen Sie das Repository klonen oder die Vorlage herunterladen und bearbeiten. 

Die Vorlage kann mithilfe der Schaltfläche „Deploy to Azure“ (In Azure bereitstellen), die in der Beschreibung der Vorlage zur Verfügung steht, oder mithilfe des entsprechenden PowerShell-/CLI-Befehls angewendet werden.

## <a name="using-azure-command-line-interface"></a>Verwenden der Azure-Befehlszeilenschnittstelle (Command Line Interface, CLI)
Das [Azure CLI-Beispiel](../../app-service/scripts/cli-integrate-app-service-with-application-gateway.md) stellt eine App Service-Instanz bereit, die durch eine Kombination aus Dienstendpunkten und Zugriffseinschränkung gesperrt wurde, um nur Datenverkehr von Application Gateway zu empfangen. Wenn Sie lediglich Datenverkehr von einer vorhandenen Application Gateway-Instanz zu einer vorhandenen App Service-Instanz isolieren möchten, genügt der folgende Befehl:

```azurecli-interactive
az webapp config access-restriction add --resource-group myRG --name myWebApp --rule-name AppGwSubnet --priority 200 --subnet mySubNetName --vnet-name myVnetName
```

In der Standardkonfiguration richtet der Befehl sowohl die Dienstendpunktkonfiguration im Subnetz als auch die Zugriffseinschränkung in der App Service-Instanz ein.

## <a name="considerations-for-ilb-ase"></a>Überlegungen zur ILB-ASE
Da eine ILB-ASE nicht für das Internet verfügbar gemacht wird, ist der Datenverkehr zwischen der Instanz und einer Application Gateway-Instanz bereits im virtuellen Netzwerk isoliert. In [dieser Anleitung](../environment/integrate-with-application-gateway.md) wird eine ILB-ASE konfiguriert und über das Azure-Portal in eine Application Gateway-Instanz integriert. 

Wenn Sie sicherstellen möchten, dass nur Datenverkehr aus dem Application Gateway-Subnetz die ASE erreicht, können Sie eine Netzwerksicherheitsgruppe (NSG) konfigurieren, die sich auf alle Web-Apps in der ASE auswirkt. Für die NSG können Sie den IP-Adressbereich des Subnetzes und optional die Ports (80/443) angeben. Achten Sie darauf, die [erforderlichen NSG-Regeln](../environment/network-info.md#network-security-groups) nicht zu überschreiben, da die ASE sonst nicht ordnungsgemäß funktioniert.

Um eingehenden Datenverkehr für eine einzelne Web-App zu isolieren, müssen IP-basierte Zugriffseinschränkungen verwendet werden, da Dienstendpunkte für die ASE nicht geeignet sind. Bei der IP-Adresse muss es sich um die private IP-Adresse der Application Gateway-Instanz handeln.

## <a name="considerations-for-external-ase"></a>Überlegungen zur externen ASE
Die externe ASE verfügt genau wie die mehrinstanzenfähige App Service-Instanz über einen öffentlichen Lastenausgleich. Da Dienstendpunkte für die ASE nicht geeignet sind, müssen IP-basierte Zugriffseinschränkungen mit der öffentlichen IP-Adresse der Application Gateway-Instanz verwendet werden. Wie Sie eine externe ASE über das Azure-Portal erstellen, erfahren Sie in [dieser Schnellstartanleitung](../environment/create-external-ase.md).

[template-app-gateway-app-service-complete]: https://github.com/Azure/azure-quickstart-templates/tree/master/201-web-app-with-app-gateway-v2/ "Azure Resource Manager-Vorlage für das vollständige Szenario"

## <a name="considerations-for-kuduscm-site"></a>Überlegungen zu Kudu bzw. zur SCM-Website
Die SCM-Website (auch Kudu genannt), ist eine für jede Web-App vorhandene Verwaltungswebsite. Für die SCM-Website kann kein Reverseproxy verwendet werden, und es empfiehlt sich, den Zugriff auf einzelne IP-Adressen oder auf ein spezifisches Subnetz zu beschränken.

Wenn Sie die gleichen Zugriffseinschränkungen verwenden möchten wie für die Hauptwebsite, können Sie die Einstellungen mithilfe des folgenden Befehls übernehmen:

```azurecli-interactive
az webapp config access-restriction set --resource-group myRG --name myWebApp --use-same-restrictions-for-scm-site
```

Wenn Sie individuelle Zugriffseinschränkungen für die SCM-Website festlegen möchten, können Sie mithilfe des Flags „--scm-site“ Zugriffseinschränkungen hinzufügen, wie hier zu sehen:

```azurecli-interactive
az webapp config access-restriction add --resource-group myRG --name myWebApp --scm-site --rule-name KudoAccess --priority 200 --ip-address 208.130.0.0/16
```

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zur App Service-Umgebung finden Sie in der [Einführung in die App Service-Umgebungen](https://docs.microsoft.com/azure/app-service/environment).

Unter [Azure Web Application Firewall für Azure Application Gateway](../../web-application-firewall/ag/ag-overview.md) finden Sie Informationen zur Web Application Firewall in Application Gateway, mit der Sie Ihre App noch sicherer machen können.