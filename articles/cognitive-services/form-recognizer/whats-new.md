---
title: Neuerungen in der Formularerkennung
titleSuffix: Azure Cognitive Services
description: Informieren Sie sich über die neuesten Änderungen an der Formularerkennungs-API.
author: PatrickFarley
manager: nitinme
ms.service: cognitive-services
ms.subservice: forms-recognizer
ms.topic: conceptual
ms.date: 04/14/2020
ms.author: pafarley
ms.openlocfilehash: c2b67989cbffb03eb182b4de2bf471a02ee33e7b
ms.sourcegitcommit: 1895459d1c8a592f03326fcb037007b86e2fd22f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82627992"
---
# <a name="whats-new-in-form-recognizer"></a>Neuerungen in der Formularerkennung

Der Formularerkennungsdienst wird fortlaufend aktualisiert. In diesem Artikel finden Sie aktuelle Informationen zu Featureverbesserungen, Fixes und Dokumentationsaktualisierungen.

> [!NOTE]
> In den Schnellstartanleitungen und Leitfäden für die Formularerkennung wird immer die neueste Version der API verwendet, sofern nicht anders angegeben.

## <a name="april-2020"></a>April 2020

### <a name="new-features"></a>Neue Funktionen
* **SDK-Unterstützung für Version 2.0 der Formularerkennungs-API (Public Preview):** Diesen Monat wurde die Dienstunterstützung um ein Vorschau-SDK für Version 2.0 der Formularerkennung (Vorschauversion) erweitert. Verwenden Sie die folgenden Links, um die ersten Schritte mit Ihrer bevorzugten Sprache auszuführen: 
   * [.NET SDK](https://github.com/Azure/azure-sdk-for-net/tree/master/sdk/formrecognizer/Azure.AI.FormRecognizer)
   * [Java SDK](https://github.com/Azure/azure-sdk-for-java/tree/master/sdk/formrecognizer/azure-ai-formrecognizer)
   * [Python SDK](https://github.com/Azure/azure-sdk-for-python/tree/master/sdk/formrecognizer/azure-ai-formrecognizer)
   * [JavaScript SDK](https://github.com/Azure/azure-sdk-for-js/tree/master/sdk/formrecognizer/ai-form-recognizer)


  Das neue SDK unterstützt alle Features von Version 2.0 der REST-API für die Formularerkennung. Sie können beispielsweise ein Modell mit oder ohne Bezeichnungen trainieren und Text, Schlüssel-Wert-Paare und Tabellen aus Ihren Formularen extrahieren, mit dem vorgefertigten Belegdienst Daten aus Belegen extrahieren sowie mit dem Layoutdienst Text und Tabellen aus Ihren Dokumenten extrahieren. Sie können Ihr Feedback zu den SDKs über das [SDK-Feedbackformular](https://aka.ms/FR_SDK_v1_feedback) teilen.
 
* **Kopieren eines benutzerdefinierten Modells:** Mithilfe der neuen Funktion zum Kopieren benutzerdefinierter Modelle können Sie nun Modelle zwischen Regionen und Abonnements kopieren. Vor dem Aufrufen der API zum Kopieren eines benutzerdefinierten Modells müssen Sie zunächst die Autorisierung zum Kopieren in die Zielressource erhalten, indem Sie den Vorgang für die Kopierautorisierung für den Zielressourcenendpunkt aufrufen.
   * REST-API zum [Generieren einer Kopierautorisierung](https://westus2.dev.cognitive.microsoft.com/docs/services/form-recognizer-api-v2-preview/operations/CopyCustomFormModelAuthorization)
   * REST-API zum [Kopieren eines benutzerdefinierten Modells](https://westus2.dev.cognitive.microsoft.com/docs/services/form-recognizer-api-v2-preview/operations/CopyCustomFormModel) 


## <a name="march-2020"></a>März 2020 

### <a name="new-features"></a>Neue Funktionen

* **Werttypen für die Beschriftung** Sie können nun die Typen der Werte angeben, die Sie mit dem Tool „Formularerkennung“ zur Beschriftung von Beispielen beschriften können. Derzeit werden die folgenden Werttypen und Variationen unterstützt:
  * `string`
    * Standardwert, `no-whitespaces`, `alphanumeric`
  * `number`
    * Standardwert, `currency`
  * `date` 
    * Standardwert, `dmy`, `mdy`, `ymd`
  * `time`
  * `integer`

  Weitere Informationen zur Verwendung dieses Features finden Sie in der Anleitung zum [Tool zum Beschriften von Beispielen](./quickstarts/label-tool.md#specify-tag-value-types).


* **Visualisierung von Tabellen** Im Tool für die Beschriftung von Beispielen werden nun im Dokument erkannte Tabellen angezeigt. Dadurch können Sie die im Dokument erkannten und aus dem Dokument extrahierten Tabellen anzeigen, bevor Sie die Beschriftung und Analyse durchführen. Dieses Feature kann mithilfe der Ebenenoption aktiviert bzw. deaktiviert werden.

  Hier sehen Sie ein Beispiel für die Erkennung und Extraktion von Tabellen:

  > [!div class="mx-imgBorder"]
  > ![Tabellenvisualisierung mit dem Tool für die Beschriftung von Beispielen](./media/whats-new/formre-table-viz.png)

    Die extrahierten Tabellen stehen in der JSON-Ausgabe unter `"pageResults"` zur Verfügung.

  > [!IMPORTANT]
  > Das Beschriften von Tabellen wird nicht unterstützt. Nicht automatisch erkannte und extrahierte Tabellen können nur als Schlüssel-Wert-Paare beschriftet werden. Beim Beschriften von Tabellen als Schlüssel-Wert-Paare muss jede Zelle als eindeutiger Wert beschriftet werden.

### <a name="extraction-enhancements"></a>Extraktionsverbesserungen

Dieses Release bietet Verbesserungen bei der Extraktion sowie eine verbesserte Genauigkeit. Hierzu zählt insbesondere die Möglichkeit, mehrere Schlüssel-Wert-Paare in der gleichen Textzeile zu beschriften und zu extrahieren. 
 
### <a name="sample-labeling-tool-is-now-open-source"></a>Tool für die Beschriftung von Beispielen jetzt als Open-Source-Projekt verfügbar

Das Tool „Formularerkennung“ für die Beschriftung von Beispielen ist jetzt als Open-Source-Projekt verfügbar. Sie können es in Ihre Lösungen integrieren und kundenspezifische Änderungen vornehmen, um es an Ihre individuellen Anforderungen anzupassen.

Weitere Informationen zum Tool „Formularerkennung“ für die Beschriftung von Beispielen finden Sie in der Dokumentation auf [GitHub](https://github.com/microsoft/OCR-Form-Tools/blob/master/README.md).

### <a name="tls-12-enforcement"></a>Erzwingen von TLS 1.2

TLS 1.2 wird nun für alle HTTP-Anforderungen erzwungen, die an diesen Dienst gerichtet werden. Weitere Informationen finden Sie unter [Sicherheit von Azure Cognitive Services](../cognitive-services-security.md).

## <a name="january-2020"></a>Januar 2020

In diesem Release wird die Formularerkennung 2.0 (Vorschauversion) eingeführt. In den folgenden Abschnitten finden Sie weitere Informationen zu neuen Features, Verbesserungen und Änderungen. 

### <a name="new-features"></a>Neue Funktionen

* **Benutzerdefiniertes Modell**
  * **Trainieren mit Bezeichnungen** Sie können jetzt ein benutzerdefiniertes Modell mit manuell gekennzeichneten Daten trainieren. Dies führt zu Modellen mit besserer Leistung und kann Modelle hervorbringen, die mit komplexen Formularen oder Formularen arbeiten, die Werte ohne Schlüssel enthalten.
  * **Asynchrone API** Sie können asynchrone API-Aufrufe verwenden, um mit großen Datasets und Dateien zu trainieren und diese zu analysieren.
  * **Unterstützung von TIFF-Dateien** Sie können jetzt mit TIFF-Dokumenten trainieren und Daten aus ihnen extrahieren.
  * **Verbesserte Extrahierungsgenauigkeit**

* **Vordefiniertes Belegmodell**
  * **Trinkgeldbeträge** Sie können jetzt Trinkgeldbeträge und andere handschriftliche Werte extrahieren.
  * **Extraktion von Zeilenelementen** Sie können Werte von Zeilenelementen aus Belegen extrahieren.
  * **Zuverlässigkeitswerte** Sie können die Zuverlässigkeit des Modells für jeden extrahierten Wert anzeigen.
  * **Verbesserte Extrahierungsgenauigkeit**

* **Layoutextraktion** Sie können nun mit der Layout-API Textdaten und Tabellendaten aus Ihren Formularen extrahieren.

### <a name="custom-model-api-changes"></a>Änderungen an der benutzerdefinierten Modell-API

Alle APIs für das Trainieren und Verwenden benutzerdefinierter Modelle wurden umbenannt, und einige synchrone Methoden sind jetzt asynchron. Dies sind die wichtigsten Änderungen:

* Der Prozess zum Trainieren eines Modells ist jetzt asynchron. Sie initiieren das Training über den API-Aufruf **/custom/models**. Dieser Aufruf gibt eine Vorgangs-ID zurück, die Sie in **custom/models/{modelID}** übergeben können, um die Trainingsergebnisse zurückzugeben.
* Die Schlüssel-Wert-Extraktion wird jetzt vom API-Aufruf **/custom/models/{modelID}/analyze** initiiert. Dieser Aufruf gibt eine Vorgangs-ID zurück, die Sie in **custom/models/{modelID}/analyzeResults/{resultID}** übergeben können, um die Extraktionsergebnisse zurückzugeben.
* Vorgangs-IDs für das Trainieren finden sich jetzt im Header **Location** von HTTP-Antworten, nicht mehr im Header **Operation-Location**.

### <a name="receipt-api-changes"></a>Änderungen an der Beleg-API

Die APIs zum Lesen von Belegen wurden umbenannt.

* Die Extraktion von Belegdaten wird jetzt vom API-Aufruf **/prebuilt/receipt/analyze** initiiert. Dieser Aufruf gibt eine Vorgangs-ID zurück, die Sie in **/prebuilt/receipt/analyzeResults/{resultID}** übergeben können, um die Extraktionsergebnisse zurückzugeben.

### <a name="output-format-changes"></a>Änderungen am Ausgabeformat

Die JSON-Antworten für alle API-Aufrufe haben neue Formate. Es wurden einige Schlüssel und Werte hinzugefügt, entfernt oder umbenannt. Beispiele für die aktuellen JSON-Formate finden Sie in den Schnellstarts.

## <a name="next-steps"></a>Nächste Schritte

Absolvieren Sie einen [Schnellstart](quickstarts/curl-train-extract.md) zu den ersten Schritten mit den [Formularerkennungs-APIs](https://westus2.dev.cognitive.microsoft.com/docs/services/form-recognizer-api-v2-preview/operations/AnalyzeWithCustomForm).