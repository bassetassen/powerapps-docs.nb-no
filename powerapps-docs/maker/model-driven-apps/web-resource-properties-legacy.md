---
title: Egenskaper for nettressurser for modelldrevne apphovedskjemaer i PowerApps | MicrosoftDocs
description: Slik fungerer egenskaper for nettressurser for hovedskjemaer
Keywords: Main form; Web resource properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 82cd41ea-95b0-4606-9e7d-43eb5ce9ecd6
ms.openlocfilehash: a08ca32b1d300d4302064940e65fd1d067c3ade6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39695576"
---
# <a name="web-resource-properties-for-model-driven-app-forms"></a>Egenskaper for nettressurser for modelldrevne appskjemaer

Du kan legge til eller redigere nettressurser i et skjema for å gjøre det mer innbydende eller nyttig for appbrukere. Skjemaaktiverte nettressurser er bilder eller HTML-filkontroller.

> [!NOTE]
> Silverlight-nettressurser er avskrevet og vil ikke fungere i klienten Enhetlig grensesnitt.

## <a name="access-web-resource-properties"></a>Egenskaper for nettressurs-tilgang

Mens du viser et skjema:
- **Når du legger til en nettressurs:**: Velger du fanen (for eksempel **Generelt** eller **Notater**) du ønsker å sette den inn i, og deretter velger du **Nettressurs** på **Sett inn**-fanen.<br />![Sett inn nettressurs](media/insert-web-resource.png)
- **Når du redigerer en nettressurs**: Velger du en skjemafane og nettressursen du vil redigere, og deretter velger du **Endre egenskaper**, på **Hjem**-fanen. <br />![Endre egenskaper for nettressurs](media/web-resource-change-properties.png)

Dette åpner dialogboksen **Legg til nettressurs** eller **Egenskaper for nettressurs**.

![Legg til dialogboksen Nettressurs](media/add-web-resource-dialog.png)


## <a name="web-resource-properties"></a>Egenskaper for nettressurs

 Dialogboksen **Legg til nettressurs** eller **Egenskaper for nettressurs** inneholder to, noen ganger tre, faner, avhengig av typen nettressurs.

### <a name="general-tab"></a>Generelt-fanen

Disse egenskapene definerer nettressursen du bør bruke og hvordan den bør fungere.

|Felt|Beskrivelse|
|--|--|
|**Nettressurs**|*Nødvendig.* Slå opp en eksisterende nettressurs eller opprett en ny. Bruk visningen **Skjemaaktivert nettressurs** for å inkludere bare HTML- og bildenettressurser som kan legges til som visuelle elementer i et skjema.|
|**Navn**|*Nødvendig.* Angi et navn for nettressurskontrollen som blir lagt til i skjemaet. Denne verdien gir en unik identifikasjon av kontrollen i skjemaet.|
|**Etikett**|*Nødvendig.* Genereres automatisk basert på feltverdien **Navn**. Angi lokaliserbar tekst for nettressurskontrollen, som blir lagt til i skjemaet. Velg **Vis etikett i skjemaet** hvis du vil gjøre denne synlig.|
|**Synlig som standard**|Når dette er aktivert, blir nettressursen synlig når skjemaet lastes inn. Hvis du har en forretningsregel eller et skjemaskript som viser den nødvendige nettressursen, kan du fjerne merket i dette feltet. Mer informasjon: [Vis eller skjul skjemaelementer](visibility-options-legacy.md)|
|**Aktiver for mobil**|Velg dette alternativet for å tillate at nettressursen er synlig i mobilapper.|

Avhengig av hvilken type nettressurs du velger, kan du angi flere egenskaper.

Du vil se disse for HTML-nettressurser:

![Egenskaper for HTML-nettressurser](media/web-resource-general-html-properties.png)

|Felt|Beskrivelse|
|--|--|
|**Tilpassede parameterdata**|Vanligvis konfigurasjonsdata som sendes til HTML-nettressursen som en spørringsstrengparameter for `data`. Skript som er tilknyttet HTML-siden, har tilgang til dataene og bruker dem til å endre hvordan siden fungerer.|
|**Begrens skript på tvers av rammer der dette støttes**|Bruk dette alternativet hvis du ikke stoler helt på innholdet i HTML-nettressursen. Mer informasjon: [Utviklerdokumentasjon: Velg om du vil begrense skript på tvers av rammer](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#select-whether-to-restrict-cross-frame-scripting)|
|**Send objekttypekode for post og unik identifikator som parametere**|Data om den gjeldende posten som er synlig i skjemaet, kan sendes til HTML-nettrettressurssiden, slik at skriptet som kjører på siden, får tilgang til data om posten. Mer informasjon: <br />[Send parametere til nettressurser](#pass-parameters-to-web-resources)<br />[Utviklerdokumentasjon: Send kontekstuell informasjon om posten](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)|

For bildenettressurser har du muligheten til å angi **Alternativ tekst**, som er viktig for hjelpeteknologi, og som gjør siden tilgjengelig for alle.

<!-- TODO: Why are Custom Parameters available to pass to image web resources? -->

### <a name="formatting-tab"></a>Formateringfanen

Alternativene som vises på **Formatering**-fanen, varierer ut ifra hvilken type nettressurs som er satt inn og konteksten der det settes inn. Disse alternativene omfatter angivelse av visning av antall kolonner og rader, om en kantlinje vises og hvordan rulling fungerer.

![Formateringsegenskaper for nettressurs](media/web-resource-formatting-properties.png)

|Egenskap|Beskrivelse|  
|--------------|-----------------|
|**Velg antall kolonner kontrollen bruker**|Når inndelingen som inneholder nettressursen, har mer enn én kolonne, kan du angi at feltet skal bruke opptil det antallet kolonner inndelingen har.|  
|**Velg antall rader kontrollen bruker**|Du kan kontrollere høyden til nettressursen ved å angi antall rader eller velge **Utvid automatisk for å bruke tilgjengelig plass** for å tillate at høyden til nettressursen utvides til tilgjengelig plass.|  
|**Velg rulletype for IFRAME**|En HTML-nettressurs er lagt til i skjemaet ved hjelp av en IFRAME.<br /><br /> - **Etter behov**: Vis rullefelt når størrelsen på nettressursen er større enn den tilgjengelige plassen.<br />- **Alltid**: Vis alltid rullefelt.<br />- **Aldri**: Vis aldri rullefelt.|  
|**Vis kantlinje**|Vis en kantlinje rundt nettressursen.|  


### <a name="dependencies-tab"></a>Avhengigheter-fane

En nettressurs kan samhandle med felt i skjemaet ved å bruke skript. Hvis et felt fjernes fra skjemaet, kan skriptet i nettressursen brytes. Legg til eventuelle felt som skriptene refererer til i nettressursen, i **Avhengige felt**, slik at de ikke kan fjernes ved et uhell.

![Avhengighetsegenskaper for nettressurser](media/web-resource-dependency-properties.png)
  
<a name="BKMK_PassingParametersToWebResource"></a> 
 
## <a name="pass-parameters-to-web-resources"></a>Send parametere til nettressurser 

En HTML-nettressurs kan godta parametere som skal sendes som spørringsstrengparametere.  
  
Informasjon om posten kan sendes ved å aktivere alternativet **Send objekttypekode for post og unike identifikatorer som parametere**. Hvis informasjon skrives inn i **Tilpassede parameterdata**-feltet, sendes dette ved å bruke dataparameteren. Verdiene som sendes, er:  
  
|Parameter|Beskrivelse|  
|---------------|-----------------|  
|`data`|Denne parameteren sendes bare når tekst er angitt for **Tilpassede parameterdata**.|  
|`orglcid`|Organisasjonens standardspråk-LCID.|  
|`orgname`|Navnet på organisasjonen.|  
|`userlcid`|Brukerens foretrukne språk-LCID|  
|`type`|**Ikke bruk dette.** Enhetstypekoden. Denne numeriske verdien kan være ulik for tilpassede enheter i ulike organisasjoner. Bruk enhetstypenavn i stedet.|  
|`typename`|Enhetstypenavnet.|  
|`id`|ID-verdien for posten. Denne parameteren har ingen verdi før enhetsposten er lagret.|  
  
Andre parametere er ikke tillatt og nettressursen åpnes ikke hvis andre parametere brukes. Hvis du trenger å sende flere verdier, kan dataparameteren overbelastes til å inneholde flere parametere.

Mer informasjon: [Utviklerdokumentasjon: Send kontekstuell informasjon om posten](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)

### <a name="see-also"></a>Se også

[Opprett eller rediger nettressurser for å utvide en app](create-edit-web-resources.md)<br />
[Bruk hovedskjemaet og tilknyttede komponenter](use-main-form-and-components.md)
