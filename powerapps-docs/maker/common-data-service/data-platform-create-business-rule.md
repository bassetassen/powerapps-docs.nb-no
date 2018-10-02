---
title: Opprette en forretningsregel i Common Data Service for Apps | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du oppretter en forretningsregel i Common Data Service (CDS) for Apps.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-business-rule-for-an-entity"></a>Opprett en forretningsregel for en enhet

Du kan opprette regler og anbefalinger for å bruke logikk og valideringer uten å skrive kode eller lage plugin-moduler. Forretningsregler har et enkelt grensesnitt for å implementere og vedlikeholde regler som endres og brukes ofte. 
  
Ved å kombinere betingelser og handlinger kan du gjøre ett av følgende med forretningsregler:  
  
* Angi feltverdier  
* Fjerne feltverdier  
* Angi feltkravnivåer  
* Vise eller skjule felt  
* Aktivere eller deaktivere felt  
* Validere data og vise feilmeldinger  
* Opprette forretningsanbefalinger basert på forretningsintelligens.  
  
## <a name="differences-between-canvas-and-model-driven-apps"></a>Forskjeller mellom lerretsapper og modellrevne apper

Modelldrevne apper kan bruke alle handlinger som er tilgjengelige i forretningsregler, men ikke alle forretningsregelhandlinger er tilgjengelige i lerretsapper for øyeblikket. Følgende handlinger er **ikke** tilgjengelige i lerretsapper:

* Vise eller skjule felt  
* Aktivere eller deaktivere felt  
* Opprette forretningsanbefalinger basert på forretningsintelligens.  

## <a name="prerequisites"></a>Forhåndskrav
Hvis du vil følge dette emnet, må du bytte til et [miljø](../canvas-apps/working-with-environments.md) der du kan opprette og redigere enheter.

## <a name="create-a-business-rule"></a>Opprette en forretningsregel
  
1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og klikk eller trykk på Pil ned for **Data** nær venstre kant.

2. I listen som vises, klikker eller trykker du på **Enheter**.
  
3. Åpne enheten du vil opprette forretningsregelen for (åpne for eksempel **Forretningsforbindelse**-enheten), og klikk deretter på kategorien **Forretningsregler**.  

4. Klikk **Ny**.  
  
    Forretningsregel-utforming-vinduet åpnes med et enkelt vilkår som allerede er opprettet for deg. Hver regel starter med en betingelse. Forretningsregelen utfører én eller flere handlinger basert på denne betingelsen.  

    > [!TIP]
    > Hvis du vil endre en ekisterende forretningsregel, må du deaktivere den før du kan redigere den.  
  
5. Legg til en beskrivelse, hvis du vil, i Beskrivelse-boksen øverst til venstre i vinduet.
  
6. Angi omfanget i henhold til følgende:  
  
    |||  
    |-|-|  
    |**Hvis du velger dette elementet...**|**Omfanget angis til...**|  
    |**Enhet**|Modelldrevne skjemaer og server|  
    |**Alle skjemaer**|Modelldrevne skjemaer|  
    |Bestemt skjema (for eksempel **Konto**-skjema)|Bare dette modelldrevne skjemaet|  

    > [!TIP]
    > Hvis du oppretter en lerretsapp, må du bruke enhet som omfang.
  
7. **Legg til betingelser.** Slik legger du til flere betingelser i forretningsregelen:  
  
    1. Dra **Betingelse**-komponenten fra **Komponenter**-kategorien til et plusstegn i utformingen.  
  
        ![Legge til en betingelse i en forretningsregel](./media/data-platform-cds-create-business-rule/add-condition-business-rule.png "Legge til en betingelse i en forretningsregel")  
  
    2. Hvis du vil angi egenskaper for betingelsen, klikker du på **Betingelse**-komponenten i utformingsvinduet, og angir deretter egenskapene i **Egenskaper**-kategorien på høyre side av skjermen. Når du angir egenskaper, oppretter Common Data Service et uttrykk nederst i **Egenskaper**-kategorien.  
  
    3. For å legge til en ekstra setningsdel (AND eller OR) klikker du betingelsen, klikker **Ny** i **Egenskaper**-kategorien for å opprette en ny regel, og angir deretter egenskapene for denne regelen. I **Regellogikk**-feltet kan du angi om du vil legge til den nye regelen som AND eller OR.  
  
        ![Legge til en ny regel i en betingelse](./media/data-platform-cds-create-business-rule/add-new-rule-condition.png "Legge til en ny regel i en betingelse")  
  
    4. Når du er ferdig med å angi egenskaper for betingelsen, klikker du **Bruk**.  
  
8. **Legg til handlinger.** Slik legger du til en handling:  
  
    1. Dra én av handlingskomponentene fra **Komponenter**-kategorien til et plusstegn ved siden av **Betingelse**-komponenten. Dra handlingen til et plusstegn ved siden av et merke hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre denne handlingen hvis betingelsen ikke er oppfylt.
  
        ![Dra en handling til en forretningsregel](./media/data-platform-cds-create-business-rule/drag-an-action-business-rule.png "Dra en handling til en forretningsregel")  
  
    2. Hvis du vil angi egenskaper for handlingen, klikker du på **Handling**-komponenten i utformingsvinduet, og angir deretter egenskapene i **Egenskaper**-kategorien på høyre side av skjermen.  
  
    3. Når du er ferdig med å angi egenskaper, klikker du **Bruk**.  
  
9. **Legg til en forretningsanbefaling. (bare modelldrevet)** Slik legger du til en forretningsanbefaling:  
  
    1. Dra **Anbefaling**-komponenten fra **Komponenter**-kategorien til et plusstegn ved siden av **Betingelse** -komponenten. Dra **Anbefaling**-komponenten til et plusstegn ved siden av et merke hvis du vil at forretningsregelen skal utføre denne handlingen når betingelsen er oppfylt, eller til et plusstegn ved siden av en x hvis du vil at forretningsregelen skal utføre denne handlingen hvis betingelsen ikke er oppfylt.  
  
    2. Hvis du vil angi egenskaper for anbefalingen, klikker du på **Anbefaling**-komponenten i utformingsvinduet, og angir deretter egenskapene i **Egenskaper**-kategorien på høyre side av skjermen.  
  
    3. Hvis du vil legge til flere handlinger i anbefalingen, drar du dem fra den **Komponenter**-kategorien, og angir egenskapene for hver handling i **Egenskaper**-kategorien.  
  
        > [!NOTE]
        >  Når du oppretter en anbefaling, legger Common Data Service til en enkelt handling som standard. Hvis du vil vise alle handlinger i en anbefaling, klikke rdu **Detaljer** i **Anbefaling**-komponenten.  
  
    4. Når du er ferdig med å angi egenskaper, klikker du **Bruk**.  
  
10. Hvis du vil validere forretningsregelen, klikker du **Valider** på handlingslinjen.  
  
11. Hvis du vil lagre forretningsregelen, klikker du **Lagre** på handlingslinjen.  
12. Hvis du vil aktivere forretningsregelen, merker du den i Løsningsutforsker-vinduet, og klikker deretter **Aktiver**. Du kan ikke aktivere forretningsregelen fra utformingsvinduet.  
  
    > [!TIP]
    >  Her er noen tips du bør huske på når du arbeider med forretningsregler i utformingsvinduet:  
    >   
    > - Hvis du vil ta et øyeblikksbilde av alt i Forretningsregel-vinduet, klikker du **Øyeblikksbilde** på handlingslinjen. Dette er nyttig, for eksempel hvis du ønsker å dele og få kommentarer om forretningsregelen fra et gruppemedlem.  
    > - Bruk minikartet til å navigere raskt til ulike deler av prosessen. Dette er nyttig når du har en komplisert prosess som ruller ut av skjermen.  
    > - Når du legger til betingelser, handlinger og forretningsanbefalinger i forretningsregelen, bygger Common Data Service koden for forretningsregelen nederst i utformingsvinduet. Denne koden er skrivebeskyttet.  
  
## <a name="localize-error-messages-used-in-business-rules"></a>Oversette feilmeldinger som brukes i forretningsregler  
 Hvis du har flere enn ett språk klargjort for organisasjonen, ønsker du kanskje å oversette eventuelle feilmeldinger som du har angitt. Hver gang du angir en melding, genereres en etikett av systemet. Hvis du eksporterer oversettelsene i organisasjonen, kan du legge til lokaliserte versjoner av meldingene og deretter importere disse etikettene tilbake til Common Data Service, slik at personer som bruker et annet språk enn basisspråket, kan vise de oversatte meldingene.  
  
