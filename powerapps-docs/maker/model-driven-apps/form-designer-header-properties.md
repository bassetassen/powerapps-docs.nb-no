---
title: Konfigurere overskriftegenskaper i skjemautformingen | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="configure-header-properties-in-the-form-designer"></a>Konfigurere overskriftegenskaper i skjemautformingen
Utviklere kan styre tettheten til skjemaoverskrifter i modelldrevne apper for å samsvare med behovene til brukere som bruker skjemaet.

## <a name="high-density-header"></a>Overskrift med høy tetthet
Skjemaoverskrifter med høy tetthet sikrer at viktig informasjon alltid er synlig for brukerne. Ved hjelp av høytetthetsoverskrift blir oppføringstittelen aldri avkortet. Selv lange oppføringtitler vises ved hjelp av flere linjer. Overskrifter med høy tetthet sikrer også at opptil fire feltverdier er direkte synlige i overskriften og aldri avkortes eller skjules.  

For å sikre at viktig informasjon alltid er synlig, viser rammeverket skrivebeskyttede feltverdier, og brukere kan ikke redigere feltverdiene direkte i overskriften. Visualiseringer som egendefinerte kontroller eller webressurser er heller ikke tillatt.

Når et skjema ikke angir overskriftstetthet, eller når et nytt skjema opprettes, settes rammeverket som standard til høytetthetsoverskrift.

> [!div class="mx-imgBorder"] 
> ![Skjemaoverskrift med høy tetthet](media/form-header-high-density.png "Skjemaoverskrift med høy tetthet")
    
## <a name="low-density-header"></a>Overskrift med lav tetthet
Skjemaoverskrifter med lav tetthet lar brukerne redigere feltverdiene i overskriften direkte. Den tillater også visualiseringer som egendefinerte kontroller og webressurser.  
  
Men ofte kommer dette på bekostning av at nøkkelinformasjon blir avkortet eller ikke er lett synlig. Overskrifter med lav tetthet avkorter oppføringstittelen og feltverdiene som vises i overskriften. Ofte er bare ett eller to felt direkte synlige i overskriften, og resten overflyter og vises i en undermeny som krever et ekstra klikk.

> [!div class="mx-imgBorder"] 
> ![Skjemaoverskrift med lav tetthet](media/form-header-low-density.png "Skjemaoverskrift med lav tetthet")

### <a name="configuring-header-density"></a>Konfigurere overskriftstetthet

Hvis du vil konfigurere overskriftstettheten for et modelldrevet skjema, følger du fremgangsmåten nedenfor.
1.  Åpne skjemautformingen for å [opprette eller redigere et skjema](create-and-edit-forms.md).
2.  Velg skjemaoverskriften ved å velge overskriften i forhåndsvisningen av skjemaet eller ved å bruke [trevisningen](using-tree-view-on-form.md).
3.  I egenskapsruten velger du **Høy tetthet** for å bruke skjemaoverskrift med høy tetthet eller fjerner avmerkingen for å bruke skjemaoverskrift med lav tetthet.
4.  Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** for å lagre og gjøre endringene synlige for brukere.

> [!NOTE]
> Bruk den nye skjemautformingen. Den klassiske skjemautformingen gir ikke mulighet til å konfigurere overskriftstetthet.

## <a name="header-flyout"></a>Undermeny for overskrift
Undermenyen for overskrift vises når brukere velger vinkeltegnet i skjemaoverskriften. Det gjør det mulig for brukere å redigere feltverdier og viser også visualiseringer som egendefinerte kontroller eller webressurser som er en del av overskriften i skjemaet.

Virkemåten for undermenyen for overskrift endres avhengig av konfigurasjonen av overskriftstettheten.

### <a name="high-density-header-flyout"></a>Undermeny for overskrift med høy tetthet
Med en skjemaoverskrift med høy tetthet viser undermenyen for overskrifter alle overskriftsfelt, inkludert de fire feltene som vises direkte i overskriften. Rammeverket viser som standard overskriftsundermenyen når overskriften for høy tetthet brukes. Utviklere kan styre synligheten til undermenyen for overskrift med en høytetthetsoverskrift.

> [!div class="mx-imgBorder"] 
> ![Undermeny for overskrift med høy tetthet](media/form-header-flyout-high-density.png "Undermeny for overskrift med høy tetthet")

### <a name="low-density-header-flyout"></a>Undermeny for overskrift med lav tetthet
Med skjemaoverskrift lav tetthet viser undermenyen for overskrift bare overflytfeltene, for eksempel felt som skjemaet ikke kan vise direkte i overskriften basert på bredden på skjemaet. Undermenyen for overskrift vises eller skjules også automatisk basert på antall felt i overskriften og bredden på skjemaet. Utviklere kan ikke styre synligheten til undermenyen for overskrift når det brukes en overskrift med lav tetthet.

> [!div class="mx-imgBorder"] 
> ![Undermeny for overskrift med lav tetthet](media/form-header-flyout-low-density.png "Undermeny for overskrift med lav tetthet")

### <a name="show-or-hide-the-header-flyout"></a>Vise eller skjule undermenyen for overskrift
Hvis du vil vise eller skjule undermenyen for overskrift for et modelldrevet skjema, følger du fremgangsmåten nedenfor.

1.  Åpne skjemautformingen for å [opprette eller redigere et skjema](create-and-edit-forms.md).
2.  Velg skjemaoverskriften i forhåndsvisningen av skjemaet, eller bruk [trevisningen](using-tree-view-on-form.md) for å velge den.
3.  I egenskapsruten velger du **Høy tetthet** for å bruke skjemaoverskrift med høy tetthet. 
4.  I egenskapsruten velger du **Vis undermeny for overskrift** for å gjøre undermenyen for overskrift synlig, eller fjern merket for å skjule undermenyen for overskrift.
5.  Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** for å lagre og gjøre endringene synlige for brukere.

> [!NOTE]
> - Bruke den nye skjemautformingen. Den klassiske skjemautformingen gir ikke mulighet til å vise eller skjule overskriftsundermenyen.   
> - Synligheten til undermenyen for overskrift kan bare styres når det brukes en skjemaoverskrift med høy tetthet. Når overskrift med lav tetthet brukes, vises eller skjules undermenyen for overskrift automatisk basert på antall felt i overskriften og bredden på skjemaet.

## <a name="form-designer-messages-related-to-form-headers"></a>Skjemautformingsmeldinger relatert til skjemaoverskrifter
Når du redigerer skjemaer ved hjelp av den nye eller klassiske skjemautformingen, kan du se noen meldinger relatert til skjemaoverskrifter. Nedenfor finner du detaljer om hver melding og hvorfor du ser den.

### <a name="weve-upgraded-your-form-to-show-a-high-density-header-that-displays-more-data-you-can-edit-this-setting-in-the-properties-of-the-header"></a>Vi har oppgradert skjemaet for å vise en overskrift med høy tetthet som viser mer data. Du kan redigere denne innstillingen i egenskapene for overskriften. 
Denne meldingen vises i skjemautformingen når en utvikler oppretter et nytt hovedskjema (inkludert via Lagre som-handlingen) eller redigerer et hovedskjema som ikke tidligere er konfigurert for høy tetthet.  
  
Rammeverket bruker som standard overskrift med høy tetthet, og denne meldingen hjelper utviklere med å bli mer bevisste på atferden. Utviklere kan overstyre rammeverkstandarden når som helst ved manuelt å konfigurere tettheten for skjemaoverskriften som beskrevet tidligere.

### <a name="this-form-isnt-using-high-density-header-access-the-setting-in-the-header-properties-high-density-header-helps-display-more-data"></a>Dette skjemaet bruker ikke høytetthetsoverskrift. Få tilgang til innstillingen i overskriftsegenskapene. Høytetthetsoverskrift bidrar til å vise mer data. 
Denne meldingen vises i skjemautforming når en utvikler åpner et hovedskjema for redigering som er konfigurert til å bruke lavtetthetsoverskrift.      
  
Denne meldingen bidrar til å øke bevisstheten om høytetthetsoverskriften og dens fordeler.

### <a name="field-moved-to-header-flyout-the-header-supports-displaying-up-to-four-read-only-field-values-the-field-field-display-name-will-now-only-be-available-from-the-flyout"></a>Felt flyttet til overskriftsundermeny: Overskriften støtter visning av opptil fire skrivebeskyttede feltverdier. Feltet *[feltvisningsnavn]* vil nå bare være tilgjengelig fra undermenyen.
Denne meldingen vises i skjemautforming når et skjema bruker høytetthetsoverskrift med overskriftsundermenyen synlig.  
  
Høytetthetsoverskriften viser skrivebeskyttede verdier av de fire første feltene i overskriften. Når utviklere legger til et felt i overskriften i de fire øverste posisjonene, fører det til at et eksisterende felt som ble vist direkte i overskriften, blir utvidet og synlig bare i undermenyen for overskrift.      
  
Denne meldingen informerer utvikleren av endringen og bekrefter om du vil fortsette med handlingen.

### <a name="header-field-limit-exceeded-the-header-supports-displaying-up-to-four-read-only-field-values-remove-unused-fields-to-add-more"></a>Overskriftsfeltgrense overskredet: Overskriften støtter visning av opptil fire skrivebeskyttede feltverdier. Fjern ubrukte felt for å legge til flere. 
Denne meldingen vises i skjemautforming når et skjema bruker høytetthetsoverskrift med overskriftsundermenyen skjult.  
  
Høytetthetsoverskriften viser skrivebeskyttede verdier av opptil fire felt i overskriften. Siden overskriftsundermenyen er skjult, vil brukere ikke kunne se flere felt.  
  
Denne meldingen informerer utvikleren om at det allerede finnes fire felt i overskriften, og hindrer at det legges til flere felt i overskriften som brukerne ikke kan se.

### <a name="header-does-not-display-custom-components-the-header-supports-displaying-up-to-four-read-only-field-values-remove-the-custom-component-from-the-field-before-adding-it-to-the-header"></a>Overskriften viser ikke egendefinerte komponenter: Overskriften støtter visning av opptil fire skrivebeskyttede feltverdier. Fjern den egendefinerte komponenten fra feltet før du legger den til i overskriften.  
Denne meldingen vises i skjemautforming når et skjema bruker høytetthetsoverskrift med overskriftsundermenyen skjult.  
  
Høytetthetsoverskriften viser skrivebeskyttede verdier av felt i overskriften. Siden overskriftsundermenyen er skjult, vil brukere ikke kunne se egendefinerte komponenter som er knyttet til feltene i overskriften.  
  
Denne meldingen informerer utvikleren om at de prøver å legge til et felt med en tilknyttet egendefinert komponent i overskriften, og de må fjerne den egendefinerte komponenten før feltet legges til i overskriften. Dette er fordi brukerne ikke vil kunne se den egendefinerte komponenten i overskriften.

### <a name="header-displays-read-only-field-values-the-header-supports-displaying-up-to-four-read-only-field-values-to-provide-editability-to-the-user-add-the-field-to-a-section-in-the-form"></a>Overskriften viser skrivebeskyttede feltverdier: Overskriften støtter visning av opptil fire skrivebeskyttede feltverdier. Hvis du vil gi brukeren redigeringsmuligheter, legger du til feltet i en inndeling i skjemaet.  
Denne meldingen vises i skjemautforming når et skjema bruker høytetthetsoverskrift med overskriftsundermenyen skjult.  
  
Høytetthetsoverskriften viser skrivebeskyttede verdier av felt i overskriften. Siden overskriftsundermenyen er skjult, vil brukere ikke kunne redigere feltverdiene.  
  
Denne meldingen informerer utvikleren om at alle felt som legges til i overskriften, er skrivebeskyttet, og at alle felt de vil at brukere skal redigere, også skal legges til i en inndeling i skjemaet.

### <a name="header-field-values-are-not-editable-moving-a-field-from-the-body-to-the-header-will-display-as-a-read-only-value-to-maintain-editability-copy-the-field-to-the-header"></a>Overskriftsfeltverdier kan ikke redigeres: Hvis du flytter et felt fra brødteksten til overskriften, vises det som en skrivebeskyttet verdi. Hvis du vil vedlikeholde redigerbarhet, kopierer du feltet til overskriften.  
Denne meldingen vises i skjemautforming bare for skjemaer som bruker høytetthetsoverskrift med overskriftsundermenyen skjult.  
  
Høytetthetsoverskriften viser skrivebeskyttede verdier av felt i overskriften. Siden overskriftsundermenyen er skjult, vil brukere ikke kunne redigere feltverdiene.  
  
Denne meldingen informerer utvikleren om at de prøver å flytte et felt fra skjemabrødteksten til skjemaoverskriften. Dette vil gjøre det skrivebeskyttet. Det gir utvikleren valget mellom å flytte feltet til overskriften eller legge til en kopi av feltet i overskriften. Hvis du flytter feltet til overskriften, blir feltet ikke tilgjengelig på den opprinnelige plasseringen i skjemabrødteksten, slik at brukerne kan redigere det. Hvis du legger til en kopi av feltet i overskriften, blir feltet værende på den opprinnelige plasseringen, slik at brukerne kan fortsette å redigere det i skjemabrødteksten.

### <a name="form-headers-now-default-to-high-density-to-display-more-data-use-the-new-form-designer-to-edit-header-density"></a>Skjemaoverskrifter får nå høy tetthet som standard for å vise flere data. Bruk den nye skjemautforming for å redigere overskrifttettheten.  
Denne meldingen vises i den klassiske skjemautformingen når en utvikler åpner et hovedskjema for redigering, og det er konfigurert til å bruke lavtetthetsoverskrift.  
  
Denne meldingen bidrar til å øke bevisstheten om høytetthetsoverskriften og dens fordeler og at utviklere bør bruke den nye skjemautformingen til å konfigurere overskriftstettheten.  

### <a name="this-form-is-using-high-density-header-for-the-best-authoring-experience-with-this-form-use-the-new-form-designer"></a>Dette skjemaet bruker høytetthetsoverskrift. Bruk den nye skjemautformingen til å få den beste redigeringsopplevelsen med dette skjemaet. 
 Denne meldingen vises i den klassiske skjemautformingen når en utvikler åpner et hovedskjema for redigering, og det er konfigurert til å bruke høytetthetsoverskrift.  
  
Den klassiske skjemautforming gir ikke en WYSIWYG-redigeringsopplevelse. Det registrerer, forhindrer eller advarer heller ikke utviklere om implikasjonene til endringene de gjør i skjemaoverskriftene. Når du for eksempel redigerer et skjema som bruker høytetthetsoverskrift med skjult overskriftsundermeny, vil ikke den klassiske skjemautformingen hindre utviklere i å legge til flere enn fire felt i overskriften, selv om disse feltene ikke vil være tilgjengelige for brukere.  
  
Denne meldingen informerer utvikleren om at når de redigerer et skjema som bruker høytetthetsoverskrift, bør de bruke den nye skjemautformingen. Dette bidrar til å sikre at utvikleren er klar over virkningen av endringene i skjemaoverskriften.

## <a name="see-also"></a>Se også
[Oversikt over den modelldrevne skjemautformingen](form-designer-overview.md)  
[Opprette eller redigere skjemaer ved hjelp av skjemautforming](create-and-edit-forms.md)  
[Legge til, flytte eller slette felt i et skjema ved hjelp av skjemautformingen.](add-move-or-delete-fields-on-form.md)  
[Legge til, flytte eller slette inndelinger i et skjema ved hjelp av skjemautformingen](add-move-or-delete-sections-on-form.md)  
[Legge til, flytte eller slette kategorier i et skjema ved hjelp av skjemautformingen](add-move-or-delete-tabs-on-form.md)  
[Egenskaper som er tilgjengelige i skjemautformingen](form-designer-properties.md)  
[Konfigurere overskriftegenskaper i skjemautformingen](form-designer-header-properties.md)  
[Bruke trevisningen i skjemautformingen](using-tree-view-on-form.md)  
[Opprette og rediger felt](../common-data-service/create-edit-field-portal.md)
