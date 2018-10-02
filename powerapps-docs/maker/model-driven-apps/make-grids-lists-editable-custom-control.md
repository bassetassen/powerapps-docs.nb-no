---
title: Gjøre rutenett (lister) i modelldrevne apper redigerbare ved hjelp av Egendefinert kontroll for redigerbart rutenett med PowerApps | MicrosoftDocs
description: Finn ut hvordan du bruker den egendefinerte kontrollen for redigerbart rutenett
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: cefbc0c2-769b-4230-ab5a-b28a84630a42
caps.latest.revision: 8
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="make-model-driven-app-grids-lists-editable-using-the-editable-grid-custom-control"></a>Gjøre rutenett (lister) i modelldrevne apper redigerbare ved hjelp av Egendefinert kontroll for redigerbart rutenett

I tidligere versjoner av Dynamics CRM kunne ikke brukerne skrive inn data direkte i rutenett (også kalt lister) eller delrutenett i skjemaer. De måtte velge oppføringen i rutenettet for å kunne åpne et skjema, redigere dataene, og deretter lagre, som krevde flere trinn. Med redigerbare rutenett kan brukere gjøre omfattende redigering direkte fra rutenett og delrutenett, enten de bruker en webapp, et nettbrett eller en telefon.  
  
 ![Eksempler på redigerbart rutenett](media/editable-grid-examples.png "Eksempler på redigerbart rutenett")  
  
 Når redigerbare rutenett er aktivert gjennom den egendefinerte kontrollen for redigerbare rutenett, kan brukere redigere de fleste typer felt, inkludert grunnleggende oppslagsfelt og alternativsett.  

**Støtte for redigerbare rutenett:**
  
-   Innebygd redigering av oppføringer på enhets- eller delrutenettnivå (inkluderer egendefinerte enheter)  
  
-   Systemvisninger og personlige visninger  
  
-   Webklienter og mobile klienter  
  
-   Navigering med tastatur eller mus  
  
-   Gruppering og sortering (du kan gruppere etter / sortere etter enhver kolonne i gjeldende visning)  
  
-   Filtrering  
  
-   Flytte og endre størrelsen på kolonner  
  
-   Paginering  
  
-   Lagring av endringer fra én økt til en annen for gruppering, sortering, filtrering, paginering og flytting og endring av størrelsen på kolonner  
  
-   Oppslagkonfigurasjon  
  
-   Beregnede felt og felt for beregnet verdi  
  
-   Forretningsregler (Vis feilmelding, Angi feltverdi, Angi som nødvendig for selskapet, Angi standardverdi, Lås eller lås opp felt)  
  
-   JavaScript-hendelser  
  
-   Aktivering eller deaktivering av celler basert på sikkerhetsrolle  
  
-   Brukere kan fortsatt bruke søk og diagrammer og får tilgang til handlingslinjen som med skrivebeskyttede rutenett  
  
## <a name="make-main-grids-editable"></a>Gjøre hovedrutenett redigerbare  
  
1.  Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).  
  
2.  I **Enheter**-listen åpner du den aktuelle enheten, velger kategorien **Kontroller** og velger deretter **Legg til kontroll**.  
  
     ![Legg til egendefinert kontroll for redigerbare rutenett](media/add-editable-grids-custom-control.png "Legg til egendefinert kontroll for redigerbare rutenett")  
  
3.  I dialogboksen **Legg til kontroll** velger du **Redigerbart rutenett** og velger deretter **Legg til**.  
  
4.  I **Redigerbart rutenett**-raden som er lagt til, velger du formfaktoren(e) du vil bruke rutenettet på. Dette gjør kontrollen for redigerbart rutenett til standardkontroll for valgt(e) formfaktor(er).  
  
     ![Rad i redigerbart rutenett med formfaktorutvalg](media/editable-grid-row-wit-factor-selection.png "Rad i redigerbart rutenett med formfaktorutvalg")    

   > [!NOTE]
   >  Under kjøring kan brukerne veksle mellom redigerbare rutenett og skrivebeskyttede rutenett.  
      
5.  Hvis du vil legge til et oppslag, går du til alternativgruppen **Redigerbart rutenett**, velger **Legg til oppslag**, og deretter i dialogboksen **Konfigurer egenskapen «Legg til oppslag»**:  
  
    1.  I listen **Tilgjengelige visninger** velger du visningen du vil legge til oppslaget for (velg for eksempel **Mine aktive forretningsforbindelser**).  
  
    2.  I listen **Tilgjengelige kolonner** velger du oppslagskolonnen du vil legge til (velg for eksempel**Primær kontakt**).  
  
    3.  I listen **Standardvisning** velger du datakilden for oppslagsfeltet.  
  
    4.  Hvis du vil begrense oppføringene som vises, merker du av for **Bare vis oppføringer hvor**, og velger deretter kriteriene fra listen. Velg deretter **OK**.  
  
         ![Legge til oppslag i kontrollen Redigerbart rutenett](media/add-lookup-in-editable-grid-control.png "Legge til oppslag i kontrollen Redigerbart rutenett")  
     
6.  Hvis du har et nestet rutenett, velger du blyantknappen for **Nestet rutenettvisning**, og deretter velger du enheten og visningen for det nestede rutenettet. For **Overordnet ID for nestet rutenett** velger du relasjonen for enhetene. Feltet ParentAccountID knytter for eksempel sammen enhetene **Forretningsforbindelse** og **Kontakt**.  
  
    > [!NOTE]
    >  Nestede rutenett er bare tilgjengelige for telefoner og nettbrett, ikke weben.  
  
7.  Hvis du ikke vil at brukeren skal kunne gruppere data etter en kolonne i visningen (du vil spare plass for eksempel), velger du blyantknappen i **Grupper etter kolonne**-raden, og deretter i **Konfigurer egenskapen "Grupper av kolonne"** velger **Deaktivert** og velger deretter **OK**.  
  
    > [!TIP]
    >  Dette er mest nyttig for delrutenett i skjemaer.  
  
8.  Hvis du vil legge til JavaScript-hendelser, velger du kategorien **Hendelser**, og deretter velger du de aktuelle enhetene, feltene og hendelsene. Mer informasjon: [Dokumentasjon for utviklere: Bruke redigerbare rutenett](/dynamics365/customer-engagement/developer/customize-dev/use-editable-grids-dynamics-365.md)  
  
     ![Legge til hendelser i kontrollen Redigerbart rutenett](media/add-events-in-editable-grid-control.png "Legge til hendelser i kontrollen Redigerbart rutenett")  
  
9. Hvis du vil lagre arbeidet, velger du **Lagre** på handlingslinjen.  
  
10. Når du er klar til å gjøre endringer tilgjengelige for teamet, velger du **Publiser** på handlingslinjen.  
  
11. Hvis du vil teste endringene, går til visningen som du angav i trinn 5, og gjør deretter noen redigeringsendringer.  
  
## <a name="make-a-sub-grid-on-a-form-editable"></a>Gjøre et delrutenett på et skjema redigerbart

> [!NOTE] 
> - For å lagre en endring i redigerbart rutenett i et delrutenett, må brukeren eksplisitt lagre før navigering ut av skjemaet.
> - Hvis du bruker gamle skjemaer (versjoner før Dynamics CRM 2016) og aktiverer et redigerbart rutenett for et delrutenett, gjengis ikke det redigerbare delrutenettet. Hvis det er nødvendig, kan systemansvarlige deaktivere gamle skjemaer i systeminnstillingene.
  
1.  Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).  
  
2.  Åpne skjemaet som inneholder delrutenettet.  
  
3.  Velg den aktuelle kontrollen, og velg deretter **Endre egenskaper** på båndet.  
  
4.  I dialogboksen **Angi egenskaper** velger du **Kontroller**, velger **Legg til kontroll** og følger deretter de samme trinnene som er oppført ovenfor.  
  
## <a name="supported-standard-entities"></a>Støttede standardenheter  
  
||||  
|-|-|-|  
|**Web/nettbrett/telefon**|**Bare nettbrett/telefon**|**Bare Web**|  
|Forretningsforbindelse<br /><br /> Avtale<br /><br /> Ressurs som kan reserveres<br /><br /> Bestilling av ressurs som kan reserveres<br /><br /> Overskrift for bestilling av ressurs som kan reserveres<br /><br /> Kategori for ressurs som kan reserveres<br /><br /> Kategoritilknytning for ressurs som kan reserveres<br /><br /> Kjennetegn for ressurs som kan reserveres<br /><br /> Ressursgruppe som kan reserveres<br /><br /> Bestillingsstatus<br /><br /> Sak<br /><br /> Kategori<br /><br /> Kjennetegn<br /><br /> Konkurrent<br /><br /> Kontakt<br /><br /> E-post<br /><br /> Rettighet<br /><br /> Tilbakemelding<br /><br /> Faktura<br /><br /> Kunnskapsartikkel<br /><br /> Visninger av kunnskapsartikkel<br /><br /> Kunnskapsbaseoppføring<br /><br /> Kundeemne<br /><br /> Salgsmulighet<br /><br /> Ordre<br /><br /> Telefonsamtale<br /><br /> Prisliste<br /><br /> Produkt<br /><br /> Kø<br /><br /> Tilbud<br /><br /> Rangeringsmodell<br /><br /> Rangeringsverdi<br /><br /> KPI-forekomst for serviceavtale<br /><br /> Sosial aktivitet<br /><br /> Sosial profil<br /><br /> Synkroniseringsfeil<br /><br /> Oppgave<br /><br /> Team<br /><br /> Bruker|Aktivitet<br /><br /> Vedlegg<br /><br /> Regelelement for kanaltilgangsprofil<br /><br /> Konkurrentadresse<br /><br /> Tilkobling<br /><br /> Tilkoblingsrolle<br /><br /> E-postsignatur<br /><br /> E-postmal<br /><br /> Utløpt prosess<br /><br /> Fakturaprodukt<br /><br /> Kunnskapsartikkelhendelse<br /><br /> Salg for emne til salgsmulighet<br /><br /> Prosess<br /><br /> Postboks<br /><br /> Ny prosess<br /><br /> Obs!<br /><br /> Salgsmulighetsprodukt<br /><br /> Salgsprosess for salgsmulighet<br /><br /> Ordreprodukt<br /><br /> Organisasjon<br /><br /> Prosess for telefon til sak<br /><br /> Prislisteelement<br /><br /> Køelement<br /><br /> Tilbudsprodukt<br /><br /> Sharepoint-dokument<br /><br /> Oversettelsesprosess|Kampanje<br /><br /> Kampanjeaktivitet<br /><br /> Kampanjesvar<br /><br /> Kanaltilgangsprofil<br /><br /> Regel for kanaltilgangsprofil<br /><br /> Kontrakt<br /><br /> Rettighetsmal<br /><br /> Ekstern part<br /><br /> Telefaks<br /><br /> Brev<br /><br /> Markedsføringsliste<br /><br /> Posisjon<br /><br /> Hurtigkampanje<br /><br /> Regelmessig avtale<br /><br /> Salgsmateriell<br /><br /> Serviceavtale|  
 
##  <a name="data-types-that-arent-editable-in-an-editable-grid"></a>Datatyper som ikke er redigerbare i et redigerbart rutenett
Følgende datatyper kan ikke redigeres i redigerbare rutenett: Kunde- og Partylist-oppslagsfelt, sammensatte (adresse)felt, tilstands-/statusfelt, felt knyttet til oppslagsenheter (for eksempel forretningsforbindelsesenheten inkluderer et kontaktoppslag, der Kontakt-feltet kan redigeres, men EmailAdress(Contact)-feltet kan ikke redigeres).  
 
## <a name="next-steps"></a>Neste trinn  
 [Bruke hurtigtaster i redigerbare rutenett](https://docs.microsoft.com/dynamics365/customer-engagement/basics/keyboard-shortcuts#editable-grids-views)

