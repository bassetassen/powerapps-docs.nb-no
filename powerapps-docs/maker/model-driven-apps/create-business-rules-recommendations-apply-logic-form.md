---
title: Opprett forretningsregler og anbefalinger for modelldrevet app | MicrosoftDocs
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
- PowerApps
ms.assetid: 00e62904-2ce9-4730-a113-02b1fedbf22e
caps.latest.revision: 31
author: Mattp123
ms.author: matp
manager: kvivek
tags:
- PowerApps maker portal impact
ms.openlocfilehash: c1a132648a63845c42cde8a80636d0e87e10a328
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693323"
---
# <a name="tutorial-create-business-rules-and-recommendations-to-apply-logic-in-a-model-driven-app-form"></a>Opplæring: Opprett forretningsregler og anbefalinger for å ta i bruk logikk i et modelldrevet appskjema

Denne opplæringen viser deg hvordan du oppretter forretningsregler og anbefalinger for å ta i bruk skjemalogikk uten å skrive JavaScript-kode eller opprette programtillegg.  Forretningsregler gir et enkelt grensesnitt som kan implementeres og opprettholde ofte brukte regler i rask endring. De kan brukes på hoved- og hurtigopprettingsskjemaer, og de fungerer i PowerApps-apper, nettapper for Dynamics 365 Customer Engagement, Dynamics 365 for nettbrett og Dynamics 365 for Outlook (tilkoblet eller frakoblet modus).  
  
 Ved å kombinere betingelser og handlinger, kan du gjøre ett av følgende med forretningsregler:  
  
-   angi feltverdier  
  
-   fjerne feltverdier  
  
-   angi nivåer for feltkrav  
  
-   vise eller skjule felt  
  
-   aktivere eller deaktivere felt  
  
-   validere data og vise feilmeldinger  
  
-   opprette forretningsanbefalinger basert på forretningsanalyse  
  
## <a name="create-a-business-rule-or-business-recommendation"></a>Opprett en forretningsregel eller -anbefaling
  
1. Åpne [løsningsutforsker](advanced-navigation.md#solution-explorer).  
  
2.  Åpne enheten du ønsker å opprette forretningsregelen for (åpne for eksempel **Konto**-enheten), og dobbeltklikk deretter på **Forretningsregler**.  
  
 ![Opprett en forretningsregel i standardløsningen](media/create-business-rule-the-default-solution.png "Opprett en forretningsregel i standardløsningen")  
  
3.  Velg **Ny**.  
  
     Utformingsvinduet for forretningsregler åpnes med et enkelt vilkår som allerede er opprettet for deg. Hver regel starter med en betingelse. Forretningsregelen utfører én eller flere handlinger basert på denne betingelsen.  
  
 ![Utformingsvinduet for forretningsregler](media/business-rules-design-window.png "Utformingsvinduet for forretningsregler")  
  
   > [!TIP]
> Hvis du vil endre en eksisterende forretningsregel, må du deaktivere den før du kan endre den.

4.  Hvis du ønsker det, kan du legge til en beskrivelse i Beskrivelse-boksen øverst til venstre i vinduet.  
  
5.  Angi omfanget, i henhold til følgende:  
  
    |||  
    |-|-|  
    |**Hvis du velger dette elementet ...**|**Området er satt til ...**|  
    |**Enhet**|Alle skjemaer og servere|  
    |**Alle skjemaer**|Alle skjemaer|  
    |Bestemt skjema (for eksempel**Konto**-skjema)|Bare dette skjemaet|  
  
6. **Å legge til betingelser.** Slik legger du til flere betingelser for forretningsregelen:  
  
    1.  Dra **Betingelse**-komponenten fra **Komponenter**-fanen til et plusstegn i utformeren.  
  
        ![Å legge til et vilkår i en forretningsregel](media/add-condition-business-rule.png "Å legge til et vilkår i en forretningsregel")  
  
    2.  Hvis du vil angi egenskaper for betingelsen, klikker du på **Betingelse**-komponenten i utformer-vinduet, og deretter angir du egenskapene i **Egenskaper**-fanen på høyre side av skjermen. Når du angir egenskaper, opprettes det et uttrykk nederst på **Egenskaper**-fanen.  
  
    3.  Hvis du vil legge til en ekstra setningsdel (en OG eller ELLER) til tilstanden, klikker du på **Ny** på **Egenskaper**-fanen for å opprette en ny regel, og deretter angir du egenskapene for denne regelen. I **regellogikk**-feltet kan du angi om du vil legge til den nye regelen som en OG eller en ELLER.  
  
        ![Å legge til en ny regel i en betingelse](media/add-new-rule-condition.png "Å legge til en ny regel i en betingelse")  
  
    4.  Når du er ferdig angi egenskaper for betingelsen, klikker du på **Bruk**.  
  
7. **Å legge til handlinger.** Slik legger du til en handling:  
  
    1.  Dra én av handlingskomponentene fra **Komponenter**-fanen til et plusstegn ved siden av **Betingelse**-komponenten. Dra handlingen til et plusstegn ved siden av en hake hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre denne handlingen hvis betingelsen ikke er oppfylt.  
  
        ![Å dra en handling til en forretningsregel](media/drag-an-action-business-rule.png "Å dra en handling til en forretningsregel")  
  
    2.  Hvis du vil angi egenskaper for handlingen, klikker du på **Handling**-komponenten i utformer-vinduet, og deretter angir du egenskapene i **Egenskaper**-fanen.  
  
    3.  Når du er ferdig med å angi egenskaper, klikker du på **Bruk**.  
  
8. **Legg til en forretningsanbefaling.** Slik legger du til en forretningsanbefaling:  
  
    1.  Dra **Anbefaling**-komponenten fra**Komponenter**-fanen til et plusstegn ved siden av en **Betingelse**-komponent. Dra **Anbefaling**-komponenten til et plusstegn ved siden av en hake hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre handlingen hvis betingelsen ikke er oppfylt.  
  
    2.  Hvis du vil angi egenskaper for anbefalingen, klikker du på **Anbefaling**-komponenten i utformer-vinduet, og deretter angir du egenskapene på **Egenskaper**-fanen.  
  
    3.  Hvis du vil legge til flere handlinger til anbefalingen, drar du dem fra **Komponenter**-fanen, og deretter angir du egenskaper for hver handling i **Egenskaper**-fanen.  
  
        > [!NOTE]
        >  Når du oppretter en anbefaling, legges én enkelt handling til som standard. Klikk på **Detaljer** på **Anbefaling**-komponenten for å se alle handlingene i en anbefaling.  
  
    4.  Når du er ferdig med å angi egenskaper, klikker du på **Bruk**.  
  
9. Klikk på **Valider** i handlingsfeltet for å validere en forretningsregel.  
  
10. Klikk på **Lagre** i handlingsfeltet for å lagre en forretningsregel.  
  
11. Hvis du vil aktivere forretningsregelen, merker du den i Løsningsutforsker-vinduet, og deretter klikker du på **Aktiver**. Du kan ikke aktivere forretningsregelen fra utformer-vinduet.  
  
> [!TIP]
>  Her er noen tips å ta med seg når du arbeider med forretningsregler i utformer-vinduet:  
>   
> - Hvis du vil ta et øyeblikksbilde av alt i vinduet for forretningsregelen, klikker du på **Øyeblikksbilde** i handlingsfeltet. Dette er for eksempel nyttig hvis du vil dele og få kommentarer om forretningsregelen fra et teammedlem.  
> - Bruk minikartet til å raskt navigere til forskjellige deler av prosessen. Dette er nyttig når du har en komplisert prosess som ikke får plass i ett skjermbilde.  
> - Når du legger til betingelser, handlinger og forretningsanbefalinger til forretningsregelen, bygges ny kode for forretningsregelen som vises nederst i utformervinduet. Denne koden er skrivebeskyttet.  
  
<a name="BKMK_LocalizingErrorMessages"></a>   
## <a name="localize-error-messages-used-in-business-rules"></a>Lokaliser feilmeldinger som brukes i forretningsregler  
 Hvis du har mer enn ett språk som er klargjort for organisasjonen, vil du oversette eventuelle feilmeldinger som du har angitt. Hver gang du angir en melding, genereres en etikett av systemet. Hvis du eksporterer oversettelsene i organisasjonen, kan du legge til lokaliserte versjoner av meldingene dine og deretter importere etikettene tilbake til systemet, slik at personer som bruker et annet språk enn ditt originalspråk kan vise de oversatte meldingene.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprett egendefinert forretningslogikk gjennom prosesser](guide-staff-through-common-tasks-processes.md)   
 [Opprett forretningsprosessflyt](/flow/create-business-process-flow)   

