---
title: Legge til skjemanavigasjon for modelldrevne apper for relaterte enheter i PowerApps | MicrosoftDocs
description: Lær hvordan du legger til skjemanavigasjon for relaterte enheter
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: b4098c96-bce1-4f57-804f-8694e6254e81
caps.latest.revision: 15
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-model-driven-app-form-navigation-for-related-entities"></a>Legge til skjemanavigasjon for modelldrevne apper for relaterte enheter

I dette emnet bruker du skjemanavigasjonsruten som brukes for å legge til koblinger i relaterte enheter. Når en appbruker klikker en av koblingene i en oppføring, vises den tilknyttede visningen for enheten.   
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

  
    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien. 
  
3.  I listen åpner du et skjema av typen **Hoved** for å redigere det.  
  
4.  Hvis du vil legge til en relatert enhet, velger du **Navigasjon** i **Velg**-gruppen i kategorien **Hjem**.  
  
     **Relasjonsutforsker**-ruten vise til høyre i skjemaredigeringsprogrammet.  
  
5.  Velg ett av følgende alternativer i **Filter**-listen i **Relasjonsutforsker**-ruten:  
  
    - **Tilgjengelige relasjoner**. Viser en liste over alle enheter som kan relateres til enheten som skjemaet er tilknyttet.  
  
    - **N:1-relasjoner**. Viser en liste over alle enheter som kan relateres i en N:1-relasjon til enheten som skjemaet er tilknyttet.  
  
    - **N:N-relasjoner**. Viser en liste over alle enheter som kan relateres i en N:N-relasjon til enheten som skjemaet er tilknyttet.  
  
    > [!NOTE]
    >  Hvis ingen relaterte enheter vises i **Relasjonsutforsker**-ruten, kan du ikke opprette en kobling i skjemaet til en relatert enhet.  
  
6.  Velg den relatert enheten du vil koble til, dra den til navigasjonsruten, og slipp den deretter der du vil den skal vises.  
  
    > [!TIP]
    >  Du kan også opprette en ny relasjon ved å velge **Ny 1:N** eller **Ny N:N** i **Relasjonsutforsker**-ruten.   
  
7. Hvis du vil redigere egenskapene for denne eller andre relaterte enhetskoblinger i navigasjonsruten, velger du koblinger og deretter **Endre egenskaper** i kategorien **Hjem**.  
  
8. Skriv inn en ny visningsetikett i kategorien **Visning** i dialogboksen **Relasjonsegenskaper**.  
  
9. Velg **Rediger** i kategorien **Navn** for å vise eller redigere detaljene som er tilknyttet relasjonsoppføringen.  
  
10. Velg **OK**.  
  
11. Forhåndsvis hovedskjemaet og prøv ut hvordan hendelser fungerer:  
  
    1.  Velg **Forhåndsvisning** i kategorien **Hjem**, og velg deretter **Opprett skjema**, **Oppdater skjema** eller **Skrivebeskyttet skjema**.  
  
    2.  Velg **Lukk** på **Fil**-menyen for å lukke **Forhåndsvisning**-skjemaet.  
  
12. Når du ferdig med å redigere skjemaet, velger du **Lagre og lukk** for å lukke skjemaet.  
  
13. Når du er ferdig med tilpassingene, publiserer du dem:  
  
    -   Hvis du vil publisere tilpassinger for bare komponenten som du redigerer, kan du velge enheten du har arbeidet med, i navigasjonsruten, og deretter velge **Publiser**.  
  
    -   Hvis du vil publisere tilpassinger for alle upubliserte komponenter samtidig, velger du **Enheter** i navigasjonsruten, og velger deretter **Publiser alle tilpassinger** på kommandolinjen.  
  
> [!NOTE]
> Installasjon av løsninger eller publisering av tilpassinger kan forstyrre den ordinære driften av systemet. Vi anbefaler at du importerer løsninger på tidspunkt der det i minst mulig grad vil forstyrre brukerne.
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette og redigere enhetsrelasjoner for Common Data Service](../common-data-service/create-edit-entity-relationships.md)
