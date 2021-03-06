---
title: Neuigkeiten Versionshinweise – Azure Active Directory | Microsoft-Dokumentation
description: Hier finden Sie Informationen zu den Neuerungen in Azure Active Directory, z. B. aktuelle Versionshinweise, bekannte Probleme, Fehlerbehebungen, veraltete Funktionen und anstehende Änderungen.
services: active-directory
author: msmimart
manager: daveba
featureFlags:
- clicktale
ms.assetid: 06a149f7-4aa1-4fb9-a8ec-ac2633b031fb
ms.service: active-directory
ms.subservice: fundamentals
ms.workload: identity
ms.topic: conceptual
ms.date: 04/30/2020
ms.author: mimart
ms.reviewer: dhanyahk
ms.custom: it-pro
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4c58c99faa83d6f04ac37d03789202e111f1b06d
ms.sourcegitcommit: 50ef5c2798da04cf746181fbfa3253fca366feaa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "82611159"
---
# <a name="whats-new-in-azure-active-directory"></a>Neuerungen in Azure Active Directory

>Lassen Sie sich über Updates auf dieser Seite benachrichtigen, indem Sie die URL `https://docs.microsoft.com/api/search/rss?search=%22release+notes+for+azure+AD%22&locale=en-us` kopieren und in Ihren ![RSS-Symbol](./media/whats-new/feed-icon-16x16.png)-Feedreader einfügen.

Es werden fortlaufend Verbesserungen an Azure AD vorgenommen. Damit Sie bezüglich der neuesten Entwicklungen auf dem neuesten Stand bleiben, bietet dieser Artikel Informationen zu Folgendem:

- Neueste Versionen
- Bekannte Probleme
- Behebung von Programmfehlern
- Veraltete Funktionen
- Pläne für Änderungen

Besuchen Sie regelmäßig diese Seite. Diese wird monatlich aktualisiert. Wenn Sie nach Elementen suchen, die älter als sechs Monate sind, können Sie sie im [Archiv für Neuheiten in Azure Active Directory](whats-new-archive.md) finden.

---

## <a name="april-2020"></a>April 2020

### <a name="combined-security-info-registration-experience-is-now-generally-available"></a>Umgebung für die kombinierte Registrierung von Sicherheitsinformationen jetzt allgemein verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** Authentifizierungen (Anmeldungen)

**Produktfunktion:** Identitätssicherheit und -schutz

Die Umgebung für die kombinierte Registrierung für Multi-Factor Authentication (MFA) und Self-Service-Kennwortzurücksetzung (Self-Service Password Reset, SSPR) ist jetzt allgemein verfügbar. Diese neue Registrierungsumgebung bietet den Benutzern die Möglichkeit, sich in einem einzigen schrittweisen Prozess für MFA und SSPR zu registrieren. Wenn Sie die neue Umgebung für Ihre Organisation bereitstellen, können sich die Benutzer schneller und unkomplizierter registrieren. Lesen Sie [hier](https://bit.ly/3etiRyQ) den Blogbeitrag.

---

### <a name="continuous-access-evaluation"></a>Fortlaufende Zugriffsevaluierung

**Typ:** Neues Feature

**Dienstkategorie:** Authentifizierungen (Anmeldungen)

**Produktfunktion:** Identitätssicherheit und -schutz

Die fortlaufende Zugriffsevaluierung ist ein neues Sicherheitsfeature, das bei Ereignissen in Azure AD (z. B. Löschen von Benutzerkonten) die Durchsetzung von Richtlinien in nahezu Echtzeit bei den vertrauenden Seiten ermöglicht, die Azure AD-Zugriffstoken verwenden. Dieses Feature wird zuerst für Teams- und Outlook-Clients eingeführt. Weitere Einzelheiten finden Sie in unserem [Blog](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/moving-towards-real-time-policy-and-security-enforcement/ba-p/1276933) und der [Dokumentation](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-continuous-access-evaluation).

---

### <a name="sms-sign-in-firstline-workers-can-sign-in-to-azure-ad-backed-applications-with-their-phone-number-and-no-password"></a>SMS-Anmeldung: Mitarbeiter in Service und Produktion können sich bei Anwendungen auf Basis von Azure AD mit ihrer Telefonnummer und ohne Kennwort anmelden

**Typ:** Neues Feature

**Dienstkategorie:** Authentifizierungen (Anmeldungen)

**Produktfunktion:** Benutzerauthentifizierung

Office startet eine Reihe von vorwiegend mobilen Business-Apps, die sich an unkonventionelle Organisationen und an Mitarbeiter in großen Organisationen richten, die E-Mails nicht als primäre Kommunikationsmethode verwenden. Zielgruppe für diese Apps sind Mitarbeiter in Service und Produktion, Mitarbeiter ohne PC-gestützten Arbeitsplatz, Außendienstmitarbeiter oder Mitarbeiter im Einzelhandel, die möglicherweise von Ihrem Arbeitgeber keine E-Mail-Adresse erhalten oder auf einen Computer bzw. Informationstechnologie zugreifen können. Dieses Projekt bietet diesen Mitarbeiter die Möglichkeit, sich durch Eingabe einer Telefonnummer und Austausch eines Codes bei Geschäftsanwendungen anzumelden. Weitere Informationen finden Sie in unserer [Administratordokumentation](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-sms-signin) und der [Endbenutzerdokumentation](https://docs.microsoft.com/azure/active-directory/user-help/sms-sign-in-explainer).

---

### <a name="invite-internal-users-to-use-b2b-collaboration"></a>Einladen von internen Benutzern zur Verwendung der B2B-Zusammenarbeit

**Typ:** Neues Feature

**Dienstkategorie:** B2B

**Produktfunktion:**

Die B2B-Einladungsfunktion wird derzeit erweitert, damit in Zukunft vorhandene interne Konten zur Verwendung von Anmeldeinformationen für die B2B-Zusammenarbeit eingeladen werden können. Zu diesem Zweck wird neben den typischen Parametern (z. B. E-Mail-Adresse des Eingeladenen) das Benutzerobjekt an die Einladungs-API übergeben. Objekt-ID, UPN, Gruppenmitgliedschaft, App-Zuweisung usw. des Benutzers bleiben unverändert. In Zukunft verwendet er jedoch B2B zum Authentifizieren mit den Anmeldeinformationen seines Basismandanten und nicht die internen, vor der Einladung verwendeten Anmeldeinformationen. Ausführliche Informationen hierzu finden Sie in der [Dokumentation](https://docs.microsoft.com/azure/active-directory/b2b/invite-internal-users).

---

### <a name="report-only-mode-for-conditional-access-is-now-generally-available"></a>Reiner Berichtsmodus für den bedingten Zugriff jetzt allgemein verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** Bedingter Zugriff

**Produktfunktion:** Identitätssicherheit und -schutz

Mit dem [reinen Berichtsmodus für den bedingten Azure AD-Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-report-only) können Sie das Ergebnis einer Richtlinie auswerten, ohne die Zugriffssteuerungen zu erzwingen. Im reinen Berichtsmodus können Sie Richtlinien in Ihrer Organisation vor der Aktivierung testen und deren Auswirkungen verstehen, sodass die Bereitstellung sicherer und einfacher wird. In den letzten Monaten haben wir eine hohe Akzeptanz des reinen Berichtsmodus festgestellt. Richtlinien im reinen Berichtsmodus weisen bereits einen Umfang von mehr als 26 Millionen Benutzer auf. Mit dieser Ankündigung werden neue Richtlinien für den bedingten Azure AD-Zugriff standardmäßig im reinen Berichtsmodus erstellt. Dies bedeutet, dass Sie die Auswirkungen Ihrer Richtlinien vom Zeitpunkt der Erstellung an überwachen können. Benutzer der MS Graph-APIs können zudem [Richtlinien im reinen Berichtsmodus programmgesteuert verwalten](https://docs.microsoft.com/graph/api/resources/conditionalaccesspolicy?view=graph-rest-beta). 

---

### <a name="conditional-access-insights-and-reporting-workbook-is-generally-available"></a>Arbeitsmappe für Erkenntnisse und Berichterstellung für den bedingten Zugriff jetzt allgemein verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** Bedingter Zugriff

**Produktfunktion:** Identitätssicherheit und -schutz

Die [Arbeitsmappe für Erkenntnisse und Berichterstellung](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-insights-reporting) für den bedingten Zugriff bietet Administratoren eine Zusammenfassungsansicht des bedingten Azure AD-Zugriffs in ihrem Mandanten. Mit der Möglichkeit, eine einzelne Richtlinie auszuwählen, können Administratoren besser verstehen, was jede Richtlinie bewirkt, und Änderungen in Echtzeit überwachen. Die Arbeitsmappe streamt die in Azure Monitor gespeicherten Daten, die Sie [anhand dieser Anweisungen](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics) in wenigen Minuten einrichten können. Damit das Dashboard leichter zu finden ist, haben wir es auf die neue Registerkarte „Erkenntnisse und Berichte“ im Menü „Bedingter Azure AD-Zugriff“ verschoben.

---

### <a name="policy-details-blade-for-conditional-access-is-in-public-preview"></a>Blatt „Richtliniendetails“ für den bedingten Zugriff als öffentliche Vorschau verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** Bedingter Zugriff

**Produktfunktion:** Identitätssicherheit und -schutz

Auf dem neuen Blatt [Richtliniendetails](https://docs.microsoft.com/azure/active-directory/conditional-access/troubleshoot-conditional-access) wird angezeigt, welche Zuweisungen, Bedingungen und Steuerelemente während der Auswertung der Richtlinie für bedingten Zugriff erfüllt wurden. Sie können auf das Blatt zugreifen, indem Sie in den Anmeldedetails auf der Registerkarte **Bedingter Zugriff** oder der Registerkarte **Nur Bericht** eine Zeile auswählen.

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---april-2020"></a>Neue Verbund-Apps im Azure AD-App-Katalog verfügbar – April 2020

**Typ:** Neues Feature

**Dienstkategorie:** Unternehmens-Apps

**Produktfunktion:** Integration von Drittanbieterprodukten

Im April 2020 haben wir diese 31 neuen Apps mit Verbundunterstützung in den App-Katalog aufgenommen: 

[SincroPool Apps](https://www.sincropool.com/), [SmartDB](https://hibiki.dreamarts.co.jp/smartdb/trial/), [Float](https://docs.microsoft.com/azure/active-directory/saas-apps/float-tutorial), [LMS365](https://lms.365.systems/), [IWT Procurement Suite](https://docs.microsoft.com/azure/active-directory/saas-apps/iwt-procurement-suite-tutorial), [Lunni](https://lunni.fi/), [EasySSO for Jira](https://docs.microsoft.com/azure/active-directory/saas-apps/easysso-for-jira-tutorial), [Virtual Training Academy](https://vta.c3p.ca/app/en/openid?authenticate_with=microsoft), [Meraki Dashboard](https://docs.microsoft.com/azure/active-directory/saas-apps/meraki-dashboard-tutorial), [Office 365 Mover](https://app.mover.io/login), [Speaker Engage](https://speakerengage.com/login.php), [Honestly](https://docs.microsoft.com/azure/active-directory/saas-apps/honestly-tutorial), [Ally](https://docs.microsoft.com/azure/active-directory/saas-apps/ally-tutorial), [DutyFlow](https://app.dutyflow.nl/), [AlertMedia](https://docs.microsoft.com/azure/active-directory/saas-apps/alertmedia-tutorial), [gr8 People](https://docs.microsoft.com/azure/active-directory/saas-apps/gr8-people-tutorial), [Pendo](https://docs.microsoft.com/azure/active-directory/saas-apps/pendo-tutorial), [HighGround](https://docs.microsoft.com/azure/active-directory/saas-apps/highground-tutorial), [Harmony](https://docs.microsoft.com/azure/active-directory/saas-apps/harmony-tutorial), [Timetabling Solutions](https://docs.microsoft.com/azure/active-directory/saas-apps/timetabling-solutions-tutorial), [SynchroNet CLICK](https://docs.microsoft.com/azure/active-directory/saas-apps/synchronet-click-tutorial), [empower](https://www.made-in-office.com/en/), [Fortes Change Cloud](https://docs.microsoft.com/azure/active-directory/saas-apps/fortes-change-cloud-tutorial), [Litmus](https://docs.microsoft.com/azure/active-directory/saas-apps/litmus-tutorial), [GroupTalk](https://recorder.grouptalk.com/), [Frontify](https://docs.microsoft.com/azure/active-directory/saas-apps/frontify-tutorial), [MongoDB Cloud](https://docs.microsoft.com/azure/active-directory/saas-apps/mongodb-cloud-tutorial), [TickitLMS Learn](https://docs.microsoft.com/azure/active-directory/saas-apps/tickitlms-learn-tutorial), [COCO](https://hexaware.com/partnerships-and-alliances/digital-transformation-using-microsoft-azure/), [Nitro Productivity Suite](https://docs.microsoft.com/azure/active-directory/saas-apps/nitro-productivity-suite-tutorial), [Trend Micro Web Security (TMWS)](https://review.docs.microsoft.com/azure/active-directory/saas-apps/trend-micro-tutorial)

Weitere Informationen zu den Apps finden Sie unter [SaaS-Anwendungsintegration mit Azure Active Directory](https://aka.ms/appstutorial). Weitere Informationen zum Listen Ihrer Anwendung im Azure AD-App-Katalog finden Sie unter [Listen Ihrer Anwendung im Azure Active Directory-Anwendungskatalog](https://aka.ms/azureadapprequest).

---

### <a name="microsoft-graph-delta-query-support-for-oauth2permissiongrant-available-for-public-preview"></a>Unterstützung der Delta-Abfrage in Microsoft Graph für oAuth2PermissionGrant in der öffentlichen Vorschau verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** MS Graph

**Produktfunktion:** Entwickleroberfläche

Die Delta-Abfrage für oAuth2PermissionGrant ist in der öffentlichen Vorschau verfügbar. Sie können jetzt Änderungen nachverfolgen, ohne kontinuierlich Microsoft Graph abfragen zu müssen. [Weitere Informationen.](https://docs.microsoft.com/graph/api/oAuth2PermissionGrant-delta?view=graph-rest-beta&tabs=http)

---

### <a name="microsoft-graph-delta-query-support-for-organizational-contact-generally-available"></a>Unterstützung der Delta-Abfrage in Microsoft Graph für Organisationskontakte jetzt allgemein verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** MS Graph

**Produktfunktion:** Entwickleroberfläche

Die Delta-Abfrage für Organisationskontakte ist allgemein verfügbar. Sie können jetzt Änderungen an Produktions-Apps nachverfolgen, ohne kontinuierlich Microsoft Graph abfragen zu müssen. Ersetzen Sie vorhandenen Code, der kontinuierlich orgContact-Daten abruft, durch die Delta-Abfrage, um die Leistung deutlich zu verbessern. [Weitere Informationen.](https://docs.microsoft.com/graph/api/orgcontact-delta?view=graph-rest-1.0&tabs=http)

---

### <a name="microsoft-graph-delta-query-support-for-application-generally-available"></a>Unterstützung der Delta-Abfrage in Microsoft Graph für Anwendungen allgemein verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** MS Graph

**Produktfunktion:** Entwickleroberfläche

Die Delta-Abfrage für Anwendungen ist allgemein verfügbar. Sie können jetzt Änderungen an Produktions-Apps nachverfolgen, ohne kontinuierlich Microsoft Graph abfragen zu müssen. Ersetzen Sie vorhandenen Code, der kontinuierlich Anwendungsdaten abruft, durch die Delta-Abfrage, um die Leistung deutlich zu verbessern. [Weitere Informationen.](https://docs.microsoft.com/graph/api/application-delta?view=graph-rest-1.0)

---

### <a name="microsoft-graph-delta-query-support-for-administrative-units-available-for-public-preview"></a>Unterstützung der Delta-Abfrage in Microsoft Graph für Verwaltungseinheiten in der öffentlichen Vorschau verfügbar

**Typ:** Neues Feature

**Dienstkategorie:** MS Graph

**Produktfunktion:** In der Entwicklerumgebung ist die Delta-Abfrage für Verwaltungseinheiten in der öffentlichen Vorschau verfügbar. Sie können jetzt Änderungen nachverfolgen, ohne kontinuierlich Microsoft Graph abfragen zu müssen. [Weitere Informationen.](https://docs.microsoft.com/graph/api/administrativeunit-delta?view=graph-rest-beta&tabs=http)

---

### <a name="manage-authentication-phone-numbers-and-more-in-new-microsoft-graph-beta-apis"></a>Verwalten von Telefonnummern für die Authentifizierung und mehr in neuen Microsoft Graph-Beta-APIs

**Typ:** Neues Feature

**Dienstkategorie:** MS Graph

**Produktfunktion:** Entwickleroberfläche

Diese APIs sind ein wichtiges Tool zum Verwalten der Authentifizierungsmethoden Ihrer Benutzer. Sie können jetzt programmgesteuert die für MFA und die Self-Service-Kennwortzurücksetzung (SSPR) verwendeten Authentifikatoren vorab registrieren und verwalten. Hierbei handelt es sich um eine der am häufigsten gewünschten Funktionen im Bereich Azure MFA, SSPR und Microsoft Graph. Mit den neuen APIs in dieser Veröffentlichungswelle haben Sie folgende Möglichkeiten:

- Lesen, Hinzufügen, Aktualisieren und Entfernen von Telefonnummern zum Authentifizieren des Benutzers
- Zurücksetzen des Kennworts für einen Benutzer
- Aktivieren und Deaktivieren der SMS-Anmeldung

Weitere Informationen finden Sie unter [Übersicht über die Azure AD-Authentifizierungsmethoden-API](https://docs.microsoft.com/graph/api/resources/authenticationmethods-overview?view=graph-rest-beta).

---

### <a name="administrative-units-public-preview"></a>Verwaltungseinheiten – öffentliche Vorschau

**Typ:** Neues Feature

**Dienstkategorie:** RBAC

**Produktfunktion:** Zugriffssteuerung

Verwaltungseinheiten ermöglichen es Ihnen, Administratorberechtigungen zu erteilen, die auf eine von Ihnen definierte Abteilung, Region oder ein anderes Segment Ihrer Organisation beschränkt sind. Mithilfe von Verwaltungseinheiten können Sie Berechtigungen an regionale Administratoren delegieren oder Richtlinien auf granularer Ebene festlegen. Beispielsweise kann ein Benutzerkontoadministrator nur in seiner Verwaltungseinheit Profilinformationen aktualisieren, Kennwörter zurücksetzen und Benutzern Lizenzen zuweisen.

Mit Verwaltungseinheiten kann ein zentraler Administrator folgende Aktionen ausführen:

- Erstellen einer Verwaltungseinheit für die dezentrale Verwaltung von Ressourcen
- Zuweisen einer Rolle mit Administratorberechtigungen nur für Azure AD-Benutzer in einer Verwaltungseinheit
- Auffüllen der Verwaltungseinheiten mit Benutzern und Gruppen nach Bedarf

Weitere Informationen finden Sie unter [Verwalten von Verwaltungseinheiten in Azure Active Directory (Vorschau)](https://aka.ms/AdminUnitsDocs).

---

### <a name="printer-administrator-and-printer-technician-built-in-roles"></a>Integrierte Rollen für Druckeradministrator und Druckertechniker

**Typ:** Neues Feature

**Dienstkategorie:** RBAC

**Produktfunktion:** Zugriffssteuerung

**Druckeradministrator**: Benutzer mit dieser Rolle können Drucker registrieren und alle Aspekte der gesamten Druckerkonfiguration in der Microsoft Universal Print-Lösung verwalten, einschließlich der Microsoft Universal Print-Connectoreinstellungen. Sie können in alle delegierten Druckberechtigungsanforderungen einwilligen. Druckeradministratoren haben außerdem Zugriff auf Druckberichte. 

**Druckertechniker**: Benutzer mit dieser Rolle können Drucker registrieren und den Druckerstatus in der Microsoft Universal Print-Lösung verwalten. Sie können außerdem alle Connectorinformationen lesen. Zu den Hauptaufgaben, die ein Druckertechniker nicht ausführen kann, gehören das Festlegen von Benutzerberechtigungen für Drucker sowie das Freigeben von Druckern. [Weitere Informationen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#printer-administrator)

---

### <a name="hybrid-identity-admin-built-in-role"></a>Integrierte Rolle für Hybrididentitätsadministrator

**Typ:** Neues Feature

**Dienstkategorie:** RBAC

**Produktfunktion:** Zugriffssteuerung

Benutzer mit dieser Rolle können Dienste und Einstellungen im Zusammenhang mit der Aktivierung der Hybrididentität in Azure AD aktivieren, konfigurieren und verwalten. Diese Rolle bietet die Möglichkeit, Azure AD für eine der drei unterstützten Authentifizierungsmethoden – Kennworthashsynchronisierung, Pass-Through-Authentifizierung oder Verbund (AD FS oder Drittanbieterverbund) – zu konfigurieren und eine zugehörige lokale Infrastruktur für die Aktivierung bereitzustellen. Die lokale Infrastruktur umfasst Bereitstellungs- und PTA-Agents. Diese Rolle gewährt die Fähigkeit, S-SSO (Seamless Single Sign-On, nahtloses einmaliges Anmelden) zu aktivieren, um eine nahtlose Authentifizierung auf Geräten ohne Windows 10 bzw. Computern ohne Windows Server 2016 zu ermöglichen. Außerdem bietet diese Rolle zur Überwachung und Problembehandlung die Möglichkeit, Anmeldeprotokolle anzuzeigen und auf Integritäts- und Analysedaten zuzugreifen. [Weitere Informationen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#hybrid-identity-administrator)

---

### <a name="network-administrator-built-in-role"></a>Integrierte Rolle für Netzwerkadministrator

**Typ:** Neues Feature

**Dienstkategorie:** RBAC

**Produktfunktion:** Zugriffssteuerung

Benutzer mit dieser Rolle können Empfehlungen zur Netzwerkumkreisarchitektur von Microsoft überprüfen, die auf Netzwerktelemetriedaten von Benutzerstandorten basieren. Die Netzwerkleistung für Office 365 basiert auf einer sorgfältigen Netzwerkumkreisarchitektur für Unternehmenskunden, die im Allgemeinen für den Benutzerstandort spezifisch ist. Diese Rolle ermöglicht das Bearbeiten von ermittelten Benutzerstandorten und das Konfigurieren von Netzwerkparametern für diese Standorte, um verbesserte Telemetriemessungen und Entwurfsempfehlungen zu ermöglichen. [Weitere Informationen.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#network-administrator)

---

### <a name="bulk-activity-and-downloads-in-the-azure-ad-admin-portal-experience"></a>Massenaktivitäten und -Downloads im Azure AD-Verwaltungsportal

**Typ:** Neues Feature

**Dienstkategorie:** Benutzerverwaltung

**Produktfunktion:** Verzeichnis

Jetzt können Sie Massenaktivitäten für Benutzer und Gruppen in Azure AD ausführen, indem Sie eine CSV-Datei in das Azure AD-Verwaltungsportal hochladen. Sie können Benutzer erstellen, Benutzer löschen und Gastbenutzer einladen. Sie können außerdem Mitglieder zu einer Gruppe hinzufügen und daraus entfernen.

Sie können auch Listen von Azure AD-Ressourcen aus dem Azure AD-Verwaltungsportal herunterladen. Sie können eine Liste der Benutzer im Verzeichnis, eine Liste der Gruppen im Verzeichnis und die Mitglieder einer bestimmten Gruppe herunterladen.

Weitere Informationen finden Sie über die folgenden Links:

- [Erstellen von Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-add) oder [Einladen von Gastbenutzern](https://docs.microsoft.com/azure/active-directory/b2b/tutorial-bulk-invite)
- [Löschen von Benutzern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete) oder [Wiederherstellen gelöschter Benutzer](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-restore)
- [Herunterladen der Benutzerliste](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-download) oder [Herunterladen der Gruppenliste](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-bulk-download)
- [Hinzufügen (Importieren) von Mitgliedern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-bulk-import-members) oder [Entfernen von Mitgliedern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-bulk-remove-members) oder [Herunterladen der Mitgliederliste](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-bulk-download-members) für eine Gruppe

---

### <a name="my-staff-delegated-user-management"></a>Delegierte Benutzerverwaltung „Meine Mitarbeiter“

**Typ:** Neues Feature

**Dienstkategorie:** Benutzerverwaltung

**Produktfunktion:**

„Meine Mitarbeiter“ bietet Managern in Service und Produktion (z. B. Geschäftsführer) die Möglichkeit sicherzustellen, dass ihre Mitarbeiter auf ihre Azure AD-Konten zugreifen können. Anstatt einen zentralen Helpdesk zu verwenden, können Organisationen häufige Aufgaben wie das Zurücksetzen von Kennwörtern oder das Ändern von Telefonnummern an einen Manager in Service oder Produktion delegieren. Bei Verwendung von „Meine Mitarbeiter“ kann ein Benutzer, der nicht auf sein Konto zugreifen kann, ohne die Hilfe des Helpdesks oder der IT-Abteilung mit wenigen Klicks den Zugriff wiedererlangen. Weitere Informationen finden Sie unter [Verwalten von Benutzern mit „Meine Mitarbeiter“ (Vorschau)](https://aka.ms/MyStaffAdminDocs) und [Delegieren der Benutzerverwaltung mit „Meine Mitarbeiter“ (Vorschau)](https://aka.ms/MyStaffUserDocs).

---

### <a name="an-upgraded-end-user-experience-in-access-reviews"></a>Aktualisierte Endbenutzerumgebung für Zugriffsüberprüfungen

**Typ:** Geändertes Feature

**Dienstkategorie:** Zugriffsüberprüfungen

**Produktfunktion:** Identity Governance

Wir haben die Überprüfungsumgebung für Azure AD-Zugriffsüberprüfungen im Portal „Meine Apps“ aktualisiert. Ab Ende April wird Ihren Prüfern, die in der Überprüfungsumgebung der Azure AD-Zugriffsüberprüfungen angemeldet sind, ein Banner angezeigt, das ihnen ermöglicht, die aktualisierte Umgebung in „Mein Zugriff“ zu testen. Beachten Sie, dass die aktualisierte Umgebung für Zugriffsüberprüfungen die gleiche Funktionalität hat wie die aktuelle Umgebung, jedoch neben neuen Funktionen auch eine verbesserte Benutzeroberfläche aufweist, damit Ihre Benutzer produktiv arbeiten können. [Hier](https://docs.microsoft.com/azure/active-directory/governance/perform-access-review) erfahren Sie mehr über die aktualisierte Umgebung. Diese öffentliche Vorschauversion gilt bis Ende Juli 2020. Ab Ende Juli werden Prüfer, die sich nicht für die Vorschauumgebung entschieden haben, automatisch zu „Mein Zugriff“ geleitet, um Zugriffsüberprüfungen durchzuführen. Wenn Ihre Prüfer jetzt schon dauerhaft auf die Vorschauumgebung in „Mein Zugriff“ umgestellt werden sollen, können Sie dies [hier](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR5dv-S62099HtxdeKIcgO-NUOFJaRDFDWUpHRk8zQ1BWVU1MMTcyQ1FFUi4u) anfordern.

---

### <a name="workday-inbound-user-provisioning-and-writeback-apps-now-support-the-latest-versions-of-workday-web-services-api"></a>Workday-Apps für die eingehende Benutzerbereitstellung und das Rückschreiben von Benutzern unterstützen jetzt die neuesten Versionen der Workday Web Services-API

**Typ:** Geändertes Feature

**Dienstkategorie:** App-Bereitstellung

**Produktfunktion:** 

Nach dem Feedback unserer Kunden haben wir nun die Workday-Apps für die eingehende Benutzerbereitstellung und das Rückschreiben von Benutzern im Katalog für Unternehmensanwendungen aktualisiert, um die neuesten Versionen der Workday Web Services (WWS)-API zu unterstützen. Mit dieser Änderung können Kunden die Version der WWS-API angeben, die sie in der Verbindungszeichenfolge verwenden möchten. Dadurch haben die Kunden die Möglichkeit, weitere Human Resources-Attribute abzurufen, die in den Workday-Versionen verfügbar sind. Die Workday-App zum Rückschreiben verwendet nun den empfohlenen Workday-Webdienst „Change_Work_Contact_Info“, um die Einschränkungen von „Maintain_Contact_Info“ zu beseitigen.

Wenn in der Verbindungszeichenfolge keine Version angegeben ist, verwenden die Workday-Apps für die eingehende Benutzerbereitstellung weiterhin WWS v21.1. Um zu den neuesten Workday-APIs für die eingehende Benutzerbereitstellung zu wechseln, müssen Kunden die Verbindungszeichenfolge, wie im [Tutorial](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial#which-workday-apis-does-the-solution-use-to-query-and-update-workday-worker-profiles) dokumentiert, und zusätzlich den für Workday-Attribute verwendeten XPath-Code aktualisieren, wie im [Referenzhandbuch für Workday-Attribute](https://docs.microsoft.com/azure/active-directory/app-provisioning/workday-attribute-reference#xpath-values-for-workday-web-services-wws-api-v30) beschrieben. 

Um die neue API für das Rückschreiben zu verwenden, sind in der Workday-App zum Bereitstellen des Rückschreibens keine Änderungen erforderlich. Stellen Sie auf Seiten von Workday sicher, dass das Konto „Workday Integration System User“ (ISU) über Berechtigungen zum Aufrufen des Geschäftsprozesses „Change_Work_Contact“ verfügt, wie im Tutorial unter [Konfigurieren der Sicherheitsrichtlinienberechtigungen für Geschäftsprozesse](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial#configuring-business-process-security-policy-permissions) beschrieben. 

Wir haben die [Anleitung in unserem Tutorial](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial) aktualisiert, um die Unterstützung der neuen API-Version widerzuspiegeln.

---

### <a name="users-with-default-access-role-are-now-in-scope-for-provisioning"></a>Benutzer mit der Rolle „Standardzugriff“ jetzt im Bereitstellungsumfang enthalten

**Typ:** Geändertes Feature

**Dienstkategorie:** App-Bereitstellung

**Produktfunktion:** Identity Lifecycle Management

In der Vergangenheit waren Benutzer mit der Rolle „Standardzugriff“ nicht im Bereitstellungsumfang enthalten. Aus dem Kundenfeedback ging der Wunsch hervor, dass Benutzer mit dieser Rolle im Bereitstellungsumfang enthalten sein sollten. Ab dem 16. April 2020 werden Benutzer mit der Rolle „Standardzugriff“ in allen neuen Bereitstellungskonfigurationen berücksichtigt. Wir werden das Verhalten der vorhandenen Bereitstellungskonfigurationen schrittweise ändern, um die Bereitstellung von Benutzern mit dieser Rolle zu unterstützen. [Weitere Informationen.](https://docs.microsoft.com/azure/active-directory/app-provisioning/application-provisioning-config-problem-no-users-provisioned)

---

### <a name="updated-provisioning-ui"></a>Aktualisierte Benutzeroberfläche für die Bereitstellung

**Typ:** Geändertes Feature

**Dienstkategorie:** App-Bereitstellung

**Produktfunktion:** Identity Lifecycle Management

Wir haben die Bereitstellungsumgebung aktualisiert, um eine stärker fokussierte Verwaltungsansicht zu erstellen. Wenn Sie zum Blatt für die Bereitstellung einer Unternehmensanwendung navigieren, die bereits konfiguriert wurde, können Sie den Fortschritt der Bereitstellung und die Verwaltung von Aktionen (z. B. Starten, Beenden und Neustarten der Bereitstellung) problemlos überwachen. [Weitere Informationen.](https://docs.microsoft.com/azure/active-directory/app-provisioning/configure-automatic-user-provisioning-portal)

---

### <a name="dynamic-group-rule-validation-is-now-available-for-public-preview"></a>Dynamische Gruppenregelüberprüfung jetzt in der öffentlichen Vorschau verfügbar

**Typ:** Geändertes Feature

**Dienstkategorie:** Gruppenverwaltung

**Produktfunktion:** Zusammenarbeit

Azure Active Directory (Azure AD) bietet nun die Möglichkeit, dynamische Gruppenregeln zu überprüfen. Auf der Registerkarte **Regeln überprüfen** können Sie Ihre dynamische Regel anhand von Beispielgruppenmitgliedern überprüfen, um zu bestätigen, dass die Regel erwartungsgemäß funktioniert. Beim Erstellen oder Aktualisieren von Regeln für dynamische Gruppen möchten Administratoren wissen, ob ein Benutzer oder ein Gerät Mitglied der Gruppe sein wird. So können sie besser auswerten, ob ein Benutzer oder Gerät die Regelkriterien erfüllt und eine entsprechende Problembehandlung durchführen, wenn keine Mitgliedschaft erwartet wird.

Weitere Informationen finden Sie unter [Überprüfen einer dynamischen Gruppenmitgliedschaftsregel (Vorschau)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-rule-validation).

---

### <a name="identity-secure-score---security-defaults-and-mfa-improvement-action-updates"></a>Identity Secure Score – Aktualisierungen von Sicherheitsstandards und MFA-Verbesserungsaktionen

**Typ:** Geändertes Feature

**Dienstkategorie:** –

**Produktfunktion:** Identitätssicherheit und -schutz

**Unterstützung von Sicherheitsstandards für Azure AD Verbesserungsaktionen:** Bei Microsoft Secure Score werden die Verbesserungsaktionen aktualisiert, um die [Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) zu unterstützen. Dadurch wird es einfacher, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen vor häufigen Angriffen zu schützen. Dies betrifft die folgenden Verbesserungsaktionen:

- Sicherstellen, dass alle Benutzer MFA für den sicheren Zugriff durchführen können
- Anfordern der MFA für Administratorrollen
- Aktivieren der Richtlinie zum Blockieren älterer Authentifizierungsmethoden
 
**Aktualisierungen für MFA-Verbesserungaktionen:** Unter Berücksichtigung der Tatsache, dass Unternehmen bei der Anwendung von funktionierenden Richtlinien für ihr Unternehmen höchste Sicherheit gewährleisten müssen, hat Microsoft Secure Score drei Verbesserungsaktionen im Zusammenhang mit Multi-Factor Authentication (MFA) entfernt und zwei hinzugefügt.

Entfernte Verbesserungsaktionen:

- Registrieren aller Benutzer für Multi-Factor Authentication (MFA)
- Anfordern der MFA für alle Benutzer
- Anfordern der MFA für privilegierte Azure AD-Rollen

Hinzugefügte Verbesserungsaktionen:

- Sicherstellen, dass alle Benutzer MFA für den sicheren Zugriff durchführen können
- Anfordern der MFA für Administratorrollen

Diese neuen Verbesserungsaktionen setzen voraus, dass sich Benutzer oder Administratoren in Ihrem Verzeichnis für die mehrstufige Authentifizierung (MFA) registrieren und den richtigen Satz von Richtlinien einrichten, die den Anforderungen Ihrer Organisation entsprechen. Das Hauptziel besteht darin, flexibel zu bleiben und gleichzeitig sicherzustellen, dass sich alle Benutzer und Administratoren mit mehrstufigen oder risikobasierten Eingabeaufforderungen für die Identitätsüberprüfung authentifizieren können. Dies kann das Einrichten mehrerer Richtlinien für die Anwendung bereichsbezogener Entscheidungen oder das Festlegen von Sicherheitsstandards (ab 16. März) bedeuten, die Microsoft entscheiden lassen, wann Benutzer zur mehrstufigen Authentifizierung (MFA) aufgefordert werden sollen. [Erfahren Sie mehr über die Neuerungen in Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide#whats-new).

---

## <a name="march-2020"></a>März 2020

### <a name="unmanaged-azure-active-directory-accounts-in-b2b-update-for-march-2021"></a>Nicht verwaltete Azure Active Directory-Konten im B2B-Update für März 2021

**Typ:** Plan für Änderung  
**Dienstkategorie:** B2B  
**Produktfunktion:** B2B/B2C
 
**Ab dem 31. März 2021** wird das Einlösen von Einladungen durch die Erstellung von nicht verwalteten Azure Active Directory-Konten und -Mandanten für B2B-Zusammenarbeitsszenarien von Microsoft nicht mehr unterstützt. Zur Vorbereitung hierauf raten wir Ihnen, sich für die [Authentifizierung mit Einmalkennung per E-Mail](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode) zu entscheiden.

---

### <a name="users-with-the-default-access-role-will-be-in-scope-for-provisioning"></a>Benutzer mit der Rolle „Standardzugriff“ im Bereitstellungsumfang enthalten

**Typ:** Plan für Änderung  
**Dienstkategorie:** App-Bereitstellung  
**Produktfunktion:** Identity Lifecycle Management
 
In der Vergangenheit waren Benutzer mit der Rolle „Standardzugriff“ nicht im Bereitstellungsumfang enthalten. Aus dem Kundenfeedback ging der Wunsch hervor, dass Benutzer mit dieser Rolle im Bereitstellungsumfang enthalten sein sollten. Wir arbeiten an der Implementierung einer Änderung, damit Benutzer mit der Rolle „Standardzugriff“ in allen neuen Bereitstellungskonfigurationen berücksichtigt werden. Wir werden schrittweise das Verhalten der bereits vorhandenen Bereitstellungskonfigurationen ändern, um die Bereitstellung von Benutzern mit dieser Rolle zu unterstützen. Es ist keine Kundenaktion erforderlich. Wir werden in unserer [Dokumentation](https://docs.microsoft.com/azure/active-directory/app-provisioning/application-provisioning-config-problem-no-users-provisioned) ein Update veröffentlichen, sobald diese Änderung vorgenommen wurde.

---

### <a name="azure-ad-b2b-collaboration-will-be-available-in-microsoft-azure-operated-by-21vianet-azure-china-21vianet-tenants"></a>Azure AD B2B-Zusammenarbeit in von 21Vianet-Mandanten (Azure China 21Vianet) betriebenen Microsoft Azure-Instanzen verfügbar

**Typ:** Plan für Änderung  
**Dienstkategorie:** B2B  
**Produktfunktion:** B2B/B2C
 
Die Funktionen der Azure AD B2B-Zusammenarbeit werden in Microsoft Azure-Instanzen verfügbar gemacht, die von 21Vianet-Mandanten (Azure China 21Vianet) betrieben werden. Dadurch können Benutzer in einem Azure China 21Vianet-Mandanten nahtlos mit Benutzern in anderen Azure China 21Vianet-Mandanten zusammenarbeiten. [Weitere Informationen zur Azure AD B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/).

---
 
### <a name="azure-ad-b2b-collaboration-invitation-email-redesign"></a>Neugestaltung der Einladungs-E-Mail für die Azure AD B2B-Zusammenarbeit

**Typ:** Plan für Änderung  
**Dienstkategorie:** B2B  
**Produktfunktion:** B2B/B2C
 
Die [E-Mails](https://docs.microsoft.com/azure/active-directory/b2b/invitation-email-elements), die der Einladungsdienst für die Zusammenarbeit in Azure AD B2B sendet, um Benutzer in das Verzeichnis einzuladen, werden neu gestaltet, um die Einladungsinformationen und die nächsten Schritte des Benutzers besser zu verdeutlichen.

---

### <a name="homerealmdiscovery-policy-changes-will-appear-in-the-audit-logs"></a>Anzeigen von HomeRealmDiscovery-Richtlinienänderungen in Überwachungsprotokollen

**Typ:** Korrigiert  
**Dienstkategorie:** Audit  
**Produktfunktion:** Überwachung und Berichterstellung
 
Bisher waren Änderungen an der [HomeRealmDiscovery-Richtlinie](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-authentication-for-federated-users-portal) nicht in den Überwachungsprotokollen enthalten. Diesen Fehler haben wir korrigiert. Jetzt können Sie erkennen, wann, wie und von wem die Richtlinie geändert wurde. 

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---march-2020"></a>Neue Verbund-Apps im Azure AD-App-Katalog verfügbar – März 2020

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten
 
Im März 2020 haben wir die folgenden 51 neuen Apps mit Verbundunterstützung in den App-Katalog aufgenommen: 

[Cisco AnyConnect](https://docs.microsoft.com/azure/active-directory/saas-apps/cisco-anyconnect), [Zoho One China](https://docs.microsoft.com/azure/active-directory/saas-apps/zoho-one-china-tutorial), [PlusPlus](https://test.plusplus.app/auth/login/azuread-outlook/), [Profit.co SAML App](https://docs.microsoft.com/azure/active-directory/saas-apps/profitco-saml-app-tutorial), [iPoint Service Provider](https://docs.microsoft.com/azure/active-directory/saas-apps/ipoint-service-provider-tutorial), [contexxt.ai SPHERE](https://contexxt-sphere.com/login), [Wisdom By Invictus](https://docs.microsoft.com/azure/active-directory/saas-apps/wisdom-by-invictus-tutorial), [Flare Digital Signage](https://spark-dev.pixelnebula.com/login), [Logz.io – Cloud Observability for Engineers](https://docs.microsoft.com/azure/active-directory/saas-apps/logzio-cloud-observability-for-engineers-tutorial), [SpectrumU](https://docs.microsoft.com/azure/active-directory/saas-apps/spectrumu-tutorial), [BizzContact](https://bizzcontact.app/), [Elqano SSO](https://docs.microsoft.com/azure/active-directory/saas-apps/elqano-sso-tutorial), [MarketSignShare](http://www.signshare.com/), [CrossKnowledge Learning Suite](https://docs.microsoft.com/azure/active-directory/saas-apps/crossknowledge-learning-suite-tutorial), [Netvision Compas](https://docs.microsoft.com/azure/active-directory/saas-apps/netvision-compas-tutorial), [FCM HUB](https://docs.microsoft.com/azure/active-directory/saas-apps/fcm-hub-tutorial), [RIB A/S Byggeweb Mobile](https://apps.apple.com/us/app/docia/id529058757), [GoLinks](https://docs.microsoft.com/azure/active-directory/saas-apps/golinks-tutorial), [Datadog](https://docs.microsoft.com/azure/active-directory/saas-apps/datadog-tutorial), [Zscaler B2B User Portal](https://docs.microsoft.com/azure/active-directory/saas-apps/zscaler-b2b-user-portal-tutorial), [LIFT](https://docs.microsoft.com/azure/active-directory/saas-apps/lift-tutorial), [Planview Enterprise One](https://docs.microsoft.com/azure/active-directory/saas-apps/planview-enterprise-one-tutorial), [WatchTeams](https://www.devfinition.com/), [Aster](https://demo.asterapp.io/login), [Skills Workflow](https://docs.microsoft.com/azure/active-directory/saas-apps/skills-workflow-tutorial), [Node Insight](https://admin.nodeinsight.com/AADLogin.aspx), [IP Platform](https://docs.microsoft.com/azure/active-directory/saas-apps/ip-platform-tutorial), [InVision](https://docs.microsoft.com/azure/active-directory/saas-apps/invision-tutorial), [Pipedrive](https://docs.microsoft.com/azure/active-directory/saas-apps/pipedrive-tutorial), [Showcase Workshop](https://app.showcaseworkshop.com/), [Greenlight Integration Platform](https://docs.microsoft.com/azure/active-directory/saas-apps/greenlight-integration-platform-tutorial), [Greenlight Compliant Access Management](https://docs.microsoft.com/azure/active-directory/saas-apps/greenlight-compliant-access-management-tutorial), [Grok Learning](https://docs.microsoft.com/azure/active-directory/saas-apps/grok-learning-tutorial), [Miradore Online](https://login.online.miradore.com/), [Khoros Care](https://docs.microsoft.com/azure/active-directory/saas-apps/khoros-care-tutorial), [AskYourTeam](https://docs.microsoft.com/azure/active-directory/saas-apps/askyourteam-tutorial), [TruNarrative](https://docs.microsoft.com/azure/active-directory/saas-apps/trunarrative-tutorial), [Smartwaiver](https://www.smartwaiver.com/m/user/sw_login.php?wms_login), [Bizagi Studio for Digital Process Automation](https://docs.microsoft.com/azure/active-directory/saas-apps/bizagi-studio-for-digital-process-automation-tutorial), [insuiteX](https://www.insuite.jp/), [sybo](https://www.systexsoftware.com.tw/), [Britive](https://docs.microsoft.com/azure/active-directory/saas-apps/britive-tutorial), [WhosOffice](https://docs.microsoft.com/azure/active-directory/saas-apps/whosoffice-tutorial), [E-days](https://docs.microsoft.com/azure/active-directory/saas-apps/e-days-tutorial), [Kollective SDN](https://portal.kollective.app/login), [Witivio](https://app.witivio.com/), [Playvox](https://my.playvox.com/login), [Korn Ferry 360](https://docs.microsoft.com/azure/active-directory/saas-apps/korn-ferry-360-tutorial), [Campus Café](https://docs.microsoft.com/azure/active-directory/saas-apps/campus-cafe-tutorial), [Catchpoint](https://docs.microsoft.com/azure/active-directory/saas-apps/catchpoint-tutorial), [Code42](https://docs.microsoft.com/azure/active-directory/saas-apps/code42-tutorial)

Weitere Informationen zu den Apps finden Sie unter [SaaS-Anwendungsintegration mit Azure Active Directory](https://aka.ms/appstutorial). Weitere Informationen zum Listen Ihrer Anwendung im Azure AD-App-Katalog finden Sie unter [Listen Ihrer Anwendung im Azure Active Directory-Anwendungskatalog](https://aka.ms/azureadapprequest).

---

### <a name="azure-ad-b2b-collaboration-available-in-azure-government-tenants"></a>Azure AD B2B-Zusammenarbeit in Azure Government-Mandanten verfügbar

**Typ:** Neues Feature  
**Dienstkategorie:** B2B  
**Produktfunktion:** B2B/B2C
 
Die Funktionen der Azure AD B2B-Zusammenarbeit sind jetzt für die Zusammenarbeit zwischen einigen Azure Government-Mandanten verfügbar.  Um festzustellen, ob Ihr Mandant diese Funktionen nutzen kann, befolgen Sie die Anweisungen unter [Wie kann ich erkennen, ob die B2B-Zusammenarbeit in meinem Mandanten der Azure-Cloud für US-Behörden verfügbar ist?](https://docs.microsoft.com/azure/active-directory/b2b/current-limitations#how-can-i-tell-if-b2b-collaboration-is-available-in-my-azure-us-government-tenant).

---

### <a name="azure-monitor-integration-for-azure-logs-is-now-available-in-azure-government"></a>Azure Monitor-Integration für Azure-Protokolle jetzt in Azure Government verfügbar

**Typ:** Neues Feature  
**Dienstkategorie:** Berichterstellung  
**Produktfunktion:** Überwachung und Berichterstellung
 
Die Integration von Azure AD-Protokollen in Azure Monitor ist jetzt in Azure Government verfügbar. Sie können Azure AD-Protokolle (Überwachungs- und Anmeldeprotokolle) an ein Speicherkonto, einen Event Hub und Log Analytics weiterleiten. Sehen Sie sich die [ausführliche Dokumentation](https://aka.ms/aadlogsinamd) sowie die [Bereitstellungspläne für die Berichterstellung und Überwachung](https://docs.microsoft.com/azure/active-directory/reports-monitoring/plan-monitoring-and-reporting) für Azure AD-Szenarien an.

---

### <a name="identity-protection-refresh-in-azure-government"></a>Identity Protection-Aktualisierung in Azure Government

**Typ:** Neues Feature  
**Dienstkategorie:** Schutz der Identität (Identity Protection)  
**Produktfunktion:** Identitätssicherheit und -schutz

Wir freuen uns, Ihnen mitteilen zu können, dass wir jetzt die aktualisierte [Azure AD Identity Protection](https://aka.ms/IdentityProtectionDocs) -Umgebung im [Microsoft Azure Government-Portal](https://portal.azure.us/) eingeführt haben. Weitere Informationen finden Sie in unserem [Ankündigungsblogbeitrag](https://techcommunity.microsoft.com/t5/public-sector-blog/identity-protection-refresh-in-microsoft-azure-government/ba-p/1223667).

---

### <a name="disaster-recovery-download-and-store-your-provisioning-configuration"></a>Notfallwiederherstellung: Herunterladen und Speichern der Bereitstellungskonfiguration

**Typ:** Neues Feature  
**Dienstkategorie:** App-Bereitstellung  
**Produktfunktion:** Identity Lifecycle Management
 
Der Azure AD-Bereitstellungsdienst stellt umfangreiche Konfigurationsfunktionen bereit. Kunden müssen in der Lage sein, ihre Konfiguration zu speichern, um diese später verwenden oder einen Rollback auf eine als funktionierend bekannte Version durchführen zu können. Wir haben die Möglichkeit hinzugefügt, Ihre Bereitstellungskonfiguration als JSON-Datei herunterzuladen und bei Bedarf hochzuladen. [Weitere Informationen](https://docs.microsoft.com/azure/active-directory/app-provisioning/export-import-provisioning-configuration)

---
 
### <a name="sspr-self-service-password-reset-now-requires-two-gates-for-admins-in-microsoft-azure-operated-by-21vianet-azure-china-21vianet"></a>Die Self-Service-Kennwortzurücksetzung (SSPR) erfordert jetzt zwei Gates für Administratoren in von 21Vianet (Azure China 21Vianet) betriebenen Microsoft Azure-Instanzen 

**Typ:** Geändertes Feature  
**Dienstkategorie:** Self-Service-Kennwortzurücksetzung  
**Produktfunktion:** Identitätssicherheit und -schutz
 
Bisher benötigten Administratoren, die in von 21Vianet (Azure China 21Vianet) betriebenen Microsoft Azure-Instanzen die Self-Service-Kennwortzurücksetzung (SSPR) zum Zurücksetzen ihrer eigenen Kennwörter verwendeten, nur ein „Gate“ (Abfrage), um ihre Identität zu beweisen. In öffentlichen und anderen nationalen Clouds müssen Administratoren bei der Verwendung von SSPR in der Regel zwei Gates verwenden, um ihre Identität nachzuweisen. Da in Azure China 21Vianet jedoch keine SMS oder Telefonanrufe unterstützt wurden, haben wir die Kennwortzurücksetzung von Administratoren über ein Gate erlaubt.

Wir sind jetzt dabei, zwischen Azure China 21Vianet und der öffentlichen Cloud gleiche Bedingungen für die SSPR-Funktion herzustellen. In Zukunft müssen Administratoren bei der Verwendung von SSPR zwei Gates verwenden. Unterstützt werden SMS, Telefonanrufe sowie Benachrichtigungen und Codes der Authenticator-App. [Weitere Informationen](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#administrator-reset-policy-differences)

---

### <a name="password-length-is-limited-to-256-characters"></a>Kennwortlänge auf 256 Zeichen beschränkt

**Typ:** Geändertes Feature  
**Dienstkategorie:** Authentifizierungen (Anmeldungen)  
**Produktfunktion:** Benutzerauthentifizierung
 
Um die Zuverlässigkeit des Azure AD-Diensts sicherzustellen, sind die Benutzerkennwörter jetzt auf 256 Zeichen beschränkt. Benutzer mit längeren Kennwörtern werden aufgefordert, ihr Kennwort bei der nächsten Anmeldung zu ändern, indem sie sich entweder an ihren Administrator wenden oder die SSPR-Funktion (Self-Service-Kennwortzurücksetzung) verwenden.

Diese Änderung ist am 13. März 2020, 10 Uhr PST (18 Uhr UTC), in Kraft getreten. Der Fehler lautet AADSTS 50052, InvalidPasswordExceedsMaxLength. Weitere Einzelheiten finden Sie in den [Hinweisen zu wichtigen Änderungen](https://docs.microsoft.com/azure/active-directory/develop/reference-breaking-changes#user-passwords-will-be-restricted-to-256-characters).

---

### <a name="azure-ad-sign-in-logs-are-now-available-for-all-free-tenants-through-the-azure-portal"></a>Azure AD-Anmeldeprotokolle jetzt für alle kostenlosen Mandanten über das Azure-Portal verfügbar

**Typ:** Geändertes Feature  
**Dienstkategorie:** Berichterstellung  
**Produktfunktion:** Überwachung und Berichterstellung
 
Ab sofort können Kunden mit kostenlosen Mandanten bis zu sieben Tage lang auf die [Azure AD-Anmeldeprotokolle im Azure-Portal](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-sign-ins) zugreifen. Bisher waren Anmeldeprotokolle nur für Kunden mit Azure Active Directory Premium-Lizenzen verfügbar. Durch diese Änderung können alle Mandanten über das Portal auf diese Protokolle zugreifen.

> [!NOTE]
> Kunden benötigen weiterhin eine Premium-Lizenz (Azure Active Directory Premium P1 oder P2), wenn sie über die Microsoft Graph-API und Azure Monitor auf die Anmeldeprotokolle zugreifen wollen.

---

### <a name="deprecation-of-directory-wide-groups-option-from-groups-general-settings-on-azure-portal"></a>Einstellung der Option für verzeichnisweite Gruppen in den allgemeinen Gruppeneinstellungen im Azure-Portal

**Typ:** Als veraltet markiert  
**Dienstkategorie:** Gruppenverwaltung  
**Produktfunktion:** Zusammenarbeit

Um Kunden eine flexiblere Möglichkeit zu bieten, optimale verzeichnisweite Gruppen für ihre Anforderungen zu erstellen, haben wir die Option **verzeichnisweite Gruppen** der Einstellungen unter **Gruppen** > **Allgemein** im Azure-Portal durch einen Link zur [dynamischen Gruppendokumentation](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) ersetzt. Wir haben unsere Dokumentation um zusätzliche Anweisungen erweitert, damit Administratoren Gruppen mit allen Benutzern (mit oder ohne Gastbenutzer) erstellen können.

---

## <a name="february-2020"></a>Februar 2020

### <a name="upcoming-changes-to-custom-controls"></a>Bevorstehende Änderungen an benutzerdefinierten Steuerelementen

**Typ:** Plan für Änderung  
**Dienstkategorie:** MFA  
**Produktfunktion:** Identitätssicherheit und -schutz
 
Wir planen, die aktuell in der Vorschau befindlichen benutzerdefinierten Steuerelemente durch einen Ansatz zu ersetzen, der vom Partner bereitgestellte Authentifizierungsfunktionen erlaubt, um nahtlos mit Azure Active Directory-Administrator- und Endbenutzerumgebungen zusammenzuarbeiten. Derzeit unterliegen MFA-Partnerlösungen folgenden Einschränkungen: Sie funktionieren nur nach Eingabe eines Kennworts und dienen nicht als MFA für die Step-up-Authentifizierung in anderen wichtigen Szenarien. Zudem sind sie nicht in Verwaltungsfunktionen für Endbenutzer- oder administrative Anmeldeinformationen integriert. Mit der neuen Implementierung können vom Partner bereitgestellte Authentifizierungsfaktoren zusammen mit integrierten Faktoren für wichtige Szenarien verwendet werden. Hierzu zählen u.a. Registrierung, Nutzung, MFA-Ansprüche, Step-up-Authentifizierung, Berichterstellung und Protokollierung. 

Neben dem neuen Design werden benutzerdefinierte Steuerelemente weiterhin in der Vorschau unterstützt, bis die allgemeine Verfügbarkeit erreicht ist. Dadurch erhalten Kunden Zeit für die Migration zum neuen Design. Aufgrund der Einschränkungen des aktuellen Ansatzes werden neue Anbieter erst dann integriert, wenn das neue Design verfügbar ist. Wir arbeiten eng mit Kunden und Anbietern zusammen und werden Ihnen zu gegebener Zeit den zeitlichen Ablauf mitteilen. [Weitere Informationen](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/upcoming-changes-to-custom-controls/ba-p/1144696#)

---

### <a name="identity-secure-score---mfa-improvement-action-updates"></a>Identity Secure Score – Updates für Verbesserungsaktionen im Zusammenhang mit MFA

**Typ:** Plan für Änderung  
**Dienstkategorie:** MFA  
**Produktfunktion:** Identitätssicherheit und -schutz
 
Unter Berücksichtigung der Tatsache, dass Unternehmen bei der Anwendung von funktionierenden Richtlinien für ihr Unternehmen höchste Sicherheit gewährleisten müssen, entfernt Microsoft Secure Score drei Verbesserungsaktionen im Zusammenhang mit Multi-Factor Authentication (MFA) und fügt zwei hinzu.

Die folgenden Verbesserungsaktionen werden entfernt:

- Registrieren aller Benutzer für MFA
- Anfordern der MFA für alle Benutzer
- Anfordern der MFA für privilegierte Azure AD-Rollen

Die folgenden Verbesserungsaktionen werden hinzugefügt:

- Für einen sicheren Zugriff wird gewährleistet, dass alle Benutzer die mehrstufige Authentifizierung (MFA) ausführen können
- Anfordern der MFA für Administratorrollen

Diese neuen Verbesserungsaktionen setzen voraus, dass sich Benutzer oder Administratoren in Ihrem Verzeichnis für die mehrstufige Authentifizierung (MFA) registrieren und den richtigen Satz von Richtlinien einrichten, die den Anforderungen Ihrer Organisation entsprechen. Das Hauptziel besteht darin, flexibel zu bleiben und gleichzeitig sicherzustellen, dass sich alle Benutzer und Administratoren mit mehrstufigen oder risikobasierten Eingabeaufforderungen für die Identitätsüberprüfung authentifizieren können. Dies kann das Festlegen von Sicherheitsstandards bedeuten, die Microsoft entscheiden lassen, wann Benutzer zur mehrstufigen Authentifizierung aufgefordert werden sollen, oder auch das Einrichten mehrerer Richtlinien für die Anwendung bereichsbezogener Entscheidungen. Diese Updates für die Verbesserungsaktionen sehen auch vor, dass Basisschutzrichtlinien nicht mehr in die Bewertungsberechnungen einbezogen werden. [Erfahren Sie mehr über die anstehenden Neuerungen in Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score-whats-coming?view=o365-worldwide).

---

### <a name="azure-ad-domain-services-sku-selection"></a>Azure AD Domain Services – SKU-Auswahl

**Typ:** Neues Feature  
**Dienstkategorie:** Azure AD Domain Services  
**Produktfunktion:** Azure AD Domain Services
 
Dem Kundenfeedback zufolge wünschten sich Kunden von Azure AD Domain Services mehr Flexibilität bei der Auswahl von Leistungsstufen für ihre Instanzen. Ab dem 1. Februar 2020 haben wir das dynamische Modell (bei dem Azure AD anhand der Objektanzahl Leistung und Tarif ermittelte) auf ein Modell mit Selbstauswahl umgestellt. Kunden können nun eine Leistungsstufe auswählen, die ihrer Umgebung entspricht. Diese Änderung ermöglicht es uns auch, neue Szenarien wie Ressourcengesamtstrukturen und Premiumfunktionen wie tägliche Sicherungen zu aktivieren. Die Objektanzahl ist jetzt unbegrenzt für alle SKUs, wir bieten jedoch weiterhin Vorschläge für die Objektanzahl auf jeder Stufe an.

**Es ist keine direkte Kundenaktion erforderlich.** Bei Bestandskunden bestimmt die dynamische Stufe, die am 1. Februar 2020 verwendet wurde, die neue Standardstufe. Diese Änderung hat keine Auswirkungen auf Preise oder Leistung. In Zukunft müssen Azure AD DS-Kunden die Leistungsanforderungen auswerten, wenn sich Verzeichnisgröße und Workloadmerkmale ändern. Ein Wechsel zwischen den Dienstebenen ist auch in Zukunft ein unterbrechungsfreier Vorgang. Wir werden Kunden jedoch nicht mehr auf Basis des Verzeichniswachstums automatisch auf eine neue Ebene umstellen. Außerdem gibt es keine Preiserhöhung. Die neue Preisgestaltung entspricht dem aktuellen Abrechnungsmodell. Weitere Informationen finden Sie in der [Dokumentation zu Azure AD DS-SKUs](https://docs.microsoft.com/azure/active-directory-domain-services/administration-concepts#azure-ad-ds-skus) und auf der [Preisseite für Azure AD Domain Services](https://azure.microsoft.com/pricing/details/active-directory-ds/).

---
 
### <a name="new-federated-apps-available-in-azure-ad-app-gallery---february-2020"></a>Neue Verbund-Apps im Azure AD-App-Katalog verfügbar – Februar 2020

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten
 
Im Februar 2020 haben wir die folgenden 31 neuen Apps mit Verbundunterstützung in unseren App-Katalog aufgenommen: 

[IamIP Patent Platform](https://docs.microsoft.com/azure/active-directory/saas-apps/iamip-patent-platform-tutorial), [Experience Cloud](https://docs.microsoft.com/azure/active-directory/saas-apps/experience-cloud-tutorial), [NS1 SSO For Azure](https://docs.microsoft.com/azure/active-directory/saas-apps/ns1-sso-azure-tutorial), [Barracuda Email Security Service](https://ess.barracudanetworks.com/sso/azure), [ABa Reporting](https://myaba.co.uk/client-access/signin/auth/msad), [In Case of Crisis – Online Portal](https://docs.microsoft.com/azure/active-directory/saas-apps/in-case-of-crisis-online-portal-tutorial), [BIC Cloud Design](https://docs.microsoft.com/azure/active-directory/saas-apps/bic-cloud-design-tutorial), [Beekeeper Azure AD Data Connector](https://docs.microsoft.com/azure/active-directory/saas-apps/beekeeper-azure-ad-data-connector-tutorial), [Korn Ferry Assessments](https://www.kornferry.com/solutions/kf-digital/kf-assess), [Verkada Command](https://docs.microsoft.com/azure/active-directory/saas-apps/verkada-command-tutorial), [Splashtop](https://docs.microsoft.com/azure/active-directory/saas-apps/splashtop-tutorial), [Syxsense](https://docs.microsoft.com/azure/active-directory/saas-apps/syxsense-tutorial), [EAB Navigate](https://docs.microsoft.com/azure/active-directory/saas-apps/eab-navigate-tutorial), [New Relic (Limited Release)](https://docs.microsoft.com/azure/active-directory/saas-apps/new-relic-limited-release-tutorial), [Thulium](https://admin.thulium.com/login/instance), [Ticket Manager](https://docs.microsoft.com/azure/active-directory/saas-apps/ticketmanager-tutorial), [Template Chooser for Teams](https://links.officeatwork.com/templatechooser-download-teams), [Beesy](https://www.beesy.me/index.php/site/login), [Health Support System](https://docs.microsoft.com/azure/active-directory/saas-apps/health-support-system-tutorial), [MURAL](https://app.mural.co/signup), [Hive](https://docs.microsoft.com/azure/active-directory/saas-apps/hive-tutorial), [LavaDo](https://appsource.microsoft.com/product/web-apps/lavaloon.lavado_standard?tab=Overview), [Wakelet](https://wakelet.com/login), [Firmex VDR](https://docs.microsoft.com/azure/active-directory/saas-apps/firmex-vdr-tutorial), [ThingLink for Teachers and Schools](https://www.thinglink.com/), [Coda](https://docs.microsoft.com/azure/active-directory/saas-apps/coda-tutorial), [NearpodApp](https://nearpod.com/signup/?oc=Microsoft&utm_campaign=Microsoft&utm_medium=site&utm_source=product), [WEDO](https://docs.microsoft.com/azure/active-directory/saas-apps/wedo-tutorial), [InvitePeople](https://invitepeople.com/login), [Reprints Desk – Article Galaxy](https://docs.microsoft.com/azure/active-directory/saas-apps/reprints-desk-article-galaxy-tutorial), [TeamViewer](https://docs.microsoft.com/azure/active-directory/saas-apps/teamviewer-tutorial)

 
Weitere Informationen zu den Apps finden Sie unter [SaaS-Anwendungsintegration mit Azure Active Directory](https://aka.ms/appstutorial). Weitere Informationen zum Listen Ihrer Anwendung im Azure AD-App-Katalog finden Sie unter [Listen Ihrer Anwendung im Azure Active Directory-Anwendungskatalog](https://aka.ms/azureadapprequest).

---
 
### <a name="new-provisioning-connectors-in-the-azure-ad-application-gallery---february-2020"></a>Neue Bereitstellungsconnectors im Azure AD-Anwendungskatalog – Februar 2020

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten
 
Sie können ab sofort das Erstellen, Aktualisieren und Löschen von Benutzerkonten für diese neu integrierten Apps automatisieren:

- [Mixpanel](https://docs.microsoft.com/azure/active-directory/saas-apps/mixpanel-provisioning-tutorial)
- [TeamViewer](https://docs.microsoft.com/azure/active-directory/saas-apps/teamviewer-provisioning-tutorial)
- [Azure Databricks](https://docs.microsoft.com/azure/active-directory/saas-apps/azure-databricks-scim-connector-provisioning-tutorial)
- [PureCloud by Genesys](https://docs.microsoft.com/azure/active-directory/saas-apps/purecloud-by-genesys-provisioning-tutorial)
- [Zapier](https://docs.microsoft.com/azure/active-directory/saas-apps/zapier-provisioning-tutorial)

Weitere Informationen dazu, wie Sie Ihre Organisation durch die automatisierte Bereitstellung von Benutzerkonten besser schützen können, finden Sie unter [Automatisieren der Bereitstellung und Bereitstellungsaufhebung von Benutzern für SaaS-Anwendungen mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/user-provisioning).

---
 
### <a name="azure-ad-support-for-fido2-security-keys-in-hybrid-environments"></a>Azure AD-Unterstützung für FIDO2-Sicherheitsschlüssel in Hybridumgebungen

**Typ:** Neues Feature  
**Dienstkategorie:** Authentifizierungen (Anmeldungen)  
**Produktfunktion:** Benutzerauthentifizierung
 
Wir geben die Azure AD-Unterstützung für FIDO2-Sicherheitsschlüssel in Hybridumgebungen (Public Preview) bekannt. Benutzer können sich jetzt mit FIDO2-Sicherheitsschlüsseln bei ihren hybrid in Azure AD eingebundenen Geräten unter Windows 10 anmelden und über die nahtlose Anmeldung (Seamless Sign-On, SSO) auf ihre lokalen und Cloudressourcen zugreifen. Die Unterstützung für Hybridumgebungen stand bei unseren Kunden mit kennwortloser Authentifizierung ganz oben auf der Wunschliste, da wir zunächst die FIDO2-Unterstützung für in Azure AD eingebundene Geräte in der Public Preview gestartet haben. Die kennwortlose Authentifizierung mit modernen Technologien wie biometrische Merkmale und Verschlüsselung mit öffentlichen/privaten Schlüsseln ist nicht nur bequem und benutzerfreundlich, sondern auch sicher. Mit dieser Public Preview haben Sie nun die Möglichkeit, eine moderne Authentifizierung wie FIDO2-Sicherheitsschlüssel für den Zugriff auf herkömmliche Active Directory-Ressourcen zu verwenden. Weitere Informationen finden Sie unter [Einmaliges Anmelden bei lokalen Ressourcen](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key-on-premises). 

Unter [Aktivieren von FIDO2-Sicherheitsschlüsseln für Ihren Mandanten](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) finden Sie schrittweise Anleitungen, um mit der Verwendung zu beginnen. 

---
 
### <a name="the-new-my-account-experience-is-now-generally-available"></a>Neue Umgebung „Mein Konto“ jetzt allgemein verfügbar

**Typ:** Geändertes Feature  
**Dienstkategorie:** Mein Profil/Konto  
**Produktfunktion:** Endbenutzerumgebungen
 
„Mein Konto“, die zentrale Anlaufstelle für alle Kontoverwaltungsaufgaben für Endbenutzer, ist jetzt allgemein verfügbar! Endbenutzer können über eine URL oder den Header der neuen Umgebung „Meine Apps“ auf die neue Site zugreifen. Unter [Übersicht über das Portal „Mein Konto“](https://docs.microsoft.com/azure/active-directory/user-help/my-account-portal-overview) erfahren Sie mehr über die Selbstbedienungsfunktionen der neuen Umgebung.

---
 
### <a name="my-account-site-url-updating-to-myaccountmicrosoftcom"></a>URL der Site „Mein Konto“ aktualisiert auf myaccount.microsoft.com

**Typ:** Geändertes Feature  
**Dienstkategorie:** Mein Profil/Konto  
**Produktfunktion:** Endbenutzerumgebungen
 
Die URL für die neue Endbenutzerumgebung „Mein Konto“ wird nächsten Monat auf `https://myaccount.microsoft.com` aktualisiert. Weitere Informationen zur Umgebung und allen Kontoselbstbedienungsfunktionen für Endbenutzer finden Sie unter [Hilfe zum Portal „Mein Konto“](https://docs.microsoft.com/azure/active-directory/user-help/my-account-portal-overview).

---
 
## <a name="january-2020"></a>Januar 2020
 
### <a name="the-new-my-apps-portal-is-now-generally-available"></a>Das neue Portal „Meine Apps“ ist jetzt allgemein verfügbar

**Typ:** Plan für Änderung  
**Dienstkategorie:** Meine Apps  
**Produktfunktion:** Endbenutzerumgebungen
 
Führen Sie für Ihre Organisation ein Upgrade auf das neue Portal „Meine Apps“ durch, das jetzt allgemein verfügbar ist! Weitere Informationen zum neuen Portal und zu Sammlungen finden Sie unter [Erstellen von Sammlungen im Portal „Meine Apps“](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).

---
 
### <a name="workspaces-in-azure-ad-have-been-renamed-to-collections"></a>Arbeitsbereiche in Azure AD wurden in Sammlungen umbenannt

**Typ:** Geändertes Feature  
**Dienstkategorie:** Meine Apps   
**Produktfunktion:** Endbenutzerumgebungen
 
Arbeitsbereiche (die Filter, die Administratoren zum Organisieren Ihrer Benutzer-Apps konfigurieren können) werden nun als Sammlungen bezeichnet. Weitere Informationen zum Konfigurieren dieser Sammlungen finden Sie unter [Erstellen von Sammlungen im Portal „Meine Apps“](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).

---
 
### <a name="azure-ad-b2c-phone-sign-up-and-sign-in-using-custom-policy-public-preview"></a>Telefonregistrierung und -anmeldung mit benutzerdefinierten Richtlinien in Azure AD B2C (Öffentliche Vorschau)

**Typ:** Neues Feature  
**Dienstkategorie:** B2C – Verwaltung von Endbenutzeridentitäten  
**Produktfunktion:** B2B/B2C
 
Mit der Telefonregistrierung und -anmeldung können Entwickler und Unternehmen ihren Kunden die Registrierung und Anmeldung mit einem Einmalkennwort ermöglichen, das per SMS an die Telefonnummer des Benutzers gesendet wird. Mit dieser Funktion kann der Kunden auch seine Telefonnummer ändern, falls er keinen Zugriff auf das Telefon mehr hat. Dank der Leistungsfähigkeit benutzerdefinierter Richtlinien können Entwickler und Unternehmen mit der Telefonregistrierung und -anmeldung ihre Marke durch Seitenanpassung kommunizieren. Weitere Informationen finden Sie unter [Einrichten von Telefonregistrierung und -anmeldung mit benutzerdefinierten Richtlinien in Azure AD B2C](https://docs.microsoft.com/azure/active-directory-b2c/phone-authentication).
 
---
 
### <a name="new-provisioning-connectors-in-the-azure-ad-application-gallery---january-2020"></a>Neue Bereitstellungsconnectors im Azure AD-Anwendungskatalog – Januar 2020

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten
 
Sie können ab sofort das Erstellen, Aktualisieren und Löschen von Benutzerkonten für diese neu integrierten Apps automatisieren:

- [Promapp]( https://docs.microsoft.com/azure/active-directory/saas-apps/promapp-provisioning-tutorial)
- [Zscaler Private Access](https://docs.microsoft.com/azure/active-directory/saas-apps/zscaler-private-access-provisioning-tutorial)

Weitere Informationen dazu, wie Sie Ihre Organisation durch die automatisierte Bereitstellung von Benutzerkonten besser schützen können, finden Sie unter [Automatisieren der Bereitstellung und Bereitstellungsaufhebung von Benutzern für SaaS-Anwendungen mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/user-provisioning).

---
 
### <a name="new-federated-apps-available-in-azure-ad-app-gallery---january-2020"></a>Neue Verbund-Apps im Azure AD-Anwendungskatalog – Januar 2020

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten
 
Im Januar 2020 haben wir die folgenden 33 neuen Apps mit Verbundunterstützung in den App-Katalog aufgenommen: 

[JOSA](https://docs.microsoft.com/azure/active-directory/saas-apps/josa-tutorial), [Fastly Edge Cloud](https://docs.microsoft.com/azure/active-directory/saas-apps/fastly-edge-cloud-tutorial), [Terraform Enterprise](https://docs.microsoft.com/azure/active-directory/saas-apps/terraform-enterprise-tutorial), [Spintr SSO](https://docs.microsoft.com/azure/active-directory/saas-apps/spintr-sso-tutorial), [Abibot Netlogistik](https://azuremarketplace.microsoft.com/marketplace/apps/aad.abibotnetlogistik), [SkyKick](https://login.skykick.com/login?state=g6Fo2SBTd3M5Q0xBT0JMd3luS2JUTGlYN3pYTE1remJQZnR1c6N0aWTZIDhCSkwzYVQxX2ZMZjNUaWxNUHhCSXg2OHJzbllTcmYto2NpZNkgM0h6czk3ZlF6aFNJV1VNVWQzMmpHeFFDbDRIMkx5VEc&client=3Hzs97fQzhSIWUMUd32jGxQCl4H2LyTG&protocol=oauth2&audience=https://papi.skykick.com&response_type=code&redirect_uri=https://portal.skykick.com/callback&scope=openid%20profile%20offline_access), [Upshotly](https://docs.microsoft.com/azure/active-directory/saas-apps/upshotly-tutorial), [LeaveBot](https://leavebot.io/#home), [DataCamp](https://docs.microsoft.com/azure/active-directory/saas-apps/datacamp-tutorial), [TripActions](https://docs.microsoft.com/azure/active-directory/saas-apps/tripactions-tutorial), [SmartWork](https://www.intumit.com/english/SmartWork.html), [Dotcom-Monitor](https://docs.microsoft.com/azure/active-directory/saas-apps/dotcom-monitor-tutorial), [SSOGEN – Azure AD SSO Gateway for Oracle E-Business Suite – EBS, PeopleSoft und JDE](https://docs.microsoft.com/azure/active-directory/saas-apps/ssogen-tutorial), [Hosted MyCirqa SSO](https://docs.microsoft.com/azure/active-directory/saas-apps/hosted-mycirqa-sso-tutorial), [Yuhu Property Management Platform](https://docs.microsoft.com/azure/active-directory/saas-apps/yuhu-property-management-platform-tutorial), [LumApps](https://sites.lumapps.com/login), [Upwork Enterprise](https://docs.microsoft.com/azure/active-directory/saas-apps/upwork-enterprise-tutorial), [Talentsoft](https://docs.microsoft.com/azure/active-directory/saas-apps/talentsoft-tutorial), [SmartDB for Microsoft Teams](http://teams.smartdb.jp/login/), [PressPage](https://docs.microsoft.com/azure/active-directory/saas-apps/presspage-tutorial), [ContractSafe Saml2 SSO](https://docs.microsoft.com/azure/active-directory/saas-apps/contractsafe-saml2-sso-tutorial), [Maxient Conduct Manager Software](https://docs.microsoft.com/azure/active-directory/saas-apps/maxient-conduct-manager-software-tutorial), [Helpshift](https://docs.microsoft.com/azure/active-directory/saas-apps/helpshift-tutorial), [PortalTalk 365](https://www.portaltalk.com/), [CoreView](https://portal.coreview.com/), [Squelch Cloud Office365 Connector](https://laxmi.squelch.io/login), [PingFlow Authentication](https://app-staging.pingview.io/), [ PrinterLogic SaaS](https://docs.microsoft.com/azure/active-directory/saas-apps/printerlogic-saas-tutorial), [Taskize Connect](https://docs.microsoft.com/azure/active-directory/saas-apps/taskize-connect-tutorial), [Sandwai](https://app.sandwai.com/), [EZRentOut](https://docs.microsoft.com/azure/active-directory/saas-apps/ezrentout-tutorial), [AssetSonar](https://docs.microsoft.com/azure/active-directory/saas-apps/assetsonar-tutorial), [Akari Virtual Assistant](https://akari.io/akari-virtual-assistant/)

Weitere Informationen zu den Apps finden Sie unter [SaaS-Anwendungsintegration mit Azure Active Directory](https://aka.ms/appstutorial). Weitere Informationen zum Listen Ihrer Anwendung im Azure AD-App-Katalog finden Sie unter [Listen Ihrer Anwendung im Azure Active Directory-Anwendungskatalog](https://aka.ms/azureadapprequest).

---

### <a name="two-new-identity-protection-detections"></a>Zwei neue Erkennungen in Identity Protection

**Typ:** Neues Feature  
**Dienstkategorie:** Schutz der Identität (Identity Protection)  
**Produktfunktion:** Identitätssicherheit und -schutz
 
Identity Protection wurde um zwei neue, mit der Anmeldung verknüpfte Erkennungstypen ergänzt: „Verdächtige Regeln zur Posteingangsänderung“ und „Unmöglicher Ortswechsel“. Diese Offline-Erkennungen werden von MACS (Microsoft Cloud App Security) erkannt und beeinflussen das Benutzer- und Anmelderisiko in Identity Protection. Weitere Informationen zu diesen Erkennungen finden Sie unter [Risikotypen für die Anmeldung](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-risks#sign-in-risk).
 
---
 
### <a name="breaking-change-uri-fragments-will-not-be-carried-through-the-login-redirect"></a>Breaking Change: URI-Fragmente werden nicht über die Anmeldeumleitung übergeben

**Typ:** Geändertes Feature  
**Dienstkategorie:** Authentifizierungen (Anmeldungen)  
**Produktfunktion:** Benutzerauthentifizierung
 
Ab dem 8. Februar 2020 fügt der Dienst ein leeres Fragment an die Anforderung an, wenn eine Anforderung an login.microsoftonline.com gesendet wird, um einen Benutzer anzumelden.  Dadurch wird eine Klasse von Umleitungsangriffen verhindert, indem sichergestellt wird, dass der Browser jedes vorhandene Fragment in der Anforderung bereinigt. Keine Anwendung sollte eine Abhängigkeit von diesem Verhalten aufweisen. Weitere Informationen finden Sie unter [Breaking Changes](https://docs.microsoft.com/azure/active-directory/develop/reference-breaking-changes#february-2020) in der Dokumentation zu Microsoft Identity Platform.

---

## <a name="december-2019"></a>Dezember 2019

### <a name="integrate-sap-successfactors-provisioning-into-azure-ad-and-on-premises-ad-public-preview"></a>Integrieren der SAP SuccessFactors-Bereitstellung in Azure AD und lokale AD-Instanzen (Public Preview)

**Typ:** Neues Feature  
**Dienstkategorie:** App-Bereitstellung  
**Produktfunktion:** Identity Lifecycle Management

Nun können Sie SAP SuccessFactors als autorisierende Identitätsquelle in Azure AD integrieren. Diese Integration unterstützt Sie bei der Automatisierung des gesamten Identitätslebenszyklus, einschließlich der Verwendung HR-basierter Ereignissen wie Neueinstellungen oder Kündigungen, um die Bereitstellung von Azure AD-Konten zu steuern.

Weitere Informationen zur Einrichtung der eingehenden SAP SuccessFactors-Bereitstellung in Azure AD finden Sie im Tutorial [Konfigurieren der Benutzerbereitstellung von SAP SuccessFactors zu Active Directory](https://aka.ms/SAPSuccessFactorsInboundTutorial).

---

### <a name="support-for-customized-emails-in-azure-ad-b2c-public-preview"></a>Unterstützung für angepasste E-Mails in Azure AD B2C (Public Preview)

**Typ:** Neues Feature  
**Dienstkategorie:** B2C – Verwaltung von Endbenutzeridentitäten  
**Produktfunktion:** B2B/B2C

Mit Azure AD B2C können Sie nun angepasste E-Mails erstellen, wenn Ihre Benutzer sich für Ihre Apps registrieren. Mithilfe von Anzeigesteuerelementen (Vorschauversion) und einem E-Mail-Drittanbieter wie [SendGrid](https://sendgrid.com/), [SparkPost](https://sparkpost.com/) oder einer benutzerdefinierten REST-API können Sie eigene Vorlagen, **Absenderadressen** und Betrefftexte verwenden. Darüber hinaus werden die Lokalisierung und benutzerdefinierte Einstellungen für einmalige Kennwörter unterstützt.

Weitere Informationen finden Sie unter [Benutzerdefinierte E-Mail-Überprüfung in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/custom-email).

---

### <a name="replacement-of-baseline-policies-with-security-defaults"></a>Ersetzung von Baselinerichtlinien durch Sicherheitsstandards

**Typ:** Geändertes Feature  
**Dienstkategorie:** Andere  
**Produktfunktion:** Identitätssicherheit und -schutz

Als Teil eines standardmäßig sicheren Authentifizierungsmodells werden die vorhandenen Baselineschutzrichtlinien aus allen Mandanten entfernt. Diese Entfernung soll bis Ende Februar abgeschlossen sein. Sicherheitsstandards sind der Ersatz für diese Baselineschutzrichtlinien. Wenn Sie Baselineschutzrichtlinien verwenden, müssen Sie die Umstellung auf die neue Richtlinie mit Sicherheitsstandards oder den bedingten Zugriff planen. Wenn Sie diese Richtlinien nicht verwendet haben, müssen Sie keine Maßnahmen ergreifen.

Weitere Informationen zu den neuen Sicherheitsstandards finden Sie unter [Was sind Sicherheitsstandards?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Weitere Informationen über Richtlinien für den bedingten Zugriff finden Sie unter [Allgemeine Richtlinien für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).

---

## <a name="november-2019"></a>November 2019

### <a name="support-for-the-samesite-attribute-and-chrome-80"></a>Unterstützung für das SameSite-Attribut und Chrome 80

**Typ:** Plan für Änderung  
**Dienstkategorie:** Authentifizierungen (Anmeldungen)  
**Produktfunktion:** Benutzerauthentifizierung

Im Rahmen des standardmäßig sicheren Modells für Cookies wird geändert, wie der Chrome 80-Browser Cookies ohne `SameSite`-Attribut verarbeitet. Cookies ohne das `SameSite`-Attribut werden so behandelt, als wäre dieses auf `SameSite=Lax` festgelegt. Dadurch blockiert Chrome bestimmte domänenübergreifenden Cookiefreigaben, von denen Ihre App möglicherweise abhängig ist. Sie können das bisherige Verhalten von Chrome beibehalten, indem Sie das `SameSite=None`-Attribut verwenden und das `Secure`-Attribut hinzufügen, damit auf seitenübergreifende Cookies nur über HTTPS-Verbindungen zugegriffen werden kann. Diese Änderung in Chrome soll bis zum 4. Februar 2020 abgeschlossen sein.

Wir empfehlen unseren Entwicklern, ihre Apps anhand dieses Leitfadens zu testen:

- Legen Sie den Standardwert für die Einstellung **Sicheres Cookie verwenden** auf **Ja** fest.

- Legen Sie den Standardwert für das **SameSite**-Attribut auf **Keine** fest.

- Fügen Sie ein zusätzliches `SameSite`-Attribut von **Secure** hinzu.

Weitere Informationen finden Sie unter [Kommende Änderungen an SameSite-Cookies in ASP.NET und ASP.NET Core](https://devblogs.microsoft.com/aspnet/upcoming-samesite-cookie-changes-in-asp-net-and-asp-net-core/) und [Mögliche Unterbrechung bei Kundenwebsites und Microsoft-Produkten und -Diensten in Chrome-Version 79 und höher](https://support.microsoft.com/help/4522904/potential-disruption-to-microsoft-services-in-chrome-beta-version-79).

---

### <a name="new-hotfix-for-microsoft-identity-manager-mim-2016-service-pack-2-sp2"></a>Neuer Hotfix für Microsoft Identity Manager (MIM) 2016 Service Pack 2 (SP2)

**Typ:** Korrigiert  
**Dienstkategorie:** Microsoft Identity Manager  
**Produktfunktion:** Identity Lifecycle Management

Ein Hotfixrolluppaket (Build 4.6.34.0) ist für Microsoft Identity Manager (MIM) 2016 Service Pack 2 (SP2) verfügbar. Dieses Rolluppaket behebt Probleme und implementiert Verbesserungen, die im Abschnitt „Behobene Probleme und Verbesserungen in diesem Update“ beschrieben werden.

Weitere Informationen und das downloadbare Hotfixpaket finden Sie unter [Microsoft Identity Manager 2016 Service Pack 2 (Build 4.6.34.0) Updaterollup](https://support.microsoft.com/help/4512924/microsoft-identity-manager-2016-service-pack-2-build-4-6-34-0-update-r).

---

### <a name="new-ad-fs-app-activity-report-to-help-migrate-apps-to-azure-ad-public-preview"></a>Neuer AD FS-Bericht zu App-Aktivitäten zum Migrieren von Apps zu Azure AD (Public Preview)

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** SSO

Verwenden Sie den neuen Bericht zu App-Aktivitäten für Active Directory-Verbunddienste (AD FS) im Azure-Portal, um zu ermitteln, welche Ihrer Apps zu Azure AD migriert werden können. Im Bericht werden alle AD FS-Apps im Hinblick auf die Kompatibilität mit Azure AD bewertet und auf Probleme überprüft sowie Anleitungen zum Vorbereiten einzelner Apps für die Migration bereitgestellt.

Weitere Informationen finden Sie unter [Verwenden das AD FS-Berichts für App-Aktivitäten zur Migration von Apps in Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/migrate-adfs-application-activity).

---

### <a name="new-workflow-for-users-to-request-administrator-consent-public-preview"></a>Neuer Workflow für Benutzer zum Anfordern der Administratoreinwilligung (Public Preview)

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Zugriffssteuerung

Der neue Workflow für die Administratoreinwilligung bietet Administratoren eine Möglichkeit, den Zugriff auf Apps zu gewähren, für die eine Administratoreinwilligung erforderlich ist. Wenn ein Benutzer versucht, auf eine App zuzugreifen, aber selbst keine Einwilligung erteilen kann, kann dieser jetzt eine Anforderung zur Administratoreinwilligung senden. Die Anforderung wird per E-Mail gesendet und in eine Warteschlange eingereiht, auf die alle Administratoren über das Azure-Portal zugreifen können, die als „Prüfer“ festgelegt sind. Nachdem eine ausstehende Anforderung überprüft wurde, wird der anfordernde Benutzer über die Entscheidung informiert.

Weitere Informationen finden Sie unter [Konfigurieren des Workflows für die Administratoreinwilligung (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).

---

### <a name="new-azure-ad-app-registrations-token-configuration-experience-for-managing-optional-claims-public-preview"></a>Neue Option „Azure AD App Registrations Token configuration“ (Konfiguration von Azure AD-App-Registrierungstoken) zur Verwaltung optionaler Ansprüche (Public Preview)

**Typ:** Neues Feature  
**Dienstkategorie:** Andere  
**Produktfunktion:** Entwickleroberfläche

Das neue Blatt **Azure AD App Registrations Token configuration** (Konfiguration von Azure AD-App-Registrierungstoken) im Azure-Portal zeigt App-Entwicklern eine dynamische Liste optionaler Ansprüche für ihre Apps an. Mit den neuen Optionen können Sie die Migration von Azure AD-Apps optimieren und Fehlkonfigurationen bei optionalen Ansprüchen auf ein Minimum reduzieren.

Weitere Informationen finden Sie unter [Bereitstellen optionaler Ansprüche für Ihre Azure AD-App](https://docs.microsoft.com/azure/active-directory/develop/active-directory-optional-claims).

---

### <a name="new-two-stage-approval-workflow-in-azure-ad-entitlement-management-public-preview"></a>Neuer zweistufiger Genehmigungsworkflow in der Azure AD-Berechtigungsverwaltung (Public Preview)

**Typ:** Neues Feature  
**Dienstkategorie:** Andere  
**Produktfunktion:** Berechtigungsverwaltung

Wir haben einen neuen zweistufigen Genehmigungsworkflow eingeführt, der es Ihnen ermöglicht, dass zwei genehmigende Personen die Anforderung eines Benutzers für den Zugriffs auf ein Paket genehmigen müssen. So können Sie z. B. festlegen, dass der Vorgesetzte des anfordernden Benutzers zunächst die Genehmigung erteilen muss. Anschließend muss der Ressourcenbesitzer die Genehmigung erteilen. Wenn eine der genehmigenden Personen keine Genehmigung verteilt, wird der Zugriff verweigert.

Weitere Informationen finden Sie unter [Ändern der Anforderungs- und Genehmigungseinstellungen für ein Zugriffspaket in der Azure AD-Berechtigungsverwaltung](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-request-policy).

---

### <a name="updates-to-the-my-apps-page-along-with-new-workspaces-public-preview"></a>Updates für die Seite „Meine Apps“ sowie neue Arbeitsbereiche (Public Preview)

**Typ:** Neues Feature  
**Dienstkategorie:** Meine Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten

Sie können jetzt anpassen, wie die Benutzer Ihrer Organisation die aktualisierte Seite „Meine Apps“ anzeigen und darauf zugreifen. Die neue Seite umfasst auch das neue Feature „Arbeitsbereiche“, mit dem Benutzer Apps einfacher suchen und organisieren können.

Weitere Informationen zur neuen Seite „Meine Apps“ und zum Erstellen von Arbeitsbereichen finden Sie unter [Erstellen von Arbeitsbereichen im Portal „Meine Apps“](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-workspaces).

---

### <a name="google-social-id-support-for-azure-ad-b2b-collaboration-general-availability"></a>Unterstützung von Google-Konten für Azure AD B2B Collaboration (allgemeine Verfügbarkeit)

**Typ:** Neues Feature  
**Dienstkategorie:** B2B  
**Produktfunktion:** Benutzerauthentifizierung

Google-Konten (Gmail-Konten) werden jetzt in Azure AD unterstützt, um die Zusammenarbeit für Benutzer und Partner zu erleichtern. Ihre Partner müssen kein neues Microsoft-Konto mehr erstellen und verwalten. Microsoft Teams unterstützt Google-Benutzer jetzt auf allen Clients sowie in den gemeinsamen und mandantenbezogenen Authentifizierungsendpunkten vollständig.

Weitere Informationen finden Sie unter [Hinzufügen von Google als Identitätsanbieter für B2B-Gastbenutzer](https://docs.microsoft.com/azure/active-directory/b2b/google-federation).

---

### <a name="microsoft-edge-mobile-support-for-conditional-access-and-single-sign-on-general-availability"></a>Microsoft Edge-Unterstützung für Mobilgeräte für bedingten Zugriff und einmaliges Anmelden (allgemeine Verfügbarkeit)

**Typ:** Neues Feature  
**Dienstkategorie:** Bedingter Zugriff  
**Produktfunktion:** Identitätssicherheit und -schutz

Azure AD für Microsoft Edge in iOS und Android unterstützt jetzt einmaliges Anmelden und bedingten Zugriff in Azure AD:

- **Einmaliges Anmelden für Microsoft Edge:** Das einmalige Anmelden ist jetzt für native Clients wie Microsoft Outlook und Microsoft Edge für alle mit Azure AD verknüpften Apps verfügbar.

- **Bedingter Zugriff für Microsoft Edge:** Durch anwendungsbasierte Richtlinien für den bedingten Zugriff müssen die Benutzer durch Microsoft Intune geschützte Browser wie Microsoft Edge verwenden.

Weitere Informationen zum bedingten Zugriff und zum einmaligen Anmelden mit Microsoft Edge finden Sie im Blogbeitrag [Jetzt allgemein verfügbar: Unterstützung für bedingten Zugriff und einmaliges Anmelden für Mobilgeräte mit Microsoft Edge](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Edge-Mobile-Support-for-Conditional-Access-and-Single/ba-p/988179). Weitere Informationen zur Einrichtung Ihrer Client-Apps mit [App-basiertem bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) oder [gerätebasiertem bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/require-managed-devices) finden Sie unter [Verwalten des Webzugriffs durch einen mittels Microsoft Intune-Richtlinien geschützte Browser](https://docs.microsoft.com/intune/apps/app-configuration-managed-browser).

---

### <a name="azure-ad-entitlement-management-general-availability"></a>Azure AD-Berechtigungsverwaltung (allgemeine Verfügbarkeit)

**Typ:** Neues Feature  
**Dienstkategorie:** Andere  
**Produktfunktion:** Berechtigungsverwaltung

Die Azure AD-Berechtigungsverwaltung ist ein neues Identity-Governance-Feature, mit dem Organisationen Identitäts- und Zugriffslebenszyklen bedarfsgesteuert verwalten können. Mit diesem neuen Feature können Workflows für Zugriffsanforderungen, Zugriffszuweisungen, Überprüfungen und das Ablaufen von Gruppen, Apps und SharePoint Online-Websites automatisiert werden.

Mit der Azure AD-Berechtigungsverwaltung können Sie den Zugriff für interne Mitarbeiter und externe Benutzer Ihrer Organisation festlegen, die Zugriff auf diese Ressourcen benötigen.

Weitere Informationen finden Sie unter [Was ist die Azure AD-Berechtigungsverwaltung?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview#license-requirements).

---

### <a name="automate-user-account-provisioning-for-these-newly-supported-saas-apps"></a>Automatisieren der Bereitstellung von Benutzerkonten für diese neu unterstützten SaaS-Apps

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten  

Sie können ab sofort das Erstellen, Aktualisieren und Löschen von Benutzerkonten für diese neu integrierten Apps automatisieren:

[SAP Cloud Platform Identity Authentication Service](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-hana-cloud-platform-identity-authentication-tutorial), [RingCentral](https://docs.microsoft.com/azure/active-directory/saas-apps/ringcentral-provisioning-tutorial), [SpaceIQ](https://docs.microsoft.com/azure/active-directory/saas-apps/spaceiq-provisioning-tutorial), [Miro](https://docs.microsoft.com/azure/active-directory/saas-apps/miro-provisioning-tutorial), [Cloudgate](https://docs.microsoft.com/azure/active-directory/saas-apps/soloinsight-cloudgate-sso-provisioning-tutorial), [Infor CloudSuite](https://docs.microsoft.com/azure/active-directory/saas-apps/infor-cloudsuite-provisioning-tutorial), [OfficeSpace Software](https://docs.microsoft.com/azure/active-directory/saas-apps/officespace-software-provisioning-tutorial), [Priority Matrix](https://docs.microsoft.com/azure/active-directory/saas-apps/priority-matrix-provisioning-tutorial)

Weitere Informationen dazu, wie Sie Ihre Organisation durch die automatisierte Bereitstellung von Benutzerkonten besser schützen können, finden Sie unter [Automatisieren der Bereitstellung und Bereitstellungsaufhebung von Benutzern für SaaS-Anwendungen mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/user-provisioning).

---

### <a name="new-federated-apps-available-in-azure-ad-app-gallery---november-2019"></a>Neue Verbund-Apps im Azure AD-App-Katalog verfügbar (November 2019)

**Typ:** Neues Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** Integration von Drittanbieterprodukten

Im November 2019 haben wir diese 21 neuen Apps mit Verbundunterstützung in unseren App-Katalog aufgenommen:

[Airtable](https://docs.microsoft.com/azure/active-directory/saas-apps/airtable-tutorial), [Hootsuite](https://docs.microsoft.com/azure/active-directory/saas-apps/hootsuite-tutorial), [Blue Access for Members (BAM)](https://docs.microsoft.com/azure/active-directory/saas-apps/blue-access-for-members-tutorial), [Bitly](https://docs.microsoft.com/azure/active-directory/saas-apps/bitly-tutorial), [Riva](https://docs.microsoft.com/azure/active-directory/saas-apps/riva-tutorial), [ResLife Portal](https://app.reslifecloud.com/hub5_signin/microsoft_azuread/?g=44BBB1F90915236A97502FF4BE2952CB&c=5&uid=0&ht=2&ref=), [NegometrixPortal Single Sign On (SSO)](https://docs.microsoft.com/azure/active-directory/saas-apps/negometrixportal-tutorial), [TeamsChamp](https://login.microsoftonline.com/551f45da-b68e-4498-a7f5-a6e1efaeb41c/adminconsent?client_id=ca9bbfa4-1316-4c0f-a9ee-1248ac27f8ab&redirect_uri=https://admin.teamschamp.com/api/adminconsent&state=6883c143-cb59-42ee-a53a-bdb5faabf279), [Motus](https://docs.microsoft.com/azure/active-directory/saas-apps/motus-tutorial), [MyAryaka](https://docs.microsoft.com/azure/active-directory/saas-apps/myaryaka-tutorial), [BlueMail](https://loginself1.bluemail.me/), [Beedle](https://teams-web.beedle.co/#/), [Visma](https://docs.microsoft.com/azure/active-directory/saas-apps/visma-tutorial), [OneDesk](https://docs.microsoft.com/azure/active-directory/saas-apps/onedesk-tutorial), [Foko Retail](https://docs.microsoft.com/azure/active-directory/saas-apps/foko-retail-tutorial), [Qmarkets Idea & Innovation Management](https://docs.microsoft.com/azure/active-directory/saas-apps/qmarkets-idea-innovation-management-tutorial), [Netskope User Authentication](https://docs.microsoft.com/azure/active-directory/saas-apps/netskope-user-authentication-tutorial), [uniFLOW Online](https://docs.microsoft.com/azure/active-directory/saas-apps/uniflow-online-tutorial), [Claromentis](https://docs.microsoft.com/azure/active-directory/saas-apps/claromentis-tutorial), [Jisc Student Voter Registration](https://docs.microsoft.com/azure/active-directory/saas-apps/jisc-student-voter-registration-tutorial), [e4enable](https://portal.e4enable.com/)

Weitere Informationen zu den Apps finden Sie unter [SaaS-Anwendungsintegration mit Azure Active Directory](https://aka.ms/appstutorial). Weitere Informationen zum Listen Ihrer Anwendung im Azure AD-App-Katalog finden Sie unter [Listen Ihrer Anwendung im Azure Active Directory-Anwendungskatalog](https://aka.ms/azureadapprequest).

---

### <a name="new-and-improved-azure-ad-application-gallery"></a>Neuer und verbesserter Azure AD-App-Katalog

**Typ:** Geändertes Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** SSO

Wir haben den Azure AD-App-Katalog überarbeitet, damit Sie einfacher nach vorintegrierten Apps suchen können, die die Bereitstellung, OpenID Connect und SAML in Ihrem Azure Active Directory-Mandanten unterstützen.

Weitere Informationen finden Sie unter [Hinzufügen einer Anwendung zum Azure Active Directory-Mandanten](https://docs.microsoft.com/azure/active-directory/manage-apps/add-application-portal).

---

### <a name="increased-app-role-definition-length-limit-from-120-to-240-characters"></a>Erhöhtes Zeichenlimit für App-Rollendefinitionen (240 statt 120 Zeichen)

**Typ:** Geändertes Feature  
**Dienstkategorie:** Unternehmens-Apps  
**Produktfunktion:** SSO

Kunden haben uns gemeldet, dass das Zeichenlimit von 120 Zeichen für die App-Rollendefinition bei einigen Apps und Diensten zu kurz ist. Deshalb haben wir die maximale Länge für Rollendefinitionen auf 240 Zeichen erhöht.

Weitere Informationen zu App-spezifischen Rollendefinitionen finden Sie unter [Hinzufügen von App-Rollen in Ihrer App und Empfangen der Rollen im Token](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps).

---
