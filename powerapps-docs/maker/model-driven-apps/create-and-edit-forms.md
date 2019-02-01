---
title: Opprette og redigere skjemaer ved hjelp av den modelldrevne skjemautformingen | MicrosoftDocs
ms.custom: ''
ms.date: 12/13/2018
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

# <a name="create-and-edit-forms-using-the-form-designer"></a>Opprette og redigere skjemaer ved hjelp av skjemautforming 
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Bruk den nye skjemautformingen til å opprette og utforme skjemaer for modelldrevne apper.

> [!IMPORTANT]
> Den nye modelldrevne skjemautformingen støtter for øyeblikket bare oppretting og redigering av hovedskjemaer. Mer informasjon: [Skjematyper](types-forms.md)

## <a name="create-a-form"></a>Opprette et skjema 
1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). 
2. Utvid **Data** i den venstre navigasjonsruten, og velg deretter **Enheter**. 
3. Velg en enhet, for eksempel forretningsforbindelsesenheten, og velg deretter kategorien **Skjemaer**. 
4. Velg **Legg til skjema**, og velg deretter **Main-skjemaet (forhåndsvisning)**.     
    Innholdet i det nye skjemaet fylles ut med den eksisterende hovedskjemadefinisjonen. Hvis det finnes flere hovedskjemaer, brukes skjemaet øverst i listen i skjemarekkefølgen til å fylle ut det nye skjemaet. 
5. Velg **Lagre** for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for appbrukere.  

## <a name="edit-a-form"></a>Redigere et skjema 
1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). 
2. Velg **Data** i den venstre navigasjonsruten, og velg deretter **Enheter**. 
3. Velg en enhet, for eksempel forretningsforbindelsesenheten, og velg deretter kategorien **Skjemaer**.
4. Velg skjemaet du vil redigere, og velg deretter **Rediger skjema (forhåndsvisning)**.  
   Du kan også velge **...** ved siden av skjemaet du vil redigere, og deretter velge **Rediger skjema (forhåndsvisning)**. 
5. Velg **Lagre** for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for appbrukere. 

## <a name="add-and-remove-fields"></a>Legge til og fjerne felt 
Hvis du vil legge til eller fjerne felt fra et skjema, kan du bruke Felt-ruten. Med Felt-ruten kan du søke og filtrere, slik at du raskt finner feltene. Den inkluderer også muligheten til å vise bare ubrukte felt. 

### <a name="add-a-field"></a>Legge til et felt
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](#create-a-form) og [Redigere et skjema](#edit-a-form)
2. Velg et annet eksisterende felt eller en inndeling i skjemaforhåndsvisningen. 
    - Når du velger et eksisterende felt, legges det nye feltet til under det eksisterende feltet. 
    - Når du velger en inndeling, legges det nye feltet til på en tilgjengelig plass, slik at felt distribueres jevnt på kolonnene. 
3. Velg **Legg til felt**, eller velg **Felt** i den venstre ruten.  
   Felt-ruten er åpen som standard når skjemautformingen åpnes. 
4. Søk, filtrer og bla for å finne feltet du vil legge til, i ruten **Felt**-ruten. 
   Hvis du ikke finner et felt, kan det hende at det allerede finnes i skjemaet. Fjern merket for **Vis bare ubrukte felt** for å vise alle feltene, inkludert de som allerede er lagt til i skjemaet. 
5. I **Felt**-ruten velger du et felt for å legge det til i skjemaet. <br />
   Du kan også velge **...** ved siden av feltet du vil ha, og deretter velge **Legg til i valgt inndeling**. 
6. Velg **Lagre** for å lagre skjemaet, eller velg **Publiser** hvis du vil lagre og gjøre endringene synlige for sluttbrukere. 

### <a name="remove-a-field"></a>Fjerne et felt
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](#create-a-form) og [Redigere et skjema](#edit-a-form)
2. I skjemaforhåndsvisningen av velger du feltet du vil fjerne fra skjemaet. 
3. Velg **Slett**. <br />
4. Velg **Lagre**. 

    > [!NOTE]
    >   -  Hvis du fjerner et felt ved en feil, kan du velge **Angre** for å tilbakestille handlingen. 
    >   -  Du kan ikke fjerne et felt som er nødvendig eller låst. 

## <a name="add-and-remove-tabs-and-sections"></a>Legge til og fjerne kategorier og inndelinger 
Hvis du vil legge til eller fjerne en kategori eller inndeling i et skjema, bruker du Oppsett-ruten. 

### <a name="add-a-tab"></a>Legge til en kategori
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](#create-a-form) og [Redigere et skjema](#edit-a-form) 
2. Velg en annen eksisterende kategori eller skjemaet i skjemaforhåndsvisningen. 
    - Når du velger en eksisterende kategori, legges den nye kategorien til til høyre i eksisterende kategorien. 
    - Når du velger skjemaet, legges den nye kategorien til som kategorien lengst til høyre i skjemaet. 
3. Velg **Legg til kontroll**, eller velg **Oppsett** i den venstre ruten.  
4. I **Oppsett**-ruten velger du en kategorikontroll, for eksempel **tokolonners kategori**, for å legge den til i skjemaet. <br />
   Du kan også velge **...** ved siden av kategorikontroll du vil ha, og deretter velge **Legg til i skjema**.  
5. Velg **Lagre**. 


### <a name="remove-a-tab"></a>Fjerne en kategori
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](#create-a-form) og [Redigere et skjema](#edit-a-form)
2. I skjemaforhåndsvisningen velger du kategorien du vil slette, og deretter velger du **Slett**. 
3. Velg **Lagre**. 
    > [!NOTE]
    >    - Når du sletter en kategori ved en feil, kan du velge **Angre** for å slette handlingen. 
    >     - Et skjema må ha minst én kategori. Du kan ikke slette en kategori som er eneste kategori i skjemaet. 
    >    - Du kan ikke slette en kategori som har låste inndelinger. 
    >    - Du kan ikke slette en kategori som har inndelinger med nødvendige eller låste felt. 

### <a name="add-a-section"></a>Legge til en inndeling 
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](#create-a-form) og [Redigere et skjema](#edit-a-form)
2. Velg en annen eksisterende inndeling eller en kategori i skjemaforhåndsvisningen. 
    - Når du velger en eksisterende inndeling, legges den nye inndelingen til under den eksisterende inndelingen. 
    - Hvis du velger en kategori, legges den nye inndelingen til nederst i den første kolonnen i kategorien. 
3. Velg **Legg til kontroll**, eller velg **Oppsett** i den venstre ruten.
4. I **Oppsett**-ruten velger du en inndelingskontroll for å legge den til i skjemaet. <br />
   Du kan også velge **...** ved siden av inndelingskontrollen du vil ha, og deretter velge **Legg til i valgt kategori**.      
5. Velg **Lagre**. 
 

### <a name="delete-a-section"></a>Slette en inndeling 
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](#create-a-form) og [Redigere et skjema](#edit-a-form) 
2. I skjemaforhåndsvisningen velger du inndelingen du vil slette, og deretter velger du **Slett**.  
3. Velg **Lagre**. 
    > [!NOTE]
    >    - Hvis du sletter en inndeling ved en feil, kan du velge **Angre** for å slette handlingen. 
    >    - En kategori må ha minst én inndeling i hver kolonne.  
    >    - Du kan ikke slette en inndeling hvis det er den eneste i kategorikolonnen. 
    >    - Du kan ikke slette en inndeling som er låst. 
    >    - Du kan ikke slette en inndeling som har nødvendige eller låste felt. 
 
## <a name="use-the-tree-view"></a>Bruke trevisningen 
I trevisningsruten vises et visuelt hierarki over kontrollene og feltene i skjemaet. Ikonene i trevisningen hjelper deg med raskt å identifisere typen felt eller kontroll. 

Du kan også bruke trevisningen til å velge felt og kontrolller som finnes i skjemaet. Trevisningen er nyttig når du vil velge elementer som er skjulte og derfor ikke vises i skjemaforhåndsvisningen. 

Du kan vise eller skjule nodene i trevisningen for å vise eller skjule elementer i en node. Når du velger et element i trevisningen, merkes det i skjemaforhåndsvisningen, og egenskapsruten viser egenskapene for elementet. 

   ![Trevisning](media/tree-view.png)

### <a name="open-the-tree-view"></a>Åpne trevisningen 
1. Åpne skjemautformingen for å opprette eller redigere et skjema. Mer informasjon: [Opprette et skjema](#create-a-form) og [Redigere et skjema](#edit-a-form)  
2. Velg **Trevisning** i venstre rute.

## <a name="see-also"></a>Se også
[Oversikt over den modelldrevne skjemautformingen](form-designer-overview.md) <br />
[Opprette og rediger felt](../common-data-service/create-edit-field-portal.md)
