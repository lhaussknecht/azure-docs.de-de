---
title: Einrichten der Registrierung und Anmeldung mit einem Facebook-Konto
titleSuffix: Azure AD B2C
description: Bereitstellen von Registrierung und Anmeldung für Kunden mit Facebook-Konten in Ihren Anwendungen mithilfe von Azure Active Directory B2C.
services: active-directory-b2c
author: msmimart
manager: celestedg
ms.service: active-directory
ms.workload: identity
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: mimart
ms.subservice: B2C
ms.openlocfilehash: cd0e19de88a6a65d72a2e7e19f7fca2a94d8da55
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "78188272"
---
# <a name="set-up-sign-up-and-sign-in-with-a-facebook-account-using-azure-active-directory-b2c"></a>Einrichten der Registrierung und Anmeldung mit einem Facebook-Konto mithilfe von Azure Active Directory B2C

## <a name="create-a-facebook-application"></a>Erstellen einer Facebook-Anwendung

Um ein Facebook-Konto als [Identitätsanbieter](authorization-code-flow.md) in Azure Active Directory B2C (Azure AD B2C) verwenden zu können, müssen Sie in Ihrem Mandanten eine Anwendung erstellen, die es darstellt. Wenn Sie noch über kein Facebook-Konto verfügen, können Sie sich unter [https://www.facebook.com/](https://www.facebook.com/) registrieren.

1. Melden Sie sich auf der [Facebook-Entwickler-Website](https://developers.facebook.com/) mit den Anmeldeinformationen für Ihr Facebook-Konto an.
1. Wenn Sie dies noch nicht getan haben, müssen Sie sich als Facebook-Entwickler registrieren. Dazu wählen Sie oben rechts auf der Seite die Option **Get Started** (Erste Schritte) aus, akzeptieren die Facebook-Richtlinien und führen die Registrierungsschritte aus.
1. Wählen Sie **My Apps** (Meine Apps) und dann **Create App** (App erstellen) aus.
1. Geben Sie unter **Display Name** einen Anzeigenamen und unter **Contact Email** (Kontakt-E-Mail) eine gültige E-Mail-Adresse ein.
1. Wählen Sie **App-ID erstellen** aus. Hierzu müssen Sie möglicherweise die Richtlinien für die Facebook-Plattform akzeptieren und eine Online-Sicherheitsüberprüfung durchführen.
1. Wählen Sie **Settings** > **Basic** (Einstellungen > Allgemeines) aus.
1. Wählen Sie eine **Kategorie**, z.B. `Business and Pages`. Dieser Wert ist für Facebook erforderlich, wird aber nicht für Azure AD B2C verwendet.
1. Wählen Sie unten auf der Seite die Option **Add Platform** (Plattform hinzufügen) und dann **Website** aus.
1. Geben Sie für **Website-URL**`https://your-tenant-name.b2clogin.com/` ein, und ersetzen Sie `your-tenant-name` durch Ihren Mandantennnamen. Geben Sie unter **Privacy Policy URL** (Datenrichtlinien-URL) eine URL ein, z.B. `http://www.contoso.com`. Die Richtlinien-URL ist eine von Ihnen verwaltete Seite, die Datenschutzinformationen zu Ihrer Anwendung enthält.
1. Klicken Sie auf **Save changes** (Änderungen speichern).
1. Kopieren Sie im oberen Bereich der Seite den Wert von **App ID** (App-ID).
1. Wählen Sie **Show** (Anzeigen) aus, und kopieren Sie den Wert unter **App Secret** (App-Geheimnis). Sie benötigen beide Angaben, um Facebook als Identitätsanbieter in Ihrem Mandanten zu konfigurieren. **App Secret** handelt es sich um eine wichtige Sicherheitsinformation für die Anmeldung.
1. Wählen Sie das Pluszeichen neben **Products** (Produkte) und dann unter **Facebook Login** (Facebook-Anmeldung) die Option **Set up** (Einrichten) aus.
1. Wählen Sie unter **Facebook Login** (Facebook-Anmeldung) die Option **Settings** (Einstellungen) aus.
1. Geben Sie `https://your-tenant-name.b2clogin.com/your-tenant-name.onmicrosoft.com/oauth2/authresp` unter **Valid OAuth redirect URIs** (Gültige OAuth-Umleitungs-URIs) ein. Ersetzen Sie `your-tenant-name` durch den Namen Ihres Mandanten. Wählen Sie unten auf der Seite die Option **Save Changes** (Änderungen speichern) aus.
1. Klicken Sie rechts oben auf der Seite auf den Statusselektor, und legen Sie ihn auf **On** (Ein) fest, um die Anwendung öffentlich und Ihre Facebook-Anwendung für Azure AD B2C verfügbar zu machen. Wählen Sie anschließend **Switch Mode** (Modus wechseln) aus.  An diesem Punkt sollte sich der Status von **Entwicklung** in **Live** ändern.

## <a name="configure-a-facebook-account-as-an-identity-provider"></a>Konfigurieren eines Facebook-Kontos als Identitätsanbieter

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) als globaler Administrator Ihres Azure AD B2C-Mandanten an.
1. Stellen Sie sicher, dass Sie das Verzeichnis verwenden, das Ihren Azure AD B2C-Mandanten enthält, indem Sie im oberen Menü auf den **Verzeichnis- und Abonnementfilter** klicken und das entsprechende Verzeichnis auswählen.
1. Klicken Sie links oben im Azure-Portal auf **Alle Dienste**, suchen Sie nach **Azure AD B2C**, und klicken Sie darauf.
1. Wählen Sie **Identitätsanbieter** und dann **Facebook** aus.
1. Geben Sie einen **Namen** ein. Beispiel: *Facebook*.
1. Geben Sie für die **Client-ID** die App-ID der Facebook-Anwendung ein, die Sie zuvor erstellt haben.
1. Geben Sie das zuvor notierte App-Geheimnis als **Geheimer Clientschlüssel** ein.
1. Wählen Sie **Speichern** aus.
