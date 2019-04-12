---
title: Spørre etter og visualisere hierarkiske data med PowerApps | MicrosoftDocs
description: Lær hvordan du spør etter og visualiserer hierarkisk relaterte data
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="query-and-visualize-hierarchically-related-data"></a>Spør etter og visualiser hierarkisk relaterte data

Du kan få verdifull innsikt i bedriftsdata ved å visualisere hierarkisk relaterte data. Den hierarkiske modelleringen og visualiseringsfunksjonene gir deg mange fordeler:  
  
-   Vise og utforske kompleks hierarkisk informasjon.  
  
-   Vise KPI-er (Key Performance Indicators) i den kontekstavhengige visningen av et hierarki.  
  
-   Visuelt analysere viktig informasjon på Internett og nettbrett.  
  
For enkelte enheter, for eksempel forretningsforbindelse og bruker, følger visualiseringene med. Andre enheter, inkludert egendefinerte enheter, kan aktiveres for et hierarki, og du kan lage visualiseringer for dem. Basert på behovet ditt kan du velge mellom en trevisning, som viser hele hierarkiet, og en rutevisning, som viser en mindre del av hierarkiet. Begge visningene vises side ved side. Du kan utforske hierarkiet ved å vise og skjule hierarkitreet. De samme hierarkiske innstillingene for visualisering angis én gang, men gjelder både for webklienter og mobile klienter. På nettbrett gjengis visuelle effekter i et endret format som passer for den mindre formfaktoren. Komponentene som kan tilpasses, som kreves for hierarkisk visualisering, er løsningsavhengige, og kan derfor transporteres mellom organisasjoner som andre tilpassinger. Du kan konfigurere attributtene som vises i visualiseringen, ved å tilpasse et hurtigskjema ved hjelp av skjemaredigeringsprogrammet. Det er ingen krav om å skrive kode.  
  
<a name="BKMK_Querydata"></a>   
## <a name="query-hierarchical-data"></a>Spørre hierarkiske data  
 I Common Data Service støttes hierarkiske datastrukturer av selvrefererende relasjoner av typen én-til-mange (1:N) for de relaterte oppføringene. Tidligere måtte du spørre iterativt etter de relaterte oppføringene for å vise hierarkiske data. Nå kan du spørre de relaterte dataene som et hierarki, i ett trinn. Du kan spørre etter enhetsoppføringene ved hjelp av logikken **Under** og **Ikke under**. De hierarkiske operatorene **Under** og **Ikke under** vises i Avansert søk og redigeringsprogrammet for arbeidsflyt. Hvis du vil ha mer informasjon om hvordan du bruker disse operatorene, kan du se [Konfigurere arbeidsflyttrinn](/flow/configure-workflow-steps). Hvis du vil ha mer informasjon om avansert søk, kan du se [Opprette, redigere eller lagre et søk i Avansert søk](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search).  
  
 Eksemplene nedenfor viser ulike scenarier for hierarkispørring:  
  
 Spørre forretningsforbindelseshierarki  
  
 ![Spørre etter forretningsforbindelser i forretningsforbindelseshierarkiet](media/query-accounts.png "Spørre etter forretningsforbindelser i forretningsforbindelseshierarkiet")  
  
 Spørre forretningsforbindelseshierarki, inkludert relaterte aktiviteter  
  
 ![Spørre etter forretningsforbindelsens tilknyttede aktiviteter](media/query-account-related-activities.png "Spørre etter forretningsforbindelsens tilknyttede aktiviteter")  
  
 Spørre forretningsforbindelseshierarki, inkludert relaterte salgsmuligheter  
  
 ![Spørre etter forretningsforbindelsens tilknyttede salgsmuligheter](media/query-account-related-opportunities.png "Spørre etter forretningsforbindelsens tilknyttede salgsmuligheter")  
  
 Hvis du vil spørre dataene som et hierarki, må du sette én av enhetens selvrefererende relasjoner av typen én-til-mange (1:N) til hierarkisk. Slik slår du på hierarkiet:  
  
1.  Åpne [løsningsutforskeren](../model-driven-apps/advanced-navigation.md#solution-explorer). 
  
2.  Velg ønsket enhet, velg **1:N-relasjoner**, og velg deretter en relasjon (1:N). 

3.  I **Relasjonsdefinisjon** setter du **Hierarkisk** til **Ja**.  
  
> [!NOTE]
> - Noen av de medfølgende (1:N)-relasjonene kan ikke tilpasses. Dette vil hindre deg i å angi disse relasjonene som hierarkiske.  
> - Du kan angi en hierarkisk relasjon for de selvreferensielle relasjonene for systemet. Dette inkluderer de selvrefererende relasjonene (1:N) av systemtype, for eksempel "contact_master_contact"-forholdet.  
  
<a name="BKMK_Visualizedata"></a>   
## <a name="visualize-hierarchical-data"></a>Visualisere hierarkiske data  
 Systemenheter som har medfølgende visualiseringer, inkluderer: `Account`, `Position`, `Product` og `User`. I rutenettvisningen for disse enhetene kan du se ikonene for hierarkidiagrammet til venstre for navnet på oppføringen. Hierarkiikonet er ikke tilgjengelig for alle oppføringer som standard. Ikonet vises for oppføringer som har en overordnet oppføring, en underordnet oppføring eller begge deler.  
 
 > [!div class="mx-imgBorder"] 
 > ![Aktive forretningsforbindelser](media/cust-hs-active-account.png "Aktive forretningsforbindelser")  
  
 Hvis du velger hierarkiikonet, kan du vise hierarkiet, med trevisningen til venstre og rutevisningen til høyre, som vist nedenfor:  
  
> [!div class="mx-imgBorder"] 
> ![Tre- og flisvisning for forretningsforbindelse](media/hierachy-security-accounts-tile-view.png "Tre- og flisvisning for forretningsforbindelse")  
  
 Det er noen flere medfølgende systemenheter som kan aktiveres for et hierarki. Disse enhetene omfatter `Case`, `Contact`, `Opportunity`, `Order`, `Quote`, `Campaign` og `Team`. Alle egendefinerte enheter kan aktiveres for et hierarki.  
  
> [!TIP]
>  Hvis en enhet kan aktiveres for et hierarki:  
>  I løsningsutforskeren utvider du ønsket enhet. Enhetskomponenten kalt **Hierarkiinnstillinger** vises. Enhetene som ikke kan aktiveres for et hierarki, har ikke denne komponenten, med unntak av enheten Salgsdistrikt i Dynamics 365 Customer Engagement. Selv om **Hierarkiinnstillinger** vises for Salgsdistrikt-enheten, kan ikke enheten aktiveres for et hierarki.  
  
 Viktig å huske når du lager visualiseringer:  
  
-   Bare én selvrefererende relasjon av typen (1:N) per enhet kan angis som hierarkisk. Hovedenheten og den relaterte enheten må være av samme type i denne relasjonen, for eksempel account_parent_account eller new_new_widget_new_widget.  
  
-   For øyeblikket er et hierarki eller en visualisering bare basert på én enhet. Du kan vise hierarkiet for forretningsforbindelser med forretningsforbindelser på flere nivåer, men du kan ikke vise forretningsforbindelser og kontakter i samme hierarkivisualisering.  
  
-   Maksimalt antall felt som kan vises i en flis, er fire. Hvis du legger til flere felt i hurtigskjemaet som brukes for rutevisningen, vises bare de første fire feltene.  
  
### <a name="visualization-example"></a>Eksempel på visualisering  
 La oss se på et eksempel som viser hvordan en visualisering for en egendefinert enhet lages. Vi har opprettet en egendefinert enhet kalt new_Widget, opprettet en selvreferensiell relasjon av typen (1:N) **new_new_widget_new_widget** og merket den som hierarkisk, som vist her.  
  
 ![Relasjonsdefinisjon for kontrollprogram](media/widget-relationship-definition.png "Relasjonsdefinisjon for kontrollprogram")  
  
 I rutenettvisningen **Hierarkiinnstillinger** valgte vi deretter den hierarkiske relasjonen **new_new_widget_new_widget**. Vi fylte ut de obligatoriske feltene i skjemaet. Hvis du ennå ikke har merket (1:N)-relasjonen som hierarkisk, tar koblingen i skjemaet deg tilbake til skjemaet for relasjonsdefinisjon der du kan merke relasjonen som hierarkisk.  
  
 For **hurtigvisningsskjemaet** opprettet vi et hurtigskjema med navnet **Widget Hierarchy Tile Form**. I dette skjemaet la vi til fire felt som skal vises i hver flis.  
  
> [!div class="mx-imgBorder"] 
> ![Opprette hurtigskjema for kontrollprogram](media/create-quickf-orm.png "Opprette hurtigskjema for kontrollprogram")  
  
 Da vi var ferdig med oppsettet, opprettet vi to poster: Standard Widget og Premium Widget. Etter at Premium Widget ble angitt som overordnet for Standard Widget ved hjelp av oppslagsfeltet, viste rutenettvisningen for new_Widget hierarkiikonene som vist nedenfor:  
  
> [!div class="mx-imgBorder"] 
> ![Kontrollprogrammets hierarkirutenett](media/widget-hierarchy-grid.png "Kontrollprogrammets hierarkirutenett")  
  
> [!TIP]
>  Hierarkiikonene vises ikke i rutenettvisningen for oppføringer før oppføringene er forbundet i en overordnet – underordnet-relasjon.  
  
 Hvis du velger hierarkiikonet, vises det nye hierarkiet med trevisningen til venstre og rutevisningen til høyre med to oppføringer. Hver flis inneholder fire felt som vi anga i **Widget Hierarchy Tile Form**.  
 
 > [!div class="mx-imgBorder"] 
 > ![Kontrollprogrammets tre- og flisvisninger](media/widget-tree-tiles.png "Kontrollprogrammets tre- og flisvisninger")  
  
## <a name="see-also"></a>Se også  
 [Video: Hierarkisk sikkerhetsmodellering](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)   
 [Video: Hierarkivisualisering](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
