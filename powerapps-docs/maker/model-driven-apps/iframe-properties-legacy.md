---
title: iFrame-egenskaper for hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå iFrame-egenskapene for hovedskjemaer
Keywords: Main form; iFrame properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 1b7e6a0c-18a9-47e2-aa7d-0cffb8c93b19
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="iframe-properties-for-model-driven-app-main-forms"></a>iFrame-egenskaper for hovedskjemaer for modelldrevne apper

Du kan legge til iFrames i et skjema for å integrere innhold fra et annet nettsted i et skjema. 

Følg denne fremgangsmåten for å vise iFrame-egenskaper.

1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

    ![Modelldrevet utformingsmodus](../model-driven-apps/media/model-driven-switch.png)

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien. 

3. I listen over skjemaer åpner du et skjema av typen **Hoved**. I kategorien **Sett inn** velger du IFRAME for å vise IFRAME-egenskapene.

![IFrame-egenskaper](media/iframe-properties.png)


> [!NOTE]
> Skjemaer er ikke utformet for å vises i en iFrame.  
  
|Tabulator|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Generelt**|**Navn**|**Nødvendig**: Angi et unikt navn for iFrame. Navnet kan bare inneholde alfanumeriske tegn og understrekingstegn.|  
||**URL-adresse**|**Nødvendig**: URL-adressen for siden som skal vises i en iFrame.|  
||**Send typekode for oppføringsobjekt og unik identifikator som parametere.**|Data om organisasjonen, bruker og oppføringen kan sendes til iFrame. Mer informasjon: [Sende parametere til iFrame](iframe-properties-legacy.md#BKMK_PassParametersToIFRAMEs).|  
||**Etikett**|**Nødvendig**: En etikett som skal vises i iFrame.|  
||**Vis etikett i skjemaet**|Angir om feltet skal vises.|  
||**Begrens skript på tvers av rammer der det støttes**|Det regnes som en sikkerhetsrisiko å tillate sider fra et annet nettsted å samhandle med Dynamics 365-programmet ved hjelp av skript. Bruk dette alternativet til å begrense skript på tvers av rammer for sider du ikke har kontroll over.<br /><br />|  
||**Synlig som standard**|Visning av iFrame er valgfritt og kan styres ved hjelp av skript. Mer informasjon: [Synlighetsalternativer](visibility-options-legacy.md)|
||**Aktiver for mobil**|Merk av i avmerkingsboksen for å aktivere iFrame for mobil.|  
|**Formatering**|**Velg antall kolonner som kontrollen bruker**|Når inndelingen som inneholder iFrame inneholder flere enn én kolonne, kan du angi at feltet skal bruke opptil antallet kolonner som inndelingen har.|  
||**Velg antallet rader kontrollen fyller**|Du kan styre høyden på iFrame ved å angi antall rader som kontrollen bruker.|  
||**Utvid automatisk for å bruke tilgjengelig plass**|I stedet for å angi høyden med antall rader, kan du tillate at iFrame-høyden kan utvides til tilgjengelig plass.|  
||**Velg rulletype for iFrame**|Du har tre alternativer:<br /><br /> - **Etter behov**: Vis rullefelt når størrelsen på iFrame er større enn tilgjengelig plass.<br />- **Alltid**: Alltid vis rullefelt.<br />- **Aldri**: Aldri vis rullefelt.|  
||**Vis kantlinje**|Vis en kantlinje rundt iFrame.|  
|**Avhengigheter**|**Avhengige felt**|En iFrame kan samhandle med felt i skjemaet ved hjelp av skript. Hvis et felt fjernes fra skjemaet, kan det hende at skriptet i iFrame ikke fungerer slik det skal. Legg til alle felt som refereres av skript i iFrames, i **Avhengige felt**, slik at de ikke kan fjernes utilsiktet.|  
  
## <a name="pass-parameters-to-iframes"></a>Sende parametere til iFrames  
 Informasjon om oppføringen kan sendes ved å aktivere alternativet **Send typekode for oppføringsobjekt og unik identifikator som parametere**. Verdiene som sendes er:  
  
|Parameter|Beskrivelse|  
|---------------|-----------------|  
|`orglcid`|Standard ID for nasjonale innstillinger for organisasjonen.|  
|`orgname`|Navnet på organisasjonen.|  
|`userlcid`|Brukerens foretrukne ID for nasjonale innstillinger|  
|`type`|Koden for enhetstypen. Denne verdien kan være forskjellig for egendefinerte enheter i ulike organisasjoner. Bruk `typename` i stedet.|  
|`typename`|Navnet på enhetstypen.|  
|`id`|ID-verdien for oppføringen. Denne parameteren har ingen verdi før enhetsoppføringen lagres.|  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
