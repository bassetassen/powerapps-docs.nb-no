---
title: 'Legge til, flytte eller slette kategorier i et skjema ved hjelp av skjemautformingen | MicrosoftDocs'
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

# <a name="add-move-or-delete-tabs-on-a-form"></a>Legge til, flytte eller slette kategorier i et skjema  
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Legge til, flytte eller slette kategorier i et skjema ved hjelp av skjemautformingen.

## <a name="add-tabs-to-a-form"></a>Legge kategorier i et skjema
Hvis du vil legge til eller fjerne kategorier i et skjema, kan du bruke **Oppsett**-ruten.  

> [!div class="mx-imgBorder"] 
> ![](media/layouts-pane.png "Oppsettruten")
   
  > [!NOTE]
  >  Kategorier kan bare legges til i hovedskjemaer. Mer informasjon: [Skjematyper](types-forms.md)

### <a name="add-tabs-to-a-form-using-drag-and-drop"></a>Legge til kategorier i et skjema ved hjelp av dra og slipp

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg **Legg til kontroll** på kommandolinjen, eller velg **Oppsett** i den venstre ruten. 
3. I **Oppsett**-ruten velger du en kategorikontroll og drar den over til skjemaforhåndsvisningen. Når du drar kategorien til forhåndsvisningen av skjemaet, vil du se et slippområde der du kan legge til kategorien. 
4. Slipp kategorien på stedet du vil ha den. Legg merke til følgende: 
    - Kategorier kan slippes før eller etter eksisterende kategorier ved å holde pekeren over kategorioverskriftene.
    - Du kan også slippe kategorier før eller etter den gjeldende kategorien ved å holde pekeren over venstre eller høyre kant av gjeldende kategori.
5. Gjenta trinn 3-4 ovenfor hvis du vil legge til flere kategorier.
6. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

### <a name="add-tabs-to-a-form-using-selection"></a>Legge til kategorier i et skjema ved hjelp av utvalg 

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg en annen eksisterende kategori eller skjemaet i skjemaforhåndsvisningen. Legg merke til følgende:
    - Når du velger en eksisterende kategori, legges den nye kategorien til etter den eksisterende kategorien. 
    - Når du velger skjemaet, legges den nye kategorien til som siste kategori i skjemaet. 
3. Velg **Legg til kontroll** på kommandolinjen, eller velg **Oppsett** i den venstre ruten.  
4. I **Oppsett**-ruten velger du en kategorikontroll for å legge den til i skjemaet. Du kan også velge **...** ved siden av kategorikontroll du vil ha, og deretter velge **Legg til i skjema**. 
5. Gjenta trinn 2-4 ovenfor hvis du vil legge til flere kategorier.
6. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

## <a name="move-tabs-on-a-form"></a>Flytte kategorier i et skjema

### <a name="move-tabs-on-a-form-using-drag-and-drop"></a>Flytte kategorier i et skjema ved hjelp av dra og slipp

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg kategorioverskriften til kategorien som du vil flytte fra skjemaforhåndsvisningen og begynn å dra. Når du drar kategorien til forhåndsvisningen av skjemaet, vil du se et slippområde du kan flytte kategorien til.  
3. Slipp kategorien på stedet du vil ha den. Legg merke til følgende:
    - Kategorier kan slippes før eller etter eksisterende kategorier ved å holde pekeren over kategorioverskriftene.
    - Du kan også slippe kategorier før eller etter den gjeldende kategorien ved å holde pekeren over venstre eller høyre kant av gjeldende kategori.
4. Gjenta trinn 2-3 ovenfor hvis du vil flytte flere kategorier.
5. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

### <a name="move-tabs-on-a-form-using-cut-and-paste"></a>Flytte kategorier i et skjema ved hjelp av kopier og lim inn

1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. Velg kategorien du vil flytte i skjemaforhåndsvisningen.
3. Velg **Klipp** på kommandolinjen.
4. Velg en annen eksisterende kategori eller skjemaet i skjemaforhåndsvisningen.
5. Velg **Lim inn** eller marker vinkelen på kommandolinjen, og velg **Lim inn før**. Legg merke til følgende: 
    - Når du velger **Lim inn**, limes kategorien som flyttes inn etter den eksisterende kategorien. 
    - Når du velger **Lim inn før**, limes kategorien som flyttes inn før den eksisterende kategorien.
    - Når du velger skjemaet, legges kategorien som flyttes til som siste kategori i skjemaet. Handlingen **Lim inn før** gjelder ikke og er derfor ikke tilgjengelig i dette tilfellet.
6. Gjenta trinn 2-5 ovenfor hvis du vil flytte flere kategorier.
7. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

## <a name="delete-tabs-on-a-form"></a>Slette kategorier i et skjema
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](create-and-edit-forms.md#create-a-form) eller [Redigere et skjema](create-and-edit-forms.md#edit-a-form)
2. I skjemaforhåndsvisningen velger du kategorien du vil slette fra skjemaet. 
3. Velg **Slette** på kommandolinjen.
4. Gjenta trinn 2-3 ovenfor hvis du vil slette flere kategorier.
4. Velg **Lagre** på kommandolinjen for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for brukere. 

    > [!NOTE]
    >   - Kategorier kan bare slettes fra hovedskjemaer. Mer informasjon: [Skjematyper](types-forms.md)
    >   - Hvis du sletter en kategori ved en feil, kan du velge **Angre** på kommandolinjen for å tilbakestille skjemaet til forrige tilstand. 
    >   - Du kan ikke slette en kategori som har inndelinger med nødvendige eller låste felt. 
    >   - Du kan ikke slette en kategori som har låste inndelinger. 
    >   - Et skjema må ha minst én kategori. Du kan ikke slette en kategori som er den siste kategorien i skjemaet. 

### <a name="see-also"></a>Se også
[Oversikt over den modelldrevne skjemautformingen](form-designer-overview.md)  
[Opprette eller redigere skjemaer ved hjelp av skjemautforming](create-and-edit-forms.md)  
[Legge til, flytte eller slette felt i et skjema ved hjelp av skjemautformingen.](add-move-or-delete-fields-on-form.md)  
[Legge til, flytte eller slette inndelinger i et skjema ved hjelp av skjemautformingen](add-move-or-delete-sections-on-form.md)  
[Egenskaper som er tilgjengelige i skjemautformingen](form-designer-properties.md)  
[Bruke trevisningen i skjemautformingen](using-tree-view-on-form.md)  
[Opprette og rediger felt](../common-data-service/create-edit-field-portal.md) 
