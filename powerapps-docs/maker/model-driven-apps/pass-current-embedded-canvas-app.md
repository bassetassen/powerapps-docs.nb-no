---
title: Sende gjeldende oppføring som datakontekst til en innebygd lerretapp | MicrosoftDocs
ms.custom: ''
ms.date: 12/17/2018
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

# <a name="pass-the-current-record-as-data-context-to-an-embedded-canvas-app"></a>Sende gjeldende oppføring som datakontekst til en innebygd lerretapp
Dette emnet beskriver hvordan du legger til en innebygd lerretapp og sender den gjeldende oppføringen (hovedskjemaet) som en datakontekst til den innebygde lerretappen.

> [!NOTE]
> Denne funksjonen er en forhåndsvisningsfunksjon. <br />
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)] 

Tenk deg at du vil legge til en innebygd lerretapp i et hovedskjema for en forretningsforbindelse og sende den gjeldende oppføringen for forretningsforbindelsen til den innebygde lerretappen. Slik gjør du det: 

1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) og åpne skjemaredigeringsprogrammet for et hovedskjema til en enhet, for eksempel forretningsforbindelsesenheten. 
2.  Velg delen i skjemaet der du vil at den innebygde lerretappen skal vises.
3.  Ved hjelp av Feltutforsker-ruten legger du til et obligatorisk felt, for eksempel **Navn på forretningsforbindelse**.
      > [!IMPORTANT]
      > Bruk alltid et obligatorisk felt som garantert har en verdi. Hvis feltet ikke har en verdi, oppdateres ikke den innebygde lerretappen i henhold til endringer i data i det vertsmodelldrevne skjemaet.
4.  I kategorien **Hjem** i **Rediger**-gruppen velger du **Endre egenskaper** med feltet valgt.
5.  I **Feltegenskaper**-dialogboksen velger du **Kontroller**-kategorien.
6.  I kategorien **Kontroller** velger du **Legg til kontroll...**.
7.  I dialogboksen **Legg til kontroll** i listen over tilgjengelige kontroller velger du **Lerretapp** og velger deretter **Legg til**.
8.  I **Feltegenskaper**-dialogboksen i listen over kontroller velger du **Lerretapp**, og velger deretter **Web**-alternativet.
9.  I delen under listen over kontroller vises listen over tilgjengelige egenskaper for lerretappkontrollen.
     - **Enhetsnavn**-egenskapen angir enheten som gir dataene til den innebygde lerretappen. Den settes til enheten som inneholder feltet du la til i et tidligere trinn.
         - Vær oppmerksom på at selv om denne egenskapen ser ut til å kunne endres, vil ikke en endring av den ha noen innvirkning på den innebygde lerretappen. Den er bare ment å fungere som en referanse for deg.
     - **App-ID**-egenskapen angir ID-en for den innebygde lerretappen. Den blir generert automatisk og utfylt for deg når lerretappen blir opprettet.
         - Vær oppmerksom på at endringer i **App-ID**-verdien bryter koblingen fra det modelldrevne skjemaet til den innebygde lerretappen.
10. Velg **Tilpass** for å opprette eller redigere lerretappen. Dette åpner PowerApps Studio i en ny kategori.
       > [!NOTE]
       > Hvis åpning av PowerApps Studio blokkeres på grunn av popup-blokkering i nettleseren, må du må aktivere webområdet web.powerapps.com eller midlertidig deaktivere popup-blokkeringen og deretter velge **Tilpass** på nytt.
11. Merk at det er en spesialkontroll **ModelDrivenFormIntegration** i den venstre ruten i PowerApps Studio. Denne kontrollen er ansvarlig for å hente kontekstavhengige data fra det vertsmodelldrevne skjemaet til den innebygde lerretappen.
12. Velg **Galleri1**-kontrollen og se at **Elementer**-egenskapen er satt til **ModelDrivenFormIntegration.Data**.
      > [!NOTE]
      > ModelDrivenFormIntegration.Data er en liste over oppføringer. I dette eksemplet har den bare én oppføring. Du kan bruke First-funksjonen for å referere direkte til oppføringen. For eksempel *First(ModelDrivenFormIntegration.Data).Name*.
13. I egenskapsruten til høyre ved siden av **Felt**velger du **Rediger**.
14. I dataruten kan du endre feltet tilordnet til **Tittel1**-kontrollen til **Navn** eller et annet felt som har data.
15. Legg merke til at galleriet viser data som sendes til det fra det vertsmodelldrevne skjemaet via ModelDrivenFormIntegration-kontrollen. Lukk dataruten.
16. Velg kategorien **Fil**, og velg deretter **Appinnstillinger**.
17. I **Avanserte innstillinger**-kategorien i **Eksperimentelle funksjoner**-delen setter du **Aktiver brukeropplevelse med appinnebygging** til **På**.
18. Velg **Lagre**. 
19. Velg **Skyen**-kategorien. Angi et unikt navn for appen, og velg deretter **Lagre** nederst til høyre. Legg merke til følgende: 
    -  Lagring av en app for første gang publiserer appen automatisk.
      -  Ved senere lagringer velger du **Publiser** og velger deretter **Publiser denne versjonen** for å gjøre endringene tilgjengelige.
20. Velg **Tilbake** på menyen og velg deretter leserkategorien som har skjemaredigeringsprogrammet åpent. Se at **App-ID**-egenskapen for lerretappkontrollen nå har en verdi som er fylt ut automatisk. Legg merke til følgende: 
    -   Skjemaredigeringsprogrammet har en direkte kobling til PowerApps Studio som ble åpnet i en annen leserfane i et tidligere trinn.
    -   Skjemaredigeringsprogrammet «lytter» etter **App-ID-en** som skal sendes til det.
    -   **App-ID-en** sendes til skjemaredigeringsprogrammet når appen lagres.
21. I **Feltegenskaper**-dialogboksen velger du **Vis**-kategorien.
22. Fjern avmerkingen for **Vis etikett** i skjemaet, og velg deretter **OK**.
    -   Hvis du allerede har en innebygd lerretapp i dette skjemaet, vises meldingen Du kan bare aktivere én lerretapp i et skjema. Hvis du vil legge til den nye lerretappen, må du først [deaktivere gjeldende innebygde lerretapp](embedded-canvas-app-guidelines.md#disable-an-embedded-canvas-app). Deretter [aktiverer du den nye innebygde lerretappen](embedded-canvas-app-guidelines.md#enable-an-embedded-canvas-app).
23. I kategorien **Hjem** velger du **Lagre**, og velger deretter **Publiser**.

Når du har lagt til en innebygd lerretapp i det modelldrevne skjemaet, kan du dele den innebygde lerretappen med andre brukere. Mer informasjon: [Dele en innebygd lerretapp](share-embedded-canvas-app.md).

Når brukere åpner en modelldrevet app (bare Enhetlig grensesnitt) som inneholder skjemaet du har endret, ser de den innebygde lerretappen i skjemaet. Når oppføringen som vises i hovedskjemaet endres, endres datakonteksten som sendes til skjemaet, og den innebygde appen oppdateres for å vise de relevante dataene.

Dette emnet viste hvordan du kommer i gang med å bygge inn en lerretapp i et modelldrevet skjema. Du kan tilpasse den innebygde lerretappen ytterligere slik at den kobler til og henter inn data fra mange forskjellige datakilder. Bruk funksjonene Filtrer, Søk og Oppslag og konteksten som ble sendt inn fra det vertsmodelldrevne skjemaet, til å filtrere eller søke etter bestemte oppføringer i disse datakildene. Bruk lerretappredigeringsprogrammet WYSIWYG til å enkelt utforme grensesnittet i henhold til kravene dine.

## <a name="see-also"></a>Se også
[Bygge inne en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Sende en liste over relaterte oppføringer som datakontekst til en innebygd lerretapp](pass-related-embedded-canvas-app.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md)
