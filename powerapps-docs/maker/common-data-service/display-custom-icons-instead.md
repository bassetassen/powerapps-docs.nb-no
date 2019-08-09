---
title: Vise egendefinerte ikoner ved siden av verdier i listevisninger med PowerApps | MicrosoftDocs
description: Finn ut hvordan du kan vise egendefinert ikongrafikk i en visning
ms.custom: ''
ms.date: 02/14/2019
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
ms.assetid: af866aed-2586-4b6f-bb1c-3519baae3645
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="display-custom-icons-alongside-values-in-list-views"></a>Vise egendefinerte ikoner ved siden av verdier i listevisninger

<a name="GridIcons"></a>   

 Administratorer og tilpassere i PowerApps-miljøet kan legge til grafikk i en visning og etablere logikken som brukes til å velge grafikken, basert på kolonneverdien med JavaScript. Denne funksjonen lar deg tilpasse listevisninger som viser ikoner ved siden av teksten eller numeriske verdier. 

> [!div class="mx-imgBorder"] 
> ![](media/icon-in-opportunity-view.png "Alle salgsmuligheter-visningen med Vurdering-kolonnen som viser ikoner og tekstverdi")
  
> [!NOTE]
>  Rutenettikoner vises bare i webgrensesnittet. De vises ikke i [!INCLUDE[pn_Outlook_short](../../includes/pn-outlook-short.md)] eller mobilappen.  
  
### <a name="add-custom-graphics-and-javascript-as-web-resources"></a>Legge til egendefinert grafikk og JavaScript som webressurser  
  
1.  Opprett de nye grafikkfilene som trengs for tilpassingen. Vi anbefaler en ikonstørrelse på 16 x 16 piksler (større bilder vil bli skalert ned).  
  
2.  Skriv én eller flere JavaScript-funksjoner som definerer hvilke ikoner som skal vises for hvilke verdier (vanligvis trenger du én funksjon for hver kolonne du vil tilpasse). Hver funksjon må godta et raddataobjekt og en språkkode (LCID) som inndata, og returnere en matrise som inneholder et bildenavn og verktøytipstekst. Se [Eksempel på JavaScript-funksjon](#SampleJavascript) for en eksempelfunksjon senere i dette emnet.  
  
3.  Logg på miljøet som administrator, og åpne løsningsutforskeren.  
  
4.  Popup-vinduet **Standardløsning** åpnes. Gå til **Komponenter** > **Webressurser**.  
  
5.  Nå skal du laste opp egendefinerte grafikk, én om gangen, som webressurser. Velg **Ny**-knappen på verktøylinjen for å opprette en ny webressurs. Et nytt popup-vindu åpnes for å hjelpe deg med å opprette ressursen. Gjør følgende:  
  
    1.  Skriv inn et beskrivende **navn** på den nye ressursen. Dette er navnet du bruker til å referere til hver enkelt grafikkforekomst fra JavaScript-koden.  
  
    2.  Sett **Type** til grafikkformatet du brukte til å lagre grafikkfilen (PNG, JPEG eller GIF).  
  
    3.  Velg **Velg fil** for å åpne et filleservindu. Bruk det til å finne og velge grafikkfilen.  
  
    4.  Legg til et **Visningsnavn** og/eller en **Beskrivelse** hvis du ønsker.  
  
    5.  Velg **Lagre**, og lukk deretter **Webressurs**-vinduet.  
  
6.  Gjenta det forrige trinnet for hver grafikkfil du har.  
  
7.  Nå skal du legge til ditt JavaScript som endelig webressurs. Velg **Ny** på verktøylinjen for å opprette en ny webressurs. Et nytt popup-vindu åpnes for å hjelpe deg med å opprette ressursen. Gjør følgende:  
  
    1.  Skriv inn et beskrivende **navn** på den nye ressursen.  
  
    2.  Sett **Type** til **Skript (JScript)**.  
  
    3.  Velg **Tekstredigering** (ved siden av **Type**-innstillingen) for å åpne et tekstredigeringsvindu. Lim inn Javascript-koden her, og velg **OK** for å lagre den.  
  
    4.  Legg til et **Visningsnavn** og/eller en **Beskrivelse** hvis du ønsker.  
  
    5.  Velg **Lagre**, og lukk deretter **Webressurs**-vinduet.  
  
8.  Med **Standardløsning**-popup-vinduet fremdeles åpent, utvider du treet **Komponenter** > **Enheter** og finner enheten som du vil tilpasse.  
  
9. Utvid din enhet, og velg **Visninger**-ikonet for enheten.  
  
10. Nå kan du se en liste over visninger for den valgte enheten. Velg en visning fra listen. Åpne rullegardinlisten **Flere handlinger** på verktøylinjen, og velg **Rediger**.  
  
11. Et popup-vindu åpnes med kontroller for å redigere den valgte visningen. Den viser hver kolonne som er del av visningen. Velg målkolonnen, og velg deretter **Endre egenskaper** i **Vanlige oppgaver**-boksen. Dialogboksen **Endre kolonneegenskaper** åpnes. Angi følgende innstillinger her:  
  
    - **Webressurs**: Angi navnet på webressursen som du opprettet for Javascript-funksjonene (velg **Bla gjennom** for å velge fra en liste).  
  
    - **Funksjonsnavn**: Skriv inn navnet på funksjonen som du skrev for å endre den merkede kolonnen og visningen.  
  
12. Velg **OK** for å lukke dialogboksen **Endre kolonneegenskaper**.  
  
13. Velg **Lagre og lukk** for å lagre visningen.  
  
14. Gjenta disse trinnene for hver enhet, visning og kolonne etter behov.  
  
15. Når du er klar, velger du **Publiser alle tilpassinger** for å publisere endringene. Lukk deretter **Standardløsning**-vinduet.  
  
<a name="SampleJavascript"></a>   

### <a name="sample-javascript-function"></a>Eksempel på JavaScript-funksjon  
 JavaScript-funksjonen for å vise egendefinerte ikoner og verktøytips forventer følgende to argumenter: hele radobjektet angitt i layoutxml og den anropende brukerens ID for nasjonal innstilling (LCID). LCID-parameteren lar deg angi teksten for verktøytipset på flere språk. Hvis du vil ha mer informasjon om språkene som støttes av miljøet, kan du se [Aktivere språk](/dynamics365/customer-engagement/admin/enable-languages) og [Installere eller oppgradere språkpakker for Dynamics 365 for Customer Engagement](/dynamics365/customer-engagement/on-premises/install-or-upgrade-language-packs). Hvis du vil ha en liste over ID-verdier for nasjonal innstilling (LCID) som du kan bruke i koden, kan du se [ID-er for nasjonal innstilling tilordnet av Microsoft](https://go.microsoft.com/fwlink/?linkid=829588).

  
 Hvis du skal legge til egendefinerte ikoner for et attributt av typen alternativsett, som har et begrenset sett med forhåndsdefinerte alternativer, må du passe på at du bruker heltallsverdien for alternativene i stedet for etiketten for å unngå lokaliseringsproblemer.  
  
 Følgende eksempelkode viser ikoner og verktøytips basert på én av tre verdier (1: Meget interessert, 2: Interessert, 3: Lite interessert) i attributtet opportunityratingcode (rangering). Eksempelkoden viser også hvordan du viser lokalisert verktøytipstekst. For at dette eksemplet skal fungere, må du opprette tre bildewebressurser med 16 x 16 bilder med følgende navn: ny_Meget interessert, ny_Interessert og ny_Lite interessert.  

> [!IMPORTANT]
> Dette eksemplet krever salgsmulighet-enheten, som er tilgjengelig med Dynamics 365 for Customer Engagement-apper.
  
```javascript
function displayIconTooltip(rowData, userLCID) {      
    var str = JSON.parse(rowData);  
    var coldata = str.opportunityratingcode_Value;  
    var imgName = "";  
    var tooltip = "";  
    switch (parseInt(coldata,10)) { 
        case 1:  
            imgName = "new_Hot";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Hot";  
                    break;  
                default:  
                    tooltip = "Opportunity is Hot";  
                    break;  
            }  
            break;  
        case 2:  
            imgName = "new_Warm";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Warm";  
                    break;  
                default:  
                    tooltip = "Opportunity is Warm";  
                    break;  
            }  
            break;  
        case 3:  
            imgName = "new_Cold";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Cold";  
                    break;  
                default:  
                    tooltip = "Opportunity is Cold";  
                    break;  
            }  
            break;  
        default:  
            imgName = "";  
            tooltip = "";  
            break;  
    }  
    var resultarray = [imgName, tooltip];  
    return resultarray;  
}  
```  
  
 <!-- This results in displaying icons with tooltips in the **Rating** column that depend on the value in each row. The result could look like this:  
  
 ![Custom column graphics example](../customize/media/custom-column-graphics-example.png "Custom column graphics example")  -->
 
 ### <a name="see-also"></a>Se også
[Forstå modelldrevne appvisninger](../model-driven-apps/create-edit-views.md)
