---
title: 'Legge til, flytte eller slette felt i et skjema | MicrosoftDocs'
ms.custom: ''
ms.date: 04/21/2019
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

# <a name="add-move-or-delete-fields-on-a-form"></a>Legge til, flytte eller slette felt i et skjema  
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Legg til, flytt og fjern felt ved hjelp av skjemautformingen.

> [!NOTE]
> Når du legger til eller flytter felt ved hjelp av dra og slipp, må du være oppmerksom på at skjemaforhåndsvisningen svarer, og kan føre til at flere delkolonner gjengis som stablet. Hvis du vil forsikre deg om at feltet som blir lagt til eller flyttes, er i riktig delkolonne, slipper eller limer du det ankret til et annet felt som allerede finnes i den aktuelle delkolonnen.

## <a name="add-fields-to-a-form"></a>Legge til felt i et skjema
Hvis du vil legge til eller fjerne felt fra et skjema, kan du bruke **Felt**-ruten. Med **Felt**-ruten kan du søke og filtrere, slik at du raskt finner feltene. Den inkluderer også muligheten til å vise bare ubrukte felt. 

> [!div class="mx-imgBorder"] 
> ![](media/fields-pane.png "Felt-ruten")

### <a name="add-fields-to-a-form-using-drag-and-drop"></a>Legge til felt i et skjema ved hjelp av dra og slipp

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg **Legg til felt** på kommandolinjen, eller velg **Felt** i den venstre ruten.  **Felt**-ruten er åpen som standard når skjemautformingen åpnes. 
3. Søk, filtrer og bla for å finne feltet du vil legge til, i ruten **Felt**-ruten. Hvis du ikke finner et felt, kan det hende at det allerede finnes i skjemaet. Fjern merket for **Vis bare ubrukte felt** for å vise alle feltene, inkludert de som allerede er lagt til i skjemaet. 
4. I **Felt**-ruten velger du et felt og drar det over til skjemaforhåndsvisningen. Når du drar feltet til forhåndsvisningen av skjemaet, vil du se et slippområde der du kan legge til feltet. 
5. Slipp feltet på stedet du vil ha det. Legg merke til følgende: 
    - Felt kan slippes før eller etter eksisterende felt.
    - Felt kan også slippes i et tomt område i en seksjon. I dette tilfellet legges det nye feltet til på en tilgjengelig plass, slik at felt distribueres jevnt på delkolonnene.
    - Hvis du holder pekeren over en kategorioverskrift når du drar et felt, endres den valgte kategorien, slik at du kan legge til feltet i en annen kategori.   
6. Gjenta trinn 3-5 ovenfor hvis du vil legge til flere felt.
7. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

### <a name="add-fields-to-a-form-using-selection"></a>Legge til felt i et skjema ved hjelp av utvalg 

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg et annet eksisterende felt eller en inndeling i skjemaforhåndsvisningen. Legg merke til følgende:
    - Når du velger et eksisterende felt, legges det nye feltet til etter det eksisterende feltet. 
    - Når du velger en inndeling, legges det nye feltet til på en tilgjengelig plass, slik at felt distribueres jevnt på delkolonnene. 
3. Velg **Legg til felt** på kommandolinjen, eller velg **Felt** i den venstre ruten. **Felt**-ruten er åpen som standard når skjemautformingen åpnes. 
4. Søk, filtrer og bla for å finne feltet du vil legge til, i ruten **Felt**-ruten. Hvis du ikke finner et felt, kan det hende at det allerede finnes i skjemaet. Fjern merket for **Vis bare ubrukte felt** for å vise alle feltene, inkludert de som allerede er lagt til i skjemaet. 
5. I **Felt**-ruten velger du et felt for å legge det til i skjemaet. Du kan også velge **...** ved siden av feltet du vil ha, og deretter velge **Legg til i valgt inndeling**. 
6. Gjenta trinn 2-5 ovenfor hvis du vil legge til flere felt.
7. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

## <a name="move-fields-on-a-form"></a>Flytte felt i et skjema

### <a name="move-fields-on-a-form-using-drag-and-drop"></a>Flytte felt i et skjema ved hjelp av dra og slipp

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg feltet som du vil flytte fra skjemaforhåndsvisningen og begynn å dra. Når du drar feltet til forhåndsvisningen av skjemaet, vil du se et slippområde du kan flytte feltet til. 
3. Slipp feltet på stedet du vil ha det. Legg merke til følgende: 
    - Felt kan slippes før eller etter eksisterende felt.
    - Felt kan også slippes i et tomt område i en seksjon. I dette tilfellet legges det nye feltet til på en tilgjengelig plass, slik at felt distribueres jevnt på delkolonnene.
    - Hvis du holder pekeren over en kategorioverskrift når du drar et felt, endres den valgte kategorien, slik at du kan legge til feltet i en annen kategori.   
4. Gjenta trinn 2-3 ovenfor hvis du vil flytte flere felt.
5. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

    > [!NOTE]
    >   Det er ikke støtte for å flytte felt i topp-og bunn tekst ved hjelp av dra og slipp ennå. 

### <a name="move-fields-on-a-form-using-cut-and-paste"></a>Flytte felt i et skjema ved hjelp av kopier og lim inn

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg feltet du vil flytte i skjemaforhåndsvisningen.
3. Velg **Klipp** på kommandolinjen.
4. Velg et annet eksisterende felt eller en inndeling i skjemaforhåndsvisningen. Du kan også bytte til en annen kategori hvis det er nødvendig.
5. Velg **Lim inn** eller marker vinkelen på kommandolinjen, og velg **Lim inn før**. Legg merke til følgende:
    - Når du velger **Lim inn**, limes feltet som flyttes inn etter det eksisterende feltet. 
    - Når du velger **Lim inn før**, limes feltet som flyttes inn før det eksisterende feltet.
    - Når du velger en inndeling, legges feltet som flyttes til på en tilgjengelig plass, slik at felt distribueres jevnt på delkolonnene. Handlingen **Lim inn før** gjelder ikke og er derfor ikke tilgjengelig i dette tilfellet.
6. Gjenta trinn 2-5 ovenfor hvis du vil flytte flere felt.
7. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

## <a name="delete-fields-on-a-form"></a>Slette felt i et skjema
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. I skjemaforhåndsvisningen velger du feltet du vil slette fra skjemaet. 
3. Velg **Slette** på kommandolinjen. 
4. Gjenta trinn 2-3 ovenfor hvis du vil slette flere felt.
5. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

     > [!NOTE]
     >   -  Hvis du sletter et felt ved en feil, kan du velge **Angre** på kommandolinjen for å tilbakestille skjemaet til forrige tilstand. 
     >   -  Du kan ikke slette et felt som er nødvendig eller låst. 

### <a name="see-also"></a>Se også
[Oversikt over den modelldrevne skjemautformingen](form-designer-overview.md)  
[Opprette eller redigere skjemaer ved hjelp av skjemautforming](create-and-edit-forms.md)  
[Legge til, flytte eller slette inndelinger i et skjema ved hjelp av skjemautformingen](add-move-or-delete-sections-on-form.md)  
[Legge til, flytte eller slette kategorier i et skjema ved hjelp av skjemautformingen](add-move-or-delete-tabs-on-form.md)  
[Egenskaper som er tilgjengelige i skjemautformingen](form-designer-properties.md)  
[Konfigurere overskriftegenskaper i skjemautformingen](form-designer-header-properties.md)  
[Bruke trevisningen i skjemautformingen](using-tree-view-on-form.md)  
[Opprette og rediger felt](../common-data-service/create-edit-field-portal.md)
