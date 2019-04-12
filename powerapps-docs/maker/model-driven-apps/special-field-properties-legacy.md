---
title: Egenskaper for spesialfelt for hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå egenskapene for spesialfelt for hovedskjemaer
Keywords: Hovedskjemaer; Spesielle feltegenskaper; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: powerapps
ms.topic: article
ms.assetid: 6ad7e43c-b6a1-48c4-9dfb-ed830142a841
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>Oversikt over egenskaper for spesialfelt for modelldrevne apper

 Alle felt har egenskapene som vises i [Vanlige egenskaper for felt](common-field-properties-legacy.md), men visse felt har flere egenskaper, for eksempel dette rettighetsfeltet som kan åpnes fra det primære hovedskjemaet for saksenheten.  

![dialogboksen om spesielle egenskaper](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>Egenskaper for oppslagsfelt  
  
> [!NOTE]
>  Alternativene som er beskrevet i tabellen nedenfor, er bare tilgjengelige for oppslagsfelt i én enhet.  
  
|Inndeling|Egenskap|Beskrivelse|  
|-------------|--------------|-----------------|  
|**Relatert oppføringsfiltrering**|**Bare vis oppføringer hvor**|Når dette er aktivert, vil det bli brukt en tilleggsfiltrering for oppføringene som vises når brukere søker etter en oppføring. Dette gir mer relevante søk når du angir verdien for oppslaget.<br /><br /> Dette er som standard ikke aktivert.<br /><br /> Mulige relasjonskombinasjoner når du filtrerer relaterte oppføringer, vises i tabellen som kommer etter denne.*<br /><br /> Den første listen fylles ut med alle potensielle relasjoner som du kan bruke for å filtrere dette oppslaget. Velg én.<br /><br /> Den andre listen fylles deretter ut med alle relasjoner som kobler den relaterte enheten (valgt i den første listen) til målenheten. Velg én.<br /><br /> Merk av for **Tillat brukere å slå av filter** for å gi brukere muligheten til å deaktivere filteret du angir her.<br /><br /> Når brukere velger alternativet **Slå opp flere oppføringer** under angivelse av verdien for et oppslag, vises denne dialogboksen.<br /><br /> ![look-up-more-records](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> Hvis du har valgt alternativet **Tillat brukere å slå av filter** under konfigurering av oppslagsfeltet, vil brukerne se i avmerkingsboksen for å deaktivere filteret.  Dette gjør det mulig for dem å vise et større utvalg av oppføringer. Hvis du vil forsikre deg om at brukere bare kan vise det begrensede utvalget av oppføringer som er angitt ved hjelp av filteret, fjerner du merket for **Tillat brukere å slå av filter**.|  
|**Flere egenskaper**|**Vis søkeboks i oppslagsdialog**|Du kan velge å ikke vise søkeboksen i oppslagsdialogboksen.|  
||**Standardvisning**|Denne visningen brukes til å filtrere resultatet av det innebygde søket og angi standardvisningen som vises i oppslagsdialogboksen når brukere velger alternativet **Slå opp flere oppføringer**.<br /><br /> Standardvisningen styrer også hvilke felt som inkluderes i det innebygde oppslaget.<br /><br /> For oppslag som bare tillater valg av én enkelt enhetstype, settes feltene som vises i innebygd oppslaget til å være de første to feltene som er inkludert i standardvisningen. I dette eksemplet er **Hovedtelefon** og **E-post** to første kolonnene i standardvisningen som er konfigurert for et kontooppslag.<br /><br /> For systemoppslag som tillater flere enhetstyper, vises de to første kolonnene av oppslagsvisningen for enheten.|  
||**Visningsvelger**|Du kan velge mellom tre alternativer:<br /><br /> -   **Av**: Ikke tillat brukere å velge en annen visning.<br />-   **Vis alle visninger**: Alle visninger er tilgjengelige.<br />-   **Vis valgte visninger**: Når du velger dette alternativet, kan du bruke CTRL-tasten og markøren til å velge hvilke visninger som skal vises. Du kan ikke oppheve valget av oppslagsvisningen for enheten.|  
  
 **\*Mulige relasjonskombinasjoner**  
  
|Relasjon for første liste|Relasjon for andre liste|Tilgjengelig?|  
|-----------------------------|------------------------------|----------------|  
|N:1|1:N|Ja|  
|N:1|N:1|Ja|  
|N:1|N:N|Ja|  
|1:N|1:N|Ja|  
|1:N|N:1|No|  
|1:N|N:N|No|  
|N:N|1:N|Ja|  
|N:N|N:1|No|  
|N:N|N:N|No|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>Egenskaper for to alternativ-felt  
 To alternativ-felt har formateringsvalgene nedenfor i kategorien for formatering  
  
- **To alternativknapper**: To merkede kontroller med etiketter. Bare én kan velges.  
  
- **Avmerkingsboks**: Én enkelt avmerkingsboks for å angi verdien sann eller usann.  
  
- **Liste**: En rullegardinliste som inneholder begge verdiene.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>Egenskaper for flere linjer med tekst  
 Felt for flere linjer med tekst og en enkelt linje med tekst som bruker `Text Area`-formatet, har egenskapen **Radoppsett**. Med denne egenskapen kan du angi en verdi for **Antall rader** eller velge **Utvid automatisk for å bruke tilgjengelig plass**.  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
