---
title: Verwenden benutzerdefinierter Schemas
description: Tipps für die Verwendung von benutzerdefinierten T-SQL-Schemas zum Entwickeln von Lösungen in einem Synapse SQL-Pool.
services: synapse-analytics
author: XiaoyuMSFT
manager: craigg
ms.service: synapse-analytics
ms.topic: conceptual
ms.subservice: ''
ms.date: 04/17/2018
ms.author: xiaoyul
ms.reviewer: igorstan
ms.custom: seo-lt-2019
ms.openlocfilehash: 7144fa75d156ca7aed9d8215592f89c167cfb221
ms.sourcegitcommit: d597800237783fc384875123ba47aab5671ceb88
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80633465"
---
# <a name="user-defined-schemas-in-synapse-sql-pool"></a>Benutzerdefinierte Schemas in einem Synapse SQL-Pool
Dieser Artikel konzentriert sich auf die Bereitstellung verschiedener Tipps für die Verwendung von benutzerdefinierten T-SQL-Schemas zum Entwickeln von Lösungen in einem Synapse SQL-Pool.

## <a name="schemas-for-application-boundaries"></a>Schemas für Anwendungsgrenzen

Herkömmliche Data Warehouses verwenden häufig separate Datenbanken, um Anwendungsgrenzen auf Basis von Workload, Domäne oder Sicherheit zu erstellen. 

Ein herkömmliches Data Warehouse in SQL Server kann z. B. eine Stagingdatenbank, eine Data Warehouse-Datenbank und einige Data Mart-Datenbanken enthalten. In dieser Topologie funktioniert jede Datenbank als Workload und Sicherheitsgrenze in der Architektur.

Im Gegensatz dazu wird in SQL-Pools die gesamte Data Warehouse-Workload innerhalb einer Datenbank ausgeführt. Datenbankübergreifende Verknüpfungen sind nicht zulässig. SQL-Pools erwarten, dass alle vom Warehouse verwendeten Tabellen innerhalb der einen Datenbank gespeichert werden.

> [!NOTE]
> In einem SQL-Pool werden keine datenbankübergreifenden Abfragen unterstützt. Data Warehouse-Implementierungen, die diese Funktion nutzen, müssen daher überarbeitet werden.
> 
> 

## <a name="recommendations"></a>Empfehlungen
Im Folgenden finden Sie Empfehlungen für die Konsolidierung der Workload-, Sicherheits-, Domänen- und Funktionsgrenzen mithilfe von benutzerdefinierten Schemas:

- Verwenden Sie eine SQL-Pooldatenbank zum Ausführen Ihrer gesamten Data Warehouse-Workload.
- Konsolidieren Sie Ihre vorhandene Data Warehouse-Umgebung zur Verwendung einer SQL-Pooldatenbank.
- Nutzen Sie **benutzerdefinierte Schemas** , um die Grenze bereitzustellen, die zuvor mithilfe von Datenbanken implementiert wurde.

Wenn zuvor keine benutzerdefinierten Schemas verwendet wurden, können Sie von Grund auf neu beginnen. Verwenden Sie einfach den alten Datenbanknamen als Grundlage für Ihre benutzerdefinierten Schemas in der SQL-Pooldatenbank.

Wenn bereits Schemas verwendet wurden, stehen Ihnen einige Optionen zur Verfügung:

- Entfernen Sie die älteren Schemanamen, und beginnen Sie von vorn.
- Behalten Sie die alten Schemanamen bei, indem Sie diese vorab an den Tabellennamen anhängen.
- Behalten Sie die älteren Schemanamen bei, indem Sie Sichten auf die Tabelle in einem zusätzlichen Schema zum Neuerstellen der alten Schemastruktur implementieren.

> [!NOTE]
> Option 3 mag auf den ersten Blick die attraktivste Option sein. Bei genauerem Hinsehen treten jedoch Probleme zutage. Sichten werden nur im SQL-Pool gelesen. Jede Änderung von Daten oder Tabellen muss für die Basistabelle ausgeführt werden. Option 3 führt außerdem eine Schicht von Sichten im System ein. Sie sollten dies besonders berücksichtigen, wenn Sie in Ihrer Architektur bereits Sichten verwenden.
> 
> 

### <a name="examples"></a>Beispiele:
Implementieren von benutzerdefinierten Schemas basierend auf Datenbanknamen:

```sql
CREATE SCHEMA [stg]; -- stg previously database name for staging database
GO
CREATE SCHEMA [edw]; -- edw previously database name for the data warehouse
GO
CREATE TABLE [stg].[customer] -- create staging tables in the stg schema
(       CustKey BIGINT NOT NULL
,       ...
);
GO
CREATE TABLE [edw].[customer] -- create data warehouse tables in the edw schema
(       CustKey BIGINT NOT NULL
,       ...
);
```

Behalten Sie die älteren Schemanamen bei, indem Sie diese vorab an den Tabellennamen anhängen. Verwenden Sie Schemas für die Workloadgrenze:

```sql
CREATE SCHEMA [stg]; -- stg defines the staging boundary
GO
CREATE SCHEMA [edw]; -- edw defines the data warehouse boundary
GO
CREATE TABLE [stg].[dim_customer] --pre-pend the old schema name to the table and create in the staging boundary
(       CustKey BIGINT NOT NULL
,       ...
);
GO
CREATE TABLE [edw].[dim_customer] --pre-pend the old schema name to the table and create in the data warehouse boundary
(       CustKey BIGINT NOT NULL
,       ...
);
```

Behalten Sie die alten Schemanamen mithilfe von Sichten bei:

```sql
CREATE SCHEMA [stg]; -- stg defines the staging boundary
GO
CREATE SCHEMA [edw]; -- stg defines the data warehouse boundary
GO
CREATE SCHEMA [dim]; -- edw defines the legacy schema name boundary
GO
CREATE TABLE [stg].[customer] -- create the base staging tables in the staging boundary
(       CustKey    BIGINT NOT NULL
,       ...
)
GO
CREATE TABLE [edw].[customer] -- create the base data warehouse tables in the data warehouse boundary
(       CustKey    BIGINT NOT NULL
,       ...
)
GO
CREATE VIEW [dim].[customer] -- create a view in the legacy schema name boundary for presentation consistency purposes only
AS
SELECT  CustKey
,       ...
FROM    [edw].customer
;
```

> [!NOTE]
> Jede Änderung in der Schemastrategie erfordert eine Überprüfung des Sicherheitsmodells für die Datenbank. In vielen Fällen können Sie das Sicherheitsmodell vereinfachen, indem Sie Berechtigungen auf Schemaebene zuweisen. Wenn präzisere Berechtigungen erforderlich sind, können Sie Datenbankrollen verwenden.
> 
> 

## <a name="next-steps"></a>Nächste Schritte
Weitere Hinweise zur Entwicklung finden Sie in der [Entwicklungsübersicht](sql-data-warehouse-overview-develop.md).

