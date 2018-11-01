---
title: Vise eller laste ned utviklerressurser | MicrosoftDocs
description: Finne ressurser for utviklere og URL-adresser til serviceendepunkt
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>Vise eller laste ned utviklerressurser

Denne siden inneholder ressurser for utviklere og informasjon om den spesifikke forekomsten som du arbeider med. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>Vis siden Ressurser for utviklere for miljøet ditt

1. Fra PowerApps-portalen velger du ![Innstillinger-knapp](../../administrator/media/settings-button-nav-bar.png) Innstillinger-knappen og velger **Avanserte tilpassinger**.

    ![Avanserte tilpassinger](media/advanced-customizations-menu.png)

1. I panelet **Avanserte tilpassinger** velger du koblingen **Ressurser for utviklere**:<br />![Koblingen Ressurser for utviklere](media/developer-resources-link.png)

## <a name="getting-started"></a>Komme i gang 

Denne delen inneholder koblinger der utviklere kan finne ressurser. Følgende ressurser er tilgjengelige:


|Kobling |Beskrivelse|
|---------|---------|
|[Utviklingssenter](https://go.microsoft.com/fwlink/?LinkId=551006)|Hovedinngangspunktet for dokumentasjon for utviklere.|
|[Foraer for utviklere](https://go.microsoft.com/fwlink/?LinkId=550993)|Få svar på spørsmål sammen med andre utviklere.|
|[NuGet-pakker](https://go.microsoft.com/fwlink/?LinkId=550994)|Finn NuGet-pakker for å legge til SDK-samlinger i prosjektene dine.|
|[Nedlastingsverktøy](https://go.microsoft.com/fwlink/?LinkID=512122)|Verktøy som du trenger, er tilgjengelige for nedlasting fra NuGet. Bruk PowerShell-skriptet på denne siden til å få den nyeste versjonen.|
|[Eksempelkode](https://go.microsoft.com/fwlink/?LinkId=553007)|En liste over tilgjengelige eksempler.|
|[Oversikt over utviklere](https://go.microsoft.com/fwlink/?LinkId=550995)|Kobling til et emne som gir en oversikt for utviklere.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>Koble apper til denne forekomsten av Common Data Service for Apps

Denne delen inneholder informasjonen du trenger for å koble til Common Data Service for Apps-forekomsten.

### <a name="instance-web-api"></a>Web-API for forekomst

Dette er URL-adressen for Web-API for forekomsten din. Web-API-et er et OData v4 RESTful-API. Du kan også laste ned servicedokumentet som beskriver metadataene og operasjonene som er tilgjengelige i forekomsten din. Hvis du vil ha mer informasjon: [Dokumentasjon for utviklere: Bruke web-API for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

### <a name="organization-service"></a>Organisasjonstjeneste

Dette er URL-adressen for SOAP-endepunktet for organisasjonstjenesten for forekomsten din.
Du kan laste ned WSDL for denne tjenesten her, men du bruker vanligvis kodegenereringsverktøyet CrmSvcUtil.exe til å bygge enhetsklasser for .NET-prosjekter. Mer informasjon: 
- [Dokumentasjon for utviklere: Opprette tidlig bundet enhets klasser med kodegenereringsverktøyet (CrmSvcUtil.exe)](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [Dokumentasjon for utviklere: Bruke organisasjonstjenesten til å lese og skrive data eller metadata](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>Referanseinformasjon for forekomst

Denne informasjonen beskriver forekomsten din unikt. Det er en GUID, **ID** og et **unikt navn**.
Denne informasjonen er nødvendig når du bruker Azure-utvidelser med forekomsten din.
Hvis du vil ha mer informasjon: [Dokumentasjon for utviklere: Azure-utvidelser for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>Koble apper til søketjensten for Common Data Service for Apps

Siden brukere kan ha tilgang til flere CDS for Apps-miljøer, tillater søketjenestene henting av de tilgjengelige miljøene som en person kan ha tilgang til, basert på brukerlegitimasjonen.

### <a name="discovery-web-api"></a>Søkeweb-API

Dette er endepunktadressen for RESTful OData v4-versjonen av søketjenesten som skal brukes for forekomsten din. Du kan også laste ned servicedokumentet her.
Mer informasjon: [Dokumentasjon for utviklere: Finne URL-adressen for organisasjonen ved hjelp av Web-API](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)


### <a name="discovery-service"></a>Søketjeneste

Dette er endepunktadressen for SOAP-versjonen av søketjenesten som skal brukes for forekomsten din. Du kan også laste ned servicedokumentet her.
Mer informasjon: [Dokumentasjon for utviklere: Finne URL-adressen for organisasjonen ved hjelp av søketjenesten](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  
### <a name="more-information"></a>Mer informasjon

[Dokumentasjon for utviklere: Siden for utviklerressurser](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[Dokumentasjon for utviklere: Bruke web-API for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[Dokumentasjon for utviklere: Bruke organisasjonstjenesten til å lese og skrive data eller metadata](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[Dokumentasjon for utviklere: Azure-utvidelser for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[Dokumentasjon for utviklere: Finne URL-adressen for organisasjonen ved hjelp av Web-API](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[Dokumentasjon for utviklere: Finne URL-adressen for organisasjonen ved hjelp av søketjenesten](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  

