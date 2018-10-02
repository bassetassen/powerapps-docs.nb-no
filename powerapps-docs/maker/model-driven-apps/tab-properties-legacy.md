---
title: Kategoriegenskaper for skjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå egenskapene for kategori for hovedskjemaer
Keywords: Tab properties; Dynamics 365; Main forms
author: matp
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: Mattp123
manager: kvivek
ms.date: 06/07/2018
ms.service: crm-online
ms.topic: article
ms.assetid: e0790865-c5a4-4e86-bce2-584af2b8ed93
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="tab-properties-for-model-driven-app-forms-overview"></a>Oversikt over kategoriegenskaper for skjemaer for modelldrevne apper

 Kategorier utgjør vannrette skiller i brødteksten i skjemaet. Kategorier har en etikett som kan vises. Hvis etiketten vises, kan du vise eller skjule kategorier for å vise eller skjule innholdet i dem, ved å velge etiketten.  
  
 Kategorier inneholder opptil tre kolonner, og bredden på hver kolonne kan settes til en prosentandel av den totale bredden. Når du oppretter en ny kategori, blir hver kolonne forhåndsutfylt med en inndeling.  

Du kan få tilgang til **Egenskaper for kategori** fra PowerApps-nettstedet. 
1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

     ![Modelldrevet utformingsmodus](media/model-driven-switch.png)

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  

3.  I listen over skjemaer åpner du skjemaet av typen **Hoved**. Dobbeltklikk deretter i en av kategoriene på skjemalerretet for å vise egenskapene for kategori.

    ![tab-properties](media/tab-properties.png)
  
 Tabellen nedenfor viser egenskapene som kan angis for kategorier i skjemaet:
  
|Tabulator|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Vis**|**Navn**|**Nødvendig**: Det unike navnet for kategorien som skal brukes ved referanse til det i skript. Navnet kan bare inneholde alfanumeriske tegn og understrekingstegn.|  
||**Etikett**|**Nødvendig**: Lokaliserbar etikett for kategorien som er synlig for brukerne.|  
||**Vis etiketten for denne kategorien på skjemaet**|Når etiketten vises, kan brukere velge den for å veksle mellom å vise eller skjule kategorien. Velg om du vil vise etiketten.|  
||**Utvid denne kategorien som standard**|Kategoritilstanden kan veksle mellom vist eller skjult ved hjelp av skjemaskript eller ved at brukere velger etiketten. Velg standardtilstanden for kategorien.|  
||**Synlig som standard**|Visning av kategorien er valgfritt og kan styres ved hjelp av skript. Velg om du vil at kategorien skal vises. Mer informasjon: [Synlighetsalternativer](visibility-options-legacy.md)|  
||**Tilgjengelighet**|Velg om du vil at kategorien skal være tilgjengelig på telefonen.|  
|**Formatering**|**Oppsett**|Kategorier kan ha opptil tre kolonner. Bruk disse alternativene til å angi antallet kategorier og hvilken prosentandel av den totale bredden de skal fylle.|  
|**Hendelser**|**Skjemabiblioteker**|Angi alle JavaScript-webressurser som skal brukes i hendelsesbehandlingskategorien `TabStateChange`.<br /><br />|  
||**Hendelsesbehandlinger**|Konfigurer funksjonene fra bibliotekene som skal kalles for kategorien `TabStateChange`-hendelse. Mer informasjon: [Konfigurere hendelsesbehandlinger](configure-event-handlers-legacy.md)|  
  
## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
