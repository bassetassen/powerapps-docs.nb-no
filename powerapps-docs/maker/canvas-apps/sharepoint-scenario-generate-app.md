---
title: Generer en lerretsapp for å administrere prosjektforespørsler | Microsoft Docs
description: I denne oppgaven skal vi generere en grunnleggende lerretsapp med tre skjermer direkte fra en SharePoint-liste.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/12/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c9c7e58c8127b1c2784e0b1d79e78a1cb9478054
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799322"
---
# <a name="generate-a-canvas-app-to-handle-project-requests"></a>Generer en lerretsapp for å administrere prosjektforespørsler
> [!NOTE]
> Denne artikkelen er en del av en opplæringsserie om hvordan du bruker PowerApps, Microsoft Flow og Power BI med SharePoint Online. Sørg for å lese [innføringen for serien](sharepoint-scenario-intro.md) for å få forståelse av det store bildet, i tillegg til relaterte nedlastinger.

Nå som vi har fått på plass SharePoint-listen, kan vi bygge og egendefinere vår første app. PowerApps er integrert med SharePoint, så det er enkelt å generere en grunnleggende *app med tre skjermer* direkte fra en liste. Med denne appen kan du vise sammendrag og detaljert informasjon for hvert listeelement, oppdatere eksisterende listeelementer, og opprette nye listeelementer. Hvis du oppretter en app direkte fra en liste, vises appen som en *visning* for den listen. Du kan deretter kjøre appen i en nettleser, så vel som på en mobiltelefon.

> [!TIP]
> [Nedlastingspakken](https://aka.ms/o4ia0f) for dette scenarioet inkluderer en fullført versjon av denne appen: project-requests-app.msapp.

## <a name="step-1-generate-an-app-from-a-sharepoint-list"></a>Trinn 1: Generer en app fra en SharePoint-liste

1. Klikk eller trykk på **PowerApps** i **Prosjektforespørsler**-listen du opprettet, og deretter på **Opprett en app**.
   
    ![Å opprette en app](./media/sharepoint-scenario-generate-app/02-01-01-create-app.png)

2. Gi appen et navn, som for eksempel «Prosjektforespørsel-app», og klikk eller trykk deretter på **Opprett**. Når appen er klar, åpnes den i PowerApps Studio.
   
    ![Å angi et navn for appen](./media/sharepoint-scenario-generate-app/02-01-02-create-app-name.png)

## <a name="step-2-review-the-app-in-powerapps-studio"></a>Trinn 2: Se gjennom appen i PowerApps Studio

1. Det venstre navigasjonsfeltet i PowerApps Studio viser som standard en hierarkisk visning av skjermene og kontrollene i appen.
   
    ![PowerApps Studio hierarkisk visning](./media/sharepoint-scenario-generate-app/02-02-01-studio-screens-hierarchy.png)

2. Klikk eller trykk på miniatyrbildeikonet for å veksle mellom visninger.
   
    ![Valg av PowerApps Studio-visning](./media/sharepoint-scenario-generate-app/02-02-02-studio-view-selector.png)

3. Klikk eller trykk på hver skjerm for å vise den i den midterste ruten. Det finnes tre skjermer:
   
    (a). **Bla Gjennom**-skjermen, hvor du blar gjennom, sorterer og filtrerer dataene som hentes fra listen.
    
    (b). **Detaljer**-skjermen, hvor du ser flere detaljer om et element.
    
    (c). **Rediger/opprett**-skjermen: der du redigerer et eksisterende element eller oppretter et nytt.
      
      ![PowerApps Studio med miniatyrbildevisning](./media/sharepoint-scenario-generate-app/02-02-03-studio-screens-thumbnails.png)

## <a name="step-3-customize-the-apps-browse-screen"></a>Trinn 3: Tilpass appens Bla gjennom-skjermen

1. Klikk eller trykk på Bla gjennom-skjermen.
   
    Denne skjermen har et *oppsett* som inneholder et *galleri* for å vise listeelementer så vel som andre *kontroller*, som for eksempel et søkefelt og en sorteringsknapp.

2. Velg **BrowseGallery1**-galleriet ved å klikke eller trykke på hvilken som helst post, bortsett fra den første.
   
    ![Bla gjennom-galleri](./media/sharepoint-scenario-generate-app/02-03-01-browse-gallery.png)

3. Klikk eller trykk på **Prosjektforespørsler** i ruten til høyre, under**Egenskaper**. 

4. Oppdater feltene for å samsvare med den følgende listen:
   
   * **RequestDate**

   * **Anmoder**

   * **Tittel**

     ![Gallerifelt](./media/sharepoint-scenario-generate-app/02-03-02-gallery-fields.png)

5. Velg **Elementer**-egenskapen, mens **BrowseGallery1** ennå er valgt.
   
    ![Elementer-egenskaper](./media/sharepoint-scenario-generate-app/02-03-03-items.png)

6. Endre formelen til **SortByColumns(Filter('Project Requests', StartsWith(Title, TextSearchBox1.Text)), "Title", If(SortDescending1, Descending, Ascending))**.
   
    ![Formellinje](./media/sharepoint-scenario-generate-app/02-03-04-formula.png)
   
    Dette lar deg sortere og søke etter **Tittel**-feltet, i stedet for standardinnstillingen som PowerApps valgte. Hvis du vil ha mer informasjon, kan du se [Grundig innføring i formler](#formula-deep-dive).

6. Klikk eller trykk på **Fil**, deretter på **Lagre**. Klikk eller trykk på ![Tilbake til app-ikonet](./media/sharepoint-scenario-generate-app/icon-back-to-app.png) for å gå tilbake til appen.

## <a name="step-4-review-the-apps-details-screen-and-edit-screen"></a>Trinn 4: Se gjennom detaljer-skjermen til appen og Rediger-skjermen
1. Klikk eller trykk på Detaljer-skjermen.
   
    Denne skjermen har et annet oppsett som inneholder et *visningsskjema* for å vise detaljer for et element som er valgt i galleriet. Den inneholder kontroller for å redigere og slette elementer, og gå tilbake til Bla gjennom-skjermen.
   
    ![Visningsskjema for detaljer](./media/sharepoint-scenario-generate-app/02-04-01-details.png)

4. Klikk eller trykk på Rediger-skjermen.
   
    Denne skjermen inneholder et *redigeringsskjema* for å redigere det utvalgte elementet, eller opprette et nytt element (hvis du kommer hit direkte fra Bla gjennom-skjermen). Den inneholder kontroller for å lagre og forkaste endringer.

    ![Redigeringsskjema](./media/sharepoint-scenario-generate-app/02-04-03-edit.png)

## <a name="step-5-run-the-app-from-the-list"></a>Trinn 5: Kjøre appen fra listen

1. Klikk eller trykk på **Alle elementer** i **Prosjektforespørsler-listen**, og deretter klikker eller trykker du på **Prosjektforespørsler-appen**.
   
    ![Å vise Prosjektforespørsler-appen](./media/sharepoint-scenario-generate-app/02-05-01-view-app.png)
2. Klikk på **Åpne**, og appen åpnes i en ny fane i nettleseren.
   
    ![Å åpne Prosjektforespørsler-appen](./media/sharepoint-scenario-generate-app/02-05-02-open-app.png)

3. Klikk eller trykk på ![Gå til detaljer-ikonet](./media/sharepoint-scenario-generate-app/icon-details-arrow.png) i appen, for det første elementet i Bla gjennom-galleriet.
   
    ![Første gallerielement](./media/sharepoint-scenario-generate-app/02-05-04-first-item.png)

4. Klikk eller trykk på ![Blyantredigering-ikonet](./media/sharepoint-scenario-generate-app/icon-pencil.png) for å redigere elementet.

5. Å oppdatere **Beskrivelse**-feltet – endre det siste ordet fra «gruppe» til «team», og klikk eller trykk deretter på ![hakemerkeikonet](./media/sharepoint-scenario-generate-app/icon-check-mark.png)
   
   ![Å oppdatere Beskrivelse-feltet](./media/sharepoint-scenario-generate-app/02-05-07-edit.png)

6. Lukk nettleserfanen.

7. Gå tilbake til **Prosjektforespørsler-listen**, klikk eller trykk på **Prosjektforespørsler-appen** og deretter på **Alle elementer**.
   
   ![Å vise alle elementer](./media/sharepoint-scenario-generate-app/02-05-08-view-all.png)
8. Bekreft endringene du foretok fra appen.
   
    ![Å bekrefte redigeringen](./media/sharepoint-scenario-generate-app/02-05-09-verify-edit.png)

Dette er et ganske enkelt trinn, og vi har bare gjort et par grunnleggende tilpasninger, men du ser det er mulig å bygge noe interessant veldig raskt. Vi skal fortsette til neste oppgave, men gjør deg kjent med appen litt mer hvis ønsker det, og se hvordan kontrollene og formlene arbeider sammen for å drive virkemåten til appen.

## <a name="formula-deep-dive"></a>Grundig innføring i formler
Denne delen er valgfri, men den hjelper deg med å forstå mer om hvordan formler fungerer. I trinn 3 til denne oppgaven endret vi formelen for **Elementer**-egenskapen til **BrowseGallery1**. Vi endret spesifikt at sorterings- og søkefunksjonen bruker **Tittel**-feltet, i stedet for det feltet som PowerApps velger. Her ser du den endrede formelen:

**SortByColumns ( Filter ( 'Project Requests', StartsWith ( Title, TextSearchBox1.Text ) ), "Title", If ( SortDescending1, Descending, Ascending ) )**

Hva gjør denne formelen? Den fastslår kildene til dataene som vises i galleriet, filtrerer dataene basert på tekst som skrives inn i søkeboksen, og sorterer resultatene basert på sorteringsknappen i appen. Formelen bruker *funksjoner*. Funksjoner tar parametere (det vil si, inndata), utfører en operasjon (som filtrering), og returnerer en verdi (det vil si, utdata):

* [**SortByColumns**-funksjonen](functions/function-sort.md) sorterer en tabell basert på én eller flere kolonner.
* [**Filter**-funksjonen](functions/function-filter-lookup.md) finner posten i en tabell som tilfredsstiller formelen du angir.
* [**StartsWith**-funksjonen](functions/function-startswith.md) tester om én tekststreng begynner med en annen tekststreng.
* [**If**-funksjonen](functions/function-if.md) returnerer én verdi hvis sann, og returnerer en annen verdi hvis samme betingelse er usann.

Når du plasserer funksjonene sammen i formelen, skjer følgende:

1. Hvis du skrev inn tekst i søkeboksen, sammenligner **StartsWith**-funksjonen den teksten med begynnelsen av hver streng i **Tittel**-kolonnen til listen.
   
    **StartsWith ( Title, TextSearchBox1.Text )**
   
    Hvis du for eksempel skrev inn «en» i søkeboksen, ser du fire resultater, inkludert elementer som begynner med «enhet» og «endre». Du ser ikke alle elementene for «Mobile enheter», fordi de *begynner ikke med* «en».

2. **Filter**-funksjonen *returnerer* rader fra **Prosjektforespørsler**-tabellen. Hvis det ikke er noen tekst i søkeboksen for sammenligning, returnerer **Filter** alle radene.
   
    **Filter ( 'Project Requests', StartsWith ( Title, TextSearchBox1.Text )**

3. **If**-funksjonen ser om variabelen **SortDescending1** er angitt til sann eller usann (sorteringsknappen i appen angir dette). Funksjonen returnerer deretter verdien **Synkende** eller **Stigende**.
   
    **If ( SortDescending1, Descending, Ascending )**

4. Nå kan **SortByColumns**-funksjonen sortere galleriet. I dette tilfellet sorterer den basert på **Tittel**-feltet, men dette kan være et annet felt enn det du søker i.

Hvis du har fulgt med så langt, håper vi at du har en bedre forståelse av hvordan denne formelen fungerer, og hvordan du kan kombinere funksjoner og andre elementer til å drive virkemåten til appene du trenger. Hvis du trenger mer informasjon, kan du se [Formelreferanse for PowerApps](formula-reference.md).

## <a name="next-steps"></a>Neste trinn
Det neste trinnet i denne opplæringsserien er å [opprette en flyt for å behandle prosjektgodkjenninger](sharepoint-scenario-approval-flow.md).

