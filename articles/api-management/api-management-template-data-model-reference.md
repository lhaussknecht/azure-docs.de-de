---
title: Datenmodellreferenz zu Azure API Management-Vorlagen | Microsoft-Dokumentation
description: Lernen Sie die Entitäts- und Typendarstellungen für gängige Elemente kennen, die in den Datenmodellen für die Entwicklerportalvorlagen in Azure API Management verwendet werden.
services: api-management
documentationcenter: ''
author: vladvino
manager: erikre
editor: ''
ms.assetid: b0ad7e15-9519-4517-bb73-32e593ed6380
ms.service: api-management
ms.workload: mobile
ms.tgt_pltfrm: na
ms.topic: article
ms.date: 11/04/2019
ms.author: apimpm
ms.openlocfilehash: 5625ff7e4fc51b9b6b894698719247902a480f44
ms.sourcegitcommit: 2ec4b3d0bad7dc0071400c2a2264399e4fe34897
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2020
ms.locfileid: "79224842"
---
# <a name="azure-api-management-template-data-model-reference"></a>Datenmodellreferenz zu Azure API Management-Vorlagen
In diesem Thema werden die Entitäts- und Typendarstellungen für gängige Elemente beschrieben, die in den Datenmodellen für die Entwicklerportalvorlagen in Azure API Management verwendet werden.  
  
 Weitere Informationen zum Arbeiten mit Vorlagen finden Sie unter [So passen Sie das Azure API Management-Entwicklerportal mithilfe von Vorlagen an](https://azure.microsoft.com/documentation/articles/api-management-developer-portal-templates/).  

[!INCLUDE [api-management-portal-legacy.md](../../includes/api-management-portal-legacy.md)]

[!INCLUDE [premium-dev-standard-basic.md](../../includes/api-management-availability-premium-dev-standard-basic.md)]

## <a name="reference"></a>Verweis

-   [API](#API)  
-   [API-Zusammenfassung](#APISummary)  
-   [Anwendung](#Application)  
-   [Anlage](#Attachment)  
-   [Codebeispiel](#Sample)  
-   [Comment](#Comment)  
-   [Filterung](#Filtering)  
-   [Kopfzeile](#Header)  
-   [HTTP-Anforderung](#HTTPRequest)  
-   [HTTP-Antwort](#HTTPResponse)  
-   [Problem](#Issue)  
-   [Vorgang](#Operation)  
-   [Vorgangsmenü](#Menu)  
-   [Vorgangsmenüelement](#MenuItem)  
-   [Seitenverwaltung](#Paging)  
-   [Parameter](#Parameter)  
-   [Produkt](#Product)  
-   [Anbieter](#Provider)  
-   [Darstellung](#Representation)  
-   [Abonnement](#Subscription)  
-   [Abonnementzusammenfassung](#SubscriptionSummary)  
-   [Benutzerkontoinformationen](#UserAccountInfo)  
-   [Benutzeranmeldung](#UseSignIn)  
-   [Benutzerregistrierung](#UserSignUp)  
  
##  <a name="api"></a><a name="API"></a> API  
 Die `API`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`id`|string|Ressourcenbezeichner. Zur eindeutigen Identifizierung der API in der aktuellen Instanz des API Management-Diensts. Der Wert ist eine gültige relative URL im Format `apis/{id}`, wobei `{id}` einen API-Bezeichner darstellt. Diese Eigenschaft ist schreibgeschützt.|  
|`name`|string|Der Name der API. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`description`|string|Beschreibung der API. Darf nicht leer sein. Kann HTML-Formatierungstags umfassen. Die maximale Länge beträgt 1000 Zeichen.|  
|`serviceUrl`|string|Absolute URL des Back-End-Diensts, der diese API implementiert.|  
|`path`|string|Relative URL, die diese API und all ihre Ressourcenpfade in der Instanz des API Management-Diensts eindeutig identifiziert. Sie wird an die Basis-URL des API-Endpunkts angehängt, die während der Dienstinstanzerstellung angegeben wurde, um eine öffentliche URL für diese API zu erstellen.|  
|`protocols`|Zahlenarray|Beschreibt, über welche Protokolle die Vorgänge in dieser API aufgerufen werden können. Zulässige Werte sind `1 - http` und `2 - https` oder beide.|  
|`authenticationSettings`|[Authentifizierungseinstellungen für den Autorisierungsserver](https://docs.microsoft.com/rest/api/apimanagement/apimanagementrest/azure-api-management-rest-api-contract-reference#AuthenticationSettings)|Die Sammlung von Authentifizierungseinstellungen, die in dieser API enthalten sind.|  
|`subscriptionKeyParameterNames`|Objekt (object)|Eine optionale Eigenschaft, mit der benutzerdefinierte Namen für Abfrage- und/oder Headerparameter angegeben werden können, in denen der Abonnementschlüssel enthalten ist. Wenn diese Eigenschaft vorhanden ist, muss sie mindestens eine der beiden folgenden Eigenschaften enthalten.<br /><br /> `{   "subscriptionKeyParameterNames":   {     "query": “customQueryParameterName",     "header": “customHeaderParameterName"   } }`|  
  
##  <a name="api-summary"></a><a name="APISummary"></a> API-Zusammenfassung  
 Die `API summary`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`id`|string|Ressourcenbezeichner. Zur eindeutigen Identifizierung der API in der aktuellen Instanz des API Management-Diensts. Der Wert ist eine gültige relative URL im Format `apis/{id}`, wobei `{id}` einen API-Bezeichner darstellt. Diese Eigenschaft ist schreibgeschützt.|  
|`name`|string|Der Name der API. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`description`|string|Beschreibung der API. Darf nicht leer sein. Kann HTML-Formatierungstags umfassen. Die maximale Länge beträgt 1000 Zeichen.|  
  
##  <a name="application"></a><a name="Application"></a> Anwendung  
 Die `application`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Id`|string|Der eindeutige Bezeichner der Anwendung.|  
|`Title`|string|Der Titel der Anwendung.|  
|`Description`|string|Die Beschreibung der Anwendung.|  
|`Url`|URI|Der URI für die Anwendung.|  
|`Version`|string|Versionsinformationen für die Anwendung.|  
|`Requirements`|string|Eine Beschreibung der Anforderungen für die Anwendung.|  
|`State`|number|Der aktuelle Status der Anwendung.<br /><br /> – 0 – registriert<br /><br /> – 1 – übermittelt<br /><br /> – 2 – veröffentlicht<br /><br /> – 3 – abgelehnt<br /><br /> – 4 – unveröffentlicht|  
|`RegistrationDate`|Datetime|Das Datum und die Uhrzeit der Anwendungsregistrierung.|  
|`CategoryId`|number|Die Kategorie der Anwendung (Finanzen, Unterhaltung usw.).|  
|`DeveloperId`|string|Der eindeutige Bezeichner des Entwicklers, der die Anwendung übermittelt hat.|  
|`Attachments`|Sammlung von [Attachment](#Attachment)-Entitäten.|Anlagen für die Anwendung, z. B. Screenshots oder Symbole.|  
|`Icon`|[Anlage](#Attachment)|Das Symbol für die Anwendung.|  
  
##  <a name="attachment"></a><a name="Attachment"></a> Anlage  
 Die `attachment`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`UniqueId`|string|Der eindeutige Bezeichner für die Anlage.|  
|`Url`|string|Die URL der Ressource.|  
|`Type`|string|Der Typ der Anlage.|  
|`ContentType`|string|Der Medientyp der Anlage.|  
  
##  <a name="code-sample"></a><a name="Sample"></a> Codebeispiel  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`title`|string|Der Name des Vorgangs.|  
|`snippet`|string|Diese Eigenschaft ist veraltet und sollte nicht verwendet werden.|  
|`brush`|string|Die bei der Anzeige des Codebeispiels zu verwendende Vorlage für Syntaxfarben. Zulässige Werte sind `plain`, `php`, `java`, `xml`, `objc`, `python`, `ruby` und `csharp`.|  
|`template`|string|Der Name dieser Codebeispielvorlage.|  
|`body`|string|Ein Platzhalter für den Codebeispielteil des Codeausschnitts.|  
|`method`|string|Die HTTP-Methode des Vorgangs.|  
|`scheme`|string|Das Protokoll, das für die Vorgangsanforderung verwendet werden soll.|  
|`path`|string|Der Pfad des Vorgangs.|  
|`query`|string|Beispiel für die Abfragezeichenfolge mit definierten Parametern.|  
|`host`|string|Die URL des API Management-Dienstgateways für die API, die diesen Vorgang enthält.|  
|`headers`|Sammlung von                                  [Header](#Header)-Entitäten.|Die Header für diesen Vorgang.|  
|`parameters`|Sammlung von [Parameter](#Parameter)-Entitäten.|Parameter, die für diesen Vorgang definiert sind.|  
  
##  <a name="comment"></a><a name="Comment"></a> Kommentar  
 Die `API`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Id`|number|Die ID des Kommentars.|  
|`CommentText`|string|Der Text des Kommentars. Kann HTML enthalten.|  
|`DeveloperCompany`|string|Der Unternehmensname des Entwicklers.|  
|`PostedOn`|Datetime|Das Datum und Uhrzeit der Bereitstellung des Kommentars.|  
  
##  <a name="issue"></a><a name="Issue"></a> Problem  
 Die `issue`-Entität weist die folgenden Eigenschaften auf.  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Id`|string|Der eindeutige Bezeichner für das Problem.|  
|`ApiID`|string|Die ID für die API, für die dieses Problem gemeldet wurde.|  
|`Title`|string|Der Titel des Problems.|  
|`Description`|string|Die Beschreibung des Problems.|  
|`SubscriptionDeveloperName`|string|Der Vorname des Entwicklers, der das Problem gemeldet hat.|  
|`IssueState`|string|Der aktuelle Status des Problems. Mögliche Werte sind „Vorgeschlagen“, „Geöffnet“, „Geschlossen“.|  
|`ReportedOn`|Datetime|Das Datum und die Uhrzeit, zu der das Problem gemeldet wurde.|  
|`Comments`|Sammlung von [Comment](#Comment)-Entitäten.|Kommentare zu diesem Problem.|  
|`Attachments`|Sammlung von [Attachment](api-management-template-data-model-reference.md#Attachment)-Entitäten.|Eventuelle Anlagen zum Problem.|  
|`Services`|Sammlung von [API](#API)-Entitäten.|Die von dem Benutzer, der das Problem gemeldet hat, abonnierten APIs.|  
  
##  <a name="filtering"></a><a name="Filtering"></a> Filterung  
 Die `filtering`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Pattern`|string|Der aktuelle Suchbegriff oder `null`, wenn kein Suchbegriff vorliegt.|  
|`Placeholder`|string|Der Text, der im Suchfeld angezeigt werden soll, wenn kein Suchbegriff angegeben ist.|  
  
##  <a name="header"></a><a name="Header"></a> Header  
 In diesem Abschnitt wird die `parameter`-Darstellung beschrieben.  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|-----------------|----------|  
|`name`|string|Parametername.|  
|`description`|string|Beschreibung des Parameters.|  
|`value`|string|Headerwert.|  
|`typeName`|string|Der Datentyp des Headerwerts.|  
|`options`|string|Optionen.|  
|`required`|boolean|Gibt an, ob der Header erforderlich ist.|  
|`readOnly`|boolean|Gibt an, ob der Header schreibgeschützt ist.|  
  
##  <a name="http-request"></a><a name="HTTPRequest"></a> HTTP-Anforderung  
 In diesem Abschnitt wird die `request`-Darstellung beschrieben.  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`description`|string|Vorgangsanforderungsbeschreibung.|  
|`headers`|Array von [Header](#Header)-Entitäten.|Anforderungsheader.|  
|`parameters`|Array von [Parametern](#Parameter)|Die Sammlung von Vorgangsanforderungsparametern.|  
|`representations`|Array von [Darstellungen](#Representation)|Die Sammlung von Vorgangsanforderungsdarstellungen.|  
  
##  <a name="http-response"></a><a name="HTTPResponse"></a> HTTP-Antwort  
 In diesem Abschnitt wird die `response`-Darstellung beschrieben.  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`statusCode`|Positive Ganzzahl|Statuscode der Vorgangsantwort.|  
|`description`|string|Vorgangsantwortbeschreibung.|  
|`representations`|Array von [Darstellungen](#Representation)|Die Sammlung von Vorgangsantwortdarstellungen.|  
  
##  <a name="operation"></a><a name="Operation"></a> Vorgang  
 Die `operation`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`id`|string|Ressourcenbezeichner. Zur eindeutigen Identifizierung des Vorgangs in der aktuellen Instanz des API Management-Diensts. Der Wert ist eine gültige relative URL im Format `apis/{aid}/operations/{id}`, wobei `{aid}` einen API-Bezeichner und `{id}` einen Vorgangsbezeichner darstellt. Diese Eigenschaft ist schreibgeschützt.|  
|`name`|string|Name des Vorgangs. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`description`|string|Beschreibung des Vorgangs. Darf nicht leer sein. Kann HTML-Formatierungstags umfassen. Die maximale Länge beträgt 1000 Zeichen.|  
|`scheme`|string|Beschreibt, über welche Protokolle die Vorgänge in dieser API aufgerufen werden können. Zulässige Werte sind `http`, `https` oder sowohl `http` als auch `https`.|  
|`uriTemplate`|string|Relative URL-Vorlage, die die Zielressource für diesen Vorgang identifiziert. Kann Parameter enthalten. Beispiel: `customers/{cid}/orders/{oid}/?date={date}`|  
|`host`|string|Die URL des API Management-Gateways, der die API hostet.|  
|`httpMethod`|string|Vorgangs-HTTP-Methode.|  
|`request`|[HTTP-Anforderung](#HTTPRequest)|Eine Entität, die Anforderungsdetails enthält.|  
|`responses`|Array von [HTTP-Antworten](#HTTPResponse)|Array von [HTTP Response](#HTTPResponse)-Entitäten des Vorgangs.|  
  
##  <a name="operation-menu"></a><a name="Menu"></a> Vorgangsmenü  
 Die `operation menu`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`ApiId`|string|Die ID der aktuellen API.|  
|`CurrentOperationId`|string|Die ID des aktuellen Vorgangs.|  
|`Action`|string|Der Menütyp.|  
|`MenuItems`|Sammlung von [Operation menu item](#MenuItem)-Entitäten.|Die Vorgänge für die aktuelle API.|  
  
##  <a name="operation-menu-item"></a><a name="MenuItem"></a> Vorgangsmenüelement  
 Die `operation menu item`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Id`|string|Die ID des Vorgangs.|  
|`Title`|string|Die Beschreibung des Vorgangs.|  
|`HttpMethod`|string|Die HTTP-Methode des Vorgangs.|  
  
##  <a name="paging"></a><a name="Paging"></a> Seitenverwaltung  
 Die `paging`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Page`|number|Die aktuelle Seitenzahl.|  
|`PageSize`|number|Die maximale Anzahl von Ergebnissen, die auf einer einzelnen Seite angezeigt werden.|  
|`TotalItemCount`|number|Die Anzahl der anzuzeigenden Elemente.|  
|`ShowAll`|boolean|Gibt an, ob alle Ergebnisse auf einer einzigen Seite angezeigt werden sollen.|  
|`PageCount`|number|Die Anzahl von Ergebnisseiten.|  
  
##  <a name="parameter"></a><a name="Parameter"></a> Parameter  
 In diesem Abschnitt wird die `parameter`-Darstellung beschrieben.  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|-----------------|----------|  
|`name`|string|Parametername.|  
|`description`|string|Beschreibung des Parameters.|  
|`value`|string|Parameterwert.|  
|`options`|Array von Zeichenfolgen|Für Abfrageparameterwerte definierte Werte.|  
|`required`|boolean|Gibt an, ob der Parameter erforderlich ist oder nicht.|  
|`kind`|number|Gibt an, ob dieser Parameter ein path-Parameter (1) oder ein querystring-Parameter (2) ist.|  
|`typeName`|string|Der Parametertyp.|  
  
##  <a name="product"></a><a name="Product"></a> Produkt  
 Die `product`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Id`|string|Ressourcenbezeichner. Zur eindeutigen Identifizierung des Produkts in der aktuellen Instanz des API Management-Diensts. Der Wert ist eine gültige relative URL im Format `products/{pid}`, wobei `{pid}` einen Produktbezeichner darstellt. Diese Eigenschaft ist schreibgeschützt.|  
|`Title`|string|Der Name des Produkts. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`Description`|string|Beschreibung des Produkts. Darf nicht leer sein. Kann HTML-Formatierungstags umfassen. Die maximale Länge beträgt 1000 Zeichen.|  
|`Terms`|string|Nutzungsbedingungen für das Produkt. Diese Bedingungen werden Entwicklern angezeigt, die das Produkt abonnieren möchten. Sie müssen die Bedingungen akzeptieren, um den Abonnementvorgang abschließen zu können.|  
|`ProductState`|number|Gibt an, ob das Produkt veröffentlicht wird. Veröffentlichte Produkte sind für Entwickler im Entwicklerportal sichtbar. Nicht veröffentlichte Produkte sind nur für Administratoren sichtbar.<br /><br /> Folgende Werte sind für den Produktstatus zulässig:<br /><br /> - `0 - Not Published`<br /><br /> - `1 - Published`<br /><br /> - `2 - Deleted`|  
|`AllowMultipleSubscriptions`|boolean|Gibt an, ob ein Benutzer zur gleichen Zeit mehrere Abonnements für dieses Produkt besitzen kann.|  
|`MultipleSubscriptionsCount`|number|Die maximale Anzahl von Abonnements für dieses Produkt, die ein Benutzer gleichzeitig haben darf.|  
  
##  <a name="provider"></a><a name="Provider"></a> Anbieter  
 Die `provider`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Properties`|Zeichenfolgenwörterbuch|Eigenschaften für diesen Authentifizierungsanbieter.|  
|`AuthenticationType`|string|Der Anbietertyp. (Azure Active Directory, Facebook-Anmeldung, Google-Konto, Microsoft-Konto, Twitter).|  
|`Caption`|string|Der Anzeigename des Anbieters.|  
  
##  <a name="representation"></a><a name="Representation"></a> Darstellung  
 In diesem Abschnitt wird eine `representation` beschrieben.  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`contentType`|string|Gibt einen registrierten oder benutzerdefinierten Inhaltstyp für diese Darstellung an, z.B. `application/xml`.|  
|`sample`|string|Ein Beispiel für die Darstellung.|  
  
##  <a name="subscription"></a><a name="Subscription"></a> Abonnement  
 Die `subscription`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Id`|string|Ressourcenbezeichner. Zur eindeutigen Identifizierung des Abonnements in der aktuellen Instanz des API Management-Diensts. Der Wert ist eine gültige relative URL im Format `subscriptions/{sid}`, wobei `{sid}` einen Abonnementbezeichner darstellt. Diese Eigenschaft ist schreibgeschützt.|  
|`ProductId`|string|Der Produktressourcenbezeichner des abonnierten Produkts. Der Wert ist eine gültige relative URL im Format `products/{pid}`, wobei `{pid}` einen Produktbezeichner darstellt.|  
|`ProductTitle`|string|Der Name des Produkts. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`ProductDescription`|string|Beschreibung des Produkts. Darf nicht leer sein. Kann HTML-Formatierungstags umfassen. Die maximale Länge beträgt 1000 Zeichen.|  
|`ProductDetailsUrl`|string|Relative URL zu den Produktdetails.|  
|`state`|string|Der Status des Abonnements. Mögliche Statusangaben:<br /><br /> - `0 - suspended`: Das Abonnement ist blockiert, und der Abonnent kann keine APIs des Produkts aufrufen.<br /><br /> - `1 - active`: Das Abonnement ist aktiv.<br /><br /> - `2 - expired`: Das Abonnement hat das Ablaufdatum erreicht und wurde deaktiviert.<br /><br /> - `3 - submitted`: Die Abonnementanforderung wurde vom Entwickler gesendet, aber noch nicht genehmigt oder abgelehnt.<br /><br /> - `4 - rejected`: Die Abonnementanforderung wurde von einem Administrator abgelehnt.<br /><br /> - `5 - cancelled`: Das Abonnement wurde vom Entwickler oder Administrator abgebrochen.|  
|`DisplayName`|string|Der Anzeigename des Abonnements.|  
|`CreatedDate`|dateTime|Das Datum, an dem das Abonnement erstellt wurde, im ISO 8601-Format: `2014-06-24T16:25:00Z`.|  
|`CanBeCancelled`|boolean|Gibt an, ob das Abonnement vom aktuellen Benutzer gekündigt werden kann.|  
|`IsAwaitingApproval`|boolean|Gibt an, ob das Abonnement zur Genehmigung vorliegt.|  
|`StartDate`|dateTime|Das Startdatum für das Abonnement im ISO 8601-Format: `2014-06-24T16:25:00Z`.|  
|`ExpirationDate`|dateTime|Das Ablaufdatum für das Abonnement im ISO 8601-Format: `2014-06-24T16:25:00Z`.|  
|`NotificationDate`|dateTime|Das Benachrichtigungsdatum für das Abonnement im ISO 8601-Format: `2014-06-24T16:25:00Z`.|  
|`primaryKey`|string|Der primäre Abonnementschlüssel. Die maximale Länge beträgt 256 Zeichen.|  
|`secondaryKey`|string|Der sekundäre Abonnementschlüssel. Die maximale Länge beträgt 256 Zeichen.|  
|`CanBeRenewed`|boolean|Gibt an, ob das Abonnement vom aktuellen Benutzer verlängert werden kann.|  
|`HasExpired`|boolean|Gibt an, ob das Abonnement abgelaufen ist.|  
|`IsRejected`|boolean|Gibt an, ob die Abonnementanforderung abgelehnt wurde.|  
|`CancelUrl`|string|Die relative URL zum Kündigen des Abonnements.|  
|`RenewUrl`|string|Die relative URL zum Verlängern des Abonnements.|  
  
##  <a name="subscription-summary"></a><a name="SubscriptionSummary"></a> Abonnementzusammenfassung  
 Die `subscription summary`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Id`|string|Ressourcenbezeichner. Zur eindeutigen Identifizierung des Abonnements in der aktuellen Instanz des API Management-Diensts. Der Wert ist eine gültige relative URL im Format `subscriptions/{sid}`, wobei `{sid}` einen Abonnementbezeichner darstellt. Diese Eigenschaft ist schreibgeschützt.|  
|`DisplayName`|string|Der Anzeigename des Abonnements.|  
  
##  <a name="user-account-info"></a><a name="UserAccountInfo"></a> Benutzerkontoinformationen  
 Die `user account info`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`FirstName`|string|Vorname. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`LastName`|string|Nachname. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`Email`|string|E-Mail-Adresse. Darf nicht leer sein und muss innerhalb der Dienstinstanz eindeutig sein. Die maximale Länge beträgt 254 Zeichen.|  
|`Password`|string|Kennwort des Benutzerkontos.|  
|`NameIdentifier`|string|Kontobezeichner, identisch mit der E-Mail-Adresse des Benutzers.|  
|`ProviderName`|string|Name des Authentifizierungsanbieters.|  
|`IsBasicAccount`|boolean|TRUE, wenn dieses Konto mithilfe von E-Mail-Adresse und Kennwort registriert wurde. FALSE, wenn das Konto mithilfe eines Anbieters registriert wurde.|  
  
##  <a name="user-sign-in"></a><a name="UseSignIn"></a> Benutzeranmeldung  
 Die `user sign in`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`Email`|string|E-Mail-Adresse. Darf nicht leer sein und muss innerhalb der Dienstinstanz eindeutig sein. Die maximale Länge beträgt 254 Zeichen.|  
|`Password`|string|Kennwort des Benutzerkontos.|  
|`ReturnUrl`|string|Die URL der Seite, auf der der Benutzer auf „Anmelden“ geklickt hat.|  
|`RememberMe`|boolean|Gibt an, ob die Informationen des aktuellen Benutzers gespeichert werden sollen.|  
|`RegistrationEnabled`|boolean|Gibt an, ob die Registrierung aktiviert ist.|  
|`DelegationEnabled`|boolean|Gibt an, ob die delegierte Anmeldung aktiviert ist.|  
|`DelegationUrl`|string|Die URL zur delegierten Anmeldung, falls diese aktiviert ist.|  
|`SsoSignUpUrl`|string|Die URL zur einmaligen Anmeldung für den Benutzer, sofern vorhanden.|  
|`AuxServiceUrl`|string|Wenn der aktuelle Benutzer ein Administrator ist, ist dies ein Link zur Dienstinstanz im Azure-Portal.|  
|`Providers`|Sammlung von [Provider](#Provider)-Entitäten.|Die Authentifizierungsanbieter für diesen Benutzer.|  
|`UserRegistrationTerms`|string|Bedingungen, denen ein Benutzer zustimmen muss, bevor er sich anmeldet.|  
|`UserRegistrationTermsEnabled`|boolean|Gibt an, ob Bedingungen aktiviert sind.|  
  
##  <a name="user-sign-up"></a><a name="UserSignUp"></a> Benutzerregistrierung  
 Die `user sign up`-Entität weist die folgenden Eigenschaften auf:  
  
|Eigenschaft|type|BESCHREIBUNG|  
|--------------|----------|-----------------|  
|`PasswordConfirm`|boolean|Der vom [Anmeldesteuerelement](api-management-page-controls.md#sign-up) verwendete Wert.|  
|`Password`|string|Kennwort des Benutzerkontos.|  
|`PasswordVerdictLevel`|number|Der vom [Anmeldesteuerelement](api-management-page-controls.md#sign-up) verwendete Wert.|  
|`UserRegistrationTerms`|string|Bedingungen, denen ein Benutzer zustimmen muss, bevor er sich anmeldet.|  
|`UserRegistrationTermsOptions`|number|Der vom [Anmeldesteuerelement](api-management-page-controls.md#sign-up) verwendete Wert.|  
|`ConsentAccepted`|boolean|Der vom [Anmeldesteuerelement](api-management-page-controls.md#sign-up) verwendete Wert.|  
|`Email`|string|E-Mail-Adresse. Darf nicht leer sein und muss innerhalb der Dienstinstanz eindeutig sein. Die maximale Länge beträgt 254 Zeichen.|  
|`FirstName`|string|Vorname. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`LastName`|string|Nachname. Darf nicht leer sein. Die maximale Länge beträgt 100 Zeichen.|  
|`UserData`|string|Der vom [Anmeldesteuerelement](api-management-page-controls.md#sign-up) verwendete Wert.|  
|`NameIdentifier`|string|Der vom [Anmeldesteuerelement](api-management-page-controls.md#sign-up) verwendete Wert.|  
|`ProviderName`|string|Name des Authentifizierungsanbieters.|

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zum Arbeiten mit Vorlagen finden Sie unter [So passen Sie das Azure API Management-Entwicklerportal mithilfe von Vorlagen an](api-management-developer-portal-templates.md).
