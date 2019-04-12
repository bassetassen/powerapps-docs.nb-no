---
title: Vanlige egenskaper for felt i modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå de vanlige egenskapene for felt for hovedskjemaer i Dynamics 365 for Customer Engagement
Keywords: Hovedskjema; Egenskaper for vanlig felt; Dynamics 365
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: powerapps
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 2b91ee28-7f09-435e-9fae-5225aa698e22
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-common-field-properties"></a>Vanlige egenskaper for felt i modelldrevne apper

 Feltene i et skjema viser kontroller som brukere bruker til å vise eller redigere data i en enhetsoppføring. Feltene kan formateres slik at de bruker opptil fire kolonner i en inndeling.  

Du kan få tilgang til **vanlige egenskaper for felt** i løsningsutforskeren. Vis **Enheter** under **Komponenter**, utvid deretter ønsket enhet, og klikk deretter **Skjemaer**. I listen over skjemaer åpner du skjemaet av typen **Hoved**. Dobbeltklik deretter ett av feltene for å vise vanlige egenskaper.

![common-field-properties](media/common-field-properties.png)
  
Tabellen nedenfor beskriver egenskaper som alle felt har. Enkelte felttyper har spesielle egenskaper. Dette er beskrevet i [Spesielle feltegenskaper](special-field-properties-legacy.md).  
  
|Tabulator|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Vis**|**Etikett**|**Nødvendig**: Etiketten vil samsvare med visningsnavnet for feltet som standard. Du kan overstyre dette navnet for skjemaet ved å skrive inn en annen etikett her.|  
||**Vis etikett i skjemaet**|Du kan også velge ikke å vise etiketten i det hele tatt.|  
||**Feltets virkemåte**|Angi feltnivåvirkemåten ved hjelp av avmerkingsboksene.|  
||**Låser**|Dette hindrer at feltet fjernes fra skjemaet ved et uhell. Dette hindrer at eventuell konfigurasjon som du har brukt for feltet, for eksempel hendelsesbehandlinger, blir fjernet hvis feltet fjernes. Hvis du vil fjerne dette feltet, må en tilpasser første fjerne denne innstillingen.|  
||**Synlighet**|Visning av feltet er valgfritt og kan styres ved hjelp av skript. Mer informasjon: [Synlighetsalternativer](visibility-options-legacy.md)|  
||**Tilgjengelighet**|Velg om du vil at kategorien skal være tilgjengelig på telefonen.|
|**Formatering**|**Velg antall kolonner som kontrollen bruker**|Når inndelingen som inneholder feltene inneholder flere enn én kolonne, kan du angi at feltet skal bruke opptil antallet kolonner som inndelingen har.|  
|**Detaljer**|**Visningsnavn**, **Navn** og **Beskrivelse**|Disse skrivebeskyttede feltene er for referanse. Klikk **Rediger** for praktisk tilgang til feltdefinisjonen hvis du vil redigere den.<br /><br /> Hver forekomst av et felt i skjemaet har en navneegenskap slik at de kan refereres i skjemaskript, men dette navnet blir styrt av programmet. Den første forekomsten av feltet er navnet på feltet som ble angitt da det ble opprettet. Mer informasjon: [Opprette og redigere felt](../common-data-service/create-edit-fields.md)<br /><br /> Hver gang et felt som legges til i et skjema, tilføyes det et nummer på slutte som starte med 1. Hvis feltnavnet ny_kostnad, er den første forekomsten ny_kostnad, den andre er ny_kostnad1 og så videre, for hver forekomst av feltet i skjemaet.<br /><br />**Merk:** Feltet **Beskrivelse** angir teksten for verktøytipset for feltet når brukere holder markøren over det.|  
|**Hendelser**|**Skjemabiblioteker**|Angi alle JavaScript-webressurser som skal brukes i hendelsesbehandlingsfeltet `OnChange`.<br /><br />|  
||**Hendelsesbehandlinger**|Konfigurer funksjoner fra skjemabibliotekene som skal kalles for felthendelsen `OnChange`. Mer informasjon: [Konfigurere hendelsesbehandlinger](configure-event-handlers-legacy.md)|  
|**Forretningsregler**|**Forretningsregler**|Vis og behandle eventuelle forretningsregler som refererer til dette feltet. Mer informasjon: [Opprette forretningsregler og anbefalinger](create-business-rules-recommendations-apply-logic-form.md)|  
|**Kontroller**|**Kontroller**|Legg til kontroller og angi tilgjengeligheten for dem på nettet, telefon og nettbrett.|  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
