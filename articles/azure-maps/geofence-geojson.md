---
title: GeoJSON-Datenformat für Geofence | Microsoft Azure Maps
description: In diesem Artikel erfahren Sie, wie die Geofencedaten vorbereitet werden, die in der GET- und POST-Geofence-API von Microsoft Azure Maps verwendet werden können.
author: philmea
ms.author: philmea
ms.date: 02/14/2019
ms.topic: conceptual
ms.service: azure-maps
services: azure-maps
manager: ''
ms.openlocfilehash: 7b9860908dd3bdf3dcda727f350578a97b890cac
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "80335619"
---
# <a name="geofencing-geojson-data"></a>Geofencing von GeoJSON-Daten

Die Azure Maps-APIs [GET Geofence](/rest/api/maps/spatial/getgeofence) und [POST Geofence](/rest/api/maps/spatial/postgeofence) ermöglichen Ihnen das Abrufen der Nähe einer Koordinate bezogen auf einen bereitgestellten Geofence oder eine Reihe von Geofences. In diesem Artikel wird detailliert beschrieben, wie die Geofencedaten, die in der Azure Maps GET- und POST-API verwendet werden können, vorbereitet werden.

Die Daten für einen Geofence oder eine Reihe von Geofences werden durch das `Feature`-Objekt und das `FeatureCollection`-Objekt im `GeoJSON`-Format dargestellt, das in [RFC7946](https://tools.ietf.org/html/rfc7946) beschrieben ist. Weitere Merkmale:

* Der GeoJSON-Objekttyp kann ein `Feature`-Objekt oder ein `FeatureCollection`-Objekt sein.
* Der Geometry-Objekttyp kann ein `Point`, `MultiPoint`, `LineString`, `MultiLineString`, `Polygon`, `MultiPolygon` oder `GeometryCollection` sein.
* Alle Featureeigenschaften sollten eine `geometryId` enthalten, die zur Identifikation des Geofence verwendet wird.
* Features mit `Point`, `MultiPoint`, `LineString` oder `MultiLineString` müssen in ihren Eigenschaften `radius` enthalten. Der `radius`-Wert wird in Metern gemessen, der Wert von `radius` reicht von 1 bis 10000.
* Features mit dem Geometrietyp `polygon` und `multipolygon` weisen keine Radiuseigenschaft auf.
* `validityTime` ist eine optionale Eigenschaft, die dem Benutzer das Festlegen von Ablaufzeit und Gültigkeitsdauer für die Geofencedaten ermöglicht. Ohne Angabe laufen die Daten nicht ab und bleiben unbeschränkt gültig.
* Die `expiredTime` stellt Ablaufdatum und -uhrzeit der Geofencingdaten dar. Wenn der Wert von `userTime` in der Anforderung später ist als dieser Wert, werden die entsprechenden Geofencedaten als abgelaufen angesehen und nicht abgefragt. Daraufhin wird die geometryId dieser Geofencedaten in das Array `expiredGeofenceGeometryId` in der Geofenceantwort aufgenommen.
* Die `validityPeriod` ist eine Liste der Gültigkeitszeiträume des Geofence. Wenn der Wert von `userTime` in der Anforderung außerhalb der Gültigkeitsdauer liegt, werden die entsprechenden Geofencedaten als ungültig angesehen und nicht abgefragt. Die geometryId dieser Geofencedaten wird in das Array `invalidPeriodGeofenceGeometryId` in der Geofenceantwort aufgenommen. In der folgenden Tabelle sind die Eigenschaften des ValidityPeriod-Elements dargestellt.

| Name | type | Erforderlich  | BESCHREIBUNG |
| :------------ |:------------: |:---------------:| :-----|
| startTime | Datetime  | true | Das Anfangsdatum und die Anfangsuhrzeit der Gültigkeitsdauer. |
| endTime   | Datetime  | true |  Das Enddatum und die Enduhrzeit der Gültigkeitsdauer. |
| recurrenceType | Zeichenfolge | false |   Der Wiederholungstyp des Zeitraums. Der Wert kann `Daily`, `Weekly`, `Monthly` oder `Yearly` lauten. Der Standardwert ist `Daily`.|
| businessDayOnly | Boolean | false |  Gibt an, ob die Daten nur an Werktagen gültig sind. Der Standardwert ist `false`.|


* Alle Koordinatenwerte werden als [Breitengrad, Längengrad] gemäß der Definition in `WGS84` dargestellt.
* Bei allen Features, die `MultiPoint`, `MultiLineString`, `MultiPolygon` oder `GeometryCollection` enthalten gelten die Eigenschaften für alle Elemente. Beispiel: Alle Punkte in `MultiPoint` verwenden den gleichen Radius, um einen Geofence aus mehreren Kreisen zu bilden.
* Im Punkt-Kreis-Szenario kann eine Kreisgeometrie mithilfe eines `Point`-Geometrieobjekts dargestellt werden, dessen Eigenschaften in [Erweitern der GeoJSON-Geometrien](https://docs.microsoft.com/azure/azure-maps/extend-geojson) dargelegt sind.      

Das Folgende ist ein Beispielanforderungstext für einen Geofence, der als Kreis-Geofencegeometrie in `GeoJSON` dargestellt ist und einen Mittelpunkt sowie einen Radius verwendet. Der Gültigkeitszeitraum der Geofencedaten beginnt am 22.10.2018 von 9 Uhr bis 17 Uhr. Die Gültigkeit wiederholt sich täglich mit Ausnahme der Wochenenden. `expiredTime` gibt an, dass diese Geofencedaten als abgelaufen angesehen werden, falls `userTime` in der Anforderung später als `2019-01-01` ist.  

```json
{
    "type": "Feature",
    "geometry": {
        "type": "Point",
        "coordinates": [-122.126986, 47.639754]
    },
    "properties": {
        "geometryId" : "1",
        "subType": "Circle",
        "radius": 500,
        "validityTime": 
        {
            "expiredTime": "2019-01-01T00:00:00",
            "validityPeriod": [
                {
                    "startTime": "2018-10-22T09:00:00",
                    "endTime": "2018-10-22T17:00:00",
                    "recurrenceType": "Daily",
                    "recurrenceFrequency": 1,
                    "businessDayOnly": true
                }
            ]
        }
    }
}
```
