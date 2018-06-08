---
title: Oversikt over Common Data Model | Microsoft Docs
description: Finn ut hvordan Common Data Model kobler Common Data Service for Apps med Common Data Service for Analytics.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 03/14/2018
ms.author: jdaly
ms.openlocfilehash: 4e9b929558de0b2451bb2df4add4b300d7115848
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803248"
---
# <a name="common-data-model-overview"></a>Oversikt over Common Data Model

**Common Data Model** (CDM) er en definisjon av standard enheter med åpen kilde som representerer brukte konsepter og aktiviteter på tvers av en rekke forretnings- og programdomener. Common Data Model tilbyr *veldefinerte, modulbaserte og utvidbare* forretningsenheter som konto, forretningsenhet, sak, kontakt, kundeemne, salgsmulighet og produkt, samt samhandlinger og relasjoner mellom leverandører, arbeidere og kunder, for eksempel aktiviteter og servicenivåavtaler. 

Common Data Model er implementert i Microsofts [Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md) og Common Data Service for Analytics<!-- TODO add link when available  -->. Disse tjenestene inneholder data som samsvarer med definisjonen for Common Data Model. Ved å bygge på toppen av disse tjenestene kan pakkede programmer og analytiske løsninger fungere med veldefinerte enhetsfigurer og delingsdata, uavhengig av hvor dataene kom fra opprinnelig eller ble opprettet. Egendefinerte bransjespesifikke apper og analytiske løsninger kan bruke de samme enhetene for datadeling og dermed støtter dine behov og forretningskrav. 

Microsoft og våre partnere er forpliktet til å bygge programmene våre oppå Common Data Service og lagre forretningsdataene i CDM-form. Det finnes en *stor og voksende samling av løsninger som fungerer effektivt sammen når dataene er lagret i CDM-form*. Det betyr at du kan implementere nye forretningsprosesser og få innsikt i forretningsdriften raskt uten friksjon eller kompleksitet. Diagrammet nedenfor viser at programmer oppå Common Data Services bruker Common Data Model-enheter.

![Programmer oppå Common Data Services bruker Common Data Model-enheter](media/cdm-overview.png)

Common Data Model forenkler utfordringene med databehandling ved å slå sammen data i en kjent form med *strukturell og semantisk konsekvens på tvers av programmer og distribusjoner*. Det hjelper deg med å integrere og *gjøre data entydig*. Dette er data som samles inn fra forretningsprosesser, digitale samhandlinger, produkttelemetri, samhandlinger mellom personer og så videre. 

Data som er lagret i Common Data Service for Apps, *integreres enkelt og automatisk* med Common Data Service for Analytics for kunder som bruker begge tjenestene. Du kan starte fra forretnings- og transaksjonsdata du allerede eier (for eksempel kundeemner, kampanjeinformasjon, tidligere kundekjøp) og kombinere dem med data fra andre kilder (for eksempel nettlogger eller produkttelemetri) for å få et enhetlig bilde.

Common Data Model er også *utvidbar* – du kan legge til felter i de egendefinerte enhetene som følger med CDM, eller så kan du opprette dine egne egendefinerte enheter. CDM-standarden definerer et felles språk for forretningsenheter som dekker hele utvalget av forretningsprosesser på tvers av salg, tjenester, markedsføring, operasjoner, økonomi, talenter og handel, og for kunden, personene og produktenhetene i kjernen av forretningsprosessene til et firma. Common Data Model tilrettelegger for dataintegrasjon på tvers av flere kanaler, serviceimplementeringer og leverandører.

Common Data Model og Common Data Service gir en omfattende og produktiv utviklingsplattform gjennom disse funksjonene:

- **Definisjon av standard enheter** – Common Data Model gir en definisjon av enheter som representerer enhetene som brukes mest på tvers av forretnings- og produktivitetsprogrammer. Offentlig CDM GitHub-repositorium [(https://github.com/Microsoft/CDM)](https://github.com/Microsoft/CDM) blir kontinuerlig forbedret med kjerneenheter som dekker hele forretningsprosesslandskapet, flere vertikale datamodeller for bransjen og kryssomfattende kilder, som undersøkelser, søkemotorer og produkttelemetri.
- **Dataintegrering** – Bruk Power Query som innebygd nettopplevelse til å importere og visuelt transformere data fra dine eksisterende systemer og til å kombinere data fra nettbaserte og lokale datakilder uten kode eller med lav kode. Du kan bruke ferdighetene dine til å transformere Excel- og Power BI-data på en enkel måte. Se [Å legge til data i en enhet i Common Data Service ved hjelp av Power Query](../maker/common-data-service/data-platform-cds-newentity-pq.md).
    
    Når du importerer data til Common Data Service, kan du tilordne den til standard Common Data Model-enheter eller opprette og tilordne den til nye enheter. Maler for integrering og tilordning av data som er klare til bruk, forenkler tilkobling til vanlige datakilder som Salesforce. Disse malene for tilordning tilpasses og utvides fullstendig. Dette skjermbildet viser importering av eksterne data og tilordning av dem til standard enheter i Power Query. 
    
    ![Importere eksterne data og tilordne dem til standard enheter i Power Query ](media/cdm-mapping-entities.png)<br />

- **Utvidbarhet** – du kan utvide enhetene uten å forstyrre datadeling med andre apper.
- **Pålitelighet** – fordi du kan bruke vanlige enheter, kan du bygge gjenbrukbare komponenter som er bundet til enhetene. Common Data Model støtter fleksibilitet og versjonskontroll som beskytter utviklingsinvesteringen din.
- **Enhetskonsekvens på tvers av distribusjoner** – løsningene dine kan koble informasjon fra produktivitetsplattformer med data fra forretningsprogrammer. Du kan for eksempel koble en avtale i kalenderen eller en Microsoft Outlook-oppgave til en salgsmulighet. 

[Common Data Service for Apps](../maker/common-data-service/data-platform-intro.md) implementerer Common Data Model, som gjør at du kan gjøre følgende med utvikling av forretningsprogrammer:

- **Å dra nytte av pakkede forretningsprogrammer** – Dynamics 365-programmer for markedsføring, salg, service, talenter, økonomi og operasjon, og bruk i tillegg tredjepartsprogrammer som er bygd på toppen av Common Data Service for Apps.
- **Å tilpasse programmer og utvikle opprinnelige utvidelser for dine behov** – De som tilpasser og utvikler appene distribuerer programløsninger med en veldefinert livssyklus for programmet. Løsninger er måten programmer og utvidelser distribueres på. Se [Innføring i løsninger](../developer/common-data-service/introduction-solutions.md).
- **Å bygge ingen kode / lav kode, modelldrevet og WYSIWYG-lerretsapper med PowerApps** – Bruk de samme delte enhetene som opprettes/brukes av de pakkede programmene eller andre tredjepartsprogrammer, og opprette flere frittstående apper. Se: 
    - [Å bygge en modelldrevet app](../maker/model-driven-apps/model-driven-app-overview.md)
    - [Å bygge en lerretsapp](../maker/canvas-apps/getting-started.md) 
- **Å automatisere forretningsprosesser med Flow** – Bruk en forretningsprosessflyt for å definere et sett med faser og trinn for å oppnå et ønsket resultat. Se [Å opprette en flyt som bruker Common Data Service](/flow/common-data-model-intro)
 
Den kommende offentlige forhåndsvisningen av **Common Data Service for Analytics**<!-- TODO add link when available  --> implementerer også Common Data Model, støtter dataanalyse av forretningsdata i standardisert form, inkludert:

- **Pakkede og tilpassede analytiske løsninger basert på standard dataenheter** – analytiske programmer, for eksempel salginnsikt, som sporer historisk salgsytelse, gir konsekvent innsikt uavhengig av hvor dataene opprinnelig ble brukt, fordi dataintegreringen tilordner data fra andre kilder (for eksempel Salesforce.com) til enhetsfigurer for Common Data Model. Dette forenkler den analytiske løsningen slik at den kan fokusere på data-semantikk for veldefinerte enheter, for eksempel kundeemner og salgsmuligheter.
- **Integrering av Power Query-data med ingen kode / lav kode** – Bruk den innebygde opplevelsen til å opprette, fylle ut, transformere og berike enheter. 
- **Bruk din egen Azure-lagring** – dra nytte av Azure-datastakken for å gjøre data tilgjengelig for Common Data Service for Analytics. Enhetene er lagret i samme felles datamodellformat, gjenkjent av analytiske løsninger.

