---
title: Gjør modelldrevne apprutenett (lister) redigerbare ved bruk av den egendefinerte kontrollen Redigerbart rutenett med PowerApps | MicrosoftDocs
description: Lær hvordan du bruke den egendefinerte kontrollen Redigerbart rutenett
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
ms.openlocfilehash: 704280dbed2177ba9a5467e2897980f78c31b050
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696578"
---
# <a name="make-model-driven-app-grids-lists-editable-using-the-editable-grid-custom-control"></a>Gjør modelldrevne apprutenett (lister) redigerbare ved bruk av den egendefinerte kontrollen Redigerbart rutenett

I tidligere versjoner av Dynamics CRM kunne ikke brukerne angi data direkte i rutenett (noen ganger kalt lister) eller delrutenett i skjemaer. De måtte velge posten i rutenettet for å åpne et skjema, redigere dataene og deretter lagre, noe som krevde flere trinn. Med redigerbare rutenett kan brukerne gjøre omfattende innebygde redigeringer direkte fra rutenett og delrutenett, enten de bruker en nettapp, et nettbrett eller en telefon.  
  
 ![Eksempler på redigerbart rutenett](media/editable-grid-examples.png "Eksempler på redigerbart rutenett")  
  
 Når du aktiverer redigerbare rutenett gjennom den egendefinerte kontrollen Redigerbart rutenett, kan brukerne redigere de fleste felttyper i tillegg til grunnleggende oppslagsfelter og alternativsett.  

**Redigerbare rutenett støtter:**
  
-   Innebygd redigering av poster på enhets- eller delrutenettsnivå (inkludert egendefinerte enheter)  
  
-   Systemvisninger og personlige visninger  
  
-   Nett- og mobilklienter  
  
-   Navigasjon med tastatur eller mus  
  
-   Gruppering og sortering (du kan gruppere/sortere etter enhver kolonne i den gjeldende visningen)  
  
-   Filtrering  
  
-   Flytting og endring av størrelsen på kolonner  
  
-   Paginering  
  
-   Lagring av endringer fra én økt til en annen for gruppering, sortering, filtrering, paginering, og flytting og endring av størrelsen på kolonner  
  
-   Oppslagskonfigurasjon  
  
-   Beregnede felter og felter for beregnet verdi  
  
-   Forretningsregler (Vis feilmelding, Angi feltverdi, Angi nødvendig for selskapet, Angi standardverdi, Lås eller lås opp felt)  
  
-   JavaScript-hendelser  
  
-   Aktivering eller deaktivering av celler basert på sikkerhetsrolle  
  
-   Brukerne kan fortsatt bruke søke og diagrammer, og de får tilgang til handlingsfeltet på lik linje med skrivebeskyttede rutenett  
  
## <a name="make-main-grids-editable"></a>Gjøre primære rutenett redigerbare  
  
1.  Åpne [løsningsutforsker](advanced-navigation.md#solution-explorer).  
  
2.  Åpne riktig enhet fra **Enheter**-listen, velg **Kontroller**-fanen, og velg deretter **Legg til kontroll**.  
  
     ![Legg til den egendefinerte kontrollen Redigerbart rutenett](media/add-editable-grids-custom-control.png "Legg til den egendefinerte kontrollen Redigerbart rutenett")  
  
3.  Merk av for **Redigerbart rutenett** i dialogboksen **Legg til kontroll**, og velg deretter **Legg til**.  
  
4.  Velg formfaktoren(e) som du vil ta i bruk rutenettet for, i **Redigerbart rutenett**-raden som ble lagt til. Dette gjør den egendefinerte kontrollen Redigerbart rutenett til standardkontrollen for de(n) utvalgte formfaktoren(e).  
  
     ![Redigerbart rutenett-rad med utvalg formfaktor](media/editable-grid-row-wit-factor-selection.png "Redigerbart rutenett-rad med utvalg formfaktor")    

   > [!NOTE]
   >  Brukerne kan veksle mellom redigerbare rutenett og skrivebeskyttede rutenett under kjøring.  
      
5.  Hvis du vil legge til oppslag, velger du **Legg til oppslag** i **Redigerbart rutenett**-alternativgruppen, og deretter i dialogboksen **Konfigurer egenskapen «Legg til oppslag»**:  
  
    1.  Velg visningen du vil legge til oppslaget i (for eksempel, velg **Mine aktive kontoer**), i **Tilgjengelige visninger**-listen.  
  
    2.  Velg oppslagskolonnen du vil legge til (for eksempel, velg**Hovedkontakt**), i **Tilgjengelige kolonner**-listen.  
  
    3.  Velg datakilden for oppslagsfeltet i **Standardvisning**-listen.  
  
    4.  Hvis du ønsker å begrense postene som vises, merker du av for **Bare vis poster der**. Deretter velger du vilkårene fra listen, og velger **OK**.  
  
         ![Legg til oppslag Redigerbart rutenett-kontrollen](media/add-lookup-in-editable-grid-control.png "Legg til oppslag Redigerbart rutenett-kontrollen")  
     
6.  Hvis du har et nestet rutenett, velger du blyantknappen for **Nestet rutenettvisning**, og deretter velger du enheten og visningen for det nestede rutenettet. Velg relasjonen for enhetene for **Overordnet ID for nestet rutenett**. ParentAccountID-feltet kobler for eksempel sammen **Konto**- og **Kontakt**-enhetene.  
  
    > [!NOTE]
    >  Nestede rutenett er bare tilgjengelig for telefoner og nettbrett, ikke på nettet.  
  
7.  Hvis du ikke vil la brukeren gruppere data etter en hvilken som helst kolonne i visningen (du ønsker å spare plass, for eksempel), velger du blyantknappen i **Grupper etter kolonne**-raden. Deretter velger du **Deaktivert** i dialogboksen **Konfigurer egenskapen «Grupper etter kolonne»**. Til slutt velger du**OK**.  
  
    > [!TIP]
    >  Dette er mest nyttig for delrutenett i skjemaer.  
  
8.  Hvis du vil legge til JavaScript-hendelser, velger du **Hendelser**-fanen. Deretter velger du de riktige enhetene, feltene og hendelsene. Mer informasjon: [Utviklerdokumentasjon: Bruk redigerbare rutenett](/dynamics365/customer-engagement/developer/customize-dev/use-editable-grids-dynamics-365.md)  
  
     ![Legg til hendelser i Redigerbart rutenett-kontrollen](media/add-events-in-editable-grid-control.png "Legg til hendelser i Redigerbart rutenett-kontrollen")  
  
9. Hvis du vil lagre arbeidet ditt, velger du **Lagre** på handlingsfeltet.  
  
10. Når du er klar til å gjøre endringene tilgjengelig for teamet ditt, velger du **Publiser** på handlingsfeltet.  
  
11. Hvis du vil teste endringene, går du til visningen du angav i trinn 5. Deretter utfører du enkelte innebygde endringer.  
  
## <a name="make-a-sub-grid-on-a-form-editable"></a>Gjør et delrutenett på et skjema redigerbart

> [!NOTE] 
> - Hvis brukeren lagrer en endring i et redigerbart rutenett i et delrutenett, må vedkommende uttrykkelig lagre før de lukker skjemaet.
> - Hvis du bruker eldre skjemaer (versjoner før Dynamics CRM 2016) og aktiverer et redigerbart rutenett på et delrutenett, gjengis ikke det redigerbare delrutenettet. Systemansvarlige kan slå av eldre skjemaer i systeminnstillinger, ved behov.
  
1.  Åpne [løsningsutforsker](advanced-navigation.md#solution-explorer).  
  
2.  Åpne skjemaet som inneholder delrutenettet.  
  
3.  Velg den riktige kontrollen, og velg deretter **Endre egenskaper** på båndet.  
  
4.  Velg **Kontroller** i dialogboksen **Angi egenskaper**, velg **Legg til kontroll**, og deretter følger du de samme trinnene som er oppført ovenfor.  
  
## <a name="supported-standard-entities"></a>Støttede standardenheter  
  
||||  
|-|-|-|  
|**Nett/nettbrett/telefon**|**Bare nettbrett/telefon**|**Bare nett**|  
|Konto<br /><br /> Avtale<br /><br /> Ressurs som kan reserveres<br /><br /> Bestilling av ressurs som kan reserveres<br /><br /> Bestillingsoverskrift for ressurs som kan reserveres<br /><br /> Kategori for ressurs som kan reserveres<br /><br /> Kategori for ressurse som kan reserveres<br /><br /> Karakteristikk for ressurs som kan reserveres<br /><br /> Ressursgruppe som kan reserveres<br /><br /> Bestillingsstatus<br /><br /> Tilfelle<br /><br /> Kategori<br /><br /> Karakteristikk<br /><br /> Konkurrent<br /><br /> Kontakt<br /><br /> E-post<br /><br /> Rettigheter<br /><br /> Tilbakemeldinger<br /><br /> Faktura<br /><br /> Kunnskapsartikkel<br /><br /> Kunnskapsartikkel-visninger<br /><br /> Kunnskapsbasepost<br /><br /> Kundeemne<br /><br /> Salgsmulighet<br /><br /> Ordre<br /><br /> Telefonsamtale<br /><br /> Prisliste<br /><br /> Produkt<br /><br /> Kø<br /><br /> Tilbud<br /><br /> Vurderingsmodell<br /><br /> Vurderingsverdi<br /><br /> SLA KPI-forekomst<br /><br /> Sosial aktivitet<br /><br /> Sosiale profil<br /><br /> Synkroniseringsfeil<br /><br /> Oppgave<br /><br /> Team<br /><br /> Bruker|Aktivitet<br /><br /> Vedlegg<br /><br /> Regelelement for kanaltilgangsprofil<br /><br /> Adresse for konkurrent<br /><br /> Tilkobling<br /><br /> Tilkoblingsrolle<br /><br /> E-postsignatur<br /><br /> E-postmal<br /><br /> Utløpt prosess<br /><br /> Fakturer produkt<br /><br /> Kunnskapsartikkel-hendelse<br /><br /> Salgsprosessen Kundeemne til<br /><br /> Prosess<br /><br /> Postboks<br /><br /> Ny prosess<br /><br /> Obs!<br /><br /> Produkt for salgsmulighet<br /><br /> Salgsprosessen Salgsmulighet<br /><br /> Bestill produkt<br /><br /> Organisasjon<br /><br /> Prosessen Telefon til sak<br /><br /> Prislisteelement<br /><br /> Køelement<br /><br /> Tilbud for produkt<br /><br /> Sharepoint-dokument<br /><br /> Oversettelsesprosess|Kampanje<br /><br /> Kampanjeaktivitet<br /><br /> Kampanjesvar<br /><br /> Kanaltilgangsprofil<br /><br /> Regel for kanaltilgangsprofil<br /><br /> Kontrakt<br /><br /> Rettighetsmal<br /><br /> Eksterne part<br /><br /> Fax<br /><br /> Brev<br /><br /> Markedsføringsliste<br /><br /> Plassering<br /><br /> Hurtigkampanje<br /><br /> Regelmessig avtale<br /><br /> Salgslitteratur<br /><br /> SLA|  
 
##  <a name="data-types-that-arent-editable-in-an-editable-grid"></a>Datatyper som ikke kan redigeres i et redigerbart rutenett
De følgende datatypene kan ikke redigeres i redigerbare rutenett: Felter for Kunde og PartyList-oppslag, Sammensatt-felter (adresse), Delstats-/statusfelter, felter for enhetsoppslag (for eksempel, kontoenheten inneholder et kontaktoppslag der Kontakt-feltet kan redigeres, men EmailAdress(Contact)-feltet kan ikke redigeres).  
 
## <a name="next-steps"></a>Neste trinn  
 [Bruk hurtigtaster i redigerbare rutenett](https://docs.microsoft.com/dynamics365/customer-engagement/basics/keyboard-shortcuts#editable-grids-views)

