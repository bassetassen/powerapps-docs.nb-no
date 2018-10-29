---
title: Enhetstyper | MicrosoftDocs
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 2f3f6053-0b9e-41e7-bd94-2239351e9f4b
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 60e16ff8cb5c40a37cf0a5243b420f77c4a695bb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697809"
---
# <a name="types-of-entities"></a>Enhetstyper

Før du oppretter eller redigerer enheter i Common Data Service for apper, bør du forstå at det finnes ulike enhetstyper. Når en egendefinert enhet er opprettet, kan ikke disse typene endres. De to største gruppene er basert på eierskap for enhet og om enhetene er aktive enheter.  
  
<a name="BKMK_EntityOwnership"></a>

## <a name="entity-ownership"></a>Eierskap for enhet  

Det finnes fire ulike typer eierskap for enheter. Når du oppretter en egendefinert enhet, er det eneste alternativene **bruker eller team** eller **organisasjon**, men du må være oppmerksom på at andre enheter har ulike eierskapstyper.  
  
|Eierskap|Beskrivelse|  
|---------------|-----------------|  
|**Eies av bedriften**|Dataene i disse enhetene tilhører bedriftsenheten. Tilgang til dataene kan kontrolleres på forretningsenhetsnivå.|  
|**Ingen**|Data som ikke eies av en annen enhet.|  
|**Eies av organisasjonen**|Data tilhører organisasjonen. Tilgang til dataene kan kontrolleres på organisasjonsnivå.|  
|**Eies av bruker eller team**|Data tilhører en bruker eller et team. Handlinger som kan utføres på disse postene, kan kontrolleres på et brukernivå.|  
  
  
> [!IMPORTANT]
>  Etter at du oppretter en enhet, kan du ikke endre eierskap. Før du oppretter en enhet, må du sørge for at du velger riktig type eierskap. Hvis du senere finner ut at den egendefinerte enheten skal ha en annen type, kan du slette enheten, og deretter opprette en ny.
  
<a name="BKMK_ActivityEntities"></a>

## <a name="activity-entities"></a>Aktivitetsenheter

En aktivitet er en hvilken som helst handling en kan føre opp i en kalender. En aktivitet har tidsdimensjoner (starttidspunkt, sluttidspunkt og varighet) som bidrar til å fastslå når handlingen skjedde eller skal skje. Aktiviteter kan også inneholde data som bidrar til å fastslå hvilken handling aktiviteten representerer, for eksempel, emne og beskrivelse. En aktivitet kan åpnes, avbrytes eller fullføres. Fullført-statusen til en aktivitet har flere delstatusverdier knyttet til seg. Dette oppklarer måten aktiviteten ble fullført på.  
  
Aktivitetsenheter kan bare eier av en bruker eller et team, de kan ikke eies av en organisasjon.  
  
Den følgende tabellen viser aktiviteter som er tilgjengelig i et standardmiljø for CDS for apper.
  
|Navn|Beskrivelse|Vis i aktivitetsmenyer|Referanse|
|----------|-----------------|----------------|---------------|  
|**Avtale**|Forpliktelse som representerer et tidsintervall med start-/sluttidspunkt og varighet.|Ja|[Avtale](/powerapps/developer/common-data-service/reference/entities/appointment)|
|**Email**|Aktivitet som leveres ved bruk av e-postprotokoller.|Ja|[E-post](/powerapps/developer/common-data-service/reference/entities/email)|
|**Telefaks**|Aktivitet som sporer samtaleresultat og antall sider for en faks, og eventuelt lagrer en elektronisk kopi av dokumentet.|Ja|[Telefaks](/powerapps/developer/common-data-service/reference/entities/fax)|
|**Letter**|Aktivitet som sporer leveringen av et brev. Aktiviteten kan inneholde den elektroniske kopien av et brev.|Ja|[Letter](/powerapps/developer/common-data-service/reference/entities/letter)|
|**Telefonsamtale**|Aktivitet for å spore en telefonsamtale.|Ja|[Telefonsamtale](/powerapps/developer/common-data-service/reference/entities/phonecall)|
|**Regelmessig avtale**|Hovedavtalen for en regelmessig avtaleserie.|Ja|[RecurringAppointmentMaster](/powerapps/developer/common-data-service/reference/entities/recurringappointmentmaster)|
|**Oppgave**|Generisk aktivitet som representerer arbeid som må utføres.|Ja|[Oppgave](/powerapps/developer/common-data-service/reference/entities/task)|
  
Du kan opprette nye egendefinerte aktivitetsenheter. Du kan for eksempel opprette en egendefinert aktivitetsenhet for å registrere direktemeldingskommunikasjon. Det å opprette en aktivitetsenhet er forskjellig fra å opprette en ikke-aktivitetsenhet, fordi du ikke angir et primærfelt. Alle aktiviteter har et **primærfelt** angitt til **Emne** og andre vanlige felt som er angitt av aktivitetsenheten. Dette gjør at alle aktivitetene kan vises i en visning der bare de vanlige feltene vises.  

> [!NOTE]
> Du kan ikke opprette en egendefinert aktivitet ved bruk av PowerApps-portalen. Du må åpne løsningsutforsker ved bruk av **Avansert**-knappen.
  
Hvis du vil opprette en egendefinert enhet, velger du **Definer som en aktivitetsenhet**. Etter at du velger dette, ser du at **Vis i aktivitetsmenyer** er valgt. Denne innstillingen gjør det mulig å opprette denne typen aktiviteter i aktivitetsmenyene. Dette velges ikke for aktiviteter som vanligvis er knyttet til bestemte hendelser, og som opprettes ved bruk av kode eller av en arbeidsflyt. Etter at du har lagret enheten, kan du ikke endre disse innstillingene.  

### <a name="see-also"></a>Se også
[Opprette eller redigere enheter](create-edit-entities.md)
