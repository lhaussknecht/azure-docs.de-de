---
title: 'Clientbibliothek für die Bing-Vorschlagssuche für C#: Schnellstart'
titleSuffix: Azure Cognitive Services
services: cognitive-services
author: aahill
manager: nitinme
ms.service: cognitive-services
ms.topic: include
ms.date: 04/06/2020
ms.author: aahi
ms.openlocfilehash: ac46eb0119ac95cf09e48823686a6c563d8d4d4a
ms.sourcegitcommit: d187fe0143d7dbaf8d775150453bd3c188087411
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "80887363"
---
Beginnen Sie mit dem Einsatz der Clientbibliothek für die Bing-Vorschlagssuche für .NET. Führen Sie die nachfolgenden Schritte zum Installieren des Pakets aus, und testen Sie den Beispielcode für grundlegende Aufgaben.

Verwenden Sie die Clientbibliothek für die Bing-Vorschlagssuche für .NET, um Suchvorschläge basierend auf Abfragen mit Teilzeichenfolgen zu erhalten.

[Referenzdokumentation](https://docs.microsoft.com/dotnet/api/overview/azure/cognitiveservices/client/bingautosuggest?view=azure-dotnet) | [Quellcode der Bibliothek](https://github.com/Azure/azure-sdk-for-net/tree/master/sdk/cognitiveservices/Search.BingAutoSuggest) | [Paket (NuGet)](https://www.nuget.org/packages/Microsoft.Azure.CognitiveServices.Search.AutoSuggest/) | [Beispiele](https://github.com/Azure-Samples/cognitive-services-quickstart-code/blob/master/dotnet/BingAutoSuggest/Program.cs)

## <a name="prerequisites"></a>Voraussetzungen

* Azure-Abonnement – [Erstellen eines kostenlosen Kontos](https://azure.microsoft.com/free/)
* Aktuelle Version von [.NET Core](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="setting-up"></a>Einrichten

### <a name="create-an-azure-resource"></a>Erstellen einer Azure-Ressource

[!INCLUDE [cognitive-services-bing-autosuggest-signup-requirements](~/includes/cognitive-services-bing-autosuggest-signup-requirements.md)]

### <a name="create-an-environment-variable"></a>Erstellen einer Umgebungsvariablen

>[!NOTE]
> Nach dem 1. Juli 2019 erstellte Endpunkte für Ressourcen, bei denen es sich nicht um Testressourcen handelt, verwenden das unten gezeigte benutzerdefinierte Format für Subdomänen. Weitere Informationen und eine vollständige Liste mit regionalen Endpunkten finden Sie unter [Benutzerdefinierte Unterdomänennamen für Cognitive Services](https://docs.microsoft.com/azure/cognitive-services/cognitive-services-custom-subdomains). 

Erstellen Sie unter Verwendung des Schlüssels und des Endpunkts der von Ihnen erstellten Ressource zwei Umgebungsvariablen für die Authentifizierung:
<!-- replace the below variable names with the names expected in the code sample.-->
* `AUTOSUGGEST_SUBSCRIPTION_KEY`: Der Ressourcenschlüssel zum Authentifizieren Ihrer Anforderungen.
* `AUTOSUGGEST_ENDPOINT`: Der Ressourcenendpunkt zum Senden von API-Anforderungen. Er sieht wie folgt aus: 
  * `https://<your-custom-subdomain>.api.cognitive.microsoft.com` 

Führen Sie die Schritte für Ihr Betriebssystem aus:
<!-- replace the below endpoint and key examples -->
#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx AUTOSUGGEST_SUBSCRIPTION_KEY <replace-with-your-autosuggest-api-key>
setx AUTOSUGGEST_ENDPOINT <replace-with-your-autosuggest-api-endpoint>
```

Starten Sie das Konsolenfenster neu, nachdem Sie die Umgebungsvariable hinzugefügt haben.

#### <a name="linux"></a>[Linux](#tab/linux)

```bash
export AUTOSUGGEST_SUBSCRIPTION_KEY=<replace-with-your-autosuggest-api-key>
export AUTOSUGGEST_ENDPOINT=<replace-with-your-autosuggest-api-endpoint>
```

Führen Sie nach dem Hinzufügen der Umgebungsvariablen im Konsolenfenster `source ~/.bashrc` aus, damit die Änderungen wirksam werden.

#### <a name="macos"></a>[macOS](#tab/unix)

Bearbeiten Sie `.bash_profile`, und fügen Sie die Umgebungsvariable hinzu:

```bash
export AUTOSUGGEST_SUBSCRIPTION_KEY=<replace-with-your-autosuggest-api-key>
export AUTOSUGGEST_ENDPOINT=<replace-with-your-autosuggest-api-endpoint>
```

Führen Sie nach dem Hinzufügen der Umgebungsvariablen im Konsolenfenster `source .bash_profile` aus, damit die Änderungen wirksam werden.
***

### <a name="create-a-new-c-application"></a>Erstellen einer neuen C#-Anwendung

Erstellen Sie eine neue .NET Core-Anwendung in Ihrem bevorzugten Editor oder Ihrer bevorzugten IDE. 

Verwenden Sie in einem Konsolenfenster (z. B. cmd, PowerShell oder Bash) den Befehl `dotnet new` zum Erstellen einer neuen Konsolen-App mit dem Namen `bing-autosuggest-quickstart`. Dieser Befehl erstellt ein einfaches C#-Projekt vom Typ „Hallo Welt“ mit einer einzelnen Quelldatei: *program.cs*. 

```console
dotnet new console -n bing-autosuggest-quickstart
```

Wechseln Sie zum Ordner der neu erstellten App. Sie können die Anwendung mit folgendem Befehl erstellen:

```console
dotnet build
```

Die Buildausgabe sollte keine Warnungen oder Fehler enthalten. 

```console
...
Build succeeded.
 0 Warning(s)
 0 Error(s)
...
```

Öffnen Sie über das Projektverzeichnis die Datei *program.cs* in Ihrem bevorzugten Editor oder Ihrer bevorzugten IDE. Fügen Sie die folgenden `using`-Anweisungen hinzu:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

Erstellen Sie in der `Program`-Klasse Variablen für den Azure-Endpunkt und -Schlüssel Ihrer Ressource. Wenn Sie die Umgebungsvariable nach dem Start der Anwendung erstellt haben, müssen der Editor, die IDE oder die Shell, in dem bzw. der sie ausgeführt wird, geschlossen und erneut geöffnet werden, damit der Zugriff auf die Variable möglich ist.

```csharp
private const string key_var = "AUTOSUGGEST_SUBSCRIPTION_KEY";
private static readonly string subscription_key = Environment.GetEnvironmentVariable(key_var);

// Note you must use the same region as you used to get your subscription key.
private const string endpoint_var = "AUTOSUGGEST_ENDPOINT";
private static readonly string endpoint = Environment.GetEnvironmentVariable(endpoint_var);
```

Fügen Sie in der `Main`-Methode der Anwendung folgende Methodenaufrufe hinzu (diese werden Sie später definieren).

```csharp
static void Main(string[] args)
{
    Task.WaitAll(RunQuickstart());
    Console.WriteLine("Press any key to exit.");
    Console.Read();
}
```

### <a name="install-the-client-library"></a>Installieren der Clientbibliothek

Installieren Sie im Anwendungsverzeichnis mit dem folgenden Befehl die Clientbibliothek für die Bing-Vorschlagssuche für .NET:

```console
dotnet add package Microsoft.Azure.CognitiveServices.Search.AutoSuggest --version 2.0.0
```

Bei Verwendung der Visual Studio-IDE ist die Clientbibliothek als herunterladbares NuGet-Paket verfügbar.

## <a name="code-examples"></a>Codebeispiele

Diese Codeausschnitte veranschaulichen, wie folgende Vorgänge mit der Clientbibliothek für die Bing-Vorschlagssuche für .NET ausgeführt werden:

* [Authentifizieren des Clients](#authenticate-the-client)
* [Senden einer Anforderung für die Vorschlagssuche](#send-an-autosuggest-request)

## <a name="authenticate-the-client"></a>Authentifizieren des Clients

> [!NOTE]
> In dieser Schnellstartanleitung wird vorausgesetzt, dass Sie eine [Umgebungsvariable](https://docs.microsoft.com/azure/cognitive-services/cognitive-services-apis-create-account#configure-an-environment-variable-for-authentication) namens `AUTOSUGGEST_SUBSCRIPTION_KEY` für Ihren Schlüssel für die Bing-Vorschlagssuche sowie eine weitere Umgebungsvariable namens `AUTOSUGGEST_ENDPOINT` für Ihren Endpunkt erstellt haben.


Instanziieren Sie in einer neuen asynchronen Methode einen Client mit Ihrem Endpunkt und Schlüssel. Erstellen Sie ein [ApiKeyServiceClientCredentials](https://docs.microsoft.com/dotnet/api/microsoft.azure.cognitiveservices.search.autosuggest.apikeyserviceclientcredentials?view=azure-dotnet)-Objekt mit Ihrem Schlüssel, und verwenden Sie dieses mit Ihrem Endpunkt, um ein [AutosuggestClient](https://docs.microsoft.com/dotnet/api/microsoft.azure.cognitiveservices.search.autosuggest.autosuggestclient?view=azure-dotnet)-Objekt zu erstellen.

```csharp
async static Task RunQuickstart()
{
    // Generate the credentials and create the client.
    var credentials = new Microsoft.Azure.CognitiveServices.Search.AutoSuggest.ApiKeyServiceClientCredentials(subscription_key);
    var client = new AutoSuggestClient(credentials, new System.Net.Http.DelegatingHandler[] { })
    {
        Endpoint = endpoint
    };
}
```

## <a name="send-an-autosuggest-request"></a>Senden einer Anforderung für die Vorschlagssuche

Verwenden Sie in derselben Methode die [AutoSuggestMethodAsync](https://docs.microsoft.com/dotnet/api/microsoft.azure.cognitiveservices.search.autosuggest.autosuggestclientextensions.autosuggestmethodasync?view=azure-dotnet#Microsoft_Azure_CognitiveServices_Search_AutoSuggest_AutoSuggestClientExtensions_AutoSuggestMethodAsync_Microsoft_Azure_CognitiveServices_Search_AutoSuggest_IAutoSuggestClient_System_String_System_String_System_String_System_String_System_String_System_String_System_String_System_String_System_String_System_String_System_String_System_Collections_Generic_IList_System_String__System_Threading_CancellationToken_)-Methode des Clients, um eine Abfrage an Bing zu senden. Durchlaufen Sie dann die [Suggestion](https://docs.microsoft.com/dotnet/api/microsoft.azure.cognitiveservices.search.autosuggest.models.suggestions?view=azure-dotnet)-Antwort, und geben Sie den ersten Vorschlag aus.

```csharp
var result = await client.AutoSuggestMethodAsync("xb");
var groups = result.SuggestionGroups;
if (groups.Count > 0) {
    var group = groups[0];
    Console.Write("First suggestion group: {0}\n", group.Name);
    var suggestions = group.SearchSuggestions;
    if (suggestions.Count > 0)
    {
        Console.WriteLine("First suggestion:");
        Console.WriteLine("Query: {0}", suggestions[0].Query);
        Console.WriteLine("Display text: {0}", suggestions[0].DisplayText);
    }
    else
    {
        Console.WriteLine("No suggestions found in this group.");
    }
}
else
{
    Console.WriteLine("No suggestions found.");
}
```

## <a name="run-the-application"></a>Ausführen der Anwendung

Führen Sie die Anwendung mit dem Befehl `dotnet run` aus dem Anwendungsverzeichnis aus.

```dotnet
dotnet run
```

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

Wenn Sie ein Cognitive Services-Abonnement bereinigen und entfernen möchten, können Sie die Ressource oder die Ressourcengruppe löschen. Wenn Sie die Ressourcengruppe löschen, werden auch alle anderen Ressourcen gelöscht, die ihr zugeordnet sind.

* [Portal](../../../cognitive-services-apis-create-account.md#clean-up-resources)
* [Azure-Befehlszeilenschnittstelle](../../../cognitive-services-apis-create-account-cli.md#clean-up-resources)

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Tutorial für die Bing-Vorschlagssuche](../../tutorials/autosuggest.md)

## <a name="see-also"></a>Weitere Informationen

- [Worum handelt es sich bei der Bing-Vorschlagssuche?](../../get-suggested-search-terms.md)
- [Referenz für die Bing-Vorschlagssuche für .NET](https://docs.microsoft.com/dotnet/api/overview/azure/cognitiveservices/client/bingautosuggest?view=azure-dotnet)
