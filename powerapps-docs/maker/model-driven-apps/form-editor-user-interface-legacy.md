---
title: Oversikt over brukergrensesnittet for skjemaredigeringsprogrammet for modelldrevne apper for PowerApps | MicrosoftDocs
description: Finn ut mer om brukergrensesnittet for skjemaredigeringsprogrammet for å redigere skjemaer i PowerApps
keywords: Skjemaer; Hovedskjema; Samlede grensesnittapper; Dynamics 365 for Customer Engagement
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.assetid: 146f8035-4fcd-4572-8e71-4270cd150495
ms.openlocfilehash: a44987e7b8809dea46f164224974a21a2d9a5010
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696482"
---
# <a name="overview-of-the-model-driven-app-form-editor-user-interface"></a>Oversikt over brukergrensesnittet for skjemaredigeringsprogrammet for modelldrevne apper

Skjemaredigeringsprogrammet viser kommandoer i tre faner: **Fil**, **Hjem** og **Sett inn**.  

- [Fil-fane](#file-tab)
- [Faneblad for hjemmeside](#home-tab)
- [Sett inn fane](#insert-tab)
  
Skjemaredigeringsprogrammet er delt inn i tre områder: **Navigasjon**, **Brødtekst**, og **Utforsker**.  

![Brukergrensesnitt for skjemaredigeringsprogram](media/form-user-interface.png)
  
**Navigering**  
Bruk navigasjonsområdet, plassert på venstre side, til å kontrollere tilgang til relaterte enheter eller for å legge til koblinger til nettadresser som skal vises i hovedruten i skjemaet. Hvis du vil redigere navigasjon, må du først velge **Navigasjon**-kommandoen i **Velg**-gruppen på **Hjem**-fanen.

Hovedskjemaer tilbyr navigeringsalternativer gjennom navigasjonsfeltet, men bruker de samme dataene i navigasjonsområdet til å kontrollere hvilke navigasjonsalternativer som er tilgjengelige. Mer informasjon: [Rediger navigasjon](use-the-form-editor-legacy.md)  


**Brødtekst** <br>
Bruk brødtekst-området, plassert i midten, til å kontrollere oppsettet for skjemaet. Du kan merke og dra skjemaelementer for å plassere dem. Egenskapene for elementet åpnes når du dobbeltklikker på elementet. 

Den første inndelingen under **Sammendrag**-fanen for sak, kontakt og hovedskjemaer for kontoer, viser kontoen eller kontaktkortskjema av typen **Hurtigvisning** som standard. For egendefinerte enheter er denne inndelingen ikke tilgjengelig som standard. Du kan sette inn en nytt inndelingen og et hurtigvisningsskjema i den. Kontaktkortskjemaet viser maksimalt fem felter. Med unntak av felter, er det ikke mulig å vise andre kontroller i den blå flisen, selv om hurtigvisningsskjema inneholder den. 
 
>[!NOTE] 
> Hvis du vil beholde kortformatet (som vist på følgende bildet), anbefaler vi at du ikke flytte hurtigvisningsskjema til en annen inndelingen av skjemaet.

![Kortformat](media/card-format.png)
   
Mer informasjon: [Opprett og redigere hurtigvisningsskjemaer](create-edit-quick-view-forms.md)  
 
-   Hvis du vil legge til et felt, kan du velge det fra **Feltutforskeren**, og dra det til en inndelingen.  
  
    -   Hvis du vil legge til et element, som ikke er et felt, kan du velge hvor du vil plassere det og bruke den aktuelle kommandoen fra **Sett inn**-fanen legg det til.  
  
    -   Hvis du vil fjerne et element, velger du det og bruker **Fjern**-kommandoen i **Rediger**-gruppen på **Hjem**-fanen.  
  
    -   Hvis du vil redigere **Topptekst** eller **Bunntekst** for skjemaet, må du først velge tilsvarende kommando i **Velg**-gruppen på **Hjem**-fanen.  
  
**Utforsker**  
Innholdet i utforskerområdet, plassert på høyre side, er avhengig av konteksten.  
  
Når du velger **Brødtekst**, **Topptekst**, eller **Bunntekst** i **Velg**-gruppen på **Hjem**-fanen, ser du **Feltutforskeren**. Bruk **Feltutforskeren** til å dra feltene du vil vise til en inndeling i skjemaet, eller i toppteksten eller bunnteksten. Du kan inkludere det samme feltet flere ganger i et skjema. Bruk **Nytt felt**-knappen som en snarvei til å opprette et nytt felt.  
  
Når du velger **Navigasjon** i **Velg**-gruppen på **Hjem**-fanen, ser du **Relasjonsutforskeren**. Dra en av relasjonene i til en av gruppene i navigasjonsområdet. Du kan ikke legge til samme relasjon to ganger. Relasjoner er tilgjengelige basert på hvordan de er konfigurerert. Hvis du konfigurerer en relasjon som ikke skal vises, vises den ikke i **Relasjonsutforskeren**. Hvis du vil ha informasjon om hvordan du konfigurerer visningsalternativer som er standard for relasjoner, kan du se [Elementet for navigasjonsrute for primær enhet](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity).
  
Du kan bruke **Ny èn-til-mange** og **Ny mange-til-mange-knapper** som en snarvei for å legge til nye enhetsrelasjoner.  

## <a name="file-tab"></a>Fil-fane

Velg **Fil**-fanen for å legge til eller vise følgende alternativer:

- **Ny aktivitet** Legg til en ny aktivitet
- **Ny post** Legg til en ny post
- **Verktøy** Bruk alternativer som importdata, duplikatregistrering og veiviser for massesletting
- **Alternativer** Endre standard for skjerminnstillinger for å tilpasse standardløsningen, og administrer e-postmalene
    - Generelt
    - Synkronisering
    - Aktiviteter
    - Formater
    - E-postmaler
    - E-postsignaturer
    - E-post
    - Personvern
    - Språk
- Hjelp
- Lukk


## <a name="home-tab"></a>Hjem-fanen  
 **Hjem**-fanen viser kommandolisten i følgende tabell:

![hjem-fane](media/home-tab.png)

|Gruppe|Kommando|Beskrivelse|
|-----------|-------------|-----------------| 
|**Lagre**|**Lagre** **(CTRL+S)**|Lagre skjemaet.|
||**Lagre som**|Opprett en kopi av dette skjemaet med et annet navn.|
||**Lagre og lukk**|Lagre skjemaet, og lukk redigeringsprogrammet for skjemaet.|
||**Publiser**|Publiser skjemaet. Mer informasjon: Publisering av tilpassinger|
|**Rediger**|**Endre egenskaper**|Endre egenskaper for det valgte elementet i brødteksten.<br /><br /> Se følgende inndelinger, avhengig av det valgte elementet:<br /><br /> -   [Egenskaper for fane](tab-properties-legacy.md)<br />-   [Egenskaper for inndeling](section-properties-legacy.md)<br />-   [Vanlige feltegenskaper](common-field-properties-legacy.md)<br />-   [Spesielle feltegenskaper](special-field-properties-legacy.md)<br />-  [Egenskaper for delrutenett](sub-grid-properties-legacy.md)<br />-   [Hurtigvisning av kontrollegenskaper](quick-view-control-properties-legacy.md)|
||**Fjern**|Fjern det valgte elementet.|
||**Angre** **(Ctrl+Z)**|Angre forrige handling.|
||**Gjør om** **(CTRL+Y)**|Gjør om forrige handling.|
|**Velg**|**Brødtekst**|Rediger brødteksten i skjemaet.|
||**Topptekst**|Rediger topptekst i skjema.|
||**Bunntekst**|Rediger bunntekst i skjema.|
||**Navigering**|Rediger skjemanavigasjon.<br /><br /> Mer informasjon: [Rediger navigasjon](use-the-form-editor-legacy.md)
|**Skjema**|**Forretningsregler**|Vise, redigere eller opprette nye forretningsregler med utforskeren for forretningsregler. **Obs!:** For de interaktive skjemaene, støttes bare «Enhet» og «Alle skjemaer» omfanget.<br /><br /> Mer informasjon: [Opprett og rediger forretningsregler](create-business-rules-recommendations-apply-logic-form.md)|
||**Skjemaegenskaper**| Mer informasjon: [Skjemaegenskaper](form-properties-legacy.md)|  
||**Forhåndsvisning**|Bruk dette til å se hvordan skjemaet ser ut når det er publisert. Du kan også forhåndsvise for å teste skripter som er tilknyttet fra hendelser.|         
||**Aktiver sikkerhetsroller**|Bruk dette til å angi hvilke sikkerhetsroller som skal ha tilgang til skjemaer. Mer informasjon: [Kontroller tilgang til skjemaer](control-access-forms.md) **Viktig:** Hvis du oppretter et nytt skjema, vil bare sikkerhetsrollene for systemansvarlig og systemtilpasser ha tilgang til skjemaet. Du må tilordne tilgang til andre sikkerhetsroller før personer kan bruke det.|  
||**Vis avhengigheter**|Se hvilke løsningskomponenter som avhenger av dette skjemaet, og hvilke løsningskomponenter som kreves av dette skjemaet. Mer informasjon: [Løsningsavhengigheter](../common-data-service/overview.md)|  
||**Forvaltede egenskaper**|Forvaltede egenskaper-kommandoen har to egenskaper **Kan tilpasses** og **Kan slettes**. Hvis du angir disse egenskapene til usann, betyr det at skjemaet ikke kan tilpasses, og ikke kan slettes etter at du har inkludert det i en løsning. Eksporter denne løsningen som en administrert løsning, og importer den administrerte løsningen til et annet miljø. Mer informasjon: [Forvaltede egenskaper](../common-data-service/solutions-overview.md#managed-properties)| 
|**Oppgradering**|**Slå sammen skjemaer**|Dette alternativet lar deg slå dette skjemaet sammen med et skjema fra en tidligere versjon av Dynamics 365-skjema, hvis det er aktuelt.|
  

## <a name="insert-tab"></a>Sett inn-fanen  
![Sett inn-fane](media/insert-tab.png)
 
Sett inn-fanen viser kommandoene i følgende tabell:

|Gruppe|Kommando|Beskrivelse|
|-----------|-------------|-----------------| 
||**Inndeling**|Legg til en inndeling til en valgt fane. Du kan inkludere en inndeling med én til fire kolonner.<br /><br /> Du kan også sette inn et referansepanel i de interaktive skjemaene. Referansepanelet også lagt til som en inndelingen i det primære – interaktive – skjemaet. Panelreferansedelen er lagt til saken, kontoen, kontakt- og egendefinerte enhetsskjemaer, som standard.<br /><br /> Mer informasjon: [Egenskaper for del](section-properties-legacy.md)|  
|**Tre faner**|**Tre kolonner**|Sett inn en fane for tre kolonner med like bredder.<br /><br /> Mer informasjon: [fane-egenskaper](tab-properties-legacy.md)|  
||**Tre kolonner**|Sett inn en fane med tre kolonner, med en bredere kolonne i midten.|  
|**To faner**|**To kolonner**|Sett inn en fane med tre kolonner, med en bredere kolonne til høyre.|  
||**To kolonner**|Sett inn en fane med tre kolonner, med en bredere kolonne til venstre.|  
||**To kolonner**|Sett inn en fane med to kolonner, med like brede kolonner.|  
|**Èn fane**|**Én kolonne**|Sett inn en fane med én kolonne.|  
|**Kontroll**|**Delrutenett**|Formater et delrutenett, og sett det inn i skjemaet.<br /><br /> Mer informasjon: [Egenskaper for delrutenett](sub-grid-properties-legacy.md)|  
||**Underlagsskive**|Sett inn et tomt område.|  
||**Hurtigvisningsskjema**|Sett inn et hurtigvisningsskjema.<br /><br /> Mer informasjon: [Kontrollegenskaper for hurtigvisning](quick-view-control-properties-legacy.md)|  
||**Nettressurs**|Sett inn en nettressurs for å bygge inn innhold fra andre steder på en side.<br /><br /> Mer informasjon: [Egenskaper for nettressurs](web-resource-properties-legacy.md)|  
||**iFRAME**|Du kan legge til en IFRAME i et skjema for å integrere innhold fra et annet nettområde i et skjema.| 
||**Tidslinje**|Sett inn en tidslinje-kontroll i skjemaet. Denne kontrollen viser tidslinjen av aktiviteter som er relatert til enheten i et skjema.|  
||**Navigasjonskobling**|Du kan sette inn en kobling i en skjemanavigasjon ved bruk av dette alternativet.|  
||**Tidtaker**|Sett inn en tidtakerkontroll i et enhetsskjema for å spore tid mot en serviceavtale. Mer informasjon: [Legg til en tidtakerkontroll](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla)|
||**Søk i kunnskapsbasen**|Sett inn en søkekontroll som brukere kan bruke til å søke i kunnskapsartikler. Mer informasjon: [Kontroll for søk i kunnskapsbasen](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-knowledge-base-search-control-forms)|  
||**Relasjonsassistent**|Du kan sette inn en relasjonsssistent-kontroll i skjemaet ved å bruke dette alternativet.|

>[!Note] 
>De følgende komponentene støttes ikke i hovedskjemaer:<br> <ul> <li>Bing-kart <br><li>Yammer <br><li>Aktivitetsfeeder <br> </li> </ul>


## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og tilknyttede komponenter](use-main-form-and-components.md)  
