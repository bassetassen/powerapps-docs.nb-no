---
title: Opprette forretningsregler og anbefalinger for modelldrevne apper| MicrosoftDocs
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="tutorial-create-business-rules-and-recommendations-to-apply-logic-in-a-model-driven-app-form"></a>Opplæring: Opprett forretningsregler og anbefalinger for å bruke logikk i et modelldrevet appskjema

Opplæringen viser hvordan du kan opprette regler og anbefalinger for å bruke skjemalogikk uten å skrive JavaScript-kode eller lage plugin-moduler. Forretningsregler har et enkelt grensesnitt for å implementere og vedlikeholde regler som endres og brukes ofte. De kan brukes i hoved- og hurtigopprettingsskjemaer, og de fungerer i PowerApps-apper, Dynamics 365 Customer Engagement-webapper, Dynamics 365 for tablets og Dynamics 365 for Outlook (tilkoblet eller frakoblet modus).  
  
 Ved å kombinere betingelser og handlinger kan du gjøre ett av følgende med forretningsregler:  
  
-   Angi feltverdier  
  
-   Fjerne feltverdier  
  
-   Angi feltkravnivåer  
  
-   Vise eller skjule felt  
  
-   Aktivere eller deaktivere felt  
  
-   Validere data og vise feilmeldinger  
  
-   Opprette forretningsanbefalinger basert på forretningsintelligens.  
  
## <a name="create-a-business-rule-or-business-recommendation"></a>Opprette en forretningsregel eller forretningsanbefaling
  
1. Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).  
  
2.  Åpne entiteten du vil opprette forretningsregel for (åpne for eksempel **konto**enheten), og dobbeltklikk deretter **Forretningsregler**.  
  
 ![Opprette en forretningsregel i standardløsningen](media/create-business-rule-the-default-solution.png "Opprette en forretningsregel i standardløsningen")  
  
3.  Velg **Nytt**.  
  
     Forretningsregel-utforming-vinduet åpnes med et enkelt vilkår som allerede er opprettet for deg. Hver regel starter med en betingelse. Forretningsregelen utfører én eller flere handlinger basert på denne betingelsen.  
  
 ![Utformingsvinduet for forretningsregler](media/business-rules-design-window.png "Utformingsvinduet for forretningsregler")  
  
   > [!TIP]
> Hvis du vil endre en ekisterende forretningsregel, må du deaktivere den før du kan redigere den.

4.  Legg til en beskrivelse, hvis du vil, i Beskrivelse-boksen øverst til venstre i vinduet.  
  
5.  Angi omfanget i henhold til følgende:  
  
    |||  
    |-|-|  
    |**Hvis du velger dette elementet...**|**Omfanget angis til...**|  
    |**Enhet**|Alle skjemaer og server|  
    |**Alle skjemaer**|Alle skjemaer|  
    |Bestemt skjema (for eksempel **Konto**-skjema)|Bare dette skjemaet|  
  
6. **Legg til betingelser.** Slik legger du til flere betingelser i forretningsregelen:  
  
    1.  Dra **Betingelse**-komponenten fra **Komponenter**-kategorien til et plusstegn i utformingen.  
  
        ![Legge til en betingelse i en forretningsregel](media/add-condition-business-rule.png "Legge til en betingelse i en forretningsregel")  
  
    2.  Hvis du vil angi egenskaper for betingelsen, klikker du på **Betingelse**-komponenten i utformingsvinduet, og angir deretter egenskapene i **Egenskaper**-kategorien på høyre side av skjermen. Når du angir egenskaper, opprettes et uttrykk nederst i **Egenskaper**-kategorien.  
  
    3.  For å legge til en ekstra setningsdel (AND eller OR) klikker du betingelsen, klikker **Ny** i **Egenskaper**-kategorien for å opprette en ny regel, og angir deretter egenskapene for denne regelen. I **Regellogikk**-feltet kan du angi om du vil legge til den nye regelen som AND eller OR.  
  
        ![Legge til en ny regel i en betingelse](media/add-new-rule-condition.png "Legge til en ny regel i en betingelse")  
  
    4.  Når du er ferdig med å angi egenskaper for betingelsen, klikker du **Bruk**.  
  
7. **Legg til handlinger.** Slik legger du til en handling:  
  
    1.  Dra én av handlingskomponentene fra **Komponenter**-kategorien til et plusstegn ved siden av **Betingelse**-komponenten. Dra handlingen til et plusstegn ved siden av et merke hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre denne handlingen hvis betingelsen ikke er oppfylt.  
  
        ![Dra en handling til en forretningsregel](media/drag-an-action-business-rule.png "Dra en handling til en forretningsregel")  
  
    2.  Hvis du vil angi egenskaper for handlingen, klikker du på **Handling**-komponenten i utformingsvinduet, og angir deretter egenskapene i **Egenskaper**-kategorien på høyre side av skjermen.  
  
    3.  Når du er ferdig med å angi egenskaper, klikker du **Bruk**.  
  
8. **Legg til en forretningsanbefaling.** Slik legger du til en forretningsanbefaling:  
  
    1.  Dra **Anbefaling**-komponenten fra **Komponenter**-kategorien til et plusstegn ved siden av **Betingelse** -komponenten. Dra **Anbefaling**-komponenten til et plusstegn ved siden av et merke hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre denne handlingen hvis betingelsen ikke er oppfylt.  
  
    2.  Hvis du vil angi egenskaper for anbefalingen, klikker du på **Anbefaling**-komponenten i utformingsvinduet, og angir deretter egenskapene i **Egenskaper**-kategorien på høyre side av skjermen.  
  
    3.  Hvis du vil legge til flere handlinger i anbefalingen, drar du dem fra den **Komponenter**-kategorien, og angir egenskapene for hver handling i **Egenskaper**-kategorien.  
  
        > [!NOTE]
        >  Når du oppretter en anbefaling, blir en enkelt handling lagt til som standard. Hvis du vil vise alle handlinger i en anbefaling, klikke rdu **Detaljer** i **Anbefaling**-komponenten.  
  
    4.  Når du er ferdig med å angi egenskaper, klikker du **Bruk**.  
  
9. Hvis du vil validere forretningsregelen, klikker du **Valider** på handlingslinjen.  
  
10. Hvis du vil lagre forretningsregelen, klikker du **Lagre** på handlingslinjen.  
  
11. Hvis du vil aktivere forretningsregelen, merker du den i Løsningsutforsker-vinduet, og klikker deretter **Aktiver**. Du kan ikke aktivere forretningsregelen fra utformingsvinduet.  
  
> [!TIP]
>  Her er noen tips du bør huske på når du arbeider med forretningsregler i utformingsvinduet:  
>   
> - Hvis du vil ta et øyeblikksbilde av alt i Forretningsregel-vinduet, klikker du **Øyeblikksbilde** på handlingslinjen. Dette er nyttig, for eksempel hvis du ønsker å dele og få kommentarer om forretningsregelen fra et gruppemedlem.  
> - Bruk minikartet til å navigere raskt til ulike deler av prosessen. Dette er nyttig når du har en komplisert prosess som ruller ut av skjermen.  
> - Når du legger til betingelser, handlinger og forretingsanbefalinger i forretningsregelen, bygges koden for forretningsregelen og vises nederst i utformingsvinduet. Denne koden er skrivebeskyttet.  
  
<a name="BKMK_LocalizingErrorMessages"></a>   
## <a name="localize-error-messages-used-in-business-rules"></a>Oversette feilmeldinger som brukes i forretningsregler  
 Hvis du har flere enn ett språk klargjort for organisasjonen, ønsker du kanskje å oversette eventuelle feilmeldinger som du har angitt. Hver gang du angir en melding, genereres en etikett av systemet. Hvis du eksporterer oversettelsene i organisasjonen, kan du legge til lokaliserte versjoner av meldingene og deretter importere disse etikettene tilbake til systemet, slik at personer som bruker et annet språk enn basisspråket, kan vise de oversatte meldingene.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette egendefinert forretningslogikk via prosesser](guide-staff-through-common-tasks-processes.md)   
 [Opprette en forretningsprosessflyt](/flow/create-business-process-flow)   

