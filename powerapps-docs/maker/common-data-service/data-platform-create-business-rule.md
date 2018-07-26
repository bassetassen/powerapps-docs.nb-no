---
title: Opprett en forretningsregel i Common Data Service for apper | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du oppretter en forretningsregel i Common Data Service (CDS) for apper.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: 5cf2a312ddba83312805f6b3b517738f1bc1da78
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218031"
---
# <a name="create-a-business-rule"></a>Å opprette en forretningsregel

Du kan opprette forretningsregler og anbefalinger for å bruke logikk og valideringer uten å skrive kode eller opprette programtillegg.  Forretningsregler gir et enkelt grensesnitt som kan implementeres og opprettholde ofte brukte regler i rask endring. 
  
Ved å kombinere betingelser og handlinger, kan du gjøre ett av følgende med forretningsregler:  
  
* angi feltverdier  
* fjerne feltverdier  
* angi nivåer for feltkrav  
* vise eller skjule felt  
* aktivere eller deaktivere felt  
* validere data og vise feilmeldinger  
* opprette forretningsanbefalinger basert på forretningsanalyse  
  
## <a name="differences-between-canvas-and-model-driven-apps"></a>Forskjeller mellom lerret-apper og modelldrevne apper

Modelldrevne apper kan bruke alle handlingene som er tilgjengelige for forretningsregler, men ikke alle forretningsregelhandlinger er tilgjengelige på lerret-apper på dette tidspunktet. Følgende handlinger er **ikke** tilgjengelig på lerret-apper:

* vise eller skjule felt  
* aktivere eller deaktivere felt  
* opprette forretningsanbefalinger basert på forretningsanalyse  

## <a name="prerequisites"></a>Forutsetninger
Du må bytte til et [miljø](../canvas-apps/working-with-environments.md) hvor du kan opprette og redigere enheter for å følge dette emnet.

## <a name="create-a-business-rule"></a>Å opprette en forretningsregel
  
1. Logg deg på [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og klikk eller trykk deretter på Ned-pilen for **Data** nær den venstre kanten.

2. Klikk eller trykk på **Enheter** i listen som vises.
  
3. Åpne enheten du ønsker å opprette forretningsregelen for (for eksempel åpner du **Konto**-enheten), og klikk deretter på **Forretningsregler**-fanen.  

4. Klikk på **Ny**.  
  
    Utformingsvinduet for forretningsregler åpnes med et enkelt vilkår som allerede er opprettet for deg. Hver regel starter med en betingelse. Forretningsregelen utfører én eller flere handlinger basert på denne betingelsen.  

    > [!TIP]
    > Hvis du vil endre en eksisterende forretningsregel, må du deaktivere den før du kan endre den.  
  
5. Hvis du ønsker det, kan du legge til en beskrivelse i Beskrivelse-boksen øverst til venstre i vinduet.
  
6. Angi omfanget, i henhold til følgende:  
  
    |||  
    |-|-|  
    |**Hvis du velger dette elementet ...**|**Området er satt til ...**|  
    |**Enhet**|Modelldrevne skjemaer og servere|  
    |**Alle skjemaer**|Modelldrevne skjemaer|  
    |Bestemt skjema (for eksempel**Konto**-skjema)|Bare dette modelldrevne skjemaet|  

    > [!TIP]
    > Hvis du bygger en lerret-app, må du bruke enheten som omfang.
  
7. **Å legge til betingelser.** Slik legger du til flere betingelser for forretningsregelen:  
  
    1. Dra **Betingelse**-komponenten fra **Komponenter**-fanen til et plusstegn i utformeren.  
  
        ![Å legge til et vilkår i en forretningsregel](./media/data-platform-cds-create-business-rule/add-condition-business-rule.png "Å legge til et vilkår i en forretningsregel")  
  
    2. Hvis du vil angi egenskaper for betingelsen, klikker du på **Betingelse**-komponenten i utformer-vinduet, og deretter angir du egenskapene i **Egenskaper**-fanen på høyre side av skjermen. Når du angir egenskaper, opprettes det et uttrykk nederst på **Egenskaper**-fanen i Common Data Service.  
  
    3. Hvis du vil legge til en ekstra setningsdel (en OG eller ELLER) til tilstanden, klikker du på **Ny** på **Egenskaper**-fanen for å opprette en ny regel, og deretter angir du egenskapene for denne regelen. I **regellogikk**-feltet kan du angi om du vil legge til den nye regelen som en OG eller en ELLER.  
  
        ![Å legge til en ny regel i en betingelse](./media/data-platform-cds-create-business-rule/add-new-rule-condition.png "Å legge til en ny regel i en betingelse")  
  
    4. Når du er ferdig angi egenskaper for betingelsen, klikker du på **Bruk**.  
  
8. **Å legge til handlinger.** Slik legger du til en handling:  
  
    1. Dra én av handlingskomponentene fra **Komponenter**-fanen til et plusstegn ved siden av **Betingelse**-komponenten. Dra handlingen til et plusstegn ved siden av en hake hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre denne handlingen hvis betingelsen ikke er oppfylt.
  
        ![Å dra en handling til en forretningsregel](./media/data-platform-cds-create-business-rule/drag-an-action-business-rule.png "Å dra en handling til en forretningsregel")  
  
    2. Hvis du vil angi egenskaper for handlingen, klikker du på **Handling**-komponenten i utformer-vinduet, og deretter angir du egenskapene i **Egenskaper**-fanen.  
  
    3. Når du er ferdig med å angi egenskaper, klikker du på **Bruk**.  
  
9. **Å legge til en forretningsanbefaling. (Bare modelldrevet)**  Å legge til en forretningsanbefaling:  
  
    1. Dra **Anbefaling**-komponenten fra**Komponenter**-fanen til et plusstegn ved siden av en **Betingelse**-komponent. Dra **Anbefaling**-komponenten til et plusstegn ved siden av en hake hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre handlingen hvis betingelsen ikke er oppfylt.  
  
    2. Hvis du vil angi egenskaper for anbefalingen, klikker du på **Anbefaling**-komponenten i utformer-vinduet, og deretter angir du egenskapene på **Egenskaper**-fanen.  
  
    3. Hvis du vil legge til flere handlinger til anbefalingen, drar du dem fra **Komponenter**-fanen, og deretter angir du egenskaper for hver handling i **Egenskaper**-fanen.  
  
        > [!NOTE]
        >  Når du oppretter en anbefaling, legges det til en enkelt handling i Common Data Service som standard. Klikk på **Detaljer** på **Anbefaling**-komponenten for å se alle handlingene i en anbefaling.  
  
    4. Når du er ferdig med å angi egenskaper, klikker du på **Bruk**.  
  
10. Klikk på **Valider** i handlingsfeltet for å validere en forretningsregel.  
  
11. Klikk på **Lagre** i handlingsfeltet for å lagre en forretningsregel.  
12. Hvis du vil aktivere forretningsregelen, merker du den i Løsningsutforsker-vinduet, og deretter klikker du på **Aktiver**. Du kan ikke aktivere forretningsregelen fra utformer-vinduet.  
  
    > [!TIP]
    >  Her er noen tips å ta med seg når du arbeider med forretningsregler i utformer-vinduet:  
    >   
    > - Hvis du vil ta et øyeblikksbilde av alt i vinduet for forretningsregelen, klikker du på **Øyeblikksbilde** i handlingsfeltet. Dette er for eksempel nyttig hvis du vil dele og få kommentarer om forretningsregelen fra et teammedlem.  
    > - Bruk minikartet til å raskt navigere til forskjellige deler av prosessen. Dette er nyttig når du har en komplisert prosess som ikke får plass i ett skjermbilde.  
    > - Når du legger til betingelser, handlinger og anbefalinger for bedriften til forretningsregelen, bygger Common Data Service koden for forretningsregelen nederst i utformer-vinduet. Denne koden er skrivebeskyttet.  
  
## <a name="localize-error-messages-used-in-business-rules"></a>Lokaliser feilmeldinger som brukes i forretningsregler  
 Hvis du har mer enn ett språk som er klargjort for organisasjonen, vil du oversette eventuelle feilmeldinger som du har angitt. Hver gang du angir en melding, genereres en etikett av systemet. Hvis du eksporterer oversettelsene i organisasjonen, kan du legge til oversatte versjoner av meldingene dine og deretter importere etikettene tilbake til Common Data Service, slik at personer som bruker et annet språk enn ditt originalspråk kan vise de oversatte meldingene.  
  