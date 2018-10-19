---
title: Opprette eller redigere en modelldrevet appvisning i PowerApps | MicrosoftDocs
description: Finn ut hvordan du oppretter eller redigerer en visning
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
ms.openlocfilehash: 215f927b68decac864a2f1b667f64a7649827682
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39694744"
---
# <a name="understand-model-driven-app-views"></a>Forstå modelldrevne appvisninger

<a name="BKMK_CreatingAndEditingViews"></a>   

Med PowerApps-apper kan du bruke visninger til å definere hvordan en liste med oppføringer for en bestemt enhet vises i applikasjonen. En visning definerer:

- Kolonnene som vises
- Hvor bred hver kolonne skal være
- Hvordan listen over poster skal standardsorteres
- Hvilke standardfiltre som skal brukes for å begrense hvilke poster som vises i listen

En rullegardinliste over visninger vises ofte i programmet slik at man har alternativer for ulike visninger av enhetsdata.

Postene som er synlige i individuelle visninger, vises i en liste, noen ganger kalt et rutenett, som ofte inneholder alternativer slik at brukere kan endre standard sortering, kolonnebredder og filtre, slik at det blir enklere å se dataene som er viktige. Visninger definerer også datakilden for diagrammene som brukes i programmet.  
  
## <a name="types-of-views"></a>Typer av visninger  
  
Det finnes tre typer visninger: *personlig visning*, *systemvisning*, og *offentlig visning*.

Dette emnet omhandler hvordan systemansvarlige og systemtilpassere arbeider med systemvisninger og offentlige visninger. 
  
### <a name="personal-views"></a>Personlige visninger  
  
 Du og andre som har tilgang til handlinger for Lagret visning-enheten på brukernivå eller høyere, kan også opprette personlige visninger. Som systemansvarlig kan du endre tilgangsnivå for hver handling i sikkerhetsrollen, slik at du kan kontrollere graden i hvilken grad brukere kan opprette, lese, skrive, slette, tilordne eller dele personlige visninger.

Personlige visninger eies av enkeltpersoner, og fordi de som standard har tilgang på brukernivå, er visningene bare synlige for den personen eller de som vedkommende velger å dele sine personlige visninger med. Du kan opprette personlige visninger ved å lagre en spørring som du definerer ved hjelp av Avansert søk, eller ved hjelp av alternativene Lagre filtre som nye visninger og Lagre filtre til gjeldende visning i listen over visninger. Disse visningene er vanligvis inkludert nederst i lister over systemvisninger eller offentlige visninger som er tilgjengelige i programmet. Selv om du kan opprette en ny personlig visning basert på en systemvisning eller offentlig visning, kan du ikke opprette en systemvisning eller offentlig visning basert på en personlig visning.
  
### <a name="system-views"></a>Systemvisninger
Som systemansvarlig eller systemtilpasser kan du redigere systemvisninger. Systemvisninger er spesielle visninger som programmet er avhengig av, som finnes for systemenheter eller opprettes automatisk når du oppretter egendefinerte enheter. Disse visningene har bestemte formål og noen tilleggsmuligheter. 


|Systemvisninger  |Beskrivelse  |
|---------|---------|
|Hurtigsøk     | Standardvisningen brukes når søk gjøres med Hurtigsøk. Denne visningen definerer også hvilke felt som søkes i når du bruker søkefunksjonene i visningene Hurtigsøk og Oppslag.        |
|Avansert søk     |  Standardvisningen brukes til å vise resultater når du bruker Avansert Søk. Denne visningen definerer også kolonnene som skal brukes som standard når nye egendefinerte offentlige visninger eller personlige visninger opprettes uten å definere en visning som skal brukes som en mal.       |
|Tilknyttede logger     |  Standardvisningen som viser en liste over relaterte enheter for en post.       |
|Oppslag     | Visningen du ser når du velger en post som skal angis for et oppslagsfelt.        |

Disse visningene vises ikke i visningsvelgeren, og du kan ikke bruke dem i underlister i et skjema eller som en liste på et instrumentbord. Du kan ikke slette eller deaktivere disse visningene. Mer informasjon: [Fjerne visninger](remove-views.md)

Systemvisninger eies av organisasjonen, slik at alle kan se dem. Alle har for eksempel tilgang på organisasjonsnivå til å lese poster for visningselementet (savedquery). Disse visningene er knyttet til spesifikke enheter og er synlige i Løsningsutforsker. Du kan inkludere disse visningene i løsninger fordi de er knyttet til enheten.

### <a name="public-views"></a>Offentlige visninger

Offentlige visninger er visninger til generell bruk som du kan tilpasse slik du ønsker. Disse visningene er tilgjengelige i visningsvelgeren, og du kan bruke dem i underlister i et skjema eller som en liste på et instrumentbord. Det finnes noen offentlige visninger som er tilgjengelige som standard for systemenheter og egendefinerte enheter. Når du oppretter en ny egendefinert enhet, vil den for eksempel ha følgende kombinasjon av offentlige visninger og systemvisninger.


|Navn  |Type  |
|---------|---------|
|Aktive *flertall navn på enhet*     |  Offentlig       |
|Inaktive *flertall navn på enhet*    |  Offentlig       |
|Hurtigsøk Aktive *flertall navn på enhet*     | Hurtigsøk        |
|*navn på enhet* Avansert søk-visning     | Avansert søk        |
|*navn på enhet* Tilknyttet visning     |  Tilknyttede logger       |
|*navn på enhet* Oppslagsvisning     | Oppslag        |

Du kan opprette egendefinerte offentlige visninger. Du kan slette egendefinerte offentlige visninger du oppretter i en ikke-administrert løsning. Du kan ikke slette systemdefinerte offentlige visninger. Egendefinerte offentlige visninger som er lagt til ved å importere en administrert løsning, kan ha administrerte sett med egenskaper som kan hindre dem fra å bli slettet, unntatt ved å avinstallere den administrerte løsningen.

## <a name="places-where-you-can-access-the-view-editor-to-create-or-edit-views"></a>Steder der du kan åpne visningsredigeringsprogrammet for å opprette eller redigere visninger

- PowerApps-området: Du får tilgang til visningsutforming på området **Modelldrevet** > **Data** > **Enheter** > **Visning**-fanen. Åpne en eksisterende visning, eller opprett en ny. Mer informasjon: [Opprett eller rediger en visning](create-and-edit-views.md)
- Apputforming: Hvis du arbeider i en app, kan du bruke Apputforming, som gir et enkelt og intuitivt brukergrensesnitt med dra-og-slipp-funksjoner for opprettede visninger. Mer informasjon: [Opplæring: Opprett og rediger offentlige visninger eller systemvisninger ved bruk av apputforming](create-edit-views-app-designer.md)
- Løsningsutforsker: Hvis du allerede har erfaring med Dynamics 365, kan du bruke Løsningsutforsker. Mer informasjon: [Gå til områdene for avansert apputvikling og tilpassing](advanced-navigation.md#solution-explorer)
 
## <a name="customize-views"></a>Tilpassing av visninger

Som systemtilpasser kan du tilpasse visningene ved hjelp av kontroller ved å gjøre rutenett (lister) redigerbare og kompatible for enhetlig grensesnitt. Følgende kontroller brukes:

- Redigerbart rutenett: Med dette kan brukerne gjøre omfattende innebygde redigeringer direkte fra rutenett og delrutenett, enten de bruker en nettapp, et nettbrett eller en telefon. Mer informasjon: [Gjør rutenett redigerbare ved hjelp av den egendefinerte Redigerbart rutenett-kontrollen](make-grids-lists-editable-custom-control.md)
- Skrivebeskyttet rutenett: Gir brukere en optimal opplevelse for visning og samhandling for enhver skjermstørrelse og -retning, for eksempel for nettbrett og mobiltelefoner, ved hjelp av responsive utformingsprinsipper. Mer informasjon: [Angi egenskaper for Enhetlig grensesnitt-apper](specify-properties-for-unified-interface-apps.md)

## <a name="next-steps"></a>Neste trinn

[Opprette eller redigere visninger](create-and-edit-views.md)
