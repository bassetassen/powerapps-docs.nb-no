---
title: Webressursegenskaper for hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå egenskapene for webressurs for hovedskjemaer
Keywords: Hovedskjema; Egenskaper for webressurser; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: powerapps
ms.topic: article
ms.assetid: 82cd41ea-95b0-4606-9e7d-43eb5ce9ecd6
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="web-resource-properties-for-model-driven-app-forms"></a>Webressursegenskaper for skjemaer for modelldrevne apper

Du kan legge til eller redigere webressurser i et skjema for å gjøre det mer tiltalende eller nyttig for appbrukere. Skjemaaktiverte webressurser er bilder eller HTML-filkontroller.

> [!NOTE]
> Silverlight-webressurser er foreldet og vil ikke fungere i Enhetlig grensesnitt-klienten.

## <a name="access-web-resource-properties"></a>Tilgang til webressursegenskaper

Når du viser et skjema:
- **Når du legger til en webressurs:**: Velg kategorien (for eksempel **Generelt** eller **Notater**) du vil sette den inn i, og deretter velger du **Webressurs** i kategorien **Sett inn**.<br />![Sett inn webressurs](media/insert-web-resource.png)
- **Når du redigerer en webressurs**: Velg en skjemakategori og webressursen du vil redigere, og deretter velger du **Endre egenskaper** i kategorien **Hjem**. <br />![Endre webressursegenskaper](media/web-resource-change-properties.png)

Dette åpner dialogboksen **Legg til webressurs** eller **Egenskaper for webressurs**.

![Dialogboksen Legg til webressurs](media/add-web-resource-dialog.png)


## <a name="web-resource-properties"></a>Egenskaper for webressurs

 Dialogboksen **Legg til webressurs** eller **Egenskaper for webressurs** har to og av og til tre kategorier, avhengig av typen webressurs.

### <a name="general-tab"></a>Kategorien Generelt

Disse egenskapene definerer webressursen som skal brukes, og hvordan den skal fungere.

|Felt|Beskrivelse|
|--|--|
|**Webressurs**|*Obligatorisk.* Slå opp en eksisterende webressurs, eller opprett en ny. Bruk visningen **Skjemaaktivert webressurs** for å inkludere bare HTML- og bildewebressurser som kan legges til som visuelle elementer i et skjema.|
|**Navn**|*Obligatorisk.* Angi et navn for webressurskontrollen som skal legges til i skjemaet. Denne verdien identifiserer kontrollen i skjemaet unikt.|
|**Etikett**|*Obligatorisk.* Automatisk generert basert på verdien i **Navn**-feltet. Angi oversettbar tekst for webressurskontrollen som skal legges til i skjemaet. Velg **Vis etikett i skjemaet** hvis du vil at dette skal vises.|
|**Synlig som standard**|Når dette er aktivert, vises webressursen når skjemaet lastes inn. Hvis du har en forretningsregel eller et skjemaskript som viser webressursen etter behov, fjerner du merket for dette feltet. Mer informasjon: [Vise eller skjule skjemaelementer](visibility-options-legacy.md)|
|**Aktiver for mobil**|Velg dette alternativet hvis du vil at webressursen skal være synlig i mobilapper.|

Avhengig av typen webressurs du velger, angi flere egenskaper.

For HTML-webressurser vises dette:

![Egenskaper for HTML-webressurs](media/web-resource-general-html-properties.png)

|Felt|Beskrivelse|
|--|--|
|**Tilpassede parameterdata**|Vanligvis konfigurasjonsdata som skal sendes til HTML-webressursen som en `data`-spørrestrengparameter. Skript som er knyttet til en HTML-side, kan få tilgang til disse dataene og bruke dem til å endre virkemåten på siden.|
|**Begrens skript på tvers av rammer der det støttes**|Bruk dette alternativet hvis du ikke stoler fullt ut på innholdet i HTML-webressursen. Mer informasjon: [Dokumentasjon for utviklere: Velg om skript på tvers av rammer skal begrenses](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#select-whether-to-restrict-cross-frame-scripting)|
|**Send typekode for oppføringsobj. og unik identifikator som parametere**|Data om den gjeldende oppføringen som vises i skjemaet, kan sendes til HTML-webressurssiden, slik at skriptet som kjører på siden, kan få tilgang til data om oppføringen. Mer informasjon: <br />[Sende parametere til webressurser](#pass-parameters-to-web-resources)<br />[Dokumentasjon for utviklere: Sende kontekstavhengig informasjon om oppføringen](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)|

For bildewebressurser kan du angi **Alternativ tekst** som er viktig for assisterende teknologi som gjør siden tilgjengelig for alle.

<!-- TODO: Why are Custom Parameters available to pass to image web resources? -->

### <a name="formatting-tab"></a>Kategorien Formatering

I kategorien **Formatering** vil alternativene som vises, variere avhengig av type webressurs som er satt inn, og konteksten der den er satt inn. Disse alternativene omfatter å angi antall kolonner og rader som skal vises, om det vises en kantlinje og virkemåte for rulling.

![Egenskaper for formatering av webressurs](media/web-resource-formatting-properties.png)

|Egenskap|Beskrivelse|  
|--------------|-----------------|
|**Velg antall kolonner som kontrollen bruker**|Når inndelingen som inneholder webressursen inneholder flere enn én kolonne, kan du angi at feltet skal bruke opptil antallet kolonner som inndelingen har.|  
|**Velg antallet rader kontrollen fyller**|Du kan styre høyden på webressursen ved å angi et antall rader eller velge **Utvid automatisk for å bruke tilgjengelig plass** for å tillate at høyden på webressursen utvides til ledig plass.|  
|**Velg rulletype for IFRAME**|En HTML-webressurs legges til i skjemaet ved hjelp av en IFRAME.<br /><br /> - **Nødvendig**: Vis rullefelt når størrelsen på webressursen er større enn tilgjengelig plass.<br />- **Alltid**: Alltid vis rullefelt.<br />- **Aldri**: Aldri vis rullefelt.|  
|**Vis kantlinje**|Vis en kantlinje rundt webressursen.|  


### <a name="dependencies-tab"></a>Kategorien Avhengigheter

En webressurs kan samhandle med felt i skjemaet ved hjelp av skript. Hvis et felt fjernes fra skjemaet, kan det hende at skriptet i webressursen ikke fungerer slik det skal. Legg til alle felt som refereres av skript i webressursen i **Avhengige felt**, slik at de ikke kan fjernes utilsiktet.

![Egenskaper for webressursavhengighet](media/web-resource-dependency-properties.png)
  
<a name="BKMK_PassingParametersToWebResource"></a> 
 
## <a name="pass-parameters-to-web-resources"></a>Sende parametere til webressurser 

En HTML-webressurs kan godta at parametere sendes som spørringsstrengparametere.  
  
Informasjon om oppføringen kan sendes ved å aktivere alternativet **Send typekode for oppføringsobjekt og unik identifikator som parametere**. Hvis informasjonen skrives inn i feltet **Tilpassede parameterdata**, sendes det ved hjelp av dataparameteren. Verdiene som sendes er:  
  
|Parameter|Beskrivelse|  
|---------------|-----------------|  
|`data`|Denne parameteren sendes bare når det angis tekst for **Tilpassede parameterdata**.|  
|`orglcid`|Standard ID for nasjonale innstillinger for organisasjonen.|  
|`orgname`|Navnet på organisasjonen.|  
|`userlcid`|Brukerens foretrukne ID for nasjonale innstillinger|  
|`type`|**Ikke Bruk dette.** Koden for enhetstypen. Denne numeriske verdien kan være forskjellig for egendefinerte enheter i ulike organisasjoner. Bruk i stedet navn for enhetstype.|  
|`typename`|Navnet på enhetstypen.|  
|`id`|ID-verdien for oppføringen. Denne parameteren har ingen verdi før enhetsoppføringen lagres.|  
  
Andre parametere er ikke tillatt, og webressursen åpnes ikke hvis det brukes andre parametere. Hvis du vil sende flere verdier, kan dataparameteren overbelastes for å inkludere flere parametere i den.

Mer informasjon: [Dokumentasjon for utviklere: Sende kontekstavhengig informasjon om oppføringen](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)

### <a name="see-also"></a>Se også

[Opprette eller redigere webressurser for å utvide en applikasjon](create-edit-web-resources.md)<br />
[Bruke hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
