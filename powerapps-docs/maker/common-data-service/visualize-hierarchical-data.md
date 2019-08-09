---
title: Visualisere hierarkiske data med modelldrevne apper | MicrosoftDocs
description: Lær hvordan du spør etter og visualiserer hierarkisk relaterte data
ms.custom: ''
ms.date: 05/28/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="visualize-hierarchical-data-with-model-driven-apps"></a>Visualisere hierarkiske data med modelldrevne apper

Når en enhet er konfigurert til å ha en hierarkisk selvrefererende relasjon, kan du konfigurere visualiseringer ved hjelp av dette hierarkiet. Mer informasjon: [Definere og spørre etter hierarkisk relaterte data](../common-data-service/define-query-hierarchical-data.md)

Enheter som har tilgjengelige visualiseringer som standard, omfatter [Forretningsforbindelse](/powerapps/developer/common-data-service/reference/entities/account), [Posisjon](/powerapps/developer/common-data-service/reference/entities/position) og [Bruker](/powerapps/developer/common-data-service/reference/entities/systemuser). I rutenettvisningen for disse enhetene kan du se ikonene for hierarkidiagrammet til venstre for navnet på oppføringen. Hierarkiikonet er ikke tilgjengelig for alle oppføringer som standard. Ikonet vises for relaterte oppføringer ved hjelp av den hierarkiske relasjonen.  
> [!div class="mx-imgBorder"] 
> ![Vis hierarki-knappen](media/view-hierarchy-button.png)  
  
 Hvis du velger hierarkiikonet, kan du vise hierarkiet, med trevisningen til venstre og rutevisningen til høyre, som vist nedenfor:  
  
> [!div class="mx-imgBorder"] 
> ![Tre- og flisvisning i hierarki](media/tree-view-and-tile-view-in-hierarchy.png)  
  
 Noen få andre enheter kan aktiveres for et hierarki. Disse enhetene omfatter [Kontakt](/powerapps/developer/common-data-service/reference/entities/contact) og [Team](/powerapps/developer/common-data-service/reference/entities/team). Alle egendefinerte enheter kan aktiveres for et hierarki.  
  
Viktig å huske når du lager visualiseringer:  
  
- Bare én selvrefererende relasjon av typen (1:N) per enhet kan angis som hierarkisk. I en selvrefererende relasjon må hovedenheten og den relaterte enheten være av samme type.  
- Et hierarki eller en visualisering er basert på bare én enhet. Du kan vise hierarkiet for forretningsforbindelser med forretningsforbindelser på flere nivåer, men du kan ikke vise forretningsforbindelser og kontakter i samme hierarkivisualisering. 
- Maksimalt antall felt som kan vises i en flis, er fire. Hvis du legger til flere felt i hurtigskjemaet som brukes for rutevisningen, vises bare de første fire feltene. 

## <a name="hierarchy-settings"></a>Hierarkiinnstillinger

Hvis du vil aktivere visualiseringer for et hierarki, må du koble hierarkiet til et hurtigvisningsskjema. Dette kan bare gjøres i løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Innstillingene for hierarkiet er knyttet til en enhet i løsningsutforskeren. 

1. Når du [viser enheter](../common-data-service/create-edit-entities-solution-explorer.md#view-entities), velger du **Hierarkiinnstillinger**.
2. Hvis det allerede finnes en hierarkiinnstilling, kan du redigere den. Hvis ikke kan du klikke **Ny** for å opprette en ny.
    
    > [!NOTE]
    > Hvis det ikke finnes hierarkiinnstillinger, kan ikke enheten ha et hierarki konfigurert.
    >Det kan bare finnes én hierarkiinnstilling. 

1. Angi dataene i følgende felt:

|Felt|Beskrivelse|
|--|--|
|**Navn**|*Obligatorisk.* Legg til et unikt navn for hierarkiinnstillingene. Dette er vanligvis bare navnet på enheten. Denne verdien inkluderer tilpassingsprefikset for løsningsutgiveren.|
|**Standard hurtigvisningsskjema**|*Obligatorisk.* Velg fra et eksisterende hurtigvisningsskjema, eller velg **Opprett ny** for å åpne redigeringsprogrammet for hurtigvisningsskjemaer for å opprette et nytt.|
|**Hierarkisk relasjon**|*Obligatorisk.* Hvis en hierarkisk relasjon allerede er definert for enheten, blir verdien angitt her. Hvis det ikke finnes en verdi, velger du **Merk en relasjon som aktivert for hierarkier** for å åpne en dialogboks for å velge en av de tilgjengelige selvrefererende relasjonene.|
|**Beskrivelse**|Ta med en beskrivelse av formålet for dette hierarkiet, slik at personer som senere tilpasser systemet, kan forstå hvorfor dette ble gjort.|
    

De samme hierarkiske innstillingene for visualisering angis én gang, men gjelder både for webklienter og mobile klienter. På nettbrett gjengis visuelle effekter i et endret format som passer for den mindre formfaktoren. Komponentene som kan tilpasses, som kreves for hierarkisk visualisering, er løsningsavhengige, og kan derfor transporteres mellom organisasjoner som andre tilpassinger. Du kan konfigurere attributtene som vises i visualiseringen, ved å tilpasse et hurtigskjema ved hjelp av skjemaredigeringsprogrammet.
  
## <a name="visualization-walk-through"></a>Gjennomgang av visualisering

La oss se på et eksempel som viser hvordan en visualisering for en egendefinert enhet lages. Vi har opprettet en egendefinert enhet kalt `new_Widget`, opprettet en selvreferensiell relasjon av typen (1:N) `new_new_widget_new_widget` og merket den som hierarkisk, som vist her:  
  
![Relasjonsdefinisjon for kontrollprogram](media/widget-relationship-definition.png)  
  
I rutenettvisningen **Hierarkiinnstillinger** valgte vi deretter den hierarkiske relasjonen `new_new_widget_new_widget`. Vi fylte ut de obligatoriske feltene i skjemaet. Hvis du ennå ikke har merket (1:N)-relasjonen som hierarkisk, tar koblingen i skjemaet deg tilbake til skjemaet for relasjonsdefinisjon der du kan merke relasjonen som hierarkisk.  

> [!IMPORTANT]
> Hver enhet kan bare ha én hierarkisk relasjon om gangen. Hvis dette endres til en annen selvrefererende relasjon, kan det få konsekvenser. Mer informasjon: [Definere hierarkiske data](../common-data-service/define-query-hierarchical-data.md#define-hierarchical-data)

> [!div class="mx-imgBorder"] 
> ![Hierarkiinnstillinger](media/hierarchy-settings.png)  
  
For **hurtigvisningsskjemaet** opprettet vi et hurtigskjema med navnet **Widget Hierarchy Tile Form**. I dette skjemaet la vi til fire felt som skal vises i hver flis.  

> [!div class="mx-imgBorder"] 
> ![Opprett hurtigskjema for kontrollprogram](media/create-quickform.png)  
  
Da vi var ferdig med oppsettet, opprettet vi to poster: *Standard Widget* og *Premium Widget*. Etter at Premium Widget ble angitt som overordnet for Standard Widget ved hjelp av oppslagsfeltet, viste rutenettvisningen for `new_Widget` hierarkiikonene som vist nedenfor:  

> [!div class="mx-imgBorder"] 
> ![Kontrollprogrammets hierarkirutenett](media/widget-hierarchy-grid.png)  
  
> [!NOTE]
>  Hierarkiikonene vises ikke i rutenettvisningen for oppføringer før oppføringene er relatert ved hjelp av den hierarkiske relasjonen.  
  
Hvis du velger hierarkiikonet, vises `new_Widget`-hierarkiet med trevisningen til venstre og rutevisningen til høyre med to oppføringer. Hver flis inneholder fire felt som vi anga i **Widget Hierarchy Tile Form**.  

> [!div class="mx-imgBorder"] 
> ![Kontrollprogrammets tre- og flisvisninger](media/widget-tree-tiles.png)  

Basert på behovet ditt kan du velge mellom en trevisning, som viser hele hierarkiet, og en rutevisning, som viser en mindre del av hierarkiet. Begge visningene vises side ved side. Du kan utforske hierarkiet ved å vise og skjule hierarkitreet. 

### <a name="see-also"></a>Se også 

[Definer og spør etter hierarkisk relaterte data](../common-data-service/define-query-hierarchical-data.md)<br />
[Video: Hierarkivisualisering](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
