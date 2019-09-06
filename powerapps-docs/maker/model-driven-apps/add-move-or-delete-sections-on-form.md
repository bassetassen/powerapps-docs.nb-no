---
title: 'Legge til, flytte eller slette inndelinger i et skjema ved hjelp av skjemautformingen | MicrosoftDocs'
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

# <a name="add-move-or-delete-sections-on-a-form"></a>Legge til, flytte eller slette inndelinger i et skjema 
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Legge til, flytte eller slette inndelinger i et skjema ved hjelp av skjemautformingen. 

> [!NOTE]
> Når du legger til eller flytter inndelinger ved hjelp av dra og slipp, må du være oppmerksom på at skjemaforhåndsvisningen svarer, og kan føre til at flere kategorikolonner gjengis som stablet. Hvis du vil forsikre deg om at inndelingen som blir lagt til eller flyttes, er i riktig kategorikolonne, slipper eller limer du det ankret til en annen inndeling som allerede finnes i den aktuelle kategorikolonnen.

## <a name="add-sections-to-a-form"></a>Legge til inndelinger i et skjema
Hvis du vil legge til eller fjerne inndelinger i et skjema, kan du bruke **Oppsett**-ruten. 

> [!div class="mx-imgBorder"] 
> ![](media/layouts-pane.png "Oppsettruten")

  > [!NOTE]
  >   Inndelinger kan bare legges til i hovedskjemaer og hurtigvisningsskjemaer. Mer informasjon: [Skjematyper](types-forms.md)

### <a name="add-sections-to-a-form-using-drag-and-drop"></a>Legge til inndelinger i et skjema ved hjelp av dra og slipp

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg **Legg til kontroll** på kommandolinjen, eller velg **Oppsett** i den venstre ruten. 
3. I **Oppsett**-ruten velger du en inndelingskontroll og drar den over til skjemaforhåndsvisningen. Når du drar inndelingen til forhåndsvisningen av skjemaet, vil du se et slippområde der du kan legge til inndelingen. 
4. Slipp inndelingen på stedet du vil ha den. Legg merke til følgende: 
    - Inndelinger kan slippes før eller etter eksisterende inndelinger.
    - Inndelinger kan også slippes i det tomme området i en kategori. I dette tilfellet blir inndelingen lagt til i et tilgjengelig område, slik at inndelingene blir jevnere distribuert i kategorikolonnene.
    - Hvis du holder pekeren over en kategorioverskrift når du drar en inndeling, endres den valgte kategorien, slik at du kan legge til inndelingen i en annen kategori.   
5. Gjenta trinn 3-4 ovenfor hvis du vil legge til flere inndelinger.
6. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

### <a name="add-sections-to-a-form-using-selection"></a>Legge til inndelinger i et skjema ved hjelp av utvalg 

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg en annen eksisterende inndeling eller en kategori i skjemaforhåndsvisningen. Merk følgende:
    - Når du velger en eksisterende inndeling, legges den nye inndelingen til etter den eksisterende inndelingen. 
    - Når du velger en kategori, legges den nye inndelingen til på en tilgjengelig plass, slik at inndelingene distribueres jevnt på kategorikolonnene. 
3. Velg **Legg til kontroll** på kommandolinjen, eller velg **Oppsett** i den venstre ruten.  
4. I **Oppsett**-ruten velger du en inndelingskontroll for å legge den til i skjemaet. Du kan også velge **...** ved siden av inndelingskontrollen du vil ha, og deretter velge **Legg til i valgt kategori**. 
5. Gjenta trinn 2-4 ovenfor hvis du vil legge til flere inndelinger.
6. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

## <a name="move-sections-on-a-form"></a>Flytte inndelinger i et skjema

### <a name="move-sections-on-a-form-using-drag-and-drop"></a>Flytte inndelinger i et skjema ved hjelp av dra og slipp

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. I forhåndsvisningen for skjemaet velger du inndelingsnavnet eller det tomme området i inndelingen du vil flytte, og deretter må du starte dra-handlingen. Når du drar inndelingen til forhåndsvisningen av skjemaet, vil du se et slippområde du kan flytte inndelingen til. 
3. Slipp inndelingen på stedet du vil ha den. Legg merke til følgende: 
    - Inndelinger kan slippes før eller etter eksisterende inndelinger.
    - Inndelinger kan også slippes i det tomme området i en kategori. I dette tilfellet blir inndelingen lagt til i et tilgjengelig område, slik at inndelingene blir jevnere distribuert i kategorikolonnene.
    - Hvis du holder pekeren over en kategorioverskrift når du drar en inndeling, endres den valgte kategorien, slik at du kan legge til inndelingen i en annen kategori.   
4. Gjenta trinn 2-3 ovenfor hvis du vil flytte flere inndelinger.
5. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

### <a name="move-sections-on-a-form-using-cut-and-paste"></a>Flytte inndelinger i et skjema ved hjelp av kopier og lim inn

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg inndelingen du vil flytte i skjemaforhåndsvisningen.
3. Velg **Klipp** på kommandolinjen.
4. Velg en annen eksisterende inndeling eller kategori i forhåndsvisningen av skjemaet. Du kan også bytte til en annen kategori hvis det er nødvendig.
5. Velg **Lim inn** eller marker vinkelen på kommandolinjen, og velg **Lim inn før**. Legg merke til følgende: 
    - Når du velger **Lim inn**, limes inndelingen som flyttes inn etter den eksisterende inndelingen. 
    - Når du velger **Lim inn før**, limes inndelingen som flyttes inn før den eksisterende inndelingen.
    - Når du velger en kategori, legges inndelingen som flyttes på en tilgjengelig plass, slik at inndelingene distribueres jevnt på kategorikolonnene. Handlingen **Lim inn før** gjelder ikke og er derfor ikke tilgjengelig i dette tilfellet.
6. Gjenta trinn 2-5 ovenfor hvis du vil flytte flere inndelinger.
7. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

## <a name="delete-sections-on-a-form"></a>Slette inndelinger i et skjema
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. I skjemaforhåndsvisningen velger du inndelingen du vil slette fra skjemaet. 
3. Velg **Slette** på kommandolinjen.
4. Gjenta trinn 2-3 ovenfor hvis du vil slette flere inndelinger.
4. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

    > [!NOTE]
    >   - Inndelinger kan bare slettes fra hovedskjemaer og hurtigvisningsskjemaer. Mer informasjon: [Skjematyper](types-forms.md)
    >   - Hvis du sletter en inndeling ved en feil, kan du velge **Angre** på kommandolinjen for å tilbakestille skjemaet til forrige tilstand. 
    >   - Du kan ikke slette en inndeling som har nødvendige eller låste felt. 
    >   - Du kan ikke slette en inndeling som er låst. 
    >   - En kategori må ha minst én inndeling i hver kategorikolonne. Hvis du sletter den siste gjenstående inndelingen i en kategorikolonne, blir det automatisk lagt til en ny inndeling. 

### <a name="see-also"></a>Se også
[Oversikt over den modelldrevne skjemautformingen](form-designer-overview.md)  
[Opprette eller redigere skjemaer ved hjelp av skjemautforming](create-and-edit-forms.md)  
[Legge til, flytte eller slette felt i et skjema ved hjelp av skjemautformingen.](add-move-or-delete-fields-on-form.md)  
[Legge til, flytte eller slette kategorier i et skjema ved hjelp av skjemautformingen](add-move-or-delete-tabs-on-form.md)  
[Egenskaper som er tilgjengelige i skjemautformingen](form-designer-properties.md)  
[Konfigurere overskriftegenskaper i skjemautformingen](form-designer-header-properties.md)  
[Bruke trevisningen i skjemautformingen](using-tree-view-on-form.md)  
[Opprette og rediger felt](../common-data-service/create-edit-field-portal.md)
