---
title: Inndelingsegenskaper for hovedskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå egenskapene for inndeling for et hovedskjema
Keywords: Main form; Section properties; Dynamics 365
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
ms.assetid: 2d3af6e9-e8a4-4129-b708-383b2740c015
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-form-section-properties"></a>Inndelingsegenskaper for skjemaer i modelldrevne apper

 En inndeling i et skjema opptar plassen som er tilgjengelig i en kategorikolonne. Inndelinger har en etikett som kan vises, og det kan vises en linje under etiketten.  
  
 Inndelinger kan ha opptil fire kolonner og inneholde alternativer for å vise hvordan etikettene for felt i inndelingen vises.  
  
 Topptekster og bunntekster er identiske med inndelinger, men kan ikke fjernes. Hvis de ikke inneholder noe, vises de ikke. 

Du kan få tilgang til **Egenskaper for inndeling** fra PowerApps-nettstedet. 
1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

     ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien. 

3.  I listen over skjemaer åpner du skjemaet av typen **Hoved**. Dobbeltklik deretter i en av inndelingene for å vise egenskapene for inndelinger. 

    ![section-properties](media/section-properties.png)
  
|Kategori|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Vis**|**Navn**|**Nødvendig**: Det unike navnet for inndelingen som skal brukes ved referanse til det i skript. Navnet kan bare inneholde alfanumeriske tegn og understrekingstegn.|  
||**Etikett**|**Nødvendig**: Lokaliserbar etikett for inndelingen som er synlig for brukerne.|  
||**Vis etiketten for på inndelingen i skjemaet**|Inndelinger brukes ofte uten etiketter til å styre formatering av feltene i dem.|  
||**Vis en linje øverst i delen**|En linje øverst i en inndeling kan bidra til å dele opp skjemaoppsettet.|  
||**Feltetikettbredde**|**Nødvendig**: Angi en verdi mellom 50 og 250 for å angi tillatt plass for feltetiketter.<br /><br /> Topptekst- og bunntekstelementer har også denne egenskapen.|  
||**Synlighet**|Visning av inndelingen er valgfritt og kan styres ved hjelp av skript. Mer informasjon: [Synlighetsalternativer](visibility-options-legacy.md)|  
||**Tilgjengelighet**|Velg om du vil at kategorien skal være tilgjengelig på telefonen.|  
||**Lås delen i skjemaet**|Dette hindrer at inndelingen utilsiktet blir fjernet, og hindrer at brukere fjerner innholdet.<br /><br /> Fjerning av en inndeling vil ikke bare fjerne inndelingen, men også alle feltene i den.<br /><br /> Noen som ønsker å fjerne denne inndelingen, må endre denne innstillingen før den fjernes.|  
|**Formatering**<br /><br /> Topptekst- og bunntekstkomponenter har også denne egenskapen.|**Oppsett**|Angi opptil fire kolonner som skal være i inndelingen.|  
||**Justering av feltetikett**|Etiketter for felt i inndelingen kan venstrejusteres, høyrejusteres eller midtstilles.|  
||**Plassering av feltetikett**|Etiketter for felt i inndelingen kan være posisjoner ved siden av eller over feltene.|  


En ny type inndeling kalt **Referansepanel**, kan også legges til. Et referansepanele er en enkelt kolonneinndeling. Du kan sette inn delrutenett, hurtigvisningskontroll eller en søkekontroll for kunnskapsbase i en referansepanelinndeling. Hver kontroll du har lagt til i referansepanelet, vises som en loddrett kategori i panelet under kjøring. Du kan dra og slippe ulike kontroller i inndelingen for referansepanelet. Standardkategori ved kjøretid er den første kontrollen som legges til i referansepanelet. De andre kategoriene vises i rekkefølgen de er lagt til i i skjemaredigeringsprogrammet. Hvis du vil slette en kategori, kan du bruke DEL-tasten på tastaturet.  
  
Når du setter inn et referansepanelet, blir det som standard lagt til som den siste inndelingen i kategorien. Du kan legge til bare ett referansepanel per skjema.  
  
> [!IMPORTANT]
>  Som standard er referansepaneldelen låst i disse standardskjemaene: Sak, Forretningsforbindelse og Kontakt. Hvis du vil fjerne det eller endre det, må du låse det opp. 

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
