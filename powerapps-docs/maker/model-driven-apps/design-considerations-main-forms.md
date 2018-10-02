---
title: Utformingshensyn for hovedskjemaer for modelldrevne apper med PowerApps | MicrosoftDocs
description: Lær hvordan du utformer hovedskjemaer
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: a83872f4-9e36-413b-8561-41a1e5ffe5dd
caps.latest.revision: 17
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="design-considerations-for-model-driven-app-main-forms"></a>Utformingshensyn for hovedskjemaer for modelldrevne apper

Hovedskjemaer er hovedbrukergrensesnittet der brukerne viser og arbeider med dataene. Hovedskjemaer har en omfattende rekke alternativer og er tilgjengelig for modelldrevne apper, med unntak av Dynamics 365 for phones.  
  
 Et av de viktigste utformingsmålene for hovedskjemaer, er at du utformer dem én gang og distribuerer dem overalt. Samme hovedskjemaet du utformer for en movelldreven app eller webprogrammet for Dynamics 365 Customer Engagement, brukes også i Dynamics 365 for Outlook og Dynamics 365 for tablets. Fordelen med denne tilnærmingsmåten er at du ikke trenger å integrere endringer i flere skjemaer. Det er imidlertid flere viktige faktorer som må vurderes ved utforming av disse skjemaene.  
  
<a name="BKMK_CustomFormsForGroups"></a>   

## <a name="custom-forms-for-different-groups"></a>Egendefinerte skjemaer for ulike grupper  
 Siden du kan opprette flere hovedskjemaer og tilordne ulike sikkerhetsroller til hvert skjema, kan du gi ulike grupper i organisasjonen et skjema som er optimalisert for hvordan de bruker programmet. Du kan til og med gi hver gruppe ulike alternativer, slik at de har forskjellige skjemaer til å velge mellom. Mer informasjon: [Styre tilgang til skjemaer](control-access-forms.md)  
  
 Ledere og beslutningstakere vil sannsynligvis ha skjemaer som er optimalisert når det gjelder referanse til viktige datapunkt. De vil gjerne se diagrammer i stedet for lister, de foretar kanskje ikke så mye dataregistrering.  
  
 Personer som kommuniserer direkte med kunder, må kanskje ha skjemaer som er skreddersydd for de vanligste oppgavene. De vil kanskje ha skjemaer der de kan registrere data mest mulig effektivt.  
  
 Du må finne ut hva personer i organisasjonen ønsker og har behov for. Dette er ofte en iterativ fremgangsmåte der du samler informasjon, prøver forskjellige ting og bygger skjemaer personer kan bruke. Husk at du har en rekke verktøy tilgjengelig for deg, og at ikke alt må gjøres i skjemaet. Bruk forretningsregler, arbeidsflytprosesser, dialoger og forretningsprosessflyter sammen med skjemaene for å gi en løsning som fungerer for organisasjonen.  
  
 Du må balansere dette med tiden du vil bruke på å behandle skjemaer. Det er relativt enkelt å opprette og redigere skjemaer, men etter hvert som du oppretter flere skjemaer, blir det også flere skjemaer å behandle.  
  
<a name="BKMK_PresentationDifferences"></a>   
## <a name="presentation-differences"></a>Presentasjonsforskjeller  
 Selv om du ikke må behandle flere skjemaer for hver presentasjon, må du vurdere hvordan forskjellene i presentasjonen kan bli gjort rede for i hovedskjemaet. [Hovedskjemapresentasjoner](main-form-presentations.md) beskriver de ulike måtene hovedskjemaet kan presenteres på. Det viktigste å ta hensyn til er følgende:  
  
- Dynamics 365 for tablets støtter ikke webressurser av typen bilde, HTML eller Silverlight som skal legges til i skjemaer.  
  
-   Oppsettet for Dynamics 365 for tablets-skjemaer genereres automatisk basert på hovedskjemaet. Det finnes ikke noe spesielt skjemaredigeringsprogram for Dynamics 365 for tablets-skjemaer. Du må kontrollere at skjemapresentasjon fungerer bra for begge klientene.  
  
-   Hvis du har skript som ikke støttes, og som samhandler med DOM-elementer i webprogrammet, fungerer ikke disse skriptene i Dynamics 365 for tablets-skjemaer, fordi de samme DOM-elementene ikke er tilgjengelige.  
  
- Leseruteskjemaer i Dynamics 365 for Outlook tillater ikke skripting. Synligheten til skjemaelementer er avhengig av standardinnstillingene og kan ikke endres ved kjøretid ved hjelp av skript.  
  
<a name="BKMK_FormPerformance"></a>   
## <a name="form-performance"></a>Skjemaytelse  
 Skjemaer som lastes inn langsomt eller ikke svarer raskt, påvirker både produktiviteten og bruken av appen. [Optimalisere skjemaytelsen](optimize-form-performance.md) inneholder en rekke anbefalinger som du bør vurdere når du utformer skjemaer, slik at tilpassinger ikke får en negativ innvirkning på bruken av skjemaet.  
  
### <a name="next-steps"></a>Neste trinn 
 [Opprette og utforme skjemaer](create-design-forms.md)    
 [Opprette og redigere hurtigopprettingsskjemaer](create-edit-quick-create-forms.md)   

 
