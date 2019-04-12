---
title: Delrutenettegenskaper for hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå egenskapene for delrutenett for hovedskjemaer
Keywords: Hovedskjema; Egenskaper for delrutenett; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/07/2018
ms.service: powerapps
ms.topic: article
ms.assetid: 82892cd3-3436-4677-b96b-f2ccd0a4f078
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="sub-grid-properties-for-model-driven-app-main-forms-overview"></a>Oversikt over delrutenettegenskaper for hovedskjemaer for modelldrevne apper

Du kan konfigurere et delrutenett i et skjema til å vise en liste over oppføringer eller et diagram. Velg **Vis bare diagram** i kategorien **Vis** for å vise et diagram i stedet for en liste.  

Du kan få tilgang til **Egenskaper for delrutenett** fra PowerApps-nettstedet. 
1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

     ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien. 

3.  I listen over skjemaer åpner du skjemaet av typen **Hoved**. I kategorien **Sett inn** velger du **Delrutenett** for å vise egenskapene for delrutenett.

    ![egenskaper for delrutenett](media/sub-grid-properties.png)
  
|Tabulator|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Vis**|**Navn**|**Nødvendig**: Det unike navnet for delrutenettet som skal brukes ved referanse til det i skript. Navnet kan bare inneholde alfanumeriske tegn og understrekingstegn.|  
||**Etikett**|**Nødvendig**: Lokaliserbar etikett for delrutenettet som er synlig for brukerne.|  
||**Vis etikett i skjemaet**|Angir om feltet skal vises i skjemaet. Dette er påkrevd hvis du aktiverer **Vis søkeboks**. Du kan også velge å ha farge på paneltoppteks.|  
||**Oppføringer**|Velge mellom to alternativer:<br /><br /> - **Bare relaterte oppføringer**: Delrutenettet viser bare oppføringer som er knyttet til den gjeldende oppføringen.<br />- **Alle oppføringstyper**: Delrutenettet viser oppføringer bare filtrert av standardvisningen, eller hvis visningsvelgeren er aktivert, visninger som brukeren velger.<br /><br /> Alternativet du velger, påvirker virkemåten til kontrollen for å vise liste. Mer informasjon: [Vis listevirkemåte](sub-grid-properties-legacy.md#BKMK_ShowListControlBehavior)|  
||**Enhet**|Avhengig av hvilket alternativ du velger for **Oppføringer**vil listen vise enten:<br /><br /> - **Bare relaterte oppføringer**: En liste over enheter som er relatert til denne enheten med navnet på oppslagsfeltet for denne enheten som definerer forholdet i parentes.<br />- **Alle oppføringstyper**: En liste over alle enheter.|  
||**Standardvisning**|Velg visningen som skal brukes som standard. Hvis du ikke aktiverer andre visninger ved hjelp av egenskapen **Visningsvelger**. Dette vil være den eneste visningen.<br /><br /> Bruk **Rediger** for å åpne standardvisningen for redigering. Bruk **Ny** for å opprette en ny visning som skal brukes for dette delrutenettet.|  
||**Vis søkeboks**|Vis søkeboksen. Når dette alternativet er valgt, er alternativet **Vis etikett i skjemaet** påkrevd.|  
||**Vis indeks**|Bare skjemaer som bruker [klassiske skjemaer](main-form-presentations.md#classic-forms), støtter Vis indeks.<br /><br /> Merk av for dette alternativet hvis du vil at en alfabetisk indeks skal være tilgjengelig med listen. Dette gjør at du kan hoppe til oppføringer som starter med en bestemt bokstav eller et bestemt tall.|  
||**Visningsvelger**|Du har tre alternativer:<br /><br /> - **Av**> Bare standardvisningen kan brukes.<br />- **Vis alle visninger**: La brukere velge hvilken som helst visning.<br />- **Vis valgte visninger**: Bruk CTRL-tasten med markøren for å velge hvilke av de tilgjengelige visningene du vil vise.|  
||**Standarddiagram**|Velg hvilket diagram som skal vises hvis det er merket av for **Vis bare diagram**.|  
||**Vis bare diagram**|Det vises et diagram i stedet for en liste over oppføringer.|  
||**Vis diagramutvalg**|Hvis **Vis bare diagram** er valgt, la andre velge ulike diagrammer.|  
||**Tilgjengelighet**|Angi om delen skal være tilgjengelig på telefonen.|
|**Formatering**|**Oppsett**|**Velg antall kolonner som kontrollen bruker**.<br /><br /> Når inndelingen som inneholder delrutenettet inneholder flere enn én kolonne, kan du angi at feltet skal bruke opptil antallet kolonner som inndelingen har.|  
||**Radoppsett**|**Antall rader** avgjør hvor mange oppføringer som skal vises på en side i et delrutenett.<br /><br /> Hvis det er merket av for **Utvid automatisk for å bruke tilgjengelig plass**, vil det bli plass til to oppføringer i skjemaet, og det vil utvide plassen når antallet oppføringer øker. Hvis antallet overskrider **Antall rader**, kan brukere navigere til andre sider for å vise oppføringene.<br /><br /> Hvis det ikke er merket av for **Utvid automatisk for å bruke tilgjengelig plass**, vil det være plass i skjemaet til antallet oppføringer som er definert av **Antall rader**, og brukere kan navigere til flere sider for å vise flere oppføringer.|  
|**Kontroller**|**Kontroller**|Velg å legge til kontroller og velg alternativknappen slik at de er tilgjengelig på nettet, telefonen eller nettbrettet.|
  
 Når du bruker [klassiske skjemaer](main-form-presentations.md#classic-forms) i skjemaer, vil handlinger som utføres på et delrutenett, være tilgjengelige på båndet. Utviklere kan tilpasse virkemåten til disse handlingene eller legge til flere handlinger ved å tilpasse båndet.  
  
 Når du bruker [oppdaterte skjemaer](main-form-presentations.md#updated-forms) i skjemaer, vil handlinger for delrutenett plasseres nær delrutenett, noe som gjør det enklere å få tilgang til dem. Kommandolinjen tillater imidlertid ikke at egendefinerte handlinger kan legges til. Utviklere kan redigere båndet for å endre handlingene for resten av de tre handlingene: vise liste, legge til oppføring og slette oppføring.  
  

## <a name="show-list-behavior"></a>Vis listevirkemåte  
 Når du viser en liste i skjemaer med [oppdaterte skjemaer](main-form-presentations.md#updated-forms), viser hvert delrutenett **Åpne visning**-knappen ![Åpne visning-knappen](media/crm-itpro-cust-openview.PNG "Åpne visning-knappen") øverst til høyre når enheten også vises som en av enhetene som er inkludert i navigasjonsområdet i skjemaredigeringsprogrammet. Når du klikker denne knappen, åpnes visningen. Virkemåten endres avhengig av hvilket alternativ som er valgt for **Oppføringer**-egenskapen.  
  
 Når du velger **Bare relaterte oppføringer**, åpnes visningen ved hjelp av én av de tilknyttede visningene i samme vindu. Hvis du vil gå tilbake til skjemaet, bruker du tilbakeknappen eller velger hovednavnverdien for gjeldende oppføring i navigasjonsfeltet.  
  
 Når du velger **Alle oppføringstyper**, åpnes visningen i et nytt vindu.  

## <a name="add-record-behavior"></a>Legge til virkemåte for kategori  
 Når du viser en liste i skjemaer med [oppdaterte skjemaer](main-form-presentations.md#updated-forms), viser hvert delrutenett knappen **Legg til oppføring** ![Legg til-knapp](media/crm-itpro-cust-subgridadd.PNG "Legg til-knapp") øverst til høyre i delrutenettet. Når du klikker denne knappen, kan du legge til en oppføring. Virkemåten endres avhengig av hvilket alternativ som er valgt for **Oppføringer**-egenskapen og om oppslaget er for aktivitetsoppføringer.  
  
 Når du velger **Bare relaterte oppføringer**, er standard virkemåte å legge til eksisterende oppføringer. Brukere ser et innebygd oppslag for å søke etter en eksisterende oppføring først. Dette bidrar til å hindre oppretting av like oppføringer.  Hvis de ikke finner en eksisterende oppføring, kan de velge alternativet **Ny**. Når en ny oppføring opprettes, brukes en av felttilordningene som er definert i relasjonen. Mer informasjon: [Tilordne enhetsfelt](../common-data-service/map-entity-fields.md)   
  
 Når du velger **Alle oppføringstyper**, er standard virkemåte å legge til en oppføring. Hurtigopprettingsskjemaet vises hvis målenheten har et. Hvis ikke, vises standard hovedskjema for enheten.  
  
 Hvis delrutenett viser aktiviteter, må brukere først velge aktivitetstype, og deretter vil virkemåten Legg til ny oppføring vises.  
  
## <a name="delete-record-behavior"></a>Slette oppføringsvirkemåte  
 Når du velger en oppføring i et delrutenett, vises **Slett**-knappen ![Ikon for sletting av underordnet liste](media/crm-itpro-cust-subgriddelete.PNG "Ikon for sletting av underordnet liste") til høyre for raden. Virkemåten til slettehandlingen varierer avhengig av hvilken relasjonstype med gjeldende enhet.  
  
 Når delrutenettet bruker en 1:N-relasjon (én-til-mange), er vanlig virkemåte for sletting av oppføring å vise en bekreftelsesdialogboks oppføringen slettes.  
  
 Når delrutenettet bruker en NN-relasjon (mange-til-mange), vil oppføringen i relasjonsenheten (eller skjæringspunktet) som er knyttet til to oppføringer, bli slettet uten bekreftelse, og oppføringen vil ikke lenger vises i delrutenettet. Oppføringen som ble vist, blir imidlertid ikke slettet.  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
