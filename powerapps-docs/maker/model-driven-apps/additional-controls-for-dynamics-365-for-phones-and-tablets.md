---
title: Flere kontroller for Dynamics 365 for telefoner og nettbrett | MicrosoftDocs
description: En liste over kontroller som er tilgjengelige for bruk med Dynamics 365 for telefoner og nettbrett
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="additional-controls-for-dynamics-365-for-phones-and-tablets"></a>Flere kontroller for Dynamics 365 for telefoner og nettbrett 

 Du kan bruke et omfattende sett med flere kontroller til å opprette en mer berøringsvennlig opplevelse på Dynamics 365 for telefoner og nettbrett. Disse inkluderer skyvekontrollene, brytere, multimediespiller, inndatamasker, kalender og andre kontroller.  

 
> [!NOTE]
>  Du kan bare bruke disse kontrollene med mobilappene. De støttes ikke i webappen.  
  
 Du bruker disse kontrollene i redigeringsprogrammet for skjema:  
  
1.  Dobbeltklikk feltet eller listen du vil legge til kontrollen i.  
  
2.  Klikk kategorien **Kontroller**.  
  
3.  Klikk **Legg til kontroll**.  
  
4.  Merk kontrollene du vil legge til, og klikk deretter **Legg til**.  
  
    > [!NOTE]
    >  Forskjellige kontroller er tilgjengelige avhengig av felt- eller listetypen. Glidebrytere kan for eksempel være tilgjengelig bare for numeriske felt eller pengefelt, og kalenderkontrollen er bare tilgjengelig for lister.  
  
5.  Velg enhetene du vil at kontrollen skal vises på (telefon, nettbrett eller begge deler). Kontroller er ikke tilgjengelig for topptekstfelt for telefon.  
  
6.  Konfigurer verdiene for hver egenskap.  
  
7.  Klikk **OK** når du er ferdig med å konfigurere kontrollen.  
  
 Nedenfor vises beskrivelser for hver kontroll du kan bruke i skjemaer for Dynamics 365 for telefoner og nettbrett.  
  
## <a name="calendar-control"></a>Kalenderkontroll  
 Bruk denne kontrollen til å konfigurere skjemaer slik at de vises som en kalendervisning i Dynamics 365 for telefoner og nettbrett. Du kan også bruke denne kontrollen til å erstatte instrumentbord, lister eller enhetsrutenett for telefoner og nettbrett.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Startdato|Angi startdato og tidspunkt for elementet som skal visualiseres i kalendervisningen. De tilgjengelige verdiene hvilke som helst av kolonnene av datotype i denne visningen.|  
|Sluttdato|Angi sluttdato og tidspunkt for elementet å visualisere i Kalender-visningen. De tilgjengelige verdiene hvilke som helst av kolonnene av datotype i denne visningen.|  
|Varighet|Varigheten (i minutter). Hvis du angir en verdi for sluttdato, ignoreres varighet.|  
|Beskrivelse|Dette er teksten du vil se for kalenderelementer.|  
  
 Minimum varighet som vises i kalenderen, er 30 minutter. Elementer med en varighet på mindre enn 30 minutter, vises likevel som 30 minutter.  
  
 Kalenderkontrollen støtter alle datovirkemåter (brukerlokal, bare dato og tidssoneuavhengig).  
  
## <a name="timeline-control"></a>Tidslinjekontroll  
 Oppgi en tidslinje med nye, aktuelle nyhetsartikler og Twitter-tweeter for en forretningsforbindelse.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|CC_Timeline_Title|Egenskap som skal tilordnes for tittelen for hvert element på tidslinjen.|  
|CC_Timeline_Title_Desc|Beskrivelse for tittelen.|  
|CC_Timeline_Label1|Felt som skal vises under tittelen for elementet på tidslinjen.|  
|CC_Timeline_Label1_Desc|Beskrivelse for etikett 1.|  
|CC_Timeline_Label2|Felt som skal vises etter etikett 1.|  
|CC_Timeline_Label2_Desc|Beskrivelse for etikett 2.|  
|CC_Timeline_Label3|Felt som skal vises etter etikett 2.|  
|CC_Timeline_Label3_Desc|Beskrivelse for etikett 3.|  
|CC_Timeline_Label4|Felt som skal vises etter etikett 3.|  
|CC_Timeline_Label4_Desc|Beskrivelse for etikett 4.|  
|CC_Timeline_Label5|Felt som skal vises etter etikett 4.|  
|CC_Timeline_Label5_Desc|Beskrivelse for etikett 5.|  
|CC_Timeline_Timestamp|Felt som skal brukes til å sortere tidslinjen i omvendt kronologisk rekkefølge.|  
|CC_Timeline_Timestamp_Desc|Beskrivelse for tidsstempelet.|  
|CC_Timeline_Group|Felt for tilordning for gruppering av tidslinjen.|  
|CC_Timeline_Group_Desc|Beskrivelse for Gruppe-feltet.|  
|CC_Timeline_GroupOrder|Rekkefølgen for gruppen varen tilhører i forhold til andre grupper (tilordne verdiene 1, 2, 3 og så videre for grupper som skal vises). Gruppen vises i stigende rekkefølge for gruppeverdiene som er tilordnet.|  
|CC_Timeline_GroupOrder_Desc|Beskrivelse for Grupperekkefølge-feltet.|  
|CC_Timeline_URL|URL-felt som skal tilordnes for å vise URL-adressen for hvert element på tidslinjen.|  
|CC_Timeline_URL_Desc|Beskrivelse for URL-feltet|  
|CC_Timeline_ThumbnailURL|Felt som skal tilordnes for miniatyrbildet av bildet/ikonet skal vises for hvert element.|  
|CC_Timeline_ThumnailURL_Desc|Beskrivelse for `ThumbnailURL`-feltet.|  
|CC_Timeline_Filter|Felt for tilordning for filtrering av tidslinjen.|  
|CC_Timeline_Filter_Desc|Beskrivelse for filteret.|  
|CC_Timeline_Footer|Nettressursen som skal vises som bunnteksten til tidslinjen.|  
|CC_Timeline_Footer_Desc|Beskrivelse for Bunntekst-feltet.|  
  
## <a name="linear-slider"></a>Lineær glidebryter  
 Den lineære glidekontrollen lar brukere legge inn numeriske verdier ved å dra en glidebryter, og har også et alternativ for å skrive inn antallet. Glidebryteren gir bare mulighet til å legge inn og vise heltall. Bruk denne kontrollen for numeriske felt eller pengefelt.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maks|Angi maksimumsverdien som skal vises på glidebryteren.|  
|Min|Angi minimumsverdien som skal vises på glidebryteren.|  
|Verdi|Verdien som skal vises på glidebryteren.|  
|Trinn|Angi mengden som skal legges til eller trekkes fra for den gjeldende verdien når det legges inn data med denne kontrollen.|  
  
## <a name="option-sets"></a>Alternativsett  
 Alternativsettkontrollen viser et sett med valg som brukerne kan velge mellom når de registrerer data. Bruk bare denne kontrollen for alternativsett med to eller tre alternativer.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="flip-switch"></a>Bryter  
 Vendebryteren er som en på/av-bryter, som gir et valg mellom to verdier.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="star-rating"></a>Stjernerangering  
 Bruk stjernervurdering til å gi en visuell representasjon av en vurdering. Maksimalt antall stjerner som du kan angi, er fem. Du kan bare bruke denne kontrollen til heltall. Den kan ikke godta desimalverdier.  
  
> [!NOTE]
>  Pass på å velge alternativet **Skjul på web** for denne kontrollen.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maks|Velg maksimumsantallet stjerner for kontrollen fra rullegardinlisten.|  
  
## <a name="radial-knob"></a>Alternativknapp  
 Den radiale knappen gjør det mulig for brukere å skrive inn data ved å skyve knappen, og vises på skjermen som en sirkel. Den radiale knappekontrollen gir bare mulighet til å legge inn og vise heltall. Bruk denne kontrollen for numeriske felt eller pengefelt. Du kan bruke berøring for å endre verdien, eller du kan bruke tastaturet til å fokusere på nummeret og redigere det.  
  
> [!NOTE]
>  Denne kontrollen støttes ikke på Android 4.2- og 4.3-enheter. Den virker inn på rulleopplevelsen i disse versjonene.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maks|Angi maksimumsverdien som skal vises på måleren.|  
|Min|Angi minimumsverdien som skal vises på måleren.|  
|Verdi|Hent eller angi verdien som skal vises på måleren.|  
|Trinn|Angi mengden som skal legges til eller trekkes fra for den gjeldende verdien når det legges inn data med denne kontrollen.|  
  
## <a name="website-preview"></a>Forhåndsvisning av nettsted  
 Bruk kontrollen for forhåndsvisning av webområde til å tilordne et URL-adressefelt og vise en forhåndsvisning av webområdet.  
  
> [!IMPORTANT]
>  Ved å aktivere denne kontrollen, samtykker du i at brukerne kan dele identifiserbar enhetsinformasjon med et eksternt system. Data som importeres fra eksterne systemer til en PowerApps-app eller Dynamics 365 Customer Engagement, er underlagt personvernreglene våre i [Personvern og informasjonskapsler for Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=521839).  
>   
>  [Personvernerklæringer](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="bullet-graph"></a>Punktdiagram  
 Punktdiagramkontrollen viser ett enkelt nøkkelmål med et sammenlignende mål og kvalitative områder for umiddelbart å signalisere om målet er godt, dårlig, eller i en annen tilstand. Bruk denne kontrollen på instrumentbord, til numeriske felt eller pengefelt. Du kan for eksempel tilordne verdien til faktisk omsetning og målet til beregnet omsetning for å visualisere faktisk kontra beregnet omsetning.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maks|Angi maksimumsverdien som skal vises i diagrammet.|  
|Min|Angi minimumsverdien som skal vises i diagrammet.|  
|Bra|Angi en verdi som anses som bra for målingen (valgfritt).|  
|Dårlig|Angi en verdi som anses som dårlig for målingen (valgfritt).|  
|Verdi|Viser feltet som kontrollen er tilordnet til.|  
|Mål|Tilordne dette til feltet du vil sammenligne verdien med. Hvis **verdi** for eksempel er tilordnet **faktisk omsetning**, kan du tilordne **mål** til **beregnet omsetning**, eller du kan angi en statisk verdi.|  
  
## <a name="pen-control"></a>Pennekontroll  
 Bruk pennkontrollen til å fange opp skriftlige inndata som for eksempel signaturer.  
  
> [!NOTE]
>  Minste anbefalte **maksimumslengde** angitt for feltet som er tilordnet denne kontrollen, er 15000.  
>   
>  Pass på å velge alternativet **Skjul på web** for denne kontrollen.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|PenMode|Angi **PenMode!Draw**, **PenMode!Erase** eller **PenMode!Select** for å finne ut hva som skjer når brukeren drar en pekeenhet i en pennekontroll.|  
  
## <a name="auto-complete"></a>Autofullfør  
 Autofullfør-kontrollen filtrerer en elementliste mens du skriver, og lar deg velge en verdi fra fra rullegardinlisten. Du kan for eksempel bruke denne kontrollen til å la brukerne velge fra en rullegardinliste over delstater eller land/regioner. Denne kontrollen tilordnes til et felt av typen **En enkelt linje med tekst**.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
|Kilde|Angi kilden for dataene (grupperte alternativer, alternativsett eller visning).|  
|Alternativsett|Velg alternativsettet for dette feltet.|  
|Vis|Velg enhet og visning for dette feltet.|  
|Felt|Velg at feltet for visningens primære enhet skal brukes som datakilden.|  
  
## <a name="multimedia"></a>Multimedia  
 Du kan bygge inn videoer for å gi en bedre kundeopplevelse for salg og feltet folk på farten. Bruk denne kontrollen til å tilordne til et felt for URL-adresse som inneholder lyd- eller videokoblingen som skal spilles av i kontrollen.  
  
> [!NOTE]
>  Denne kontrollen støttes bare på Android-versjoner 4.4 og senere.  
>   
>  YouTube-videoer støttes ikke på Windows 8 og Windows 8.1-nettbrett og -telefoner. På Windows 10 støttes for øyeblikket bare HTTPS-videoer (inkludert YouTube).  
  
 Medietyper som støttes, inkluderer:  
  
-   Strømming av MP4-filer  
  
-   YouTube-videoer  
  
-   Azure-medier  
  
-   Lydstrømmer  
  
 [Personvernerklæring](use-the-form-editor-legacy.md#BKMK_PrivacyNotices)  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Medium|Angi URL-adressen til mediet skal spilles av i denne kontrollen.|  
  
## <a name="number-input"></a>Tallinndata  
 Bruk tallinndata-kontrollen til å hjelpe brukere å registrere data raskt. Brukere trenger bare å trykke pluss og minus for å endre en numerisk verdi i intervaller som du angir. Bruk denne kontrollen for numeriske felt eller pengefelt. Brukere kan også skrive inn et tall direkte i feltet. Dette feltet støttes bare i redigeringsmodus.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Trinn|Angi mengden som skal legges til eller trekkes fra for den gjeldende verdien når det legges inn data med denne kontrollen.|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="input-mask"></a>Inndatamaske  
 Med kontrollen inndatamaske, kan du angi formateringen for et felt som telefonnummer eller kredittkort for å forhindre ugyldig dataregistrering. Hvis du for eksempel vil at brukere skal skrive inn et telefonnummer i USA i formatet + 1-222-555-1011, bruker du inndatamasken + 1-000-000-0000.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maske|Angi masken som skal brukes for validering av data etter som brukerne legger dem inn. Du kan bruke en kombinasjon av følgende tegn for masken:<br /><br /> 0 – siffer<br /><br /> 9 – siffer eller mellomrom<br /><br /> # – siffer, tegn eller mellomrom<br /><br /> L – bokstav<br /><br /> I – bokstav eller mellomrom<br /><br /> A – alfanumerisk<br /><br /> A – alfanumerisk eller mellomrom<br /><br /> < – konverterer tegn som følger, til små bokstaver<br /><br /> > – konverterer tegn som følger, til store bokstaver<br /><br /> &#124; – deaktiverer konvertering av bokstavtype<br /><br /> \ – Escape-tegn som overser et hvilket som helst tegn og konverterer det til en litteral<br /><br /> Alle andre – litteraler|  
|Felt|Viser feltet som kontrollen er tilordnet til.|  
  
## <a name="linear-gauge"></a>Lineær måler  
 Den lineær måleren lar brukere legge inn numeriske verdiene ved å dra en glidebryter i stedet for å skrive inn i et eksakt antall. Glidebryteren gir bare mulighet til å legge inn og vise heltall. Bruk denne kontrollen for numeriske felt og pengefelt.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maks|Angi maksimumsverdien som skal vises på måleren.|  
|Min|Angi minimumsverdien som skal vises på måleren.|  
|Verdi|Hent eller angi verdien som skal vises på måleren.|  
|Trinn|Angi mengden som skal legges til eller trekkes fra for den gjeldende verdien når det legges inn data med denne kontrollen.|  
  
## <a name="arc-knob"></a>Buet knapp  
 Den buede knappen gjør det mulig for brukere å skrive inn data ved å skyve knob, og vises på skjermen som en bue. Den buede knappekontrollen gir bare mulighet til å legge inn og vise heltall. Bruk denne kontrollen for numeriske felt og pengefelt. Du kan bruke berøring for å endre verdien, du kan også fokusere på nummeret og redigere det ved hjelp av tastaturet.  
  
> [!NOTE]
> Denne kontrollen støttes ikke på Android 4.2- og 4.3-enheter. Den virker inn på rulleopplevelsen i disse versjonene.  
  
|Egenskap|Beskrivelse|  
|--------------|-----------------|  
|Maks|Angi maksimumsverdien som skal vises på måleren.|  
|Min|Angi minimumsverdien som skal vises på måleren.|  
|Verdi|Hent eller angi verdien som skal vises på måleren.|  
|Trinn|Angi mengden som skal legges til eller trekkes fra for den gjeldende verdien når det legges inn data med denne kontrollen.|  
  
## <a name="next-steps"></a>Neste trinn
[Opplæring: Bruke egendefinerte kontroller for datavisualiseringer](use-custom-controls-data-visualizations.md)
