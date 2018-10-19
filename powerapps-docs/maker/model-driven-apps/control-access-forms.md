---
title: Få kontroll over tilgangen til modelldrevne appskjema i PowerApps | MicrosoftDocs
description: Lær hvordan du kontrollerer tilgangen til hovedskjemaer
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 15d123e0-b604-45dd-ab34-0b37787a04bb
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: a895bd9ea0257585f942840924a7044a4dcc23fb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691216"
---
# <a name="control-access-to-model-driven-app-forms"></a>Få kontroll over tilgangen til modelldrevne appskjema

 Det finnes to måter du kan kontrollere tilgangen til hovedskjemaer på:  
  
- **Gjøre et hovedskjema inaktivt**  
  
     Du kan angi en aktiv eller inaktiv status til hovedskjemaer. Denne funksjonen er inkludert hovedsakelig for å administrere nye skjemaer som er inkludert når Dynamics 365 Customer Engagement-organisasjoner oppgraderes, men ved hjelp av denne kan du hindre brukere fra å kunne bruke hovedskjemaer.   
  
- **Tilordne sikkerhetsroller til hovedskjema**  
  
     Bruk denne til å gjøre et hovedskjema tilgjengelig for spesifikke grupper.  
  
 Forskjellige personer i organisasjonen kan samhandle med de samme dataene på forskjellige måter. Ledere kan være avhengige av muligheten til raskt å gå gjennom informasjon i en post, og tjenesteytere kan kreve et skjema som strømlinjeformer dataregistrering. Du kan håndtere ulike krav ved å tilordne skjemaer til sikkerhetsroller som tilhører forskjellige grupper.  
  
 Se [Tilordne sikkerhetsroller til skjemaer](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form) for trinnvis fremgangsmåte.  
  
 Når du har mer enn ett primært eller mobilt skjema som er definert for en enhet, kan du velge hvilke skjemaer brukere skal kunne bruke basert på sikkerhetsrollene deres. Fordi hver enhet må være i stand til å vise et skjema for alle brukere, må minst et skjema være angitt som «tilbakefallsskjema» – et skjema som er synlige for brukere hvis sikkerhetsroller ikke har noen skjemaer eksplisitt tilordnet.  
  
> [!NOTE]
>  Skjemaer for rask oppretting og rask visning kan ikke tilordnes til sikkerhetsroller.  
  
 Du kan tilordne sikkerhetsroller til et skjema i redigeringsprogrammet for skjema eller fra skjemarutenettet. Men hvis det er bare ett skjema for enheten, vil du ikke kunne fjerne **Aktivert for tilbakefall**-alternativet i dialogboksen **Tilordne sikkerhetsroller**. I dette tilfellet kan alle som er forbundet med en sikkerhetsrolle som du ikke inkluderte, fortsatt kunne vise skjemaet, selv om du har tilordnet sikkerhetsroller til skjemaet, fordi det er aktivert for «tilbakefall».  
  
 Når du har opprettet et annen primært eller mobilt skjema for enheten, vil du kunne fjerne **Aktivert for tilbakefall**-alternativet for ett av dem. Systemet vil alltid sikre at minst ett skjema er aktivert for tilbakefall.  
  
 Hvis du har mer enn ett hovedskjema, kan du angi en skjemarekkefølge som skal styre hvilke av skjemaene som brukere har tillatelse til å se, som vil være det de ser som standard. Hvis det er flere skjema brukerene kan bruke, kan de endre skjema, og det de velger, vil være standardskjemaet frem til de velger et annet. Denne preferansen er lagret i nettleseren. Hvis brukere bruker en annen datamaskin eller nettleser, ser de det opprinnelige standardskjemaet.  
  
## <a name="strategies-to-manage-the-fallback-form"></a>Strategier for å behandle tilbakefallskjemaet  
 Strategier for å behandle tilbakefallskjemaet inkluderer følgende:  
  
<a name="BKMK_DoNotUseMultipleForms"></a>   
### <a name="all-users-view-the-same-form"></a>Alle brukere viser det samme skjemaet  
 Hvis du ikke trenger flere skjemaer for en enhet, trenger du ikke et basisskjema.  
  
<a name="BKMK_Contingecyform"></a>   
### <a name="create-a-contingency-form"></a>Opprett et alternativt skjema  
 Hvis du bruker rollebaserte skjemaer fordi du ønsker å begrense informasjonen som vises eller redigeres, bør du vurdere å opprette et skjema der minst mulig av informasjonen vises. Deretter, velger du **, vis bare for disse valgte sikkerhetsrollene** i dialogboksen **Tilordne sikkerhetsroller**, men velg ikke noen roller med unntak av systemansvarlig, og velg **aktivert for tilbakefall**. Resultatet blir at dette skjemaet aldri vil bli sett av noen bortsett fra systemansvarlig og alle hvis sikkerhetsroller ikke er knyttet til et bestemt skjema. Du kan legge til en HTML-nettressurs i skjemaet med informasjon om hvorfor så lite informasjon er synlig i skjemaet og en kobling til informasjon om hvordan brukere sender en forespørsel om å få tildelt en sikkerhetsrolle som er tilknyttet et skjema, eller inkluderer en ny sikkerhetsrolle for et skjema.  
  
> [!NOTE]
>  Du kan ikke inkludere en nettressurs i en topptekst eller bunntekst i et skjema.  
  
<a name="BKMK_CreateGenericForm"></a>   
## <a name="create-a-generic-form"></a>Opprett et generisk skjema  
 Hvis du bruker rollebaserte skjemaer for å gi en tilpasset opplevelse basert på en brukers rolle, kan du angi det minst spesialiserte skjemaet som «tilbakefall»-skjema og konfigurere at det skal vises for alle. Så oppretter du tilpassede skjemaer for bestemte sikkerhetsroller, og konfigurerer at disse skjemaene skal vises kun for sikkerhetsrollene som krever dem. Ikke aktiver tilbakefall for disse skjemaene. Til slutt bruker du dialogboksen **skjemarekkefølge** i **skjemaer**-listen for å angi hvilke skjemaer som skal vises, ved å rangere dem fra mest eksklusiv til minst eksklusiv. Tilbakefall-skjemaet ditt skal ligge nederst i listen. Denne strategien vil føre til at personer som ser skjemaet som er tilpasset for deres rolle som standardskjema, men de kan fortsatt bruke skjemavelgeren til å velge det vanligste skjemaet hvis de vil. Uansett hvilket skjema de velger, forblir det standardskjemaet til de velger et annet.  
  
<a name="BKMK_UseFormScripting"></a>   
## <a name="use-form-scripting"></a>Bruk skjemaskripting  

 Til slutt, i nettprogrammet er det mulig, men ikke anbefalt, for utvikler å bruke skript i Onload-hendelsen for skjema for å bruke [Xrm.Page.ui.formSelector.items samling](http://go.microsoft.com/fwlink/p/?LinkID=513300) til å spørre tilgjengelige skjemaer og bruke navigeringsmetoden til å sende brukere til et bestemt skjema. Husk at [navigeringsmetoden](http://go.microsoft.com/fwlink/p/?LinkID=513301) vil føre til at skjemaet lastes inn på nytt, (og Onload-hendelsen skjer på nytt). Logikken i hendelsesbehandlingsprogrammet bør alltid kontrollere noen betingelser før du bruker navigeringsmetoden for å unngå en uendelig løkke eller unødvendig begrense brukernes muligheter til å navigere mellom skjemaer.  
  
 Denne fremgangsmåten fungerer ikke for Dynamics 365 for nettbrett fordi flere skjemaer ikke kan velges samtidig.  

### <a name="next-steps"></a>Neste trinn  

[Tilordne sikkerhetsroller til skjemaer](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)
