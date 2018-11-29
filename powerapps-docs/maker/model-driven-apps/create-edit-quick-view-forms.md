---
title: Opprette eller redigere hurtigvisningsskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter eller redigerer et hurtigvisningsskjema
ms.custom: ''
ms.date: 05/23/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 9b101734-cc11-4d05-bd45-eb611eae9931
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-model-driven-app-quick-view-form-to-view-information-about-a-related-entity"></a>Opprette et hurtigvisningsskjema for modelldrevne apper for å vise informasjon om en relatert enhet

I dette emnet skal du lære hvordan du oppretter et hurtigvisningsskjema og hvordan du legger til en hurtigvisningskontroll i et hovedskjema. 

Et hurtigvisningsskjema kan legges til i et annet skjema som en hurtigvisningskontroll. Det gir en mal for visning av informasjon om en relatert enhetsoppføring i et skjema for en annen enhetsoppføring. Dette betyr at appbrukere ikke trenger å gå til en annen oppføring for å se informasjonen de trenger for å utføre jobben.  
  
 Hurtigvisningskontroller er knyttet til et oppslagsfelt som er inkludert i et skjema. Hvis verdien i oppslagsfeltet ikke er angitt, vises ikke hurtigvisningskontrollen. Data i hurtigvisningskontroller kan ikke redigeres, og hurtigvisningsskjemaer støtter ikke skjemaskript.  
  
 Siden hurtigvisningsskjemaer vises ved hjelp av en hurtigvisningskontroll i et skjema, inneholder de ikke topptekst, bunntekst eller navigasjonsområder. Sikkerhetsroller kan ikke tilordnes til hurtigvisningsskjemaer, og de kan ikke aktiveres eller deaktiveres.  
  
<a name="BKMK_CreateQFV"></a>   
## <a name="create-a-quick-view-form"></a>Opprette et hurtigvisningsskjema  
 Du lager hurtigvisningsskjemaer ved å bruke skjemaredigeringsprogrammet omtrent slik som når du lager andre skjemaer. Hurtigvisningsskjemaer er skrivebeskyttet. Du kan bruke dem til å lage skjemaer som bare skal leses.  
  
1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  


    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2. Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien. 
  
3. Velg **Legg til skjema** > **Hurtigvisningsskjema** på verktøylinjen.  
  
4. Velg **Skjemaegenskaper** på verktøylinjen for skjemaredigeringsprogrammet.  
  
5. Skriv inn et **Skjemanavn** og en **Beskrivelse** i dialogboksen **Skjemaegenskaper** for å skille dette hurtigvisningsskjemaet fra andre. Velg **OK** for å lukke dialogboksen **Skjemaegenskaper**.  
  
6. Dra et felt fra **Feltutforsker** inn til delen i skjemaet, i skjemautformingen. 
  
    > [!IMPORTANT]
    >  Hvis du legger til et felt og velger **Feltkrav** > **Nødvendig for selskapet** og deretter lagre det, vil du ikke kunne slette feltet.  
  
7. Velg **Lagre** for å lagre skjemaet og lukke skjemaredigeringsprogrammet.  

8. Velg **Publiser** for å se det nye skjemaet i programmet.
  
<a name="BKMK_EditQVF"></a>   
## <a name="edit-a-quick-view-form"></a>Redigere et hurtigvisningsskjema  
 Hurtigvisningsskjemaer har et forenklet oppsett fordi de er utformet for å vises i en skjemadel. Bare én kategori med én kolonne er tilgjengelig. Du kan legge til ytterligere deler, felt, delrutenett og avstandsstykker med bare én kolonne.   
  
> [!NOTE]
>  Du kan ikke slette et felt som er **Nødvendig for selskapet**. Du får denne meldingen hvis du prøver å slette feltet: "Feltet du prøver å fjerne, er nødvendig for systemet eller selskapet." Hvis du ikke vil ha feltet i skjemaet, må du slette hele skjemaet og deretter opprett det på nytt.  
  
 Når du redigerer et hurtigvisningsskjema, må du publisere endringene for at de skal vises i programmet.  
  
<a name="BKMK_AddQVF"></a>   
## <a name="add-a-quick-view-control-to-a-main-form"></a>Legge til en hurtigvisningskontroll i et hovedskjema  
 Hurtigvisningsskjemaer kan bare legges til i et hovedskjema der det finnes et oppslagsfelt som er rettet mot enheten for hurtigvisningsskjemaet.  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  

3. Velg et skjema der **Type** er **Hoved**.

4. I skjemautformingen velger du **Sett inn**-kategorien, og velger deretter **Hurtigvisningsskjema** på verktøylinjen.  
  
5.  I dialogboksen **Egenskaper for hurtigvisningskontroll** angir du egenskapene for hurtigvisningskontrollen, for eksempel **Navn**, **Etikett** og **Hurtigvisningsskjema**. Mer informasjon: [Egenskaper for hurtigvisningskontroll](quick-view-control-properties-legacy.md)  
  
6.  Velg **OK** for å lukke dialogboksen **Egenskaper for hurtigvisningskontroll**.  
  
7.  Velg kategorien **Hjem**, og velg deretter **Publiser** slik at hurtigvisningskontrollen vises i skjemaet.  
  
## <a name="next-steps"></a>Neste trinn   
 [Opprette og utforme skjemaer](create-design-forms.md)   
 [Opprette eller redigere hurtigopprettingsskjemaer](create-edit-quick-create-forms.md)
