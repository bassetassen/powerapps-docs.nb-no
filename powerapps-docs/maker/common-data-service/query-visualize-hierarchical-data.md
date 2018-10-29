---
title: Spør og visualiser hierarkiske data med PowerApps | MicrosoftDocs
description: Lær hvordan du kan spørre og visualisere hierarkisk-relaterte data
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 0cf62817-5ff5-40bb-ad17-e1f6b0921720
caps.latest.revision: 42
ms.author: matp
manager: kvivek
ms.openlocfilehash: ec45f43266c1920d05301c92bdd67838b40b7734
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691176"
---
# <a name="query-and-visualize-hierarchically-related-data"></a>Spør og visualiser hierarkisk-relaterte data

Du kan få verdifull forretningsinnsikt ved å visualisere og hierarkisk-relaterte data. De hierarkiske modellerings- og visualiseringsfunksjonene gir deg en rekke fordeler:  
  
-   Vis og utforsk kompleks hierarkisk informasjon.  
  
-   Vis sentrale ytelsesindikatorer (KPI-er) i den kontekstuelle visningen av et hierarki.  
  
-   Visuell analyse av viktig informasjon på nettet og på nettbrett.  
  
For noen enheter, for eksempel kontoen og bruker, tilbys visualiseringer som de er. Andre enheter, inkludert egendefinerte enheter, kan være aktivert for et hierarki, og du kan opprette visualiseringer for dem. Basert på behovene dine, kan du velge mellom å bruke trevisning, som viser hele hierarkiet, eller en flisvisning, som viser en mindre del av hierarkiet. Begge visningene vises ved siden av hverandre. Du kan utforske et hierarki ved å utvide og redusere et hierarkitre. Samme hierarkiske innstillinger for visualisering angis én gang, men gjelder for både nett- og mobilklienter. På nettbrett gjengis visualiseringer i et modifisert format som er tilpasset en mindre formfaktor. Tilpassbare komponenter som er obligatoriske for hierarkiske visualiseringer, er løsningsorienterte og kan derfor transporteres mellom organisasjoner som alle andre tilpassinger. Du kan konfigurere attributtene som vises i visualiseringen ved å tilpasse et hurtigskjema med skjemaredigeringsprogrammet. Det finnes ingen krav til å skrive kode.  
  
<a name="BKMK_Querydata"></a>   
## <a name="query-hierarchical-data"></a>Spørring av hierarkiske data  
 Med Common Data Service for Apps, støttes hierarkiske datastrukturer av selvreferensielle én-til-mange (1:N)-relasjoner for de relaterte postene. For å vise hierarkiske data, måtte du tidligere spørre gjentatte ganger etter de relaterte postene. Du kan for øyeblikket spørre de tilknyttede dataene som et hierarki, i ett trinn. Du kan spørre etter poster ved å bruke **Under**- og **Ikke under**-logikken. De hierarkiske operatorene **Under** og **Ikke under** vises i det avanserte søket og redigeringsprogrammet for arbeidsflyt. Hvis du vil ha mer informasjon om hvordan du bruker disse operatorene, kan du se [Konfigurer trinn for arbeidsflyt](/flow/configure-workflow-steps). Hvis du vil ha mer informasjon om Avansert søk, kan du se [Opprett, rediger eller lagre et avansert søk](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search)  
  
 Følgende eksempler illustrerer forskjellige scenarioer for spørring av hierarkier:  
  
 Hierarki for spørringskonto  
  
 ![Spørringskontoer i kontohierarkiet](media/query-accounts.png "Spørringskontoer i kontohierarkiet")  
  
 Hierarki for spørringskonto, inkludert relaterte aktiviteter  
  
 ![Relaterte aktiviteter for spørringskontoen](media/query-account-related-activities.png "Relaterte aktiviteter for spørringskontoen")  
  
 Hierarki for spørringskonto, inkludert relaterte muligheter  
  
 ![Relaterte muligheter for spørringskontoen](media/query-account-related-opportunities.png "Relaterte muligheter for spørringskontoen")  
  
 Du må angi én-til-mange (1:N)-relasjoner til en selvreferensiell relasjon som hierarkisk for én av enhetene, for å spørre dataene som et hierarki. Slik slår du på hierarkiet:  
  
1.  Åpne [Løsningsutforsker](../model-driven-apps/advanced-navigation.md#solution-explorer). 
  
2.  Velg enheten du ønsker, velg **én-til-mange (1:N)-relasjoner**, og velg deretter en én-til-mange (1:N)-relasjon. 

3.  Angi **Hierarkisk** som **Ja** i **Relasjonsdefinisjonen**.  
  
> [!NOTE]
> - Enkelte av de ferdiglagede én-til-mange-relasjonene kan ikke tilpasses. Dette vil hindre deg i å angi disse relasjonene som hierarkiske.  
> - Du kan angi en hierarkisk relasjon for systemrelasjoner som er selvreferensielle. Dette omfatter én-til-mange-selvreferensielle relasjoner for systemtype, for eksempel "contact_master_contact"-relasjonen.  
  
<a name="BKMK_Visualizedata"></a>   
## <a name="visualize-hierarchical-data"></a>Visualiser hierarkiske data  
 Systemenheter som har visualiseringer tilgjengelige som de er inkluderer `Account`, `Position`, `Product`, og `User`. Du kan se ikonet som viser hierarkidiagrammet, i rutenettet for disse enhetene, til venstre for postnavnet. Hierarkiikonet er ikke tilgjengelig for alle postene som standard. Ikonet vises for postene som har en overordnet post, en underordnet post, eller begge deler.  
  
 ![Aktive kontoer](media/cust-hs-active-account.png "Aktive kontoer")  
  
 Hvis du velger hierarkiikonet, kan du vise hierarkiet, med trevisning til venstre og flisvisning til høyre, som vist nedenfor:  
  
 ![Kontotre og flisvisning](media/hierachy-security-accounts-tile-view.png "Kontotre og flisvisning")  
  
 Enkelte andre ferdige systemenheter kan være aktivert for et hierarki. Disse enhetene inkluderer `Case`, `Contact`, `Opportunity`, `Order`, `Quote`, `Campaign`, og `Team`. Alle egendefinerte enheter kan aktiveres for et hierarki.  
  
> [!TIP]
>  Alle egendefinerte enheter kan aktiveres for et hierarki:  
>  Utvid enheten du vil bruke i løsningsutforsker. Du ser enhetskomponenten kalt **Hierarkiinnstillinger**. Enhetene som ikke kan aktiveres for et hierarki har ikke denne komponenten, med unntak av salgsområde for Dynamics 365 Customer Engagement-enheten. Selv om **Hierarkiinnstillinger** vises i enheten for salgsområdet, kan ikke enheten aktiveres for et hierarki.  
  
 Viktige ting å huske på når du oppretter visualiseringer:  
  
-   Bare én én-til-mange-selvreferensiell relasjon kan angis som hierarkisk per enhet. Den primære enheten og den relaterte enheten må være av samme type i denne relasjonen, for eksempel account_parent_account eller new_new_widget_new_widget.  
  
-   Et hierarki eller en visualisering er for øyeblikket basert på bare én enhet. Du kan vise kontohierarkiet med kontoer på flere nivåer, men du kan ikke vise kontoer og kontakter i samme hierarkivisualisering.  
  
-   Maksimalt antall felter som kan vises i en flis, er fire. Hvis du legger til flere felter i hurtigskjemaet som brukes for flisvisningen, er det bare de første fire feltene som vises.  
  
### <a name="visualization-example"></a>Visualiseringseksempel  
 La oss se på et eksempel på å opprette en visualisering for en egendefinert enhet. Vi opprettet en egendefinert enhet kalt new_Widget, opprettet en én-til-mange-selvreferensiell relasjon **new_new_widget_new_widget**, og merket den som hierarkisk, som vist her.  
  
 ![Relasjonsdefinisjon for kontrollprogram](media/widget-relationship-definition.png "Relasjonsdefinisjon for kontrollprogram")  
  
 Deretter valgte vi hierarkirelasjonen **new_new_widget_new_widget** i rutenettvisning for **Hierarkiinnstillinger**. Vi har fylt ut de obligatoriske feltene i skjemaet. Hvis du ennå ikke har merket én-til-mange-relasjonen som hierarkisk, tar koblingen på skjemaet deg tilbake til relasjonsdefinisjonskjemaet, der du kan merke relasjonen som hierarkisk.  
  
 Vi opprettet et hurtigskjema kalt **Flisskjema for kontrollprogramhierarki** for **Hurtigvisningsskjemaet**. I dette skjemaet har vi lagt til fire felter som skal vises i hver flis.  
  
 ![Opprett hurtigskjema for kontrollprogram](media/create-quickf-orm.png "Opprett hurtigskjema for kontrollprogram")  
  
 Etter at vi fullførte konfigurasjonen, opprettet vi to poster: Standard-kontrollprogram og Premium-kontrollprogram. Rutenettvisningen viste hierarkiikonene som vist nedenfor, etter å ha gjort Premium-kontrollprogrammet overordnet til et Standard-kontrollprogram ved hjelp av oppslagsfeltet:  
  
 ![Hierarkirutenettet for kontrollprogrammet](media/widget-hierarchy-grid.png "Hierarkirutenettet for kontrollprogrammet")  
  
> [!TIP]
>  Hierarkiikoner vises ikke i rutenettvisningen for poster før postene sammenkobles i overordnet – underordnet-relasjonen.  
  
 Hvis du velger hierarkiikonet, vises new_Widget-hierarkiet med trevisning til venstre, og flisvisning til høyre, som to poster. Hver flis inneholder fire felter som vi har angitt i **Tre- og flisvisningen for kontrollprogramhierarkiet**.  
  
 ![Tre- og flisvisning for kontrollprogram](media/widget-tree-tiles.png "Tre- og flisvisning for kontrollprogram")  
  
## <a name="see-also"></a>Se også  
 [Video: Hierarkisk sikkerhetsmodellering](http://www.youtube.com/watch?v=kx5So32DrCo&index=10&list=PLC3591A8FE4ADBE07)   
 [Video: Hierarkivisualisering](http://www.youtube.com/watch?v=_dGBE6icLNw&index=9&list=PLC3591A8FE4ADBE07)
