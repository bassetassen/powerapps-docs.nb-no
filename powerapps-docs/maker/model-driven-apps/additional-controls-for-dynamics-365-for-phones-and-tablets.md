---
title: Flere kontroller for Dynamics 365 for telefoner og nettbrett | MicrosoftDocs
description: En liste over kontroller som er tilgjengelig for bruk med Dynamics 365 for telefoner og nettbrett
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 7920ef78-2540-48ad-ba25-9ce9cb995ed1
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: d6293f1fc0913a7e2f66e3830702458e3249f0f0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691184"
---
# <a name="additional-controls-for-dynamics-365-for-phones-and-tablets"></a>Flere kontroller for Dynamics 365 for telefoner og nettbrett 

 Du kan bruke et omfattende sett med flere kontroller til å opprette en mer berøringsvennlig opplevelse på Dynamics 365 for telefoner og nettbrett. Disse inkluderer glidebrytere, brytere, multimediaspillere, inndatamasker, kalender og andre kontroller.  

 
> [!NOTE]
>  Du kan bare bruke disse kontrollene med mobilappene. De støttes ikke i nettappen.  
  
 Slik bruker du disse kontrollene i redigeringsprogrammet for skjema:  
  
1.  Dobbeltklikk på feltet eller listen du ønsker å legge til kontrollene i.  
  
2.  Klikk på **Kontroller**-fanen.  
  
3.  Klikk på **Legg til kontroll**.  
  
4.  Velg kontrollen du ønsker, og klikk deretter på **Legg til**.  
  
    > [!NOTE]
    >  Forskjellige kontroller er tilgjengelig avhengig av felt- eller listetypen. Glidebryterkontroller kan for eksempel bare være tilgjengelig for numeriske felter eller pengefelter, og kalenderkontrollen er bare tilgjengelig for lister.  
  
5.  Velg enhetene du vil at kontrollen skal vises på (telefon, nettbrett eller begge deler). Kontroller er ikke tilgjengelige for telefonoverskriftsfelter.  
  
6.  Konfigurer verdiene for hver egenskap.  
  
7.  Klikk på **OK** når du er ferdig med å konfigurere kontrollen.  
  
 Dette er beskrivelser for hver kontroll som du kan bruke i skjemaer for Dynamics 365 for telefoner og nettbrett.  
  
## <a name="calendar-control"></a>Kalenderkontrollen  
 Bruk denne kontrollen til å konfigurere skjemaer slik at de vises som en kalendervisning i Dynamics 365 for telefoner og nettbrett. Du kan også bruke denne kontrollen til å erstatte instrumentbord, lister eller enhetsrutenett for telefoner og nettbrett.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Startdato|Definer startdatoen og klokkeslettet for elementet for å visualisere i kalendervisningen. Tilgjengelige verdier er hvilke som helst av kolonnene i denne visningen av typedato.|  
|Sluttdato|Definer sluttdatoen og klokkeslettet for elementet for å visualisere i kalendervisningen. Tilgjengelige verdier er hvilke som helst av kolonnene i denne visningen av typedato.|  
|Varighet|Varigheten i minutter. Hvis du angir en verdi for Sluttdato, ignoreres Varighet.|  
|Beskrivelse|Dette er teksten du ser for elementer i kalenderen.|  
  
 Den korteste varigheten som vises i kalenderen, er 30 minutter. Elementer med en varighet på mindre enn 30 minutter, vil fortsatt vises med en varighet på 30 minutter.  
  
 Kalenderkontrollen støtter alle datovirkemåter (bruker lokal, bare dato, og tidssoneuavhengig).  
  
## <a name="timeline-control"></a>Tidslinje-kontrollen  
 Vis en tidslinje for nylige, relevante nyhetsartikler og Twitter-tweeter for en konto.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|CC_Timeline_Title|Egenskap som skal tilordnes for tittelen på hvert element på tidslinjen.|  
|CC_Timeline_Title_Desc|Beskrivelse for Tittel.|  
|CC_Timeline_Label1|Feltet som skal vises under tittelen på tidslinjeelementet.|  
|CC_Timeline_Label1_Desc|Beskrivelse for Etikett 1.|  
|CC_Timeline_Label2|Feltet som skal vises etter Etikett 1.|  
|CC_Timeline_Label2_Desc|Beskrivelse for Etikett 2.|  
|CC_Timeline_Label3|Feltet som skal vises etter Etikett 2.|  
|CC_Timeline_Label3_Desc|Beskrivelse for Etikett 3.|  
|CC_Timeline_Label4|Feltet som skal vises etter Etikett 3.|  
|CC_Timeline_Label4_Desc|Beskrivelse for Etikett 4.|  
|CC_Timeline_Label5|Feltet som skal vises etter Etikett 4.|  
|CC_Timeline_Label5_Desc|Beskrivelse for Etikett 5.|  
|CC_Timeline_Timestamp|Felt som skal brukes til å sortere tidslinjen i motsatt kronologisk rekkefølge.|  
|CC_Timeline_Timestamp|Beskrivelse for Tidsstempel.|  
|CC_Timeline_Group|Felt som skal tilordnes for grupperingstidslinje.|  
|CC_Timeline_Group_Desc|Beskrivelse for Gruppe-feltet.|  
|CC_Timeline_GroupOrder|Rekkefølgen på gruppen elementet tilhører i forhold til andre grupper (tilordne verdiene 1, 2, 3, og så videre for grupper som skal vises). Gruppen vises i stigende verdien for verdier som er tilordnet for gruppen.|  
|CC_Timeline_GroupOrder_Desc|Beskrivelse for Grupperekkefølge-feltet.|  
|CC_Timeline_URL|Nettadressen som skal tilordnes for å vise nettadressen for hvert tidslinjeelement.|  
|CC_Timeline_URL_Desc|Beskrivelse for Nettadresse-feltet.|  
|CC_Timeline_ThumbnailURL|Felt som skal tilordnes for miniatyrbilde av bilde/ikon som skal vises for hvert element.|  
|CC_Timeline_ThumnailURL_Desc|Beskrivelse for `ThumbnailURL`-feltet.|  
|CC_Timeline_Filter|Felt som skal tilordnes for tidslinjefilteret.|  
|CC_Timeline_Filter_Desc|Beskrivelse for Filter.|  
|CC_Timeline_Footer|Nettressursen skal vises som bunnteksten på tidslinjen.|  
|CC_Timeline_Footer_Desc|Beskrivelse for Bunntekst-feltet.|  
  
## <a name="linear-slider"></a>Lineær glidebryter  
 Ved bruk av den lineære glidebryteren kan brukerne dine angi numeriske verdier ved å dra en glidebryter, og de kan også skrive inn antallet. Med glidebryteren kan de kun angi heltall og se en visning av tallene. Bruk denne kontrollen for et hvilket som helst numeriske felt eller pengefelt.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|maks|Angi maksimumsverdien som skal vises på glidebryteren.|  
|Min.|Angi minimumsverdien som skal vises på glidebryteren.|  
|Verdi|Angi verdien som vises på glidebryteren.|  
|Trinn|Angi beløpet som skal legges til eller trekkes fra den gjeldende verdien, når du skriver inn data med denne kontrollen.|  
  
## <a name="option-sets"></a>Alternativsett  
 Alternativsettkontrollen viser et sett med valg for brukerne når de skriver inn data. Bruk denne kontrollen for alternativsett med bare to eller tre alternativer.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="flip-switch"></a>Bryteren  
 Bryteren er som en på-av-bryter, og gir et valg mellom to verdier.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="star-rating"></a>Stjerneklassifisering  
 Bruk stjerneklassifiseringen for å gi en visuell representasjon av en vurdering. Du kan bare angi maksimalt fem stjerner. Du kan bruke denne kontrollen bare for heltall. Den godtar ikke desimalverdier.  
  
> [!NOTE]
>  Sørg for at du merker av for **Skjul på nettet** for denne kontrollen.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|maks|Velg maksimalt antall stjerner for kontrollen fra rullegardinlisten.|  
  
## <a name="radial-knob"></a>Radial knapp  
 Ved bruk av den radiale knappen kan brukerne angi data ved å skyve knappen, og den vises som en sirkel på skjermen. Med kontrollen for radial knapp kan de angi heltallinndata og se en visning av tallene. Bruk denne kontrollen for eventuelle numeriske felter eller pengefelter. Du kan bruke berøring til å endre verdien, eller du kan bruke tastaturet til å fokusere på tallet og redigere det.  
  
> [!NOTE]
>  Denne kontrollen støttes ikke på Android 4.2- og 4.3-enheter. Det påvirker rulleopplevelsen på disse versjonene.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|maks|Angi maksimumsverdien som skal vises på måleren.|  
|Min.|Angi minimumsverdien som skal vises på måleren.|  
|Verdi|Hent eller angi verdien som skal vises på måleren.|  
|Trinn|Angi beløpet som skal legges til eller trekkes fra den gjeldende verdien, når du skriver inn data med denne kontrollen.|  
  
## <a name="website-preview"></a>Forhåndsvisning av nettsted  
 Bruk kontrollen for forhåndsvisning av nettsted for å tilordne et nettadressefelt og vise en forhåndsvisning av nettstedet.  
  
> [!IMPORTANT]
>  Ved å aktivere denne kontrollen samtykker du i at brukerne kan dele identifiserbar enhetsinformasjon med et eksternt system. Data som importeres fra eksterne systemer og inn i PowerApps-appen eller Dynamics 365 Customer Engagement, er underlagt vår personvernerklæring på [Personvernerklæring og retningslinjer for informasjonskapsler for Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=521839).  
>   
>  [Personvernerklæring](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="bullet-graph"></a>Sammenlignende målediagram  
 Det sammenlignende målediagrammet kontrollerer én enkel og viktig måling med en sammenlignende måling og kvalitative områder. Dette viser umiddelbart om målingen er bra, dårlig eller i en annen tilstand. Bruk denne kontrollen på instrumentbord for eventuelle numeriske felt eller pengefelt. Du kan for eksempel tilordne verdien til en faktisk omsetning og målet til en anslått omsetning, for å visualisere faktisk omsetning kontra anslått omsetning.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|maks|Angi maksimumsverdien som skal vises på målediagrammet.|  
|Min.|Angi minimumsverdien som skal vises på målediagrammet.|  
|God|Angi en verdi som anslås som bra for målingen (valgfritt).|  
|Dårlig|Angi en verdi som anslås som dårlig for målingen (valgfritt).|  
|Verdi|Viser feltet som kontrollen er tilordnet til.|  
|Mål|Tilordne dette til feltet du ønsker å sammenligne verdien med. Hvis **Verdi** for eksempel er tilordnet til **Faktisk omsetning**, kan du tilordne **Mål** til **Anslått omsetning**, eller du kan oppgi en statisk verdi.|  
  
## <a name="pen-control"></a>Pennekontrollen  
 Bruk pennekontrollen til å registrere skriftlig inndata som signaturer.  
  
> [!NOTE]
>  Minimum anbefalte **maksimumslengde** som er angitt for feltet denne kontrollen er tilordnet til, er 15 000.  
>   
>  Sørg for at du merker av for **Skjul på nettet** for denne kontrollen.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Pennemodus|Angi **PenMode!Draw**, **PenMode!Erase** eller **PenMode!Select** for å fastslå hva som skjer når en bruker drar en pekeenhet i en pennekontroll.|  
  
## <a name="auto-complete"></a>Autofullfør  
 Kontrollen for autofullfør filtrerer et elementliste mens du skriver inn verdier, og du kan velge en verdi fra rullegardinlisten. Brukerne kan for eksempel bruke denne kontrollen til å velge fra en rullegardinliste over delstater eller land/områder. Denne kontrollen tilordnes til typefeltet **Enkeltlinje med tekst**.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
|Kilde|Angi kilden for dataene (grupperte alternativer, alternativsett eller visning).|  
|Alternativsett|Velg alternativsettet for dette feltet.|  
|Vis|Velg enheten og visningen for dette feltet.|  
|Felt|Velg feltet til visningens primærenhet for å bruke det som datakilden.|  
  
## <a name="multimedia"></a>Multimedia  
 Du kan bygge inn videoer for å gi en rikere kundeopplevelse for salgs- og feltmedarbeidere som er på farten. Bruk denne kontrollen til å tilordne et felt for nettadressen som inneholder lyd- eller videokoblingen, som skal spilles av i kontrollen.  
  
> [!NOTE]
>  Denne kontrollen støttes på Android-versjoner 4.4 og nyere.  
>   
>  YouTube-videoer støttes ikke for øyeblikket på nettbrett og telefoner som kjører Windows 8 og Windows 8.1. På Windows 10 støttes bare HTTPS-videoer (inkludert YouTube).  
  
 Støttede medietyper inkluderer:  
  
-   Strømmende MP4-filer  
  
-   YouTube-videoer  
  
-   Azure-media  
  
-   Lydstrømmer  
  
 [Personvernerklæring](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Medier|Skriv inn nettadressen til mediet som skal spilles av i denne kontrollen.|  
  
## <a name="number-input"></a>Tallinndata  
 Bruk tallinndatakontrollen for å hjelpe brukerne med å skrive inn data raskt. Brukerne trenger bare å trykke på pluss- og minusknappene for å endre en numerisk verdi i de intervallene du angir. Bruk denne kontrollen for et hvilket som helst numeriske felt eller pengefelt. Brukerne kan også skrive inn et tall direkte i feltet. Dette feltet støttes bare i redigeringsmodus.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Trinn|Angi beløpet som skal legges til eller trekkes fra den gjeldende verdien, når du skriver inn data med denne kontrollen.|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="input-mask"></a>Inndatamaske  
 Med inndatamasken angir du formateringen for et felt som telefonnummer eller kredittkort, slik at du unngår at noen skriver inn ugyldig data. Hvis du vil at brukere skal oppgi et telefonnummer fra USA i formatet + 1-222-555-1011, bruker du for eksempel inndatamasken + 1-000-000-0000.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maske|Angi masken som skal brukes for validering av dataene brukerne skriver inn. Du kan bruke en kombinasjon av følgende tegn for masken:<br /><br /> 0 – Tegn<br /><br /> 9 – Tegn eller mellomrom<br /><br /> # – Tegn, merke eller mellomrom<br /><br /> L – Bokstav<br /><br /> I – Bokstav eller mellomrom<br /><br /> A – Alfanumerisk<br /><br /> A – Alfanumerisk eller mellomrom<br /><br /> < – Konverterer etterfølgende tegn til små bokstaver<br /><br /> > – Konverterer etterfølgende tegn til store bokstaver<br /><br /> &#124; – Deaktiverer endring av bokstavstørrelse<br /><br /> \ – Avbryter alle tegn, gjør det om til et litteral<br /><br /> Alle andre – Litteraler|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="linear-gauge"></a>Lineær måler  
 Med den lineære måleren kan brukere skrive inn numeriske verdier ved å dra i en glidebryter, i stedet for å skrive inn i det nøyaktige antallet. Med glidebryteren kan de kun angi heltall og se en visning av tallene. Bruk denne kontrollen for eventuelle numeriske felter og pengefelter.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|maks|Angi maksimumsverdien som skal vises på måleren.|  
|Min.|Angi minimumsverdien som skal vises på måleren.|  
|Verdi|Hent eller angi verdien som skal vises på måleren.|  
|Trinn|Angi beløpet som skal legges til eller trekkes fra den gjeldende verdien, når du skriver inn data med denne kontrollen.|  
  
## <a name="arc-knob"></a>Buet knapp  
 Ved bruk av den buede knappen kan brukerne angi data ved å skyve knappen, og den vises som en bue på skjermen. Med kontrollen for buet knapp kan de angi heltallinndata og se en visning av tallene. Bruk denne kontrollen for eventuelle numeriske felter og pengefelter. Du kan bruke berøring til å endre verdien, og du kan også fokusere på tallet og redigere det ved bruk av tastaturet.  
  
> [!NOTE]
> Denne kontrollen støttes ikke på Android 4.2- og 4.3-enheter. Det påvirker rulleopplevelsen på disse versjonene.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|maks|Angi maksimumsverdien som skal vises på måleren.|  
|Min.|Angi minimumsverdien som skal vises på måleren.|  
|Verdi|Hent eller angi verdien som skal vises på måleren.|  
|Trinn|Angi beløpet som skal legges til eller trekkes fra den gjeldende verdien, når du skriver inn data med denne kontrollen.|  
  
## <a name="next-steps"></a>Neste trinn
[Opplæring: Bruk egendefinerte kontroller for datavisualiseringer](use-custom-controls-data-visualizations.md)