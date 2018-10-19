---
title: Visualiser hierarkiske data med modelldrevne apper | MicrosoftDocs
description: Finn ut hvordan du kan spørre og visualisere hierarkisk relaterte data
ms.custom: ''
ms.date: 06/02/2018
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
ms.author: matp
manager: kvivek
ms.openlocfilehash: bed8662d7d9475215df8e92490702b68e36574e2
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696152"
---
# <a name="visualize-hierarchical-data-with-model-driven-apps"></a>Visualiser hierarkiske data med modelldrevne apper

> [!NOTE]
> Hierarkiske datavisualiseringer er tilgjengelig bare for modelldrevne apper som er konfigurert for **Nett**klienten. Visualiseringer er ikke tilgjengelige for **Enhetlig grensesnitt**-klienten. Mer informasjon: [Opprett en modelldrevet app ved hjelp av apputforming](../model-driven-apps/create-edit-app.md)

Når en enhet er konfigurert til å ha en hierarkisk relasjon med selvreferanse, kan du konfigurere visualiseringer ved hjelp av dette hierarkiet. Mer informasjon: [Definer og spør hierarkisk relaterte data](../common-data-service/define-query-hierarchical-data.md)

Enhetene som har visualiseringer tilgjengelig som standard, omfatter [Konto](/powerapps/developer/common-data-service/reference/entities/account), [Posisjon](/powerapps/developer/common-data-service/reference/entities/position) og [Bruker](/powerapps/developer/common-data-service/reference/entities/systemuser). Du kan se ikonet som viser hierarkidiagrammet, i rutenettet over disse enhetene, til venstre for postnavnet. Hierarkiikonet er ikke tilgjengelig for alle postene som standard. Ikonet vises for postene som er relatert ved hjelp av den hierarkiske relasjonen.  
  
 ![Kontoer med hierarki](media/account-list-with-hierarchy.png)  
  
 Hvis du velger hierarkiikonet, kan du vise hierarkiet, med trevisning til venstre og rutevisning til høyre, som vist nedenfor:  
  
 ![Trevisning og rutevisning for kontoen](media/hierachy-security-accounts-tile-view.png)  
  
 Enkelte andre enheter kan være aktivert for et hierarki. Disse enhetene omfatter [Kontakt](/powerapps/developer/common-data-service/reference/entities/contact) og [Team](/powerapps/developer/common-data-service/reference/entities/team). Alle egendefinerte enheter kan aktiveres for et hierarki.  
  
Viktige ting å huske når du oppretter visualiseringer:  
  
- Bare én (1:N)-relasjon med selvreferanse kan angis som hierarkisk per enhet. Den primære enheten og den relaterte enheten må være av samme type i en relasjon med selvreferanse.  
- Et hierarki eller en visualisering er basert på bare én enhet. Du kan vise kontohierarkiet med kontoer på flere nivåer, men du kan ikke vise kontoer og kontakter i samme hierarkivisualisering. 
- Maksimalt antall felt som kan vises i en rute, er fire. Hvis du legger til flere felt i hurtigskjemaet som brukes for rutevisningen, er det bare de første fire feltene som vises. 

## <a name="hierarchy-settings"></a>Hierarkiinnstillinger

Hvis du vil aktivere visualiseringer for et hierarki, må du koble hierarkiet til et hurtigvisningsskjema. Dette kan bare gjøres ved hjelp av løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Hierarkiinnstillingene er knyttet til en enhet i løsningsutforskeren. 

1. Velg **Hierarkiinnstillinger** mens du [viser enheter](../common-data-service/create-edit-entities-solution-explorer.md#view-entities).
2. Hvis det finnes en hierarkiinnstilling, kan du redigere den. Hvis ikke, klikker du på **Ny** for å opprette en ny.
    
    > [!NOTE]
    > Hvis hierarkiinnstillingene ikke finnes, er ikke enheten kvalifisert for konfigurasjon av et hierarki.
    >Det kan bare være én hierarkiinnstilling 

1. Angi dataene i feltene nedenfor:

|Felt|Beskrivelse|
|--|--|
|**Navn**|*Obligatorisk.* Legg til et unikt navn for hierarkiinnstillingene. Dette er vanligvis bare navnet på enheten. Denne verdien omfatter tilpassingsprefikset for løsningsutgiveren.|
|**Standard hurtigvisningsskjema**|*Obligatorisk.* Velg fra et eksisterende hurtigvisningsskjema eller velg **Opprett ny** for å åpne redigeringsprogrammet for hurtigvisningsskjema for å opprette et nytt et.|
|**Hierarkisk relasjon**|*Obligatorisk.* Hvis en hierarkisk relasjon allerede er definert for enheten, angis verdien her. Hvis det ikke finnes en verdi, velger du **Merk en relasjon som aktivert for hierarkier**, for å åpne en dialogboks og velge en av de tilgjengelige relasjonene med selvreferanse.|
|**Beskrivelse**|Ta med en beskrivelse av formålet til hierarkiet, slik at personer som tilpasser systemet i fremtiden, forstår hvorfor dette ble gjort.|
    

Samme hierarkiske innstillinger for visualisering angis én gang, men gjelder for både nett- og mobilklienter. På nettbrett gjengis visualiseringer i et modifisert format som er tilpasset en mindre formfaktor. Tilpassbare komponenter som er obligatoriske for hierarkiske visualiseringer, er løsningsorienterte og kan derfor transporteres mellom organisasjoner som alle andre tilpassinger. Du kan konfigurere attributtene som vises i visualiseringen, ved å tilpasse et hurtigskjema med skjemaredigeringsprogrammet.
  
## <a name="visualization-walk-through"></a>Gjennomgang av visualiseringer

La oss se på et eksempel på å opprette en visualisering for en egendefinert enhet. Vi opprettet en egendefinert enhet som heter `new_Widget`, opprettet en (1:N)-relasjon med selvreferanse `new_new_widget_new_widget` og merket den som hierarkisk, som vist her.  
  
![Relasjonsdefinisjon for kontrollprogram](media/widget-relationship-definition.png)  
  
Deretter valgte vi hierarkisk relasjon for **i rutenettvisningen av**Hierarkiinnstillinger`new_new_widget_new_widget`. Vi har fylt ut de obligatoriske feltene i skjemaet. Hvis du ennå ikke har merket (1:N)-relasjonen som hierarkisk, tar koblingen på skjemaet deg tilbake til relasjonsdefinisjonskjemaet, der du kan merke relasjonen som hierarkisk.  

> [!IMPORTANT]
> Hver enhet kan ha bare én hierarkisk relasjon om gangen. Hvis du endrer dette til en annen relasjon med selvreferanse, kan dette få følger. Mer informasjon: [Definer hierarkiske data](../common-data-service/define-query-hierarchical-data.md#define-hierarchical-data)
  
![Hierarkiinnstillinger](media/hierarchy-settings.png)  
  
Vi opprettet et hurtigskjema som heter **Ruteskjema for kontrollprogramhierarki** for **Hurtigvisningsskjemaet**. I dette skjemaet har vi lagt til fire felt som skal vises i hver rute.  
  
![Opprett hurtigskjema for kontrollprogram](media/create-quickform.png)  
  
Etter at vi fullførte konfigurasjonen, opprettet vi to poster: *Standard-kontrollprogram* og *Premium-kontrollprogram*. Etter å ha gjort Premium-kontrollprogrammet til et Standard-kontrollprogram ved hjelp av oppslagsfeltet, viste rutenettvisningen for `new_Widget` hierarkiikonene som vist nedenfor:  
  
![Hierarkirutenettet for kontrollprogrammet](media/widget-hierarchy-grid.png)  
  
> [!NOTE]
>  Hierarkiikoner vises ikke rutenettvisningen for poster, før postene er relatert ved hjelp av den hierarkiske relasjonen.  
  
Hvis du velger hierarkiikonet, vises `new_Widget`-hierarkiet, med trevisning til venstre og rutevisning til høyre, som viser to poster. Hver rute inneholder fire felt som vi har angitt i **Ruteskjema for kontrollprogramhierarki**.  
  
![Trevisning og rutevisning for kontrollprogrammet](media/widget-tree-tiles.png)  

Basert på behovene dine, kan du velge mellom å bruke trevisning, som viser hele hierarkiet, eller rutevisning, som viser en mindre del av hierarkiet. Begge visningene vises ved siden av hverandre. Du kan utforske et hierarki ved å utvide og redusere et hierarkitre. 

### <a name="see-also"></a>Se også 

[Definer og spør hierarkisk relaterte data](../common-data-service/define-query-hierarchical-data.md)<br />
[Video: Hierarkivisualisering](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)