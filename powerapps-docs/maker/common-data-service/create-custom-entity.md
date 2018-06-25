---
title: Opplæring for hvordan du oppretter en egendefinert enhet som har komponenter med PowerApps | Microsoft Docs
description: Håndbok med trinnvise instruksjoner for oppretting og konfigurering av en enhet som brukes med en PowerApps-app.
author: Mattp123
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: tutorial
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: c587ed6488ae498e3ec662016ee1d028023e4095
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168255"
---
# <a name="tutorial-create-a-custom-entity-that-has-components-in-powerapps"></a>Opplæring: Oppretting av en egendefinert enhet som har PowerApps-komponenter

Med [!INCLUDE [powerapps](../../includes/powerapps.md)] kan du skreddersy appen slik at den passer godt til organisasjonens bransje, terminologi og unike forretningsprosesser. [!INCLUDE [powerapps](../../includes/powerapps.md)] apputvikling inkluderer å legge til standard ferdiglagde enheter eller opprette egendefinerte enheter. En enhet definerer informasjonen du ønsker å spore i form av poster, noe som vanligvis inneholder egenskaper som for eksempel firmanavn, plassering, produkter, e-post og telefon. 

I denne opplæringen oppretter du en enhet, og deretter legger du til eller tilpasser viktige komponenter, som foreksempel felt, relasjoner, visninger og former. Du finner ut hvordan du kan gjøre følgende:

- Opprette en egendefinert enhet
- Legge til egendefinerte felt på enheten din
- Legge til en enhetsrelasjon
- Tilpasse en visning 
- Tilpasse et skjema

Denne opplæringen følger firmaet Contoso, som er et dyrefrisørfirma som steller hunder og katter. Contoso trenger en app for sporing av klienter og kjæledyr, som kan brukes av ansatte på en rekke enheter.

## <a name="prerequisites"></a>Forutsetninger

Logg deg på [PowerApps](https://powerapps.microsoft.com/). Hvis du ikke allerede har en [!INCLUDE [powerapps](../../includes/powerapps.md)]konto, velger du koblingen **Kom i gang gratis** fra [powerapps.com](https://web.powerapps.com).

## <a name="create-a-custom-entity"></a>Opprette en egendefinert enhet

1. Utvid **Data** på den venstre navigasjonsruten, velg **Enheter** og velg så **Ny enhet**.
    ![Ny enhet](media/create-custom-entity/create-new-entity.png)
2. Skriv følgende verdier inn i den høyre ruten, og velg deretter **Neste**.
  - **Visningsnavn**: *Kjæledyr* 
  - **Beskrivelse**: *Egendefinert enhet som sporer kjæledyr-tjenester*
3. Velg **Lagre enhet**.

## <a name="add-and-customize-fields"></a>Slik legger du til og tilpasser felt
 
1. Velg **Primærnavn**-feltet på **Felt**-fanen.
2. I den høyre ruten kan du gjøre følgende endringer i **Primærnavn**-feltet: 
  - Endre **Visningsnavn** fra **Primærnavn** til *Navn på kjæledyr*
  - Velg **Søkbar**  
  
    ![Endring av primærfeltet](media/create-custom-entity/primary-field.png)
3. Velg **Ferdig**.
4. Velg **Legg til** felt på verktøylinjen for enhetsutforming, på **Felt**-fanen. Skriv inn eller velg de følgende verdiene og alternativene i **feltegenskaper**-ruten.
  - **Visningsnavn**. *Art*
  - **Datatype**. *Alternativsett*
  - **Alternativsett**. *Nytt alternativsett*
5. Lage alternativsettet

  a. Velg **Legg til nytt element**. 
  
  b. Erstatt **Nytt alternativ** med *Hund*. 
   
  c. Velg **Legg til nytt element**. 
    
  d.  Erstatt **Nytt alternativ** med *Katt*. 
    
  e. Velg **Lagre**. 

  ![Nytt alternativsett](media/create-custom-entity/optionset-add-items.png)

6. Velg **Søkbar**, og velg deretter **Ferdig**.

7. Velg **Legg til felt** på verktøylinjen for enhetsutforming. Skriv inn eller velg de følgende verdiene og alternativene i **Feltegenskaper**-ruten, og velg deretter **Ferdig**.
  - **Visningsnavn**. *Rase*
  - **Datatype**. *Tekst*
  - **Søkbar**. *Ja*

8. Velg **Legg til felt** på verktøylinjen for enhetsutforming. 

9. Skriv inn eller velg de følgende verdiene og alternativene i **Feltegenskaper**-ruten, og velg deretter **Ferdig**. 
  - **Visningsnavn**. *Avtaledato*
  - **Datatype**. *Dato og klokkeslett*

10. Velg **Lagre enhet**.

## <a name="add-a-relationship"></a>Oppretting av en relasjon

1. Velg **Relasjoner**-fanen, og velg deretter **Legg til relasjon** på verktøylinjen for enhetsutforming. Velg avslutningsvis **Mange-til-én**. 
2. I ruten til høyre i **Beslektet**-listen velger du **Konto**.
3. Velg **Ferdig**.
4. Velg **Lagre enhet**.

Legg merke til at når du legger til en relasjon, legges et **Konto**-felt med datatypen **Oppslag** automatisk til i listen over felt på **Felt**-fanen. ![Oppslagsfelt for konto](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>Tilpasse en visning

1. Velg **Visninger**-fanen, og velg deretter **Aktive kjæledyr**-visning. Hvis du ikke ser **Aktive kjæledyr**-visningen, velger du **Fjern filter**.
2. Velg **Legg til kolonner** i visningsutformeren, velg følgende kolonner og velg deretter **OK**.
  - Konto
  - Avtaledato 
  - Rase 
  - Art
3. Velg **Opprettet på**-fanen, velg **Fjern**, og velg deretter **OK** for å bekrefte slettingen av kolonnen.
4. Hvis du vil ordne kolonnene, merker du kolonnen du vil flytte, og deretter bruker du pilknappene <- og -> til visningen ser slik ut.
    ![Visning av aktive kjæledyr ](media/create-custom-entity/active-pets-view.png)
5. Velg **Lagre og lukk** på verktøylinjen for visningsutforming.  

## <a name="model-driven-apps-only-customize-the-main-form"></a>Bare modell-drevne apper: Tilpass hovedskjema

Hopp over dette trinnet hvis du bare vil bruke kjæledyr-enheten i en lerretsapp. 

1. Velg **Modelldrevet** i den [!INCLUDE [powerapps](../../includes/powerapps.md)] venstre navigasjonsruten.
2. Utvid **Data** på den venstre navigasjonsruten, velg **Enheter** og velg så **Kjæledyr**.
3. Velg **Skjemaer**-fanen, og velg deretter **Informasjon** ved siden av **Hoved**-skjematypen for å åpne redigeringsprogrammet for skjema.
    ![Redigering av hovedskjema](media/create-custom-entity/main-form-edit.png)
4. Du kan dra og slippe feltene **Art**, **Rase**, **Avtaledato** og **Konto** i redigeringsprogrammet for skjema, som er plassert i Generelt-delen i skjemalerretet i Feltutforsker-ruten, til skjemaet ser slik ut.
    ![Valg av felt for hovedskjema](media/create-custom-entity/main-form-edit2.png) 
5. Velg **Lagre**.
6. Velg **Publiser**.
7. Velg **Lagre og lukk** for å lukke skjemautformeren.

## <a name="add-the-custom-entity-to-an-app"></a>Slik legger du til den egendefinerte enheten i en app

Enheten er nå klar til å brukes til å utvikle enten et lerret eller en modelldrevet app. 

## <a name="next-steps"></a>Neste trinn

I denne opplæringen har du sett hvordan du oppretter en enhet som kan brukes til å opprette en nyttig app. 
- Hvis du vil lære hvordan du oppretter en modelldreven app, kan du se [Slik lager du din første modelldrevne app](../model-driven-apps/build-first-model-driven-app.md).
- Hvis du vil lære hvordan du oppretter en lerretsapp, kan du se [Oppretting av en app fra grunnen av](../canvas-apps/get-started-create-from-blank.md).
