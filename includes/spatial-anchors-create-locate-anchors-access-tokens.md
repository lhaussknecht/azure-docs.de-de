---
author: ramonarguelles
ms.service: azure-spatial-anchors
ms.topic: include
ms.date: 02/21/2019
ms.author: rgarcia
ms.openlocfilehash: 63725d55e2b2935ec6a899789249259b096865c3
ms.sourcegitcommit: 0947111b263015136bca0e6ec5a8c570b3f700ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "67177786"
---
### <a name="access-tokens"></a>Zugriffstoken

Zugriffstoken sind eine robustere Methode zur Authentifizierung bei Azure Spatial Anchors. Vor allem, wenn Sie Ihre Anwendung für eine Produktionsbereitstellung vorbereiten. Die Zusammenfassung dieses Ansatzes besteht darin, einen Back-End-Dienst einzurichten, bei dem sich Ihre Clientanwendung sicher authentifizieren kann. Ihr Back-End-Dienst kommuniziert zur Runtime mit AAD und mit dem STS-Dienst (Secure Token Service) von Azure Spatial Anchors, um ein Zugriffstoken anzufordern. Dieses Token wird dann der Clientanwendung bereitgestellt und im SDK zur Authentifizierung bei Azure Spatial Anchors verwendet.
