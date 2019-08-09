---
title: Legge til en innebygd lerretapp i et modelldrevet skjema | MicrosoftDocs
ms.custom: ''
ms.date: 06/25/2019
ms.reviewer: ''
ms.service: powerapps
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

# <a name="add-an-embedded-canvas-app-on-a-model-driven-form"></a>Legge til en innebygd lerretapp i et modelldrevet skjema
Dette emnet forklarer hvordan du bygger inn en ny lerretapp i et modelldrevet skjema.

Forestill deg at du vil opprette en ny lerretapp og bygge den inn i et hovedskjema for forretningsforbindelser-enheten. Slik gjør du det: 

1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2.  [Opprette eller redigere hovedskjemaet](create-and-edit-forms.md) for en enhet – forretningsforbindelsesenhet i vårt eksempel. 
3.  Velg **Bytt til klassisk** på kommandolinjen for å åpne skjemaet i den klassiske skjemautformingen.
4.  I den klassiske skjemautformingen velger du delen i skjemaet der du vil at den innebygde lerretappen skal vises.
5.  Ved hjelp av feltruten legger du til et obligatorisk felt, for eksempel **Navn på forretningsforbindelse**.
      > [!IMPORTANT]
      > Bruk alltid et obligatorisk felt som garantert har en verdi. Hvis feltet ikke har en verdi, oppdateres ikke den innebygde lerretappen i henhold til endringer i data i det vertsmodelldrevne skjemaet.
6.  I kategorien **Hjem** i **Rediger**-gruppen velger du **Endre egenskaper** med feltet valgt.
7.  I **Feltegenskaper**-dialogboksen velger du **Kontroller**-kategorien.
8.  I kategorien **Kontroller** velger du **Legg til kontroll**.
9.  I dialogboksen **Legg til kontroll** i listen over tilgjengelige kontroller velger du **Lerretapp** og velger deretter **Legg til**.
10. I **Feltegenskaper**-dialogboksen i listen over kontroller velger du **Lerretapp**, og velger deretter **Web**-alternativet.
11. I delen under listen over kontroller vises listen over tilgjengelige egenskaper for lerretappkontrollen.
     - **Enhetsnavn**-egenskapen angir enheten som gir dataene til den innebygde lerretappen. Den settes til enheten som inneholder feltet du la til i et tidligere trinn.
         - Vær oppmerksom på at selv om denne egenskapen ser ut til å kunne endres, vil ikke en endring av den ha noen innvirkning på den innebygde lerretappen. Den er bare ment å fungere som en referanse for deg.
     - **App-ID**-egenskapen angir ID-en for den innebygde lerretappen. Den blir generert automatisk og utfylt for deg når lerretappen blir opprettet.
         - Vær oppmerksom på at endringer i **App-ID**-verdien bryter koblingen fra det modelldrevne skjemaet til den innebygde lerretappen.
12. Velg **Tilpass** for å opprette eller redigere lerretappen. Dette åpner PowerApps Studio i en ny fane.
       > [!NOTE]
       > Hvis åpning av PowerApps Studio blokkeres på grunn av popup-blokkering i nettleseren, må du må aktivere webområdet web.powerapps.com eller midlertidig deaktivere popup-blokkeringen og deretter velge **Tilpass** på nytt.
13. Merk at det er en egen **ModelDrivenFormIntegration**-kontroll i den venstre ruten i PowerApps Studio. Denne kontrollen er ansvarlig for å hente kontekstavhengige data fra det vertsmodelldrevne skjemaet til den innebygde lerretappen.
14. Legg merke til at en [skjemakontroll for en lerretapp](../canvas-apps/controls/control-form-detail.md) ble lagt til automatisk i det innebygde lerretet, og at denne viser dataene som sendes til den fra det vertsmodelldrevne skjemaet via ModelDrivenFormIntegration-kontrollen. 
15. Velg kategorien **Vis**, og deretter **Datakilder**. Legg merke til at en datakilde for den overordnede enheten for det vertsmodelldrevne skjemaet, forretningsforbindelser i dette tilfellet, ble automatisk lagt til i den innebygde lerretappen.
16. Velg **Skjema1**-kontrollen og se at **Datakilde**-egenskapen er satt til **Forretningsforbindelser**.
17. Mens **Skjema1**-kontrollen fortsatt er valgt, se at **Element**-egenskapen er satt til **ModelDrivenFormIntegration.Item**.
    > [!NOTE]
    > Den innebygde lerretappen har full tilgang til å hente informasjon fra det vertsmodelldrevne skjemaet via ModelDrivenFormIntegration.Item. Hvis du for eksempel vil hente verdien for et felt med navnet **accountnumber** og visningsnavn **nummer for forretningsforbindelse**, kan du bruke **ModelDrivenFormIntegration.Item.accountnumber** eller **ModelDrivenFormIntegration.Item.'nummer'**.
18. I egenskapsruten til høyre ved siden av **Felt**velger du **Rediger felt**.
19. Velg **+ Legg til felt** for å legge til flere felt i skjemaet for lerretappen, eller endre rekkefølgen på eksisterende felt ved hjelp av dra og slipp. Lukk dataruten når du er ferdig med å legge til og endre rekkefølgen på felt.
20. Velg kategorien **Fil**, og deretter **Lagre**.
21. Velg **Skyen**-kategorien. Angi et unikt navn for appen, og velg deretter **Lagre** nederst til høyre. Legg merke til følgende: 
    -  Lagring av en app for første gang publiserer appen automatisk.
      -  Ved senere lagringer velger du **Publiser** og velger deretter **Publiser denne versjonen** for å gjøre endringene tilgjengelige.
22. Velg **Tilbake** i menyen.
23. Velg fanen som har klassisk skjemautforming åpen. Se at **App-ID**-egenskapen for lerretappkontrollen nå har en verdi som er fylt ut automatisk.
    > [!NOTE]
    > - Skjemautformingsprogrammet har en direkte kobling til PowerApps Studio som ble åpnet i en annen fane i et tidligere trinn.
    > - Skjemautformingsprogrammet lytter etter app-ID-en som skal sendes til det. 
    > - App-ID-en sendes til skjemautformingsprogrammet når appen lagres.
24. I **Feltegenskaper**-dialogboksen velger du **Vis**-kategorien.
25. Fjern avmerkingen for **Vis etikett** i skjemaet, og velg deretter **OK**.
    -   Hvis du allerede har en innebygd lerretapp i dette skjemaet, vises meldingen Du kan bare aktivere én lerretapp i et skjema. Hvis du vil legge til den nye lerretappen, må du først [deaktivere gjeldende innebygde lerretapp](embedded-canvas-app-guidelines.md#disable-an-embedded-canvas-app). Deretter [aktiverer du den nye innebygde lerretappen](embedded-canvas-app-guidelines.md#enable-an-embedded-canvas-app).
26. I kategorien **Hjem** velger du **Lagre**, og velger deretter **Publiser**.

Når du har lagt til en innebygd lerretapp i det modelldrevne skjemaet, kan du dele den innebygde lerretappen med andre brukere. Mer informasjon: [Dele en innebygd lerretapp](share-embedded-canvas-app.md).

Når brukere åpner en modelldrevet app (bare Enhetlig grensesnitt) som inneholder skjemaet du har endret, ser de den innebygde lerretappen i skjemaet. Når oppføringen som vises i hovedskjemaet endres, endres datakonteksten som sendes til skjemaet, og den innebygde appen oppdateres for å vise de relevante dataene.

Dette emnet viste hvordan du kommer i gang med å bygge inn en lerretapp i et modelldrevet skjema. Du kan tilpasse den innebygde lerretappen ytterligere slik at den kobler til og henter inn data fra mange forskjellige datakilder. Bruk funksjonene Filtrer, Søk og Oppslag og konteksten som ble sendt inn fra det vertsmodelldrevne skjemaet, til å filtrere eller søke etter bestemte oppføringer i disse datakildene. Bruk lerretappredigeringsprogrammet WYSIWYG til å enkelt utforme grensesnittet i henhold til kravene dine.

## <a name="see-also"></a>Se også
[Bygge inn en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Redigere en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-edit-classic-designer.md) <br />
[Tilpasse skjermstørrelsen og -retningen for en lerretapp som er innebygd i et modelldrevet skjema](embedded-canvas-app-customize-screen.md) <br />
[Utføre forhåndsdefinerte handlinger på vertsskjemaet fra en innebygd lerretapp](embedded-canvas-app-actions.md) <br />
[Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll](embedded-canvas-app-properties-actions.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md) <br />
[Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon av nyeste](embedded-canvas-app-migrate-from-preview.md) <br />
