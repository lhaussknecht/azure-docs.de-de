---
title: 'Azure CLI-Skriptbeispiel: Abonnieren eines Azure-Abonnements | Microsoft-Dokumentation'
description: In diesem Artikel wird anhand eines Beispielskripts für die Azure-Befehlszeilenschnittstelle das Abonnieren von Azure Event Grid-Ereignissen unter Verwendung der Azure-Befehlszeilenschnittstelle veranschaulicht.
services: event-grid
documentationcenter: na
author: spelluru
ms.service: event-grid
ms.devlang: azurecli
ms.topic: sample
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/23/2020
ms.author: spelluru
ms.openlocfilehash: 9d40367c8d0f4f1250504c30fcd6c4846921a830
ms.sourcegitcommit: 0947111b263015136bca0e6ec5a8c570b3f700ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "76720893"
---
# <a name="subscribe-to-events-for-an-azure-subscription-with-azure-cli"></a>Abonnieren von Ereignissen für ein Azure-Abonnement mit der Azure CLI

Dieses Skript erstellt ein Event Grid-Abonnement für die Ereignisse für ein Azure-Abonnement.

[!INCLUDE [sample-cli-install](../../../includes/sample-cli-install.md)]

[!INCLUDE [quickstarts-free-trial-note](../../../includes/quickstarts-free-trial-note.md)]

Für das Vorschaubeispielskript ist die Event Grid-Erweiterung erforderlich. Führen Sie zum Installieren `az extension add --name eventgrid` aus.

## <a name="sample-script---stable"></a>Beispielskript: stabil

[!code-azurecli[main](../../../cli_scripts/event-grid/subscribe-to-azure-subscription/subscribe-to-azure-subscription.sh "Subscribe to Azure subscription")]

## <a name="sample-script---preview-extension"></a>Beispielskript: Vorschauerweiterung

[!code-azurecli[main](../../../cli_scripts/event-grid/subscribe-to-azure-subscription-preview/subscribe-to-azure-subscription-preview.sh "Subscribe to Azure subscription")]

## <a name="script-explanation"></a>Erläuterung des Skripts

Dieses Skript verwendet den folgenden Befehl, um das Ereignisabonnement zu erstellen. Jeder Befehl in der Tabelle ist mit der zugehörigen Dokumentation verknüpft.

| Get-Help | Notizen |
|---|---|
| [az eventgrid event-subscription create](/cli/azure/eventgrid/event-subscription#az-eventgrid-event-subscription-create) | Erstellen Sie ein Event Grid-Abonnement. |
| [az eventgrid event-subscription create](/cli/azure/ext/eventgrid/eventgrid/event-subscription#ext-eventgrid-az-eventgrid-event-subscription-create) - extension version | Erstellen Sie ein Event Grid-Abonnement. |

## <a name="next-steps"></a>Nächste Schritte

* Informationen zum Abfragen von Abonnements finden Sie unter [Abfragen von Event Grid-Abonnements](../query-event-subscriptions.md).
* Weitere Informationen zur Azure CLI finden Sie in der [Azure CLI-Dokumentation](https://docs.microsoft.com/cli/azure).
