---
title: Egenskaper som er tilgjengelige i skjemautformingen | MicrosoftDocs
ms.custom: ''
ms.date: 02/19/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="properties-available-in-the-form-designer"></a>Egenskaper som er tilgjengelige i skjemautformingen

Med egenskapsruten, som befinner seg til høyre i den modelldrevne skjemautformingen, kan du raskt vise og oppdatere egenskapene for elementer som er valgt fra forhåndsvisningen eller navigasjonsrutene. 

> [!div class="mx-imgBorder"] 
> ![](media/form-designer-property-pane.png "Egenskapsruten for skjemautforming")

## <a name="form-properties"></a>Skjemaegenskaper


|Navn  |Beskrivelse  |
|---------|---------|
|**Tittel**     | Skriv inn et navn som gir mening for brukere. Dette navnet vises for brukere når de bruker skjemaet. Hvis de kan bruke flere skjemaer som er konfigurert for enheten, bruker de dette navnet til å skille mellom tilgjengelige skjemaer. <br /> Denne egenskapen er obligatorisk.        |
|**Beskrivelse**     |  Skriv inn en beskrivelse som forklarer hvordan dette skjemaet er forskjellig fra andre hovedskjemaer. Denne beskrivelsen vises bare i listen over skjemaer for en enhet i løsningsutforskeren.        |
|**Maksbredde**     | Angi en maksimumsbredde (i piksler) for å begrense bredden på skjemaet. Standardverdien er 1 900. <br /> Denne egenskapen er obligatorisk.       |
|**Vis bilde**      | Vise enhetens **Hovedbilde** hvis angitt. Denne innstillingen aktiverer visning av bildefeltet i toppteksten for dette skjemaet. <br /> Se Aktivere eller deaktivere enhetsalternativer hvis du vil ha mer informasjon om alternativene for enheten.         |


## <a name="tab-properties"></a>Egenskaper for kategori

|Area   |Navn  |Beskrivelse  |
|---------|---------|---------|
|**Visningsalternativer**      | **Kategorietikett**      | Lokaliserbar etikett for kategorien som er synlig for brukerne. <br /> Denne egenskapen er obligatorisk.         |
| **Visningsalternativer**      |  **Navn**     |  Det unike navnet for kategorien som skal brukes ved referanse til det i skript. Navnet kan bare inneholde alfanumeriske tegn og understrekingstegn. <br />Denne egenskapen er obligatorisk.      |
| **Visningsalternativer**      |  **Utvid denne kategorien som standard**      |  Kategoritilstanden kan veksle mellom vist eller skjult ved hjelp av skjemaskript eller ved at brukere velger etiketten. Velg standardtilstanden for kategorien.       |
| **Visningsalternativer**      | **Skjul kategori**     | Når dette er valgt, skjules kategorien som standard og kan vises med kode.       |
| **Visningsalternativer**      | **Skjul på telefon**     |  For en komprimert versjon av skjemaet på telefonskjermer kan kategorier skjules.     |
| **Formatering**   | **Oppsett**     |  Kategorier kan ha opptil tre kolonner. Bruk disse alternativene til å angi antallet kategorier og hvilken prosentandel av den totale bredden de skal fylle.      |

## <a name="section-properties"></a>Egenskaper for inndeling


|Area   |Navn  |Beskrivelse  |
|---------|---------|---------|
|**Visningsalternativer**      | **Deletikett**    | Lokaliserbar etikett for delen som er synlig for brukerne. <br /> Denne egenskapen er obligatorisk.      |
|**Visningsalternativer**      | **Navn**    | Det unike navnet for delen som skal brukes ved referanse til den i skript. Navnet kan bare inneholde alfanumeriske tegn og understrekingstegn. <br /> Denne egenskapen er obligatorisk.        |
|**Visningsalternativer**      | **Skjul etikett**   |  Når dette er valgt, skjules deletiketten.  |
|**Visningsalternativer**      | **Lås del**    | Lås denne delen slik at den ikke blir fjernet.      |
|**Visningsalternativer**      | **Skjul del**     | Når dette er valgt, skjules delen som standard og kan vises med kode.      |
|**Visningsalternativer**      | **Skjul på telefon**     |  For en komprimert versjon av skjemaet på telefonskjermer kan deler skjules.     |
|**Formatering**     |  **Kolonner**    |  Angi opptil fire kolonner som skal være i inndelingen.      |

## <a name="field-properties"></a>Feltegenskaper


|Area  |Navn  |Beskrivelse  |
|---------|---------|---------|
|**Visningsalternativer**     | **Feltetikett**    | Etiketten vil samsvare med visningsnavnet for feltet som standard. Du kan overstyre dette navnet for skjemaet ved å skrive inn en annen etikett her.       |
|**Visningsalternativer**     |  **Feltnavn**    | Navnet på feltet. Dette kommer fra feltegenskapene på enheten og er skrivebeskyttet.     |
|**Visningsalternativer**     | **Skjul etikett**     | Når dette er valgt, skjules feltetiketten.      |
|**Visningsalternativer**     | **Skrivebeskyttet felt**    | Når dette er valgt, kan ikke feltverdien redigeres.      |
|**Visningsalternativer**     |  **Lås felt**   |  Lås dette feltet slik at det ikke blir fjernet.     |
|**Visningsalternativer**     |  **Skjul felt**     | Når dette er valgt, skjules feltet som standard og kan vises med kode.      |
|**Visningsalternativer**     |  **Skjul på telefon**    | For en komprimert versjon av skjemaet på telefonskjermer kan felt skjules.         |
|**Visningsalternativer**     | **Feltbredde**      |  Når inndelingen som inneholder feltene inneholder flere enn én kolonne, kan du angi at feltet skal bruke opptil antallet kolonner som inndelingen har.       |


## <a name="see-also"></a>Se også
[Oversikt over den modelldrevne skjemautformingen](form-designer-overview.md) <br />
[Opprette eller redigere skjemaer ved hjelp av skjemautforming](create-and-edit-forms.md)
