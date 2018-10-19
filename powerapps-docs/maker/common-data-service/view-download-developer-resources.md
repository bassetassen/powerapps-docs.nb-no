---
title: Vis eller last ned utviklerressurser | MicrosoftDocs
description: Finn utviklerressurser og nettadresser for tjenesteendepunkter
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.openlocfilehash: ae93b57d9ead3a62fb538ae986eb524367259545
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696145"
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>Vis eller last ned utviklerressurser

Denne siden leverer ressurser til utviklere og informasjon om den bestemte forekomsten du jobber med. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>Vis siden for utviklerressurser for miljøet ditt

1. Velg ![Innstillinger-knappen](../../administrator/media/settings-button-nav-bar.png) Innstillinger-knappen, fra PowerApps-portalen, og velg **Avanserte tilpassinger**.

    ![Avanserte tilpassinger](media/advanced-customizations-menu.png)

1. Velg koblingen **Utviklerressurser** i panelet **Avanserte tilpassinger**:<br />![Utviklerressurser-kobling](media/developer-resources-link.png)

## <a name="getting-started"></a>Komme i gang 

Denne inndelingen inneholder koblinger for at utviklere skal finne ressurser. Følgende ressurser er tilgjengelige:


|Kobling |Beskrivelse|
|---------|---------|
|[Utviklersenter](https://go.microsoft.com/fwlink/?LinkId=551006)|Hovedinngangspunkt for dokumentasjon for utviklere.|
|[Foraer for utviklere](https://go.microsoft.com/fwlink/?LinkId=550993)|Still og svar på spørsmål med andre utviklere.|
|[NuGet-pakker](https://go.microsoft.com/fwlink/?LinkId=550994)|Oppdag NuGet-pakker for å legge til SDK-samlinger i prosjektene dine.|
|[Nedlastingsverktøy](https://go.microsoft.com/fwlink/?LinkID=512122)|Verktøy du har behov for at er tilgjengelige for nedlasting fra NuGet. Bruk PowerShell-skriptet på denne siden for å få de nyeste versjonene.|
|[Eksempelkode](https://go.microsoft.com/fwlink/?LinkId=553007)|En liste over eksemplene som er tilgjengelige.|
|[Oversikt for utviklere](https://go.microsoft.com/fwlink/?LinkId=550995)|Kobling til et emne som gir oversikt for utviklere.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>Koble appene dine til denne forekomsten av Common Data Service for apper

Denne inndelingen gir informasjon du trenger for å koble til Common Data Service for apper-forekomsten.

### <a name="instance-web-api"></a>Web-API for forekomst

Dette er nettadressen for Web-API-en for forekomsten. Web API-en er en OData v4 RESTful-API. Du kan også laste ned tjenestedokumentet som beskriver metadata og operasjonene som er tilgjengelige i forekomsten din. Mer informasjon: [Utviklerdokumentasjon: Bruk Dynamics 365 Customer Engagement Web-API-en](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

### <a name="organization-service"></a>Organisasjonstjeneste

Dette er nettadressen for SOAP-endepunktet for organisasjonstjenesten for forekomsten.
Du kan laste ned WSDL for denne tjenesten her, men vanligvis bruker du kodegeneringsverktøyet CrmSvcUtil.exe til å bygge enhetsklasser for .NET-prosjekter. Mer informasjon: 
- [Utviklerdokumentasjon: Opprett tidlig bundete enhetsklasser med kodegeneringsverktøyet (CrmSvcUtil.exe)](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [Utviklerdokumentasjon: Bruk organisasjonstjenesten til å lese og skrive data eller metadata](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>Referanseinformasjon for forekomst

Denne informasjonen gir en unik beskrivelse av forekomsten. Det finnes en GUID-**ID** og et **Unikt navn**.
Denne informasjonen er nødvendig når du bruker Azure-utvidelser med forekomsten.
Mer informasjon: [Utviklerdokumentasjon: Azure-utvidelser for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>Koble appene dine til søketjenesten Common Data Service for apper

Ettersom personer kan ha tilgang til flere miljøer for CDS for apper, tillater søketjenesten henting av tilgjengelige miljøer en person har tilgang til basert på brukerlegitimasjonen.

### <a name="discovery-web-api"></a>Discovery Web API

Dette er endepunktadressen for RESTful OData v4-versjonen av søketjenesten som skal brukes for forekomsten. Du kan også laste ned tjenestedokumentet her.
Mer informasjon: [Utviklerdokumentasjon: Oppdag nettadressen for organisasjonen ved å bruke Web-API-en](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)


### <a name="discovery-service"></a>Søketjeneste

Dette er endepunktadressen for SOAP-versjonen av søketjenesten som skal brukes for forekomsten. Du kan også laste ned tjenestedokumentet her.
Mer informasjon: [Utviklerdokumentasjon: Oppdag nettadressen for organisasjonen ved å bruke søketjenesten](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  
### <a name="more-information"></a>Mer informasjon

[Utviklerdokumentasjon: Utviklerdokumentasjonsside](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[Utviklerdokumentasjon: Bruk Dynamics 365 Customer Engagement Web-API-en](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[Utviklerdokumentasjon: Bruk organisasjonstjenesten til å lese og skrive data eller metadata](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[Utviklerdokumentasjon: Azure-utvidelser for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[Utviklerdokumentasjon: Oppdag nettadressen for organisasjonen ved å bruke Web-API-en](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[Utviklerdokumentasjon: Oppdag nettadressen for organisasjonen ved å bruke Web-API-en](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  

