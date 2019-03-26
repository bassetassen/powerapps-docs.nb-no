---
title: Opprette eller redigere hurtigopprettingsskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter eller redigerer et hurtigopprettingsskjema
ms.custom: ''
ms.date: 01/25/2019
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
ms.assetid: 68ca9059-cc5a-45e7-88bd-cc57186bbb48
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-quick-create-forms-for-a-streamlined-data-entry-experience"></a>Opprette eller redigere hurtigopprettingsskjemaer for modelldrevne apper for en strømlinjeformet dataregistreringsopplevelse

I dette emnet kan du opprette og redigere et hurtigopprettingsskjema.

 Med hurtigopprettingsskjemaer har appen en strømlinjeformet dataregistreringsopplevelse med full støtte for logikk som defineres med skjemaskript og forretningsregler. I en modelldrevet PowerApps-app vises hurtigopprettingsskjemaer når du velger **Opprett**-knappen i navigasjonsfeltet, eller når du velger **+ Ny** når du oppretter en ny post fra et oppslag eller delrutenett.
  
 Mobilappene for Dynamics 365 customer engagement bruker hurtigopprettingsskjemaer for å opprette nye oppføringer. Hvis et hurtigopprettingsskjema allerede er konfigurert for en enhet, bruker mobilappene dette skjemaet. Hvis en enhet ikke har et hurtigopprettingsskjema, genererer PowerApps et hurtigopprettingsskjema for å opprette poster i mobilappene basert på definisjonen av hovedskjemaet.  
  
<a name="BKMK_QuickCreateFormEntities"></a>   
## <a name="entities-with-quick-create-forms"></a>Enheter med hurtigopprettingsskjemaer  
 Bare følgende systemenheter har som standard hurtigopprettingsskjemaer.  
  
|||||  
|-|-|-|-|  
|Forretningsforbindelse|Kampanjesvar|Sak|Konkurrent|  
|Kontakt|Emne|Salgsmulighet||  
  
Selv om du kan opprette hurtigopprettingsskjemaer for systemaktivitetsenheter, støtter de ikke hurtigopprettingsskjemaer, med unntak av avtaleenheten. Med utgivelse av Dynamics 365, versjon 9.0, inneholder avtaleenheten et hurtigopprettingsskjemaet for bruk med Enhetlig grensesnitt. For øyeblikket støttes ikke alternativet for å deaktivere hurtigopprettingsskjemaet for avtaleenheten. Du kan aktivere støtte for disse skjemaene for alle andre [oppdaterte enheter](create-design-forms.md) og alle egendefinerte enheter, ved å velge **Tillat hurtigoppretting** i enhetsdefinisjonen og opprette et hurtigopprettingsskjema for enheten. 

Du kan aktivere støtte for hurtigopprettingsskjemaer for egendefinerte aktivitetsenheter, og du kan opprette hurtigopprettingsskjemaer for disse enhetene. Hurtigopprettingsskjemaet for egendefinerte aktivitetsenheter brukes imidlertid ikke når brukere velger **Opprett** i navigasjonsfeltet. Disse hurtigopprettingsskjemaene kan bare brukes når noen legger til en ny oppføring for et delrutenett som viser den egendefinerte aktivitetsenheten.  
  
<a name="BKMK_CreateQuickCreate"></a>   
## <a name="create-a-quick-create-form"></a>Opprette et hurtigopprettingsskjema  
 Selv om du kan definere flere hurtigopprettingsskjemaer, er det bare ett hurtigopprettingsskjema som kan brukes av alle. Skjemarekkefølgen brukes til å angi skjemaet som alle skal bruke. Hurtigopprettingsskjemaer kan ikke tilordnes sikkerhetsroller, og de gjør det ikke mulig for brukeren å bytte skjemaer.  
  
> [!NOTE]
>  - Enheten må ha alternativet **Tillat hurtigoppretting** aktivert for at hurtigopprettingsskjemaet skal vises. 
>  - Noen felt, for eksempel feltet CREATEDON, er ikke tilgjengelige for å legge til et hurtigopprettingsskjema.  
  
### <a name="how-to-create-a-quick-create-form"></a>Opprette et hurtigopprettingsskjema  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).


> [!IMPORTANT]
> "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  

3.  Velg **Legg til skjema** > **Hurtigopprettingsskjema** på verktøylinjen.  
  
4.  Dra et felt fra **Feltutforsker** inn til delene i skjemaet, i skjemautformingen.  
  
5.  Velg **Lagre** når du er ferdig.  
  
6.  Velg **Publiser** for å se det nye skjemaet i programmet.  
  
<a name="BKMK_EditQuickCreate"></a>   
## <a name="edit-a-quick-create-form"></a>Redigere et hurtigopprettingsskjema  
 Hurtigopprettingsskjemaer støtter skjemaskript og forretningsregler, men de har et annet formål enn i hovedskjemaer, og de støtter ikke alle funksjonene som er i hovedskjemaer. Hurtigopprettingsskjemaer har alltid én del med tre kolonner. Du kan ikke legge til flere deler eller kolonner.  
  
 Følgende kontroller kan ikke legges til i hurtigopprettingsskjemaer:  
  
-   Delrutenett  
  
-   Hurtigvisningsskjemaer  
  
-   Webressurser  
  
-   iFrames  
  
-   Merknader  
  
-   Bing-kart  
  
Hvis du legger til et sammensatt felt i et hurtigopprettingsskjema, vises det som separate felt.  
  
### <a name="to-edit-a-quick-create-form"></a>Slik redigerer du et hurtigopprettingsskjema:  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

> [!IMPORTANT]
> "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).    
  
2. Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.    

3. Velg et skjema i skjemalisten der **Type** skjema er **Hurtigoppretting**.  
  
3.  Dra et felt fra **Feltutforsker** inn til delene i skjemaet.  
  
     Se [Konfigurere hendelsesbehandlinger](configure-event-handlers-legacy.md) hvis du vil ha informasjon om hvordan du redigerer hendelsesbehandling for skjemaskript.  
  
4.  Velg **Lagre** når du er ferdig.  
  
5.  Velg **Publiser** for å se det endrede skjemaet i programmet.  
  
### <a name="next-steps"></a>Neste trinn  
[Oversikt over brukergrensesnittet i skjemaredigeringsprogrammet](form-editor-user-interface-legacy.md)
