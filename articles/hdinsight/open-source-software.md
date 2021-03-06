---
title: Open-Source-Softwareunterstützung in Azure HDInsight
description: Microsoft Azure bietet lediglich allgemeinen Support für Open-Source-Technologien.
author: hrasheed-msft
ms.author: hrasheed
ms.reviewer: jasonh
ms.service: hdinsight
ms.topic: conceptual
ms.custom: seoapr2020
ms.date: 04/21/2020
ms.openlocfilehash: 65f21450f194175af37c6c198468978392cee462
ms.sourcegitcommit: 849bb1729b89d075eed579aa36395bf4d29f3bd9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82195161"
---
# <a name="open-source-software-support-in-azure-hdinsight"></a>Open-Source-Softwareunterstützung in Azure HDInsight

Der Dienst Microsoft Azure HDInsight verwendet eine Umgebung von Open-Source-Technologien für Apache Hadoop. Microsoft Azure bietet lediglich allgemeinen Support für Open-Source-Technologien. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zum Azure-Support](https://azure.microsoft.com/support/faq/) im Abschnitt **Supportumfang**. Der HDInsight-Dienst bietet zusätzliche Unterstützung für integrierte Komponenten.

## <a name="components"></a>Komponenten

Im HDInsight-Dienst sind zwei Arten von Open-Source-Komponenten verfügbar:

### <a name="built-in-components"></a>Integrierte Komponenten

Diese Komponenten sind in HDInsight-Clustern vorinstalliert und stellen Kernfunktionen des Clusters bereit. Zu dieser Kategorie gehören folgende Komponenten:

* [Apache Hadoop YARN](https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html) (Ressourcen-Manager)
* Die Hive-Abfragesprache [HiveQL](https://cwiki.apache.org/confluence/display/Hive/LanguageManual)
* [Apache Mahout](https://mahout.apache.org/)

Eine vollständige Liste der Clusterkomponenten finden Sie unter [Welche Apache Hadoop-Komponenten und -Versionen sind in HDInsight verfügbar?](hdinsight-component-versioning.md).

### <a name="custom-components"></a>Benutzerdefinierte Komponenten

Als Benutzer des Clusters können Sie in Ihrer Workload eine beliebige, in der Community verfügbare oder von Ihnen erstellte Komponente installieren oder verwenden.

> [!WARNING]  
> Mit dem HDInsight-Cluster bereitgestellte Komponenten werden vollständig unterstützt. Der Microsoft-Support unterstützt Sie beim Isolieren und Beheben von Problemen im Zusammenhang mit diesen Komponenten.
>
> Für benutzerdefinierte Komponenten steht wirtschaftlich angemessener Support für eine weiterführende Behandlung des Problems zur Verfügung. Unter Umständen kann Ihnen der Microsoft-Support bei der Lösung des Problems helfen. Möglicherweise werden Sie auch gebeten, verfügbare Kanäle für die Open-Source-Technologien in Anspruch zu nehmen, die über umfassende Kenntnisse für diese Technologien verfügen. Hierzu kommen zahlreiche Communitywebsites in Frage. Beispiele hierfür sind das [MSDN-Forum für HDInsight](https://social.msdn.microsoft.com/Forums/azure/home?forum=hdinsight) und [Stack Overflow](https://stackoverflow.com).
>
> Für Apache-Projekte stehen auf der [Apache-Website](https://apache.org) auch Projektwebsites zur Verfügung. Ein Beispiel hierfür ist [Hadoop](https://hadoop.apache.org/).

## <a name="component-usage"></a>Komponentennutzung

Der HDInsight-Dienst bietet mehrere Möglichkeiten, benutzerdefinierte Komponenten zu verwenden. Der Supportumfang ist unabhängig davon, wie die Komponente verwendet oder im Cluster installiert wird. Die folgende Tabelle enthält Beschreibungen der gängigsten Möglichkeiten für die Verwendung benutzerdefinierter Komponenten in HDInsight-Clustern:

|Verwendung |BESCHREIBUNG |
|---|---|
|Auftragsübermittlung|Hadoop-Aufträge und andere Auftragstypen, die benutzerdefinierte Komponenten ausführen oder verwenden, können an den Cluster übermittelt werden.|
|Clusteranpassung|Während der Clustererstellung können Sie zusätzliche Einstellungen und benutzerdefinierte Komponenten angeben, die auf den Clusterknoten installiert werden.|
|Beispiele|Für beliebte benutzerdefinierte Komponenten stellen Microsoft und andere Anbieter ggf. Beispiele für die Verwendung dieser Komponenten in HDInsight-Clustern bereit. Für diese Beispiele wird kein Support bereitgestellt.|

## <a name="next-steps"></a>Nächste Schritte

* [Anpassen von Azure HDInsight-Clustern mithilfe von Skriptaktionen](./hdinsight-hadoop-customize-cluster-linux.md)
* [Entwickeln von Skriptaktionsskripts für HDInsight](hdinsight-hadoop-script-actions-linux.md)
* [Sicheres Verwalten der Python-Umgebung in Azure HDInsight mithilfe einer Skriptaktion](./spark/apache-spark-python-package-installation.md)
