---
title: Opprette en egendefinert enhet som har komponenter med PowerApps | Microsoft Docs
description: Emnet med trinnvise instruksjoner for å opprette og konfigurere en enhet for bruk med en PowerApps-app.
author: Mattp123
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: tutorial
ms.date: 01/23/2019
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-custom-entity-that-has-components-in-powerapps"></a>Opprette en egendefinert enhet som har komponenter i PowerApps

Med PowerApps kan du skreddersy appen slik at den passer til organisasjonens bransje, terminologi og unike forretningsprosesser. Utvikling av PowerApps-apper består av å legge til standard medfølgende enheter eller opprette egendefinerte enheter. En enhet definerer informasjonen du vil spore ved hjelp av oppføringer, som vanligvis inneholder egenskaper som firmanavn, sted, produkter, e-post og telefon. 

I dette emnet oppretter du en enhet og legger deretter til eller tilpasser viktige komponenter, for eksempel felt, relasjoner, visninger og skjemaer. Du lærer hvordan du gjør følgende.

- Opprette en egendefinert enhet
- Legge til egendefinerte felt i enheten
- Legge til en enhetsrelasjon
- Tilpasse en visning 
- Tilpasse et skjema

Emnet følger selskapet Contoso, som er en virksomhet for kjæledyrstell som pleier hunder og katter. Contoso trenger en app for kunde- og kjæledyrsporing som kan brukes av ansatte på tvers av flere enheter.

## <a name="prerequisites"></a>Forhåndskrav

Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Hvis du ikke allerede har en PowerApps-konto, velger du **Kom i gang gratis**-koblingen fra [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-a-custom-entity"></a>Opprette en egendefinert enhet

1. Utvid **Data** i den venstre navigasjonsruten, velg **Enheter**, og velg deretter **Ny enhet**.
    > [!div class="mx-imgBorder"] 
    > ![ny enhet](media/create-custom-entity/create-new-entity.png)
2. Angi følgende verdier i ruten til høyre, og velg deretter **Neste**.
  - **Visningsnavn**: *Kjæledyr* 
  - **Beskrivelse**: *Egendefinert enhet for å spore kjæledyrtjenester*
3. Velg **Lagre enhet**.

## <a name="add-and-customize-fields"></a>Legge til og tilpasse felt
 
1. I listen over enheter velger du **Kjæledyr**-enheten som ble opprettet i forrige del.
2. I **Felt**-kategorien velger du **Kjæledyr**-feltet.
3. I den høyre ruten kan du gjøre følgende endringer i **Visningsnavn**-feltet: 
  - Endre **visningsnavnet** fra **Kjæledyr** til *Navn på kjæledyr*.
  - Velg **Søkbar**.  
  
    > [!div class="mx-imgBorder"] 
    > ![Endre hovedfelt](media/create-custom-entity/primary-field.png)
3. Velg **Ferdig**.
4. I **Felt**-kategorien på verktøylinjen enhetsutforming velger du **Legg til felt**. I **Feltegenskaper**-ruten angir eller velger du følgende verdier og alternativer.
  - **Visningsnavn**. *Art*
  - **Datatype**. *Alternativsett*
  - **Alternativsett**. *Nytt alternativsett*
5. Opprett alternativsettet

  a. Velg **Legg til nytt element**. 
  
  b. Erstatt **Nytt alternativ** med *Hund*. 
   
  c. Velg **Legg til nytt element**. 
    
  d.  Erstatt **Nytt alternativ** med *Katt*. 
    
  e. Velg **Lagre**. 

  > [!div class="mx-imgBorder"] 
  > ![Nytt alternativsett](media/create-custom-entity/optionset-add-items.png)

6. Velg **Søkbar**, og velg deretter **Ferdig**.

7. På verktøylinjen enhetsutforming velger du **Legg til felt**. I **Feltegenskaper**-ruten angir eller velger du følgende verdier og velger deretter **Ferdig**.
  - **Visningsnavn**. *Rase*
  - **Datatype**. *Tekst*
  - **Søkbar**. *Ja*

8. På verktøylinjen enhetsutforming velger du **Legg til felt**. 

9. I **Feltegenskaper**-ruten angir eller velger du følgende verdier og velger deretter **Ferdig**. 
  - **Visningsnavn**. *Avtaledato*
  - **Datatype**. *Dato og klokkeslett*

10. Velg **Lagre enhet**.

## <a name="add-a-relationship"></a>Legge til en relasjon

1. Velg **Relasjoner**-kategorien, på verktøylinjen for enhetsutforming velger du **Legg til relasjon**, og velger deretter **Mange-til-én**. 
2. I ruten til høyre i **Relatert**-listen velger du **Forretningsforbindelse**.
3. Velg **Ferdig**.
4. Velg **Lagre enhet**.

  Legg merke til at når du legger til en mange-til-én-relasjon legges et **Forretningsforbindelse**-felt med datatypen **Oppslag** automatisk til i listen over felt i **Felt**-kategorien.
  > [!div class="mx-imgBorder"]
  > ![Oppslagsfelt for forretningsforbindelse](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>Tilpasse en visning

1. Velg kategorien **Visninger**, og velg deretter **Aktive kjæledyr**-visningen. Hvis du ikke ser **Aktive kjæledyr**-visningen, velger du **Fjern filter**.
2. I visningsutformingen velger du **Legg til kolonner**, velger følgende kolonner, og velger deretter **OK**.
  - Forretningsforbindelse
  - Avtaledato 
  - Rase 
  - Art
3. Velg **Opprettet den**-kolonnen, velg **Fjern**, og velg deretter **OK** for å bekrefte at kolonnen skal fjernes.
4. For å ordne kolonnene velger du kolonnen du vil flytte, og bruker deretter <- og -> pilknappene til visningen ser slik ut.
    > [!div class="mx-imgBorder"] 
    > ![Visning av aktive kjæledyr](media/create-custom-entity/active-pets-view.png)
5. Velg **Lagre og lukk** på verktøylinjen for visningsutforming.  

## <a name="model-driven-apps-only-customize-the-main-form"></a>Bare modelldrevne apper: Tilpasse hovedskjemaet

Hopp over dette trinnet hvis du bare vil bruke kjæledyrenheten i en lerretsapp. 

1. Utvid **Data** i den venstre navigasjonsruten, velg **Enheter**, og velg deretter **Kjæledyr**.
2. Velg kategorien **Skjemaer**, og velg deretter **Informasjon** ved siden av **Hoved**-skjematypen for å åpne skjemaredigeringsprogrammet.
    > [!div class="mx-imgBorder"] 
    > ![Redigere hovedskjema](media/create-custom-entity/main-form-edit.png)
3. I skjemaredigeringsprogrammet drar og slipper du feltet **Art**, **Rase**, **Avtaledato** og **Forretningsforbindelse** i ruten Feltutforsker i Generelt-delen på skjemalerretet til skjemaet ser slik ut.
    > [!div class="mx-imgBorder"] 
    > ![Velge felt for hovedskjema](media/create-custom-entity/main-form-edit2.png) 
4. Velg **Lagre**.
5. Velg **Publiser**.
6. Velg **Lagre og lukk** for å lukke skjemautformingen.

## <a name="add-the-custom-entity-to-an-app"></a>Legge til den egendefinerte enheten i en app

Nå er enheten klar til å brukes for å bygge et lerret eller en modelldrevet app. 

## <a name="next-steps"></a>Neste trinn

Du har lært hvordan du oppretter en enhet som kan brukes til å opprette en nyttig app, i dette emnet. 
- Hvis du vil vite hvordan du oppretter en modelldrevet app, kan du se [Lage din første modelldrevne app](../model-driven-apps/build-first-model-driven-app.md).
- Hvis du vil vite hvordan du oppretter en lerretsapp, kan du se [Opprette en app fra bunnen](../canvas-apps/get-started-create-from-blank.md).
