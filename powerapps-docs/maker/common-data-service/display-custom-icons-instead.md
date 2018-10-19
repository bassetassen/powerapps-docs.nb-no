---
title: Vis egendefinerte ikoner i stedet for verdier i listevisninger med PowerApps | MicrosoftDocs
description: Finn ut hvordan du viser egendefinert ikongrafikk i en visning
ms.custom: ''
ms.date: 06/21/2018
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
ms.assetid: af866aed-2586-4b6f-bb1c-3519baae3645
caps.latest.revision: 25
ms.author: matp
manager: kvivek
ms.openlocfilehash: 592d2ad73b192d7f03c552563c4f91d52f3d201d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691328"
---
# <a name="display-custom-icons-instead-of-values-in-list-views"></a>Vis egendefinerte ikoner i stedet for verdier i listevisninger

<a name="GridIcons"></a>   

 Administratorer og tilpassere for PowerApps-miljøet kan legge til grafikk i en visning, og etablere logikken som brukes til å velge grafikk, basert på kolonneverdier ved å bruke JavaScript. Muligheten til å vise listevisninger som viser ikoner i stedet for tekst eller tallverdier i noen kolonner, ble innført i relasjoninnsikt. 
  
> [!NOTE]
>  Rutenettikoner vises bare i nettgrensesnittet. De vises ikke i [!INCLUDE[pn_Outlook_short](../../includes/pn-outlook-short.md)] eller mobilappen.  
  
### <a name="add-custom-graphics-and-javascript-as-web-resources"></a>Legg til egendefinert grafikk og JavaScript som nettressurser  
  
1.  Opprett nye grafikkfiler som er nødvendige for tilpassingen. Vi anbefaler en ikonstørrelse på 16 x 16 piksler (større bilder skaleres ned).  
  
2.  Skriv én eller flere JavaScript-funksjoner som etablerer hvilke ikoner som skal vises for hvilke verdier (du trenger vanligvis én funksjon for hver kolonne du vil tilpasse). Hver funksjon må godta et raddataobjekt og en språkkode( LCID) som inndata, og returnere en matrise som inneholder et bildenavn og en verktøytipstekst. Hvis du vil se en eksempelfunksjon, kan du se [Eksempel på JavaScript-funksjon](#SampleJavascript) senere i dette emnet.  
  
3.  Logg på miljøet ditt som administrator, og åpne [løsningsutforsker](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
4.  Hurtigmenyvinduet **Standardløsningen** åpnes. Gå til **Komponenter** > **Nettressurser** her.  
  
5.  Nå kan du laste opp den egendefinerte grafikken, en om gangen, som nettressurser. Velg **Ny**-knappen på verktøylinjen for å opprette en ny nettressurs. Et annet hurtigmenyvindu åpnes, slik at du kan opprette ressursen. Gjør følgende:  
  
    1.  Gi den nye ressursen en meningsbærende **Navn**. Dette er navnet du bruker for å referere til hver grafikk fra JavaScript-koden din.  
  
    2.  Angi **Type** til grafikkformatet du har brukt for å lagre grafikkfilen (PNG, JPEG eller GIF).  
  
    3.  Velg **Velg fil** for å åpne leservinduet for filen. Bruk det til å finne og velge grafikkfilen.  
  
    4.  Legg til et **Visningsnavn** eller en **Beskrivelse** hvis du ønsker det.  
  
    5.  Velg **Lagre**, og lukk deretter **Nettressurs**-vinduet.  
  
6.  Gjenta forrige trinn for hver grafikkfil du har.  
  
7.  Nå legger du til JavaScript som siste nettressurs. Velg **Ny** på verktøylinjen, for å opprette en ny nettressurs. Et annet hurtigmenyvindu åpnes, slik at du kan opprette ressursen. Gjør følgende:  
  
    1.  Gi den nye ressursen en meningsbærende **Navn**.  
  
    2.  Angi hvilken **Type** du **skripter (JScript)**.  
  
    3.  Velg **Tekstredigeringsprogram** (ved siden **Type**-innstillingen) for å åpne et vindu for tekstredigeringsprogrammet. Lim inn Javascript-koden her, og velg **OK** for å lagre den.  
  
    4.  Legg til et **Visningsnavn** eller en **Beskrivelse** hvis du ønsker det.  
  
    5.  Velg **Lagre**, og lukk deretter **Nettressurs**-vinduet.  
  
8.  Mens hurtigmenyvinduet **Standardløsning** fremdeles er åpent, utvider du **Komponenter** > **Enheter**-treet og finner enheten du vil tilpasse.  
  
9. Utvid enheten, og velg **Visninger**-ikonet.  
  
10. Du ser nå en liste over visninger for den valgte enheten. Velg en visning fra listen. Deretter åpner du rullegardinlisten **Flere handlinger** i verktøylinjen, og velger **Rediger**.  
  
11. Et hurtigmenyvindu åpnes med kontroller for redigering av valgt visning. Det viser hver kolonne som er en del av visningen. Velg målkolonnen, og velg deretter **Endre egenskaper** i **Vanlige oppgaver**-boksen. Dialogboksen **Endre kolonneegenskaper** åpnes. Lag følgende innstillinger her:  
  
    - **Nettressurs**: Angi navnet på nettressursen du opprettet for å inneholde Javascript-funksjonene (velg **Bla gjennom** for å velge fra en liste).  
  
    - **Funksjonsnavn**: Skriv inn navnet på funksjonen du skrev for å endre den valgte kolonnen og visningen.  
  
12. Velg **OK** for å lukke dialogboksen **Endre kolonneegenskaper**.  
  
13. Velg **Lagre og lukk** for å lagre visningen.  
  
14. Gjenta disse trinnene for hver enhet, visning og kolonne etter behov.  
  
15. Når du er klar, velger du **Publiser alle tilpassinger** for å publisere endringene dine. Deretter lukker du vinduet **Standardløsning**.  
  
<a name="SampleJavascript"></a>   

### <a name="sample-javascript-function"></a>Eksempel på JavaScript-funksjon  
 JavaScript-funksjonen for å vise egendefinerte ikoner og verktøytips forventer følgende to argumenter: hele radobjektet som er angitt i layoutxml og ID for nasjonal innstilling (LCID) for den anropende brukeren. LCID-parameteren sørger for at du kan angi verktøytipstekst på flere språk. Hvis du vil ha mer informasjon om språkene som støttes av miljøet, kan du se [Aktivere språk](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) og [Installer eller oppgrader språkpakker for Dynamics 365](https://technet.microsoft.com/library/hh699674.aspx). Hvis du vil ha en liste over verdier for ID for nasjonal innstilling (LCID) du kan bruke i koden din, kan du se [ID for nasjonal innstilling tilordnet av Microsoft](https://go.microsoft.com/fwlink/?linkid=829588).

  
 Forutsatt at du legger til egendefinerte ikoner for en attributtype med angitt verdi, som har et begrenset sett med forhåndsdefinerte alternativer, må du kontrollere at du bruker heltallsverdien av alternativene, i stedet for etikett, for å unngå lokaliseringsproblemer.  
  
 Følgende eksempelkode viser ikoner og verktøytips som er basert på en av tre verdier (1: Hot, 2: Warm, 3: Cold) i opportunityratingcode (vurdering)-attributtet. Eksempelkoden viser også hvordan du viser lokalisert verktøytipstekst. For at dette eksempelet skal fungere, må du opprette tre bildenettressurser med 16 x 16 bilder, med disse navnene : new_Hot, new_Warm, and new_Cold.  
  
```  
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
  
 Dette resulterer i visning av ikoner med verktøytips i **Vurdering**-kolonnen som avhenger av verdien i hver rad. Resultatet kan se slik ut:  
  
 ![Eksempel på egendefinert kolonnegrafikk eksempel](media/custom-column-graphics-example.png "Eksempel på egendefinert kolonnegrafikk")  
 
 ### <a name="see-also"></a>Se også
 [Opprette eller redigere visninger](../model-driven-apps/create-edit-views.md)
