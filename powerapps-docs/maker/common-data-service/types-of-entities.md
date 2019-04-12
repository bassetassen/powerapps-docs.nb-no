---
title: Typer enheter | MicrosoftDocs
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="types-of-entities"></a>Typer enheter

Før du oppretter eller redigerer enheter i Common Data Service, må du være innforstått med at det finnes ulike typer enheter. Når en egendefinert enhet er opprettet, kan ikke disse typene endres. De to største skillene er basert på enhetseierskap og om enhetene er aktivitetsenheter.  
  
<a name="BKMK_EntityOwnership"></a>

## <a name="entity-ownership"></a>Enhetseierskap  

Det finnes fire typer enhetseierskap. Når du oppretter en egendefinert enhet, er de eneste alternativene **bruker- eller teameid** eller **organisasjonseid**, men du bør være oppmerksom på at andre enheter har forskjellige eierskapstyper.  
  
|Eierskap|Beskrivelse|  
|---------------|-----------------|  
|**Firmaeid**|Dataene i disse enhetene tilhører forretningsenheten. Tilgang til dataen kan kontrolleres på forretningsenhetsnivå.|  
|**Ingen**|Data eies ikke av en annen enhet.|  
|**Organisasjonseid**|Data tilhører organisasjonen. Tilgang til dataene kontrolleres på organisasjonsnivå.|  
|**Bruker- eller teameid**|Data tilhører en bruker eller et team. Handlinger som kan utføres på disse oppføringene, kan kontrolleres på brukernivå.|  
  
  
> [!IMPORTANT]
>  Når en enhet er opprettet, kan du ikke endre eierskapet. Før du oppretter en enhet, må du sørge for at du velger riktig type eierskap. Hvis du senere finner ut at den egendefinerte enheten må være av en annen type, må du slette den og opprette en ny.
  
<a name="BKMK_ActivityEntities"></a>

## <a name="activity-entities"></a>Aktivitetsenheter

Du kan tenke på en aktivitet som en hvilken som helst handling som det kan lages en oppføring for i en kalender. En aktivitet har tidsdimensjoner (starttidspunkt, sluttidspunkt, forfallsdato og varighet) som bidrar til å bestemme når handlingen fant sted, eller vil finne sted. Aktiviteter inneholder også data som hjelper deg med å bestemme hvilken handling aktiviteten representerer, for eksempel emne og beskrivelse. En aktivitet kan åpnes, avbrytes eller fullføres. Den fullførte statusen for en aktivitet har flere underordnede statusverdier tilknyttet for å klargjøre hvordan aktiviteten ble fullført.  
  
Aktivitetsenheter kan bare eies av en bruker eller et team, de kan ikke eies av en organisasjon.  
  
Tabellen nedenfor viser aktivitetsenheter som er tilgjengelige i et standard Common Data Service-miljø.
  
|Navn|Beskrivelse|Vis på aktivitetsmenyer|Referanse|
|----------|-----------------|----------------|---------------|  
|**Avtale**|Forpliktelse som representerer et tidsintervall med start-/sluttidspunkt og varighet.|Ja|[Avtale](/powerapps/developer/common-data-service/reference/entities/appointment)|
|**E-postadresse**|Aktivitet som leveres ved bruk av e-postprotokoller.|Ja|[E-post](/powerapps/developer/common-data-service/reference/entities/email)|
|**Telefaks**|Aktivitet som sporer oppringingsresultat og antall sider for en faks, og kan lagre en elektronisk kopi av dokumentet.|Ja|[Telefaks](/powerapps/developer/common-data-service/reference/entities/fax)|
|**Brev**|Aktivitet som sporer levering av et brev. Aktiviteten kan inneholde den elektroniske kopien av brevet.|Ja|[Brev](/powerapps/developer/common-data-service/reference/entities/letter)|
|**Telefonsamtale**|Aktivitet for å spore en telefonsamtale.|Ja|[PhoneCall ](/powerapps/developer/common-data-service/reference/entities/phonecall)|
|**Regelmessig avtale**|Hovedavtalen for en serie med regelmessighetsavtaler.|Ja|[RecurringAppointmentMaster](/powerapps/developer/common-data-service/reference/entities/recurringappointmentmaster)|
|**Oppgave**|Generell aktivitet som representerer arbeid som må utføres.|Ja|[Oppgave](/powerapps/developer/common-data-service/reference/entities/task)|
  
Du kan opprette nye egendefinerte aktivitetsentiteter. Du kan for eksempel opprette en egendefinert aktivitetsenhet for å registrere direktemeldingskommunikasjon. Å opprette en aktivitetsenhet er forskjellig fra å opprette en ikke-aktivitetsenhet fordi du ikke angir et hovedfelt. Alle aktivitetsentiteter har et **hovedfelt** angitt til **Emne** og andre fellesfelt som er definert av aktivitetsenheten. Dette gjør at alle typer aktiviteter kan vises i en visning der bare fellesfeltene vises.  

> [!NOTE]
> Du kan ikke opprette en egendefinert aktivitet ved hjelp av PowerApps-portalen. Du må åpne løsningsutforskeren ved hjelp av den **Avansert**-knappen.
  
Hvis du vil opprette en egendefinert aktivitetsenhet, kan du velge **Definer som aktivitetsenhet**. Når du har valgt dette, ser du at **Vis på aktivitetsmenyer** er valgt. Denne innstillingen gjør at brukere kan opprette denne typen aktivitet i aktivitetsmenyene. Dette er ikke valgt for aktiviteter som vanligvis er tilknyttet bestemte hendelser og opprettet i bakgrunnen ved hjelp av kode eller ved hjelp av en arbeidsflyt. Når du har lagret enheten, kan du ikke endre disse innstillingene.  

### <a name="see-also"></a>Se også
[Opprette eller redigere enheter](create-edit-entities.md)
