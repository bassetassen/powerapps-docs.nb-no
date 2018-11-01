---
title: Kontrollere tilgang til modelldrevne appskjemaer i PowerApps | MicrosoftDocs
description: Lær hvordan du kontrollerer tilgang til hovedskjemaer
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
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="control-access-to-model-driven-app-forms"></a>Kontrollere tilgang til modelldrevne appskjemaer

 Du kan styre tilgang til hovedskjemaer på to ulike måter:  
  
- **Gjøre et hovedskjema inaktivt**  
  
     Du kan ikke angi en aktiv eller inaktiv tilstand for hovedskjemaer. Denne funksjonen ble inkludert hovedsakelig for å administrere nye skjemaer som tas med når Dynamics 365 customer engagement-organisasjoner oppgraderer, men du kan bruke den til å forhindre brukere fra å bruke ethvert hovedskjema.   
  
- **Tilordne sikkerhetsroller til hovedskjemaet**  
  
     Bruk denne til å gjøre et hovedskjema tilgjengelig for bestemte grupper.  
  
 Ulike brukere i organisasjonen kan arbeide med de samme dataene på ulike måter. Ledere kan være avhengige av å kunne søke raskt etter informasjon i en oppføring, og tjenestepersonell kan ha behov for et skjema som effektiviserer dataregistrering. Du kan ta hensyn til ulike behov ved å tilordne skjemaer til sikkerhetsroller som ulike brukergrupper tilhører.  
  
 Du finner trinnvise fremgangsmåter under [Tilordne sikkerhetsroller til skjema](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form).  
  
 Når flere hovedskjemaer eller mobile skjemaer er definert for en enhet, kan du velge hvilke skjemaer brukere skal kunne bruke, basert på sikkerhetsrollene deres. Siden hver enhet må kunne vise et skjema for enhver bruker, må minst ett skjema brukes som et basisskjema – et skjema som vises for brukere med sikkerhetsroller uten eksplisitt tilordnede skjemaer.  
  
> [!NOTE]
>  Hurtigopprettings- og hurtigvisningsskjemaer kan ikke tilordnes til sikkerhetsroller.  
  
 Du kan tilordne sikkerhetsroller til et skjema i skjemaredigeringsprogrammet eller fra skjemarutenettet. Hvis det bare er ett skjema for enheten, kan du imidlertid ikke fjerne merket for alternativet **Aktivert for basis** i dialogboksen **Tilordne sikkerhetsroller**. Selv om du i slike tilfeller har tilordnet sikkerhetsroller til skjemaet, kan alle som er knyttet til en sikkerhetsrolle som du ikke tok med, fortsatt vise skjemaet fordi det er aktivert som basisskjema.  
  
 Når du har opprettet et andre hovedskjema eller mobilt skjema for enheten, kan du fjerne merket for alternativet **Aktivert for basis** for ett av dem. Systemet sikrer at minst ett skjema alltid er aktivert for basis.  
  
 Når du har flere hovedskjemaer, kan du angi en skjemarekkefølge som styrer hvilket av skjemaene en bruker kan se, blir det de ser som standard. Hvis det er flere skjemaer de kan bruke, kan de bytte skjema, og skjemaet de velger, blir standardskjemaet til de velger et annet skjema. Denne innstillingen lagres i nettleseren. Hvis de bruker en annen datamaskin eller nettleser, ser de det opprinnelige standardskjemaet.  
  
## <a name="strategies-to-manage-the-fallback-form"></a>Strategier for å behandle basisskjemaet  
 Strategier for å behandle basisskjemaet omfatter følgende:  
  
<a name="BKMK_DoNotUseMultipleForms"></a>   
### <a name="all-users-view-the-same-form"></a>Alle brukere viser samme skjema  
 Hvis du ikke trenger flere skjemaer for en enhet, trenger du ikke et basisskjema.  
  
<a name="BKMK_Contingecyform"></a>   
### <a name="create-a-contingency-form"></a>Opprette et alternativt skjema  
 Hvis du bruker rollebaserte skjemaer fordi du vil begrense informasjonen brukere kan vise eller redigere, bør du vurdere å opprette et skjema der minst mulig informasjon vises. Velg deretter **Vis bare for disse valgte rollene** i dialogboksen **Tilordne sikkerhetsroller**, men ikke velg noen roller bortsett fra Systemansvarlig, og velg **Aktivert for basis**. Resultatet er at dette skjemaet aldri blir sett av noen andre enn systemansvarlig og alle med sikkerhetsroller som ikke er knyttet til et bestemt skjema. Du kan ta med en HTML-webressurs i skjemaet med informasjon om hvorfor så lite informasjon vises i skjemaet, og en kobling til informasjon om hvordan brukerne kan be om å bli lagt til i en sikkerhetsrolle som er knyttet til et skjema, eller for å inkludere en ny sikkerhetsrolle for et skjema.  
  
> [!NOTE]
>  Du kan ikke inkludere en webressurs i en topptekst eller bunntekst.  
  
<a name="BKMK_CreateGenericForm"></a>   
## <a name="create-a-generic-form"></a>Opprette et generisk skjema  
 Hvis du bruker rollebaserte skjemaer til å tilby en tilpasset opplevelse basert på brukerens rolle, kan du bruke det minst spesialiserte skjemaet som basisskjema og konfigurere det slik at det vises for alle. Opprett deretter tilpassede skjemaer for bestemte sikkerhetsroller, og konfigurer disse skjemaene slik at de bare vises for sikkerhetsroller som trenger dem. Ikke aktiver disse skjemaene for basis. Bruk til slutt dialogboksen **Skjemarekkefølge** i **Skjemaer**-listen til å angi hvilke skjemaer som skal vises, ved å rangere dem fra mest eksklusive til minst eksklusive. Basisskjemaet er nederst i listen. Denne strategien fører til at brukere ser skjemaet som er tilpasset for deres rolle, som standardskjema, men de kan fortsatt bruke skjemavelgeren til å velge det mest vanlige skjemaet, hvis de vil. Uansett hvilket skjema de velger, blir det standardskjemaet til de velger et annet skjema.  
  
<a name="BKMK_UseFormScripting"></a>   
## <a name="use-form-scripting"></a>Bruke skjemaskript  

 I webprogrammet er det mulig, men ikke anbefalt, for en utvikler å bruke skript i Onload-skjemahendelsen for å bruke samlingen [Xrm.Page.ui.formSelector.items](http://go.microsoft.com/fwlink/p/?LinkID=513300) til å spørre tilgjengelige skjemaer og bruke navigate-metoden til å dirigere brukere til et bestemt skjema. Husk at [navigate-metoden](http://go.microsoft.com/fwlink/p/?LinkID=513301) fører til at skjemaet lastes inn på nytt (og at Onload-hendelsen skjer på nytt). Logikken i hendelsesbehandlingen må alltid kontrollere en betingelse før du bruker navigate-metoden, for å unngå en uendelig løkke eller unødig begrense brukeralternativer for navigering mellom skjemaer.  
  
 Denne fremgangsmåten fungerer ikke for Dynamics 365 for tablets fordi flere skjemaer ikke er tilgjengelige for valg.  

### <a name="next-steps"></a>Neste trinn  

[Tilordne sikkerhetsroller til skjemaer](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)
