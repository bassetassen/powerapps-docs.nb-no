---
title: Oversikt over brukergrensesnittet for skjemaredigeringsprogrammet for modelldrevne apper for PowerApps | MicrosoftDocs
description: Få kjennskap til brukergrensesnittet for skjemaredigeringsprogrammet for å redigere skjemaer i PowerApps
keywords: Skjemaer; Hovedskjema; Apper for enhetlig grensesnitt; Dynamics 365 for Customer Engagement
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.assetid: 146f8035-4fcd-4572-8e71-4270cd150495
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-the-model-driven-app-form-editor-user-interface"></a>Oversikt over brukergrensesnittet for skjemaredigeringsprogrammet for modelldrevne apper

Skjemaredigeringsprogrammet viser kommandoer i tre kategorier: **Fil**, **Hjem** og **Sett inn**.  

- [Kategorien Fil](#file-tab)
- [Kategorien Hjem](#home-tab)
- [Kategorien Sett inn](#insert-tab)
  
Skjemaredigeringsprogrammet er delt inn i tre områder: **navigasjon**, **brødtekst** og **utforsker**.  

> [!div class="mx-imgBorder"] 
> ![Brukergrensesnitt for skjemaredigeringsprogram](media/form-user-interface.png)
  
**Navigasjon**  
Plassert på venstre side, Bruk navigasjonsområdet til å styre tilgang til relaterte enheter eller legge til koblinger til URL-adresser som skal vises i hovedruten i skjemaet. Hvis du vil redigere navigasjonen, må du først velge **Navigasjon**-kommandoen i **Velg**-gruppen i kategorien **Hjem**.

Hovedskjemaer har navigasjonsalternativer på navigasjonsfeltet, men du kan bruke de samme dataene i navigasjonsområdet til å kontrollere hvilke navigasjonsalternativer som er tilgjengelige. Mer informasjon: [Redigere navigasjon](use-the-form-editor-legacy.md)  


**Brødtekst** <br>
Bruk brødtekstområdet, som er plassert i midten, til å styre oppsettet for skjemaet. Du kan merke og dra skjemaelementer for å plassere dem.. Når du dobbeltklikker et element, åpnes egenskapene for elementet. 

Som standard for hovedskjemaene for Sak, Kontakt og Forretningsforbindelse, viser den første delen i kategorien **Sammendrag** skjemaet for forretningsforbindelse eller kontaktkort av typen **Hurtigvisning**. Denne delen er ikke tilgjengelig som standard for egendefinerte enheter. Du kan sette inn en ny inndeling og et hurtigvisningsskjema i den. Kortskjemaet viser maksimalt fem felt. Utover felt, er det ikke mulig å vise andre kontroller i den blå flisen selv om hurtigvisningsskjemaet inneholder den. 
 
>[!NOTE] 
> Hvis du vil beholde i kortformat (som vist på bildet nedenfor), anbefaler vi at du ikke flytter hurtigvisningsskjemaet til en annen inndeling i skjemaet.

> [!div class="mx-imgBorder"] 
> ![Kortformat](media/card-format.png)
   
Mer informasjon: [Opprette og redigere hurtigvisningsskjemaer](create-edit-quick-view-forms.md)  
 
-   Hvis du vil legge til et felt, velger du det fra **Feltutforsker** og drar det til en inndeling.  
  
    -   Hvis du vil legge til et element som ikke er et felt, velger du hvor du vil plassere det og bruker den riktige kommandoen fra kategorien **Sett inn** legge for å sette det inn.  
  
    -   Hvis du vil fjerne et element, merker du det og bruke **Fjern**-kommandoen i **Rediger**-gruppen i kategorien **Hjem**.  
  
    -   Hvis du vil redigere **topptekst** eller **bunntekst** for skjemaet, må du først velge tilsvarende kommando i **Velg**-gruppen i kategorien **Hjem**.  
  
**Utforsker**  
Plassert på høyre side. Innholdet i utforskerområdet er avhengig av konteksten.  
  
Når du velger **brødtekst**, **topptekst** eller **bunntekst** i **Velg**-gruppen i kategorien **Hjem**, vises **feltutforskeren**. Bruk **feltutforskeren** til å dra feltene du vil vise, inn i en inndeling i skjemaet eller i toppteksten eller bunnteksten. Du kan inkludere det samme feltet flere ganger i et skjema. Bruk knappen **Nytt felt** som en snarvei til å opprette et nytt felt.  
  
Når du velger **Navigasjon** i **Valg**-gruppen i kategorien **Hjem**, vises **relasjonsutforskeren**. Dra en av relasjonene til en av gruppene i navigasjonsområdet. Du kan ikke legge til samme relasjon to ganger. Relasjoner er tilgjengelige avhengig av hvordan de er konfigurert. Hvis du konfigurerer en relasjon til ikke å vises, vises den ikke i **relasjonsutforskeren**. Hvis du vil ha informasjon om hvordan du konfigurerer standard visningsalternativer for relasjoner, kan du se [Navigasjonsruteelement for primærenhet](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity).
  
Du kan bruke knappene **Ny 1:N** og **Ny N:N** som snarveier til å legge til nye enhetsrelasjoner.  

## <a name="file-tab"></a>Kategorien Fil

Velg kategorien **Fil** for å legge til/vise følgende alternativer:

- **Ny aktivitet** Legg til en ny aktivitet
- **Ny oppføring** Legg til en ny oppføring
- **Verktøy** Bruk alternativer som Importer data, Duplikatregistrering og Veiviser for massesletting
- **Alternativer** Endre standard skjerminnstillinger for å tilpasse standardløsningen og administrere e-postmalene
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


## <a name="home-tab"></a>Kategorien Hjem  
 Kategorien **Hjem** viser kommandoene i som er oppført i tabellen nedenfor:

> [!div class="mx-imgBorder"] 
> ![Kategorien Hjem](media/home-tab.png)

|Gruppe|Kommando|Beskrivelse|
|-----------|-------------|-----------------| 
|**Lagre**|**Lagre**  **(Ctrl+S)**|Lagre skjemaet.|
||**Lagre som**|Opprett en kopi av skjemaet med et nytt navn.|
||**Lagre og lukk**|Lagre skjemaet, og lukk skjemaredigeringsprogrammet.|
||**Publiser**|Publiser skjemaet. Mer informasjon: Publisere tilpassinger|
|**Rediger**|**Endre egenskaper**|Endre egenskaper for det valgte elementet i brødteksten.<br /><br /> Se delene nedenfor avhengig av det valgte elementet:<br /><br /> -   [Egenskaper for kategori](tab-properties-legacy.md)<br />-   [Egenskaper for inndeling](section-properties-legacy.md)<br />-   [Vanlige egenskaper for felt](common-field-properties-legacy.md)<br />-   [Egenskaper for spesialfelt](special-field-properties-legacy.md)<br />-  [Egenskaper for delrutenett](sub-grid-properties-legacy.md)<br />-   [Egenskaper for hurtigvisningskontroll](quick-view-control-properties-legacy.md)|
||**Fjern**|Fjern det valgte elementet.|
||**Angre** **(CTRL+Z)**|Angre den forrige handlingen.|
||**Gjør om** **(CTRL+Y)**|Gjør om forrige handling.|
|**Velg**|**Brødtekst**|Rediger hovedteksten i skjemaet.|
||**Topptekst**|Rediger skjemaoverskriften.|
||**Bunntekst**|Rediger skjemabunnteksten.|
||**Navigasjon**|Rediger skjemanavigasjonen.<br /><br /> Mer informasjon: [Redigere navigasjon](use-the-form-editor-legacy.md)
|**Skjema**|**Forretningsregler**|Vis, rediger eller opprett nye forretningsregler med forretningsregelutforskeren. **Merk:**  For interaktive skjemaer støttes bare omfanget "Enhet" og "Alle skjemaer".<br /><br /> Mer informasjon: [Opprette og redigere forretningsregler](create-business-rules-recommendations-apply-logic-form.md)|
||**Skjemaegenskaper**| Mer informasjon: [Skjemaegenskaper](form-properties-legacy.md)|  
||**Forhåndsvis**|Bruk denne for å se hvordan skjemaet ser ut etter at det er publisert. Du kan forhåndsvise for å teste tilknyttede skript fra hendelser.|         
||**Aktiver sikkerhetsroller**|Bruk denne til å angi hvilke sikkerhetsroller som skal ha tilgang til skjemaene. Mer informasjon: [Styre tilgang til skjemaer](control-access-forms.md) **Viktig:** Hvis du oppretter et nytt skjema, vil bare sikkerhetsrollene Systemadministrator og Systemtilpasser ha tilgang til skjemaet. Du må tilordne tilgang til andre sikkerhetsroller før brukere kan bruke det.|  
||**Vis avhengigheter**|Se hvilke løsningskomponenter som avhenger av dette skjemaet og hvilke løsningskomponenter som kreves av dette skjemaet. |  
||**Forvaltede egenskaper**|Kommandoen Forvaltede egenskaper har to egenskaper: **Kan tilpasses** og **Kan slettes**. Hvis du setter disse egenskapene til usann, betyr dette at skjemaet ikke kan tilpasses eller slettes etter at du har tatt det med i en løsning, eksportert løsningen som en administrert løsning og importert den administrerte løsningen til et annet miljø. Mer informasjon: [Forvaltede egenskaper](../common-data-service/solutions-overview.md#managed-properties)| 
|**Oppgrader**|**Slå sammen skjemaer**|Hvis det er aktuelt, lar dette alternativet deg slå sammen dette skjemaet med et skjema fra en tidligere versjon av Dynamics 365|
  

## <a name="insert-tab"></a>Kategorien Sett inn  
> [!div class="mx-imgBorder"] 
> ![Kategorien Sett inn](media/insert-tab.png)
 
Kategorien Sett inn viser kommandoene i følgende tabell:

|Gruppe|Kommando|Beskrivelse|
|-----------|-------------|-----------------| 
||**Inndeling**|Legg til en inndeling i en valgt kategori. Du inkludere en inndeling med én til fire kolonner.<br /><br /> Du kan også sette inn et referansepanel i interaktive skjemaer. Referansepanelet er også lagt til som en inndeling i skjemaet Hovedskjema – interaktiv opplevelse. Som standard legges referansepaneldelen til skjemaene for sak, forretningsforbindelse, kontakt og egendefinert enhet.<br /><br /> Mer informasjon: [Egenskaper for inndeling](section-properties-legacy.md)|  
|**3 kategorier**|**Tre kolonner**|Sett inn en kategori med tre kolonner med lik bredde.<br /><br /> Mer informasjon: [Egenskaper for kategori](tab-properties-legacy.md)|  
||**Tre kolonner**|Sett inn en kategori med tre kolonner med en bredere kolonne i midten.|  
|**2 kategorier**|**To kolonner**|Sett inn en kategori med to kolonner med en bredere høyrekolonne.|  
||**To kolonner**|Sett inn en kategori med to kolonner med en bredere venstrekolonne.|  
||**To kolonner**|Sett inn en kategori med to kolonner med lik bredde.|  
|**1 Kategori**|**Én kolonne**|Sett inn en enkolonners kategori.|  
|**Kontroll**|**Delrutenett**|Formater et delrutenett, og sett det inn i skjemaet.<br /><br /> Mer informasjon: [Egenskaper for delrutenett](sub-grid-properties-legacy.md)|  
||**Underlagsskive**|Sett inn en tom plass.|  
||**Hurtigvisningsskjema**|Sett inn et hurtigvisningsskjema.<br /><br /> Mer informasjon: [Egenskaper for hurtigvisningskontroll](quick-view-control-properties-legacy.md)|  
||**Webressurs**|Sett inn en webressurs for å bygge inn innhold fra andre steder på én side.<br /><br /> Hvis du vil ha mer informasjon: [Egenskaper for webressurs](web-resource-properties-legacy.md)|  
||**IFRAME**|Du kan legge til en IFRAME i et skjema for å integrere innhold fra et annet nettsted i et skjema.| 
||**Tidslinje**|Sett inn en tidslinjekontroll i skjemaet. Denne kontrollen viser tidslinjen for aktiviteter relatert til enheten, i et skjema.|  
||**Navigasjonskobling**|Ved hjelp av dette alternativet kan du sette inn en kobling i en skjemanavigasjon.|  
||**Tidtaker**|Sett inn en tidtakerkontroll i et enhetsskjema for å spore tid mot en serviceavtale. Mer informasjon: [Legge til en tidtakerkontroll](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla)|
||**Søk i kunnskapsbasen**|Sett inn en søkekontroll som brukere kan bruke til å søke etter kunnskapsartikler. Mer informasjon: [Kontroll for søk i kunnskapsbase](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-knowledge-base-search-control-forms)|  
||**Relasjonsassistent**|Ved hjelp av dette alternativet kan du sette inn en relasjonsassistentkontroll i skjemaet.|

>[!Note] 
>Følgende komponenter støttes ikke i hovedskjemaer:<br> <ul> <li>Bing-kart <br><li>Yammer <br><li>Aktivitetsfeeder <br> </li> </ul>


## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)  
