---
title: Spesielle feltegenskaper for modelldrevne apper for hovedskjemaer i PowerApps | MicrosoftDocs
description: Slik fungerer de spesielle feltegenskapene for hovedskjemaer
Keywords: Main forms; Special field properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 6ad7e43c-b6a1-48c4-9dfb-ed830142a841
ms.openlocfilehash: 0c4e67b14816ae6eaf100221ac0ac29269000f9b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690243"
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>Oversikt over spesielle feltegenskaper for modelldrevne apper

 Alle felt har egenskapene oppført i [Felles feltegenskaper](common-field-properties-legacy.md), men enkelte felt har tilleggsegenskaper, for eksempel dette feltet for rettigheter, som kan åpnes fra hovedskjemaet for saksenheten.  

![dialogboks for spesielle egenskaper](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>Egenskaper for oppslagsfelt  
  
> [!NOTE]
>  Alternativene som beskrives i tabellen nedenfor, er tilgjengelige bare for oppslagsfelt for enkeltenheter.  
  
|Inndeling|Egenskap|Beskrivelse|  
|-------------|--------------|-----------------|  
|**Filtrering av relaterte poster**|**Vis poster bare der hvor**|Når dette er aktivert, bruker postene som viser når brukere søker etter en post, ekstra filtrering. Dette bidrar til mer relevante søk når verdien i oppslag angis.<br /><br /> Som standard er dette slått av.<br /><br /> Relasjonskombinasjonene som er mulige når du filtrerer relaterte poster, er oppført i neste tabell *<br /><br /> Den første listen fylles ut med alle de potensielle relasjonene du kan bruke til å filtrere dette oppslaget. Velg én.<br /><br /> Den andre listen fylles deretter ut med alle relasjonene som kobler den relaterte enheten (valgt i den første listen) til målenheten. Velg én.<br /><br /> Merk av for **Tillat at brukere kan slå av filter** for å gi brukerne mulighet til å slå av filteret du definerer her.<br /><br /> Når brukerne velger alternativet **Slå opp flere poster** mens de angir verdien for et oppslag, ser de denne dialogboksen.<br /><br /> ![slå-opp-flere-poster](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> Hvis du har valgt alternativet **Tillat at brukere kan slå av filter** mens du konfigurerte oppslagsfeltet, ser brukerne avmerkingsboksen for å slå av filteret.  Dette gjør det mulig for dem å se et større utvalg av poster. Hvis du vil sikre at brukerne bare ser et begrenset utvalg av poster som defineres av dette filteret, fjerner du merket i **Tillat at brukere kan slå av filter**.|  
|**Tilleggsegenskaper**|**Vis søkeboks i dialogboksen oppslag**|Du kan velge ikke å vise søkeboksen i dialogboksen oppslag.|  
||**Standardvisning**|Denne visningen brukes til å filtrere resultatene for innebygd søk og angi standardvisningen som vises i dialogboksen oppslag når brukere velger alternativet **slå opp flere poster**.<br /><br /> Standardvisningen kontrollerer også hvilke felt som er inkludert i det innebygde oppslaget.<br /><br /> For oppslag som bare tillater valg av en enkel enhetstype, settes feltene som vises i det innebygde oppslaget, til de første to feltene som er inkludert i standardvisningen. I dette eksemplet er **Hovedtelefon** og **E-post** de første to kolonnene i standardvisningen som er konfigurert for et kontooppslag.<br /><br /> For systemoppslag som tillater flere enhetstyper, vises de første to kolonnene i enhetsoppslagsvisningen.|  
||**Visningsvelger**|Du kan velge mellom tre alternativer:<br /><br /> -   **Av**: Ikke tillat at brukere kan velge en annen visning.<br />-   **Vis alle visninger**: Alle visninger er tilgjengelige.<br />-   **Vis alle valgte visninger**: Når du velger dette alternativet, kan du bruke CTRL-tasten og markøren for å velge hvilke visninger som skal vises. Du kan ikke fjerne merket for oppslagsvisning.|  
  
 **\*Mulige relasjonskombinasjoner**  
  
|Første listerelasjon|Andre listerelasjon|Tilgjengelig?|  
|-----------------------------|------------------------------|----------------|  
|N:1|1:N|Ja|  
|N:1|N:1|Ja|  
|N:1|N:N|Ja|  
|1:N|1:N|Ja|  
|1:N|N:1|Nei|  
|1:N|N:N|Nei|  
|N:N|1:N|Ja|  
|N:N|N:1|Nei|  
|N:N|N:N|Nei|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>Feltegenskaper med to alternativer  
 To alternativfelt på formateringsfanen har følgende formateringsalternativer:  
  
- **To valgknapper**: To merkede kontroller med etiketter. Bare en kan velges.  
  
- **Avmerkingsboks**: Én enkelt avmerkingsboks hvor du angir om verdien er sann eller usann.  
  
- **Liste**: En rullegardinliste som inneholder begge verdier.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>Feltegenskaper for flere linjer med tekst  
 Felt for flere linjer og enkeltlinjer med tekst, som bruker `Text Area`-formatet, har egenskapen **Radoppsett**. Med denne egenskapen kan du angi en verdi for **Antall rader** eller velge **Utvid automatisk for å bruke tilgjengelig plass**.  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjema og tilknyttede komponenter](use-main-form-and-components.md)
