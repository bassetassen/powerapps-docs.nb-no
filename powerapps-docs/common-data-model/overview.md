---
title: Hva er Common Data Model? | Microsoft Docs
description: Common Data Model er en standardisert, modulær, utvidbar samling av dataskjemaer publisert av Microsoft som er ment å gjøre det enklere å bygge, bruke og analysere data.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 07/24/2018
ms.author: robruc
ms.openlocfilehash: 1469646301c273067ad035428f03c452ae223604
ms.sourcegitcommit: abe4d4728db7f56088f618af5b820af78e7099c9
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/28/2018
ms.locfileid: "39331998"
---
# <a name="what-is-the-common-data-model"></a>Hva er Common Data Model?

Hvis du noen gang har støtt på utfordringer med data som er *nesten* like, eller som *burde* fungere sammen, og deretter har brukt mye krefter på å transformere felter og tabeller slik at de fungerer med de andre dataene dine, så vet du at felles dataelementer kan spare deg for krefter, effektivisere fremtidig utvikling og muliggjøre raskere analyse. Common Data Model (CDM) kan gi deg disse funksjonene med mer.

**Common Data Model (CDM)** er en standardisert, modulær, utvidbar samling av dataskjemaer publisert av Microsoft som er ment å gjøre det enklere å bygge, bruke og analysere data. Denne samlingen av forhåndsdefinerte skjemaer, som består av *enheter*, *attributter*, *semantiske metadata* og *relasjoner*, representerer konsepter og aktiviteter som brukes ofte, for eksempel Konto og Kampanje, for å forenkle oppretting, aggregasjon og analyse av data. Mer informasjon: [CDM-repositoriet på GitHub](https://aka.ms/cdmrepo)

![Common Data Model](media/cdm-entities.png)

Mer informasjon:[CDM-plakat](https://aka.ms/cdmposter)

## <a name="why-use-the-common-data-model"></a>Fordeler ved å bruke Common Data Model

CDM forenkler dataadministrasjon og programutvikling ved å slå sammen data i en kjent form, og ved å bruke strukturell og semantisk konsekvens på tvers av flere programmer og distribusjoner. Når dataene er i CDM, kan du med andre ord bruke dem i mange forskjellige programmer, effektivisere opprettelsen eller bruken av andre programmer slik at de kan nyttiggjøre seg av de eksisterende dataene, og lage rapporter for hvert av dem (eller alle) på en enkel måte. I tillegg kan dataintegratorer som henter data fra mange forskjellige systemer, fokusere på å plassere dataene i CDM i stedet for å bygge en ny modell for hvert program.

Tenk deg at du har tre forretningsprogrammer – ett program for materialer, ett for produksjon og ett for salg. Ofte ville hvert av disse programmene ha blitt opprettet med ulike strukturer som ville ha representert en enhet, for eksempel *Konto*, som er nesten lik (men som ikke er det). Med CDM ville du ha kunnet bygge dataene dine i et standardisert format (ved hjelp av CDM-enheter, -attributter, og -relasjoner), og deretter kunne hvert av disse programmene ha brukt de samme dataene som grunnlag. Hvert program kunne selvfølgelig hatt egne tilleggsdata og -skjemaer, basert på funksjonaliteten til hvert program. Når det gjelder utvikling, ville imidlertid programmene og rapportene ha kunnet hente de felles dataelementene raskt, smertefritt og trygt.

Og enn hvis det blir behov for å opprette et fjerde program? Dataene dine ligger klare i CDM-skjemaet, slik at du kan fokusere på forretningslogikk i stedet for dataproblemer og trege transformasjoner i utviklingsarbeidet.

Med andre ord tilbyr CDM følgende for dataene dine:

-   **Strukturell og semantisk konsekvens** på tvers av programmer og distribusjoner.

-   **Forenklet integrering og entydige data**, som samles inn fra prosesser, digitale samhandlinger, produkttelemetri, samhandlinger mellom personer og så videre.

-   **En enhetlig figur**, der dataintegreringer kan **kombinere eksisterende forretningsdata med andre kilder** og bruke disse dataene holistisk til å utvikle nye programmer eller utlede innsikt.

-   **Mulighet til å utvide skjemaet og CDM-enhetene** for å skreddersy Common Data Model for organisasjonen.

Du kan bruke CDM til å opprette nye datarepositorier som samsvarer med skjemaet, og du kan transformere eksisterende data til Common Data Model-skjemaet. Uansett hva du har tenkt til å gjøre med dataene etterpå, kan effektiviteten som følger av standardiseringen, få fart på og strømlinjeforme prosessen.

## <a name="who-uses-the-common-data-model"></a>Hvem bruker Common Data Model?

CDM brukes av en rekke kunder, partnere og produkter, der alle har samme mål om å slå sammen data i en velkjent form med semantisk betydning.

-   **Programutviklere**: Uavhengig av om disse brukerne benytter kodebaserte plattformer eller en plattform med svært lite eller ingen kode, for eksempel PowerApps, må de lagre og behandle data for programmene sine.

-   **Dataintegratorer**: Disse brukerne er ansvarlige for å hente data fra en rekke systemer, slik at de kan brukes av programmer.

Historisk sett har arbeidet med å bygge programmer vært nært knyttet til dataintegrering, men med CDM og plattformene som støtter den, kan disse prosessene skje uavhengig av hverandre.

## <a name="common-data-model-in-action"></a>Common Data Model i praksis

Microsoft og Microsofts partnere bruker CDM til sine egne programmer og tilbud og utvikler tilleggstjenester og -tilbud basert på CDM-skjemaer. Eksemplene nedenfor viser hvordan organisasjoner bruker CDM:

-   **Common Data Service (CDS) for apper**, som støtter Dynamics og PowerApps, lagrer data i samsvar med CDM-definisjonen. Mange av de opprinnelige forretningsenhetene som er inkludert i CDM, kom faktisk fra Dynamics-tilbud, for eksempel Dynamics 365 for Sales og Dynamics 365 for Marketing.

-   **Industrivertikaler**, for eksempel Helsevesen, samarbeider tett med Microsoft om å utvide CDM for deres bestemte forretningskonsepter, for eksempel *Pasient*- og *Omsorgsplan*, slik at de kan dele data og utvikle tjenester som gjør det mulig for partnere å utveksle data på en enkel måte, opprette interoperable programmer og tjenester og opprette raske analyser som er enkle å dele.

## <a name="next-step"></a>Neste trinn

[Slik bruker du Common Data Model](use-common-data-model.md): beskriver CDM i detalj og tar for seg brukstilfeller for oppretting av nye data i CDM eller transformering av eksisterende data til CDM.