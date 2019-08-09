---
title: Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon | MicrosoftDocs
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

# <a name="migrate-embedded-canvas-apps-on-model-driven-forms-created-using-the-public-preview-release"></a>Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon
> [!IMPORTANT]
> I den nyeste versjonen er innebygde lerretapper på modelldrevne skjemaer vanligvis tilgjengelige. Alle innebygde lerretapper i modelldrevne skjemaer som opprettes ved hjelp av den offentlige forhåndsversjonen, bør overføres til nye innebygde lerretapper som er opprettet ved hjelp av den nyeste versjonen.
> Støtte for innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon avsluttes snart. 

For å overføre innebygde lerretapper i modelldrevne skjemaer som opprettes ved hjelp av den offentlige forhåndsversjonen, må utviklerne først opprette en ny innebygd lerretapp ved hjelp av den nyeste versjonen. Deretter kan utviklerne kopiere kontrollene fra den eksisterende innebygde lerretappen til den nye, legge til nødvendige datakilder og oppdatere brutte referanser. Du finner en detaljert fremgangsmåte nedenfor.

1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2. Åpne den innebygde lerretappen som ble opprettet med den offentlige forhåndsversjonen for redigering i PowerApps Studio. Hvis du vil ha fremgangsmåte for redigering av en lerretapp, se [Redigere en lerretapp](../canvas-apps/edit-app.md).
3. I en ny fane, følg fremgangsmåten for å [legge til en innebygd lerretapp for et modelldrevet skjema](embedded-canvas-app-add-classic-designer.md).
4. Kopier kontrollene fra den innebygde lerretappen som ble opprettet med den offentlige forhåndsversjonen, til den nye innebygde lerretappen ett skjermbilde av gangen ved hjelp av fremgangsmåten nedenfor.
    1. Velg fanen fra trinn 2, som har den innebygde lerretappen som ble opprettet ved hjelp av den offentlige forhåndsversjonen, åpen i PowerApps Studio.
    2. Velg et skjermbilde å kopiere kontroller fra.
    3. Trykk **Ctrl + A** for å velge alle kontrollene på skjermen.
    4. Trykk **Ctrl + C** for å kopiere alle valgte kontroller.
    5. Velg fanen fra trinn 3, som har den nye innebygde lerretappen som ble opprettet ved hjelp av den nyeste versjonen.
    6. Velg et skjermbilde, eller legg til et nytt.
    7. Trykk **Ctrl + V** for å lime inn kontrollene på det valgte skjermbildet.
    8. Gjenta trinnene for å kopiere hvert skjermbilde.
5. Når du har kopiert alle skjermene, velger du fanen fra trinn 3, som har den nye innebygde lerretappen som ble opprettet ved hjelp av den nyeste versjonen.
6. Oppdater alle stedene der oppføringen fra det vertsmodelldrevne skjemaet hentes. Erstatt **First(ModelDrivenFormIntegration.Data)** med **ModelDrivenFormIntegration.Item**.
7. Legg til eventuelle manglende datakilder i den nye innebygde lerretappen.
8. Oppdater alle brutte referanser i den nye innebygde lerretappen. 
9. Når du er ferdig med å gjøre endringer, velger du kategorien **Fil**, og deretter **Lagre**.
10. For å tilby endringene til sluttbrukerne velger du **Publiser** og deretter **Publiser denne versjonen**.

## <a name="migrating-embedded-canvas-apps-on-model-driven-forms-that-use-a-list-of-records-related-to-the-current-main-form-record"></a>Overføre innebygde lerretapper i modelldrevne skjemaer som bruker en liste over oppføringer som er relatert til gjeldende (hovedskjema-) oppføring

I forhåndsversjonen, for å kunne bygge inn en lerretapp på et modelldrevet skjema, måtte utviklerne bestemme på forhånd om de ville sende gjeldende (hovedskjema-) oppføring som datakontekst eller en liste over oppføringer relatert til den gjeldende (hovedskjema-) oppføringen. De måtte deretter legge til lerretappenkontrollen i enten en felt- eller en delrutenettkontroll.

Ved hjelp av den nyeste versjonen kan det å legge til en innebygd lerretapp på et modelldrevet skjema forenkles og strømlinjeformes kun til feltet. Utviklere kan fremdeles enkelt få tilgang til listen over relaterte oppføringer direkte i lerretappen ved hjelp av Common Data Service-koblingen. 

For å overføre innebygde lerretapper i modelldrevne skjemaer som bruker en liste over oppføringer som er relatert til gjeldende (hovedskjema-) oppføring, følger du fremgangsmåten nedenfor.

1. Følg fremgangsmåten i delen ovenfor for å overføre innebygde lerretapper i modelldrevne skjemaer som er opprettet ved hjelp av offentlig forhåndsversjon til nyeste.
2. Bruk Common Data Service-koblingen til å legge til en datakilde for den relaterte enheten i appen. Hvis du vil lære hvordan du legger til en datakilde i en lerretapp, kan du lese [Legge til en datatilkobling til en lerretapp i PowerApps](../canvas-apps/add-data-connection.md).
3. Når du bruker datakilden til den relaterte enheten for en kontroll, for eksempel [Galleri](../canvas-apps/controls/control-gallery.md) eller [Datatabell](../canvas-apps/controls/control-data-table.md), må du bruke **[Filter](../canvas-apps/functions/function-filter-lookup.md)**-funksjonen til å filtrere oppføringene til dem som er relatert til den gjeldende (hovedskjema-) oppføringen. Gjeldende (hovedskjema-) oppføring er tilgjengelig via **ModelDrivenFormIntegration.Item**.
    > [!NOTE]
    > Den innebygde lerretappen har full tilgang til å hente informasjon fra det vertsmodelldrevne skjemaet via ModelDrivenFormIntegration.Item. Hvis du for eksempel vil hente verdien for et felt med navnet **accountnumber** og visningsnavn **nummer for forretningsforbindelse**, kan du bruke **ModelDrivenFormIntegration.Item.accountnumber** eller **ModelDrivenFormIntegration.Item.'nummer'**.
4. Med nylige oppdateringer gir Common Data Service nå også støtte til å bruke enhetsvisninger som et filter. Se dette blogginnlegget for mer informasjon: [Forbedrede datakildevalg og Common Data Service-visninger](https://powerapps.microsoft.com/blog/improved-data-source-selection-and-common-data-service-views/). 

## <a name="see-also"></a>Se også
[Bygge inn en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Legge til en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-add-classic-designer.md) <br />
[Redigere en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-edit-classic-designer.md) <br />
[Tilpasse skjermstørrelsen og -retningen for en lerretapp som er innebygd i et modelldrevet skjema](embedded-canvas-app-customize-screen.md) <br />
[Utføre forhåndsdefinerte handlinger på vertsskjemaet fra en innebygd lerretapp](embedded-canvas-app-actions.md) <br />
[Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll](embedded-canvas-app-properties-actions.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md) <br />
