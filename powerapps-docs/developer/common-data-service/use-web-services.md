---
title: Bruk nettjenester for Common Data Service for apper | Microsoft Docs
description: Lær hvordan utviklere kan bruke nettjenester for Common Data Service for apper.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/26/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 7e9e14a9d44a3326fb8ac32b11e46b61cc119c27
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42854442"
---
# <a name="use-common-data-service-for-apps-web-services"></a>Bruke Common Data Service for nettjenester for apper

Common Data Service for apper har to nettjenester som du kan bruke til å samhandle med dataene. Velg den som best passer best til kravene og ferdighetene dine. Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Velg din utviklingsstil for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/choose-development-style)

## <a name="web-api"></a>Web API
Web API-en er et OData v4 RESTful-endepunkt. Bruk dette for alle programmeringsspråk som støtter HTTP-forespørsler og godkjenning ved bruk av OAuth 2.0.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Bruk Web API-en for Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)

## <a name="organization-service"></a>Organisasjonstjeneste

Organisasjonstjenesten er en viktig del av plattformen Common Data Service for apper. Den er en Windows Communication Foundation (WCF)-tjeneste og viser for øyeblikket bare et SOAP-endepunkt. .NET-utviklere kan bruke SDK-samlinger til å utføre dataoperasjoner. I et programtillegg må du kjøre organisasjonstjenesten via SDK-samlinger.
> [!NOTE]
> Det er mulig for utviklere å bruke SOAP-endepunktet til organisasjonstjenesten uten å bruke .NET SDK-samlinger. Men RESTful-typen av Web API-en gjør den til et mer overlegent alternativ.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Å bruke organisasjonstjenesten i Dynamics 365](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service)

## <a name="about-the-web-services-and-the-platform"></a>Nettjenestene og plattformen

Det er nyttig å anerkjenne at organisasjonstjenesten er det som definerer plattformen. Web API-en gir en RESTful-programmeringsopplevelse, men til sjuende og sist går alle dataoperasjoner gjennom den underliggende organisasjonstjenesten. 

Organisasjonstjenesten definerer de støttede operasjonene som meldinger. Hver melding har et navn. Hver melding har et tilsvarende *&lt;meldingsnavn&gt;*`Request` og *&lt;meldingsnavn&gt;*`Response`-klasse i SDK-samlingene. [IOrganizationService-grensesnittet](/dotnet/api/microsoft.xrm.sdk.iorganizationservice) i `Microsoft.Xrm.Sdk.dll` definerer flere hjelpermetoder for vanlige CRUD-operasjoner så vel som en [Kjør-metode](/dotnet/api/microsoft.xrm.sdk.iorganizationservice.execute), som kan brukes til å aktivere meldinger. Alle meldinger bruker den underliggende [OrganizationRequest-klassen](/dotnet/api/microsoft.xrm.sdk.organizationrequest).

Web API-en inneholder alle de samme operasjonene som organisasjonstjenesten, men presenterer dem i en RESTful-stil ved bruk av OData v4-protokollen. OData v4 gir navngitte operasjoner via *funksjoner* eller *handlinger*. Nesten hver melding tilgjengelig i organisasjonstjenesten er en tilsvarende navngitt funksjon eller handling. Disse meldingene som tilsvarer CRUD-operasjoner, er ikke tilgjengelig i Web API-en fordi som en RESTful-tjeneste har de implementeringer ved bruk av metodene HENT, POST, OPPDATERING og SLETT HTTP.

.NET SDK-samlinger for SOAP-endepunktet i organisasjonstjenesten ble utformet for å ligne på de underliggende plattformtjenestene basert på[IOrganizationService-grensesnittet](/dotnet/api/microsoft.xrm.sdk.iorganizationservice). De er imidlertid ikke de samme komponentene og må derfor ikke forveksles med hverandre. 

SOAP-endepunktet for organisasjonstjenesten ble innført i 2011, og vi har kunngjort at den er avskrevet. Dette betyr at det fortsetter å fungere og støttes til vi fjerner det. Vi har også kunngjort at vi skal oppdatere .NET SDK-samlinger, slik at de fortsetter å fungere etter at SOAP-endepunktet er fjernet. Dette betyr at det blir gjort tilgjengelig oppdaterte SDK-samlinger før SOAP-endepunktet fjernes, og utviklerne må oppdatere koden for å bruke disse nye samlingene på et senere tidspunkt.

## <a name="discovery-services"></a>Søketjenester

Hver bruker av Common Data Service for apper får tilgang til flere forekomster av Common Data Service for apper. Med søketjenester kan du skrive kode for å gi brukerne en liste over forekomster de kan koble til, som er basert på Microsoft-kontoen de bruker. Hver forekomst inkluderer en nettadresse som du kan bruke til å koble til ønsket forekomst. 

Du får tilgang til en søketjeneste gjennom enten Web API-en eller organisasjonstjenesten.

- For Web API-en kan du se: [Dynamics 365 Customer Engagement – Veiledning for utviklere: Oppdag nettadressen for organisasjonen ved bruk av Web API-en](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)
- For organisasjonstjenesten kan du se: [Dynamics 365 Customer Engagement – Veiledning for utviklere: Oppdag nettadressen for organisasjonen ved bruk av organisasjonstjenesten](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)

## <a name="use-custom-actions"></a>Bruk egendefinerte handlinger

Én av de deklarative alternativene som er tilgjengelig for prosessene, er å opprette en *egendefinert handling*. En egendefinert handling betyr i hovedsak å opprette en ny melding i organisasjonstjenesten. Du kan bruke egendefinerte handlinger til å kombinere et sett med operasjoner i en navngitt gjenbrukbar operasjon. Du kan for eksempel opprette en ny melding *new_Escalate* som kombinerer et standardsett med operasjoner. Det bidrar til å varsle de riktige personene når en viktig kunde opplever et alvorlig problem.

Når du definerer en egendefinert handling, velger du signaturen til operasjonen. Dette gjør du ved å definere inndataparametere og egenskaper som skal inkluderes i resultatene som skal returneres. Egendefinerte handlinger kan deretter aktiveres fra en deklarativ prosess, ved å bruke utformingsprogrammet eller ved bruk av kode. 

Den unike verdien til egendefinerte handlinger er at de bestemte operasjonene de inneholder, kan endres av noen som ikke er en utvikler ved bruk av utformingsprogrammet, uten at dette får noen innvirkning på andre prosesser eller koden som påkaller den.  Dette forblir sant hvis signaturen til handling ikke endres. Hvis du trenger andre inndataparametere eller utdataegenskaper, kan du opprette en ny, forskjellig egendefinert handling for å unngå å bryte prosesser eller kode som bruker en eksisterende en.

Når en egendefinert handling defineres i et miljø, er en ny OData v4-handling tilgjengelig ved bruk av Web API-en. Den egendefinerte handlingen kan aktiveres ved bruk av [OrganizationRequest-klassen](/dotnet/api/microsoft.xrm.sdk.organizationrequest) direkte eller indirekte fra selve organisasjonstjenesten, ved bruk av *kodegenereringsverktøyet (CrmSvcUtil.exe)*.

Mer informasjon: 
- [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Oversikt over handlinger](/dynamics365/customer-engagement/customize/actions)
- [Utviklerveiledning for Dynamics 365 Customer Engagement – Opprett dine egne handlinger](/dynamics365/customer-engagement/developer/create-own-actions)
- [Dynamics 365 Customer Engagement – Veiledning for utviklere: Bruk Web API-handlinger > Bruk en egendefinert handling](/dynamics365/customer-engagement/developer/webapi/use-web-api-actions#use-a-custom-action)

## <a name="metadata-services"></a>Metadatatjenester

Både Web API-en og organisasjonstjenesten inneholder funksjoner for å utføre CRUD-operasjoner i enhetsskjemaet. Selv om du kan utføre disse operasjonene ved bruk av kode, bruker du generelt utformingsprogrammer til å legge til, oppdatere eller slette egendefinerte skjemaelementer. Brukere må ha administratorrettigheter for å ta i bruk skjemaendringer, men alle brukerne kan lese metadata.

Et litt mer vanlig bruksområde for metadatatjenestene er å hente metadata om miljøet som utvidelsen kjører i. Fordi hvert miljø kan være annerledes og skjemametadata inneholder mye av informasjonen om hvordan miljøet er konfigurert, kan det hende at du må hente denne informasjonen slik at utvidelsene kan tilpasse seg til andre tilpassinger som er i bruk i miljøet.

Noen eksempler:
- Antallet tilgjengelig alternativer i et alternativsettattributt kan endre seg. I stedet for å hardkode verdiene i miljøet, kan du heller se om andre alternativer er tilstede. Du kan spørre systemet for å avgjøre om det gjeldende miljøet har ulike alternativer.
- Visningsnavnet for en enhet kan endres. Standard visningsnavn for kontoenheten er *Konto*. Dette kan endres til *Firma*. Hvis du ønsker å vise en melding til en bruker og henvise til et enhetsnavn, bør du ikke hardkode dette. Du bør heller bruke verdien som samsvarer med det brukeren er vant til å se, og heller bruke visningsnavnet hentet fra enhetsmetadataene.

Hvis du utvikler en god forståelse av metadataene i systemet, er det enklere å forstå hvordan plattformen Common Data Service for apper fungerer. Utformingsprogrammene som er tilgjengelig for å redigere metadata, kan ikke vise alle detaljene fra metadataene. Du kan installere en modelldrevet app med navnet *Metadata Browser*. Ved bruk av appen kan du vise alle de skjulte enhetene og metadataegenskapene i systemet. 

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Bla gjennom metadataene for organisasjonen](/dynamics365/customer-engagement/developer/browse-your-metadata)

Hvis du vil ha mer informasjon om det å arbeide med metadata programmatisk, kan du se:
- [Dynamics 365 Customer Engagement – Veiledning for utviklere: Bruk Web API-en med metadata](/dynamics365/customer-engagement/developer/webapi/use-web-api-metadata)
- [Dynamics 365 Customer Engagement – Veiledning for utviklere: Bruk organisasjonstjenesten med Dynamics 365-metadata](/dynamics365/customer-engagement/developer/org-service/use-organization-service-metadata)
 
### <a name="see-also"></a>Se også

[Common Data Service for apper – Oversikt for utviklere](overview.md)

