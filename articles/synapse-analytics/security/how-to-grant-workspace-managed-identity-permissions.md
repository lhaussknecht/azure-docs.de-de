---
title: Gewähren von Berechtigungen für die verwaltete Identität in einem Azure Synapse-Arbeitsbereich
description: In diesem Artikel wird erläutert, wie Berechtigungen für die verwaltete Identität im Azure Synapse-Arbeitsbereich konfiguriert werden.
author: RonyMSFT
ms.service: synapse-analytics
ms.topic: how-to
ms.date: 04/15/2020
ms.author: ronytho
ms.reviewer: jrasnick
ms.openlocfilehash: 9f519022fffe98c565c3b2d30f6578b9ebb70c57
ms.sourcegitcommit: b80aafd2c71d7366838811e92bd234ddbab507b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81426458"
---
# <a name="grant-permissions-to-workspace-managed-identity-preview"></a>Erteilen von Berechtigungen für die verwaltete Identität eines Arbeitsbereichs (Vorschau)

In diesem Artikel erfahren Sie, wie Sie der verwalteten Identität in einem Azure Synapse-Arbeitsbereich Berechtigungen gewähren. Berechtigungen wiederum ermöglichen den Zugriff auf SQL-Pools im Arbeitsbereich und im ADLS Gen2-Speicherkonto über das Azure-Portal.

>[!NOTE]
>Diese verwaltete Identität des Arbeitsbereichs wird im Rest dieses Dokuments als „verwaltete Identität“ bezeichnet.

## <a name="grant-the-managed-identity--permissions-to-the-sql-pool"></a>Gewähren von Berechtigungen für die verwaltete Identität für den SQL-Pool

Die verwaltete Identität gewährt Berechtigungen für die SQL-Pools im Arbeitsbereich. Mit gewährten Berechtigungen können Sie Pipelines orchestrieren, die auf SQL-Pools bezogene Aktivitäten ausführen. Wenn Sie über das Azure-Portal einen Azure Synapse-Arbeitsbereich erstellen, können Sie der verwalteten Identität CONTROL-Berechtigungen für SQL-Pools erteilen.

Wählen Sie beim Erstellen Ihres Azure Synapse-Arbeitsbereichs **Sicherheit + Netzwerk** aus. Wählen Sie dann **Der verwalteten Identität des Arbeitsbereichs die CONTROL-Berechtigung für SQL-Pools erteilen** aus.

![CONTROL-Berechtigung für SQL-Pools](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-16.png)

## <a name="grant-the-managed-identity-permissions-to-adls-gen2-storage-account"></a>Gewähren von Berechtigungen für die verwaltete Identität für das ADLS Gen2-Speicherkonto

Ein ADL Gen2-Speicherkonto ist erforderlich, um einen Azure Synapse-Arbeitsbereich zu erstellen. Um Spark-Pools erfolgreich im Azure Synapse-Arbeitsbereich zu starten, benötigt die verwaltete Azure Synapse-Identität für dieses Speicherkonto die Rolle *Mitwirkender an Storage-Blobdaten*. Die Pipelineorchestrierung in Azure Synapse profitiert ebenfalls von dieser Rolle.

### <a name="grant-permissions-to-managed-identity-during-workspace-creation"></a>Gewähren von Berechtigungen für die verwaltete Identität während der Erstellung eines Arbeitsbereichs

Azure Synapse versucht, der verwalteten Identität die Rolle „Mitwirkender an Storage-Blobdaten“ zu gewähren, nachdem Sie den Azure Synapse-Arbeitsbereich über das Azure-Portal erstellt haben. Die Details zum ADLS Gen2-Speicherkonto stellen Sie auf der Registerkarte **Grundlagen** bereit.

![Registerkarte „Grundlagen“ im Erstellungsfluss des Arbeitsbereichs](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-1.png)

Wählen Sie das ADLS Gen2-Speicherkonto und Dateisystem in **Kontoname** und **Dateisystemname** aus.

![Bereitstellen der Details eines ADLS Gen2-Speicherkontos](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-2.png)

Wenn der Ersteller des Arbeitsbereichs ebenfalls der **Besitzer** des ADLS Gen2-Speicherkontos ist, weist Azure Synapse der verwalteten Identität die Rolle *Mitwirkender an Storage-Blobdaten* zu. Unterhalb der von Ihnen eingegebenen Speicherkontodetails wird die folgende Meldung angezeigt.

![Erfolgreiche Zuweisung von „Mitwirkender an Storage-Blobdaten“.](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-3.png)

Wenn der Ersteller des Arbeitsbereichs nicht der Besitzer des ADLS Gen2-Speicherkontos ist, weist Azure Synapse der verwalteten Identität nicht die Rolle *Mitwirkender an Storage-Blobdaten* zu. Die Meldung, die unter den Speicherkontodetails angezeigt wird, informiert den Ersteller des Arbeitsbereichs, dass er keine ausreichenden Berechtigungen besitzt, um der verwalteten Identität die Rolle *Mitwirkender an Storage-Blobdaten* zu gewähren.

![Nicht erfolgreiche Zuweisung von „Mitwirkender an Storage-Blobdaten“.](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-4.png)

Wie die Meldung besagt, können Sie Spark-Pools nur erstellen, wenn der verwalteten Identität *Mitwirkender an Storage-Blobdaten* zugewiesen wurde.

### <a name="grant-permissions-to-managed-identity-after-workspace-creation"></a>Gewähren von Berechtigungen für die verwaltete Identität nach der Erstellung eines Arbeitsbereichs

Wenn Sie während der Erstellung eines Arbeitsbereichs der verwalteten Identität nicht *Mitwirkender an Storage-Blobdaten* zuweisen, weist der **Besitzer** des ADLS Gen2-Speicherkontos diese Rolle der Identität manuell zu. Die folgenden Schritten helfen Ihnen bei der manuellen Zuweisung.

#### <a name="step-1-navigate-to-the-adls-gen2-storage-account-in-azure-portal"></a>Schritt 1: Navigieren zum ADLS Gen2-Speicherkonto im Azure-Portal

Öffnen Sie im Azure-Portal das ADLS Gen2-Speicherkonto, und wählen Sie im linken Navigationsbereich **Übersicht** aus. Sie müssen die Rolle *Mitwirkender an Storage-Blobdaten* nur auf Container- oder Dateisystemebene zuweisen. Wählen Sie **Container**aus.  
![ADLS Gen2-Speicherkonto – Übersicht](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-5.png)

#### <a name="step-2-select-the-container"></a>Schritt 2: Auswählen des Containers

Die verwaltete Identität sollte über Datenzugriff auf den Container (das Dateisystem) verfügen, der (das) beim Erstellen des Arbeitsbereichs bereitgestellt wurde. Sie finden diesen Container oder das Dateisystem in Azure-Portal. Öffnen Sie den Azure Synapse-Arbeitsbereich im Azure-Portal, und wählen Sie im linken Navigationsbereich die Registerkarte **Übersicht** aus.
![ADLS Gen2-Speicherkontocontainer](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-7.png)


Wählen Sie denselben Container oder dasselbe Dateisystem aus, um der verwalteten Identität die Rolle *Mitwirkender an Storage-Blobdaten* zu gewähren.
![Auswahl des ADLS Gen2-Speicherkontocontainers](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-6.png)

#### <a name="step-3-navigate-to-access-control"></a>Schritt 3: Navigieren zur Zugriffssteuerung

Wählen Sie **Access Control (IAM)** aus.

![Zugriffssteuerung (IAM)](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-8.png)

#### <a name="step-4-add-a-new-role-assignment"></a>Schritt 4: Hinzufügen einer neuen Rollenzuweisung

Wählen Sie **+ Hinzufügen**.

![Neue Rollenzuweisung hinzufügen](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-9.png)

#### <a name="step-5-select-the-rbac-role"></a>Schritt 5: Auswählen der RBAC-Rolle

Wählen Sie die Rolle **Mitwirkender an Storage-Blobdaten** aus.

![Auswählen der RBAC-Rolle](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-10.png)

#### <a name="step-6-select-the-azure-ad-security-principal"></a>Schritt 6: Auswählen des Azure AD-Sicherheitsprinzipals

Wählen Sie in der Dropdownliste **Zugriff zuweisen zu** die Option **Azure AD-Benutzer, -Gruppe oder -Dienstprinzipal** aus.

![AAD-Sicherheitsprinzipal auswählen](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-11.png)

#### <a name="step-7-search-for-the-managed-identity"></a>Schritt 7: Suchen der verwalteten Identität

Der Name der verwalteten Identität ist auch der Name des Arbeitsbereichs. Suchen Sie nach Ihrer verwalteten Identität, indem Sie den Namen Ihres Azure Synapse-Arbeitsbereichs in **Auswählen** eingeben. Die verwaltete Identität sollte aufgeführt werden.

![Die verwaltete Identität suchen](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-12.png)

#### <a name="step-8-select-the-managed-identity"></a>Schritt 8: Auswählen der verwalteten Identität

Wählen Sie die verwaltete Identität für **Ausgewählte Mitglieder** aus. Klicken Sie auf **Speichern**, um die Rollenzuweisung hinzuzufügen.

![Auswählen der verwalteten Identität](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-13.png)

#### <a name="step-9-verify-that-the-storage-blob-data-contributor-role-is-assigned-to-the-managed-identity"></a>Schritt 9: Überprüfen, ob die Rolle „Mitwirkender an Storage-Blobdaten“ der verwalteten Identität für das Speicherkonto zugewiesen ist

Wählen Sie **Zugriffssteuerung (IAM)** und anschließend **Rollenzuweisungen** aus.

![Überprüfen der Rollenzuweisung](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-14.png)

Ihre verwaltete Identität sollte im Abschnitt **Mitwirkender an Storage-Blobdaten** mit der zugewiesenen Rolle *Mitwirkender an Storage-Blobdaten* angezeigt werden. 
![Auswahl des ADLS Gen2-Speicherkontocontainers](./media/how-to-grant-workspace-managed-identity-permissions/configure-workspace-managed-identity-15.png)

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zur [Verwalteten Identität des Arbeitsbereichs](./synapse-workspace-managed-identity.md).
