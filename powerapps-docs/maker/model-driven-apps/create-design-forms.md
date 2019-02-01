---
title: Opprette og utforme modelldrevne appskjemaer | MicrosoftDocs
ms.custom: ''
ms.date: 12/06/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 99c795e0-9165-4112-85b1-6b5e1a4aa5ec
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags:
  - Links to topic not migrated
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-design-model-driven-app-forms"></a>Opprette og utforme modelldrevne appskjemaer 

Med PowerApps har skjemaer brukergrensesnittet som brukerne bruker til å arbeide med dataene de trenger for å kunne gjøre jobben sin. Det er viktig at skjemaene for brukerne er utformet slik at de kan søke etter eller registrere informasjon effektivt. 

Du kan opprette nye skjemaer eller redigere eksisterende skjemaer for alle enheter som tillater skjematilpassing, i standardløsningen eller i en uadministrert løsning. I en uadministrert løsning kan du redigere de forvaltede egenskapene for en uadministrert egendefinert enhet som ble opprettet for løsningen.
Hvis du viser en administrert løsning, kan du ikke opprette nye skjemaer eller redigere eksisterende skjemaer for enheter. Hvis de forvaltede egenskapene for en enhet i den administrerte løsningen tillater tilpassing, kan du imidlertid legge til eller redigere skjemaer for enheten. 
  

<a name="BKMK_TypesOfForms"></a> 
## <a name="type-of-forms"></a>Skjematyper
Det finnes ulike skjematyper, og hver type har en bestemt funksjonalitet eller bruk. Mer informasjon: [Skjematyper i PowerApps](types-forms.md).  

  
<a name="BKMK_FormDifferencesByEntity"></a>   
## <a name="updated-versus-classic-entities"></a>Oppdaterte kontra klassiske enheter  
PowerApps gir mange muligheter for utforming av skjemaer. Med enhetlig grensesnitt ble de fleste enheter oppdatert, slik at de passet bedre til det responsive grensesnittet. Oppdaterte enheter og dine egne egendefinerte enheter har støtte for Dynamics 365 for tablets-klienten , forretningsprosessflyter og forretningsregler. Når du bruker disse enhetene, kan du utforme én gang og distribuere til alle klienter.  
  
Det er fortsatt et antall enheter, her kalt klassiske enheter, som beholder utseendet og funksjonene fra tidligere versjoner. Disse enhetene brukes sjeldnere. De vises her:  
  
||||||  
|-|-|-|-|-|  
|Adresse|Artikkel|Artikkelkommentar|Masseslettingsoperasjon|Tilkobling|  
|Rabatt|Rabattliste|Dokumentplassering|E-postvedlegg|Følg|  
|Mål|Metrikkverdi for mål|Importer kildefil|Fakturaprodukt|Ordreprodukt|  
|Prisliste|Køelement|Tilbudsprodukt|Felt for beregnet verdi|Spørring etter beregnet verdi|  
|Lagret visning|Service|Serviceaktivitet|SharePoint-område|Sted|  
|Distrikt|Enhet|Enhetsgruppe|||  
  
## <a name="form-display-faq"></a>Vanlige spørsmål for visningsskjema

### <a name="why-is-my-form-not-visible-in-the-form-selector-drop-down-in-my-app"></a>Hvorfor er ikke skjemaet mitt synlig i rullegardinlisten for skjemavelgeren i appen min?
Et skjema er kanskje ikke tilgjengelig, fordi det ikke er lagt til i appen.
1. Åpne appen i apputforming.
2. I **Enhetsvisning**-området velger du **Skjemaer** ved siden av enheten.
3. I kategorien **Komponenter** kontrollerer du hovedskjemaene som er inkludert for appen. Kontroller at skjemaet du vil vise, er kontrollert. Hvis ikke velger du den, lagrer, og publiser appen.

   > [!div class="mx-imgBorder"] 
   > ![](media/forms-included-in-app.png "Skjemaer som er inkludert i appen")
   
### <a name="why-isnt-my-form-displayed-as-the-default-form-in-the-app"></a>Hvorfor vises ikke skjemaet mitt som standardskjema i appen?
Et skjema kan angis som standardskjema via konfigurasjon av skjemarekkefølgen, eller når en bruker angir standardskjemaet som en tilpassingsinnstilling.
1. Åpne løsningsutforskeren. Utvid enheten som har skjemaene du vil ordne i rekkefølge, og velg deretter **Skjemaer**.
2. Velg **Skjemarekkefølge** > **Hovedskjemasett** på verktøylinjen. 

   > [!div class="mx-imgBorder"] 
   > ![](media/form-order-toolbar.png "Verktøylinjekommando for skjemarekkefølge")
   
3. Skjemarekkefølgen vises. Velg skjemaet og bruk pil opp og pil ned for å flytte skjemaet i skjemarekkefølgen. Skjemaet øverst i listen er standardskjemaet. 

   > [!div class="mx-imgBorder"] 
   > ![](media/form-order-dialog.png "Dialogboks for skjemarekkefølge")
   
4. Velg **OK** for å lagre endringene i skjemarekkefølgen.
5. Velg **Publiser** på verktøylinjen for skjemautforming, slik at skjemarekkefølgen blir tilgjengelig i apper.
 
#### <a name="form-order-user-personalization-setting"></a>Innstillinger for brukertilpassing av skjemarekkefølgen
Legg merke til at når en appbruker endrer skjemavalget i rullegardinlisten for skjemavelgeren for en app, blir dette skjemaet standardskjema for brukeren. Denne tilpassingen overstyrer standardskjemaet som er angitt for enheten i appen.

   > [!div class="mx-imgBorder"] 
   > ![](media/change-form-user-setting.png "Brukerinnstilling for å endre standardskjemaet")
   
### <a name="related-topics"></a>Beslektede emner  
    
[Tilordne skjemarekkefølge](assign-form-order.md) <br />
[Kontroller tilgang til skjemaer](control-access-forms.md) <br />
[Hvordan hovedskjemaer vises i ulike klienter](main-form-presentations.md) <br />
