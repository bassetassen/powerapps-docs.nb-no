---
title: Opprette eller redigere hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter eller redigerer et hovedskjema
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
ms.assetid: <needs new guid>
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-a-model-driven-app-main-form-for-an-entity"></a>Opprette eller redigere et hovedskjema for modelldrevet app for en enhet 

I dette emnet skal du lære hvordan du oppretter eller redigerer et hovedskjema for en enhet.

Når du oppretter et nytt skjema for en enhet, er skjematypen Hovedskjema. Når det nye skjemaet åpnes, er det identisk med skjemaet med navnet Informasjon. Du kan legge til eller redigere felt, inndelinger, kategorier, navigasjon og egenskaper som er tilknyttet skjemaet, og deretter lagre skjemaet.

Hvert hovedskjema består av én eller flere kategorier. Hver kategori kan ha én eller flere deler. Hver del inneholder ett eller flere felt eller IFRAME-elementer. Hvis du vil basere det nye skjemaet på et eksisterende, kan du klone et skjema. 

Sørg for at du har sikkerhetsrollen som systemansvarlig eller systemtilpasser eller tilsvarende tillatelser for å utføre denne oppgaven.

## <a name="how-to-create-or-edit-a-main-form"></a>Opprette eller redigere et hovedskjema
  
1.   Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).


> [!IMPORTANT]
> "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien. 

3. Hvis du vil opprette et nytt hovedskjema, velger du **Legg til skjema** på verktøylinjen > **Hovedskjema**.  
    \-ELLER- Hvis du vil redigere et eksisterende hovedskjema, velger du et skjema av **typen** **Hoved**.
  
3.  Endre skjemautformingen på følgende måter, etter behov:
    -   Legge en kategori i et skjema
    -   Legge til en del i et skjema
    -   Legge til et felt i et skjema
    -   Legge til eller redigere en skjema-IFRAME
    -   Legge til eller redigere et delrutenett i et skjema
    -   Legge til eller redigere en skjemawebressurs
    -   Legge til eller redigere skjemanavigasjon for relaterte enheter
    -   Redigere skjematopptekster og -bunntekster
    -   Fjerne et kategoriinndelingsfelt eller en IFRAME
    -   Aktivere eller deaktivere skjemahjelperen
    
4.  Rediger egenskapene for deler av skjemaet etter behov:
    -   Redigere skjemaegenskaper
    -   Redigere egenskaper for skjemafelt
    -   Redigere egenskaper for kategori
    -   Redigere egenskaper for del

5.  Legg til hendelsesskript etter behov. 

6.  Avgjør hvilke sikkerhetsroller som skal kunne se skjemaet. Mer informasjon: [Tilordne sikkerhetsroller til et skjema](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)

7.  Forhåndsvis hovedskjemaet og prøv ut hvordan hendelser fungerer:
    - Velg **Forhåndsvisning** i kategorien **Hjem**, og velg deretter **Opprett skjema**, **Oppdater skjema** eller **Skrivebeskyttet skjema**.
    - Velg **Lukk** på **Fil**-menyen for å lukke Forhåndsvisning-skjemaet.

8.  Når redigering av skjemaet er fullført, velger du **Lagre som**, skriver inn et navn på skjemaet, og velger deretter **OK**.

9.  Når du er ferdig med tilpassingene, publiserer du dem:
    -   Hvis du vil publisere tilpassinger for bare komponenten du redigerer, kan du klikke enheten du har arbeidet med, under **Komponenter**, og deretter klikke **Publiser**.
    -   Hvis du vil publisere tilpassinger for alle upubliserte komponenter samtidig, klikker du **Enheter** under **Komponenter**, og klikker deretter **Publiser alle tilpassinger** på kommandolinjen.
    
 
### <a name="next-steps"></a>Neste trinn  
[Oversikt over brukergrensesnittet i skjemaredigeringsprogrammet](form-editor-user-interface-legacy.md)
 
