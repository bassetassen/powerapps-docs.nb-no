---
title: Utformingsvurderinger for modelldrevne apphovedskjemaer med PowerApps | MicrosoftDocs
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
ms.openlocfilehash: 68915af214b86511f7fba4bbb05ee59f598340b0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39697865"
---
# <a name="design-considerations-for-model-driven-app-main-forms"></a>Utformingsvurderinger for modelldrevne apphovedskjemaer

Hovedskjemaer er det primære brukergrensesnittet der du viser og samhandler med dataene. Hovedskjemaer inneholder det største utvalget av alternativer og er tilgjengelig for modelldrevne apper, med unntak av Dynamics 365 for telefoner.  
  
 Et av de viktigste utformingsmålsetningene for hovedskjemaer er at du utformer dem én gang, og distribuerer dem overalt. Det samme hovedskjemaet du oppretter for en modelldrevet app eller nettprogrammet Dynamics 365 Customer Engagement, brukes også i Dynamics 365 for Outlook og Dynamics 365 for nettbrett. Fordelen med denne tilnærmingen er at du ikke trenger å integrere endringer i flere skjemaer. Det er imidlertid flere viktige faktorer du bør vurdere når du skal utforme disse skjemaene.  
  
<a name="BKMK_CustomFormsForGroups"></a>   

## <a name="custom-forms-for-different-groups"></a>Egendefinerte skjemaer for ulike grupper  
 Fordi du kan opprette flere hovedskjemaer og tilordne ulike sikkerhetsroller til hvert skjema, kan du presentere ulike grupper i organisasjonen med et skjema som er optimalisert for hvordan de bruker programmet. Du kan til og med gi hver gruppe forskjellige alternativer slik at de har ulike skjemaer å velge mellom. Mer informasjon: [Kontroller tilgangen til skjemaer](control-access-forms.md)  
  
 Du kan forvente at ledere og beslutningstakere ønsker skjemaer som er optimalisert for å referere til viktige datapunkter veldig raskt. De vil sette pris på å se diagrammer i stedet for lister, og det er ikke sikkert at de registrerer mye data selv.  
  
 Personer som samhandler direkte med kunder, kan trenge skjemaer som er skreddersydd til oppgavene de utfører oftest. Det kan hende de ønsker skjemaer som muliggjør den mest effektive dataregistreringen.  
  
 Du må finne ut hva personene i organisasjonen ønsker og trenger. Dette er ofte en gjentakende prosess hvor du samler inn informasjon, prøver forskjellige ting, og bygger skjemaer de kan bruke. Vær oppmerksom på at du har en rekke verktøy tilgjengelig, og at ikke alt må gjøres i selve skjemaet. Bruk forretningsregler, arbeidsflytprosesser, dialogbokser og forretningsprosessflyter sammen med skjemaene for å gi en løsning som fungerer for organisasjonen.  
  
 Du må balansere dette med hvor lang tid du ønsker å bruke på å administrere skjemaer. Det er relativt enkelt å opprette og redigere skjemaer, men jo flere skjemaer du oppretter, jo flere skjemaer må du administrere.  
  
<a name="BKMK_PresentationDifferences"></a>   
## <a name="presentation-differences"></a>Forskjeller på presentasjon  
 Selv om du ikke må administrere flere skjemaer for hver presentasjon, må du vurdere hvordan forskjeller i presentasjonen kan inkluderes i hovedskjemaet. [Presentasjoner ved bruk av hovedskjemaer](main-form-presentations.md) beskriver måten at hovedskjemaet kan presenteres. Hovedbudskapet her er:  
  
- Dynamics 365 for nettbrett støtter ikke at nettressurser for bilder, HTML eller Silverlight legges til i skjemaene.  
  
-   Oppsettet til skjemaer for Dynamics 365 for nettbrett er automatisk generert på bakgrunn av hovedskjemaet. Det finnes ikke noe spesielt redigeringsprogram for skjema for Dynamics 365 for nettbrett. Du må bekrefte at skjemapresentasjonen fungerer bra på begge klientene.  
  
-   Hvis du har ikke støttede skript som samhandler med DOM-elementer i nettprogrammer, fungerer ikke disse skriptene i skjemaer for Dynamics 365 for nettbrett. Det er fordi de samme DOM-elementene ikke er tilgjengelig.  
  
- Leseruteskjema for Dynamics 365 for Outlook tillater ikke skript. Synligheten for skjemaelementene avhenger av standardinnstillingene, og de kan ikke endres under kjøring ved bruk av skript.  
  
<a name="BKMK_FormPerformance"></a>   
## <a name="form-performance"></a>Skjemaytelse  
 Skjemaer som lastes inn sakte eller ikke svarer raskt nok, påvirker produktiviteten til og innføringen av appen blant brukere. [Optimaliser skjemaytelse](optimize-form-performance.md) gir en rekke anbefalinger som du bør vurdere når du utformer skjemaer, slik at tilpassingene ikke får en negativ innvirkning på skjemaet.  
  
### <a name="next-steps"></a>Neste trinn 
 [Opprett og utform skjemaer](create-design-forms.md)    
 [Opprett eller rediger hurtigopprettingsskjemaer](create-edit-quick-create-forms.md)   

 
