---
title: Aufrufen einer Web-API aus einer Daemon-App – Microsoft Identity Platform | Azure
description: Erfahren Sie, wie Sie eine Daemon-App erstellen, die Web-APIs aufruft.
services: active-directory
author: jmprieur
manager: CelesteDG
ms.service: active-directory
ms.subservice: develop
ms.topic: conceptual
ms.workload: identity
ms.date: 10/30/2019
ms.author: jmprieur
ms.custom: aaddev
ms.openlocfilehash: e440628526dada7655cc71f63fc9fff006cc5ef5
ms.sourcegitcommit: 849bb1729b89d075eed579aa36395bf4d29f3bd9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "80885445"
---
# <a name="daemon-app-that-calls-web-apis---call-a-web-api-from-the-app"></a>Daemon-App, die Web-APIs aufruft – Aufrufen einer Web-API aus der App

.NET-Daemon-Apps können eine Web-API aufrufen. .NET-Daemon-Apps können auch mehrere vorab genehmigte Web-APIs aufrufen.

## <a name="calling-a-web-api-from-a-daemon-application"></a>Aufrufen einer Web-API aus einer Daemonanwendung

Gehen Sie wie folgt vor, um eine API unter Verwendung des Tokens aufzurufen:

# <a name="net"></a>[.NET](#tab/dotnet)

[!INCLUDE [Call web API in .NET](../../../includes/active-directory-develop-scenarios-call-apis-dotnet.md)]

# <a name="python"></a>[Python](#tab/python)

```Python
endpoint = "url to the API"
http_headers = {'Authorization': 'Bearer ' + result['access_token'],
                'Accept': 'application/json',
                'Content-Type': 'application/json'}
data = requests.get(endpoint, headers=http_headers, stream=False).json()
```

# <a name="java"></a>[Java](#tab/java)

```Java
HttpURLConnection conn = (HttpURLConnection) url.openConnection();

// Set the appropriate header fields in the request header.
conn.setRequestProperty("Authorization", "Bearer " + accessToken);
conn.setRequestProperty("Accept", "application/json");

String response = HttpClientHelper.getResponseStringFromConn(conn);

int responseCode = conn.getResponseCode();
if(responseCode != HttpURLConnection.HTTP_OK) {
    throw new IOException(response);
}

JSONObject responseObject = HttpClientHelper.processResponse(responseCode, response);
```

---

## <a name="calling-several-apis"></a>Aufrufen mehrerer APIs

Für Daemon-Apps müssen die von Ihnen aufgerufenen Web-APIs vorab genehmigt werden. Es gibt keine inkrementelle Einwilligung für Daemon-Apps. (Es gibt keine Benutzerinteraktion.) Der Mandantenadministrator muss vorab in die Berechtigungen für die Anwendung und alle APIs einwilligen. Wenn Sie mehrere APIs aufrufen möchten, müssen Sie für jede Ressource ein Token abrufen, indem Sie jedes Mal `AcquireTokenForClient` aufrufen. MSAL verwendet den Tokencache der Anwendung, um unnötige Dienstaufrufe zu vermeiden.

## <a name="next-steps"></a>Nächste Schritte

# <a name="net"></a>[.NET](#tab/dotnet)

> [!div class="nextstepaction"]
> [Daemon app - move to production (Daemon-App – Übergang in die Produktion)](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-production?tabs=dotnet)

# <a name="python"></a>[Python](#tab/python)

> [!div class="nextstepaction"]
> [Daemon app - move to production (Daemon-App – Übergang in die Produktion)](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-production?tabs=python)

# <a name="java"></a>[Java](#tab/java)

> [!div class="nextstepaction"]
> [Daemon app - move to production (Daemon-App – Übergang in die Produktion)](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-production?tabs=java)

---
