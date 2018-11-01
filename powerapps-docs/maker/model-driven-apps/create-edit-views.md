---
title: Opprette eller redigere en modelldrevet appvisning i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter eller redigerer en visning
ms.custom: ''
ms.date: 06/11/2018
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
ms.assetid: bd1d393d-16ea-40ac-8136-26643c37dd2a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="understand-model-driven-app-views"></a>Forstå modelldrevne appvisninger

<a name="BKMK_CreatingAndEditingViews"></a>   

Med PowerApps-applikasjoner kan du bruke visninger til å definere hvordan en liste over oppføringer for en bestemt enhet vises i applikasjonen. En visning brukes til å definere følgende:

- Kolonnene som skal vises
- Hvor bred hver kolonne skal være
- Hvordan listen over oppføringer skal sorteres som standard
- Hvilke standardfiltre som skal brukes til å begrense oppføringene som vises i listen

En rullegardinliste over visninger vises ofte i programmet, slik at personer har alternativer for forskjellige visninger av enhetsdata.

Oppføringene som vises i enkeltvisninger, vises i en liste, noen ganger kalt et rutenett. Denne listen inneholder ofte alternativer for å endre standardsortering, kolonnebredder og filtre, slik at det blir enklere for brukerne å se dataene som er viktige for dem. Visninger kan også definere datakilden for diagrammer som brukes i programmet.  
  
## <a name="types-of-views"></a>Visningstyper  
  
Det finnes tre typer visninger: *personlige* visninger, *system*visninger og *felles*visninger.

Dette emnet handler om hvordan systemansvarlige og systemtilpassere arbeider med system- og fellesvisninger. 
  
### <a name="personal-views"></a>Personlige visninger  
  
 Du og alle andre som minst har tilgang på brukernivå til handlinger for enheten for lagret visning, kan også opprette personlige visninger. Som systemansvarlig kan du endre tilgangsnivået for hver handling i sikkerhetsrollen for å kontrollere i hvilken grad personer kan opprette, lese, skrive, slette, tilordne eller dele personlige visninger.

Personlige visninger eies av enkeltpersoner, og siden de har standardtilgangsnivået Bruker, vises de bare for denne personen eller alle andre som vedkommende ønsker å dele sine personlige visninger med. Du kan opprette personlige visninger ved å lagre en spørring du definerer ved hjelp av Avansert søk, eller ved hjelp av alternativene Lagre filtre som ny visning og Lagre filtre i gjeldende visning i listen over visninger. Du finner vanligvis disse visningene nederst i lister over system- eller fellesvisninger som er tilgjengelige i programmet. Du kan opprette en ny personlig visning basert på en system- eller fellesvisning, men du kan ikke opprette en system- eller fellesvisning basert på en personlig visning.
  
### <a name="system-views"></a>Systemvisninger
Som systemansvarlig eller systemtilpasser kan du redigere systemvisninger. Systemvisninger er spesialvisninger som programmet er avhengig av, og som finnes for systemenheter eller opprettes automatisk når du oppretter egendefinerte enheter. Disse visningene har bestemte formål og enkelte tilleggsfunksjoner. 


|Systemvisninger  |Beskrivelse  |
|---------|---------|
|Hurtigsøk     | Standardvisningen som brukes når søk utføres ved hjelp av Hurtigsøk. Denne visningen definerer også feltene det søkes i når du bruker søkefunksjonene i Hurtigsøk- og Oppslag-visninger.        |
|Avansert søk     |  Standardvisningen som brukes til å vise resultater når du bruker Avansert søk. Denne visningen definerer også kolonnene som brukes som standard når nye egendefinerte fellesvisninger eller personlige visninger opprettes uten å definere en visning som skal brukes som mal.       |
|Tilknyttet     |  Standardvisningen som viser relaterte enheter for en oppføring.       |
|Oppslag     | Visningen du ser når du velger en oppføring du vil angi for et oppslagsfelt.        |

Disse visningene vises ikke i visningsvelgeren, og du kan ikke bruke dem i underlister i et skjema eller som en liste på et instrumentbord. Du kan ikke slette eller deaktivere disse visningene. Mer informasjon: [Fjerne visninger](remove-views.md)

Systemvisninger eies av organisasjonen, slik at alle kan se dem. Alle har for eksempel organisasjonsnivåtilgang til å lese oppføringer for enheten for visning (savedquery). Disse visningene er knyttet til bestemte enheter og vises i løsningsutforskeren. Du kan ta med disse visningene i løsninger fordi de er knyttet til enheten.

### <a name="public-views"></a>Fellesvisninger

Fellesvisninger er generelle visninger du kan tilpasse etter eget behov. Disse visningene er tilgjengelige i visningsvelgeren, og du kan bruke dem i delrutenett i et skjema eller som en liste på et instrumentbord. Enkelte fellesvisninger finnes som standard for systemenheter og alle egendefinerte enheter. Når du for eksempel oppretter en ny egendefinert enhet, har den følgende kombinasjon av felles- og systemvisninger.


|Navn  |Type  |
|---------|---------|
|Aktiv *enhetens flertallsnavn*     |  Offentlig       |
|Inaktiv *enhetens flertallsnavn*    |  Offentlig       |
|Hurtigsøk etter aktive *enhetens flertallsnavn*     | Hurtigsøk        |
|*enhetsnavn* Visning for avansert søk     | Avansert søk        |
|*enhetsnavn* Tilknyttet visning     |  Tilknyttet       |
|*enhetsnavn* Oppslagsvisning     | Oppslag        |

Du kan opprette egendefinerte fellesvisninger. Du kan slette egendefinerte fellesvisninger du oppretter i en uadministrert løsning. Du kan ikke slette systemdefinerte fellesvisninger. Egendefinerte fellesvisninger som er tilføyd ved å importere en administrert løsning, kan ha forvaltede egenskaper angitt som gjør at de kanskje ikke kan slettes, med mindre du avinstallerer den administrerte løsningen.

## <a name="places-where-you-can-access-the-view-editor-to-create-or-edit-views"></a>Steder der du kan få tilgang til visningsredigeringsprogrammet for å opprette eller redigere visninger

- PowerApps-området: Du kan få tilgang til visningsredigeringsprogrammet i **Modelldrevet**-området > **Data** > **Enheter** > **Vis**-kategorien. Åpne en eksisterende visning, eller opprett en ny. Mer informasjon: [Opprette eller redigere en visning](create-and-edit-views.md)
- Apputforming: Hvis du jobber i en app, vil du kanskje bruke apputformingen, som inneholder et enkelt og brukervennlig grensesnitt med dra-og-slipp-funksjoner for opprettede visninger. Mer informasjon: [Opplæring: Opprette og redigere offentlige visninger eller systemvisninger ved hjelp av apputforming](create-edit-views-app-designer.md)
- Løsningsutforsker: Hvis du allerede har erfaring med Dynamics 365, vil du kanskje bruke løsningsutforskeren. Mer informasjon: [Navigere til avanserte områder for apputvikling og -tilpassing](advanced-navigation.md#solution-explorer)
 
## <a name="customize-views"></a>Tilpasse visninger

Du kan som systemtilpasser tilpasse visningene via kontroller, ved å gjøre rutenett (lister) redigerbare og kompatible for enhetlig grensesnitt. Følgende kontroller brukes:

- Redigerbart rutenett: Lar brukere gjøre omfattende redigering direkte fra rutenett og delrutenett, om de bruker en webapp, et nettbrett eller en telefon. Mer informasjon: [Gjøre rutenett redigerbare ved hjelp av Egendefinert kontroll for redigerbart rutenett](make-grids-lists-editable-custom-control.md)
- Skrivebeskyttet rutenett: Gir brukere en optimal visnings- og samhandlingsopplevelse for alle skjermstørrelser eller -retninger, for eksempel mobiltelefoner og nettbrett, ved hjelp av utformingsprinsipper. Mer informasjon: [Angi egenskaper for Enhetlig grensesnitt-apper](specify-properties-for-unified-interface-apps.md)

## <a name="next-steps"></a>Neste trinn

[Opprette eller redigere visninger](create-and-edit-views.md)
