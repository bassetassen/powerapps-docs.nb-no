---
title: Forstå komponenter for modelldrevne apper i PowerApps | MicrosoftDocs
description: 'Forstå ulike komponenter i en modelldrevet app, for eksempel data, brukergrensesnitt, logikk og visualisering.'
Keywords: 'fields, attributes, model-driven app'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="understand-model-driven-app-components"></a>Forstå komponenter for modelldrevne apper
En godt utformet modelldrevet app består av flere komponenter som du velger ved hjelp av designeren for å bygge utseende og funksjonalitet i den ferdige appen. Komponentene og komponentegenskapene som utformere bruker til å lage en app, blir metadataene. 

For å forstå hvordan hver av komponentene er relatert til apputformingen, er de atskilt her i kategoriene *data*, *brukergrensesnitt*, *logikk*, og *visualisering*. 

## <a name="data"></a>Data
Disse komponentene avgjør hvilke data appen er basert på.


|Komponent  |Beskrivelse  |Designer  |
|---------|---------|---------|
|Enhet     |Et element med egenskaper som du sporer, for eksempel en kontakt eller en forretningsforbindelse. Mange standardenheter er tilgjengelige. Du kan tilpasse en ikke-system standardenhet (produksjon) eller opprette en egendefinert enhet fra bunnen av.     | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutforming        |
|Felt     | En egenskap som er knyttet til en enhet. Et felt er definert av datatypen, som bestemmer datatypen som kan angis eller velges. Eksempler omfatter tekst, tall, dato og klokkeslett, valuta eller oppslag (oppretter en relasjon med en annen enhet). Felt brukes vanligvis med skjemaer, visninger og søk.        | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutforming   |
|Relasjon     | Entitetsrelasjoner definerer hvordan enheter kan være relatert til hverandre. Relasjonstypene er 1:N (én-til-mange), N:1 (mange-til-én) og N:N (mange-til-mange). Det å legge til et oppslagsfelt i en enhet oppretter for eksempel en ny 1:N-relasjon mellom de to enhetene og lar deg sette oppslagsfeltet i et skjema.   | [!INCLUDE [powerapps](../../includes/powerapps.md)] enhetsutforming        |
|Felt for alternativsett     | Dette er en spesiell type felt som inneholder et sett med forhåndsdefinerte alternativer for brukeren. Hvert alternativ har en tallverdi og etikett. Når feltet legges til i et skjema, vises en kontroll, der brukeren kan velge et alternativ.  Det finnes to typer alternativsett: alternativsett, der brukeren bare kan velge ett alternativ, og alternativsett med flere valg, som tillater flere enn ett valg.  | [!INCLUDE [powerapps](../../includes/powerapps.md)] designer for alternativsett     |

Mer informasjon: [Definere data for din modelldrevne app](define-data-model-driven-app.md) 

## <a name="ui"></a>Brukergrensesnitt
Disse komponentene bestemmer hvordan brukere samhandler med appen. 

|Komponent  |Beskrivelse  |Designer  |
|---------|---------|---------|
|App     | Bestemmmer det grunnleggende for appen, for eksempel komponenter, egenskaper, klienttype og URL-adresse.      | Apputforming   |
|Områdekart     | Angir navigasjonen for appen din.        | Utforming av områdekart        |
|Skjema     | Et sett med dataregistreringsfelt for en gitt enhet som samsvarer med elementene som organisasjonen sporer for enheten. Hvis du for eksempel et sett med dataregistrering felt at der brukerens inndata relevant informasjon til å spore en kunde som er tidligere ordne ordrer sammen med spesifikke forespurt datoer.        | Skjemautforming        |
|Visning     | Visninger definerer hvordan en liste over oppføringer for en bestemt enhet vises i programmet. En visning definerer kolonnene som skal vises, bredden av hver kolonne, sorteringsfunksjonaliteten og standardfiltrene.   |  Visningsutforming       |

![Apputforming og skjemautforming](media/model-driven-app-overview/app-and-form-designers.png)

## <a name="logic"></a>Logikk
Avgjør forretningsprosesser, regler, og automatiseringen appen får. [!INCLUDE [powerapps](../../includes/powerapps.md)]-konstruktører bruker en designer som er spesifikk for typen prosess eller en regel. 


|Type logikk  |Beskrivelse  |Designer  |
|---------|---------|---------|
|Forretningsprosessflyt     | En online-prosess som veileder brukerne gjennom en standard forretningsprosess. Bruk for eksempel en forretningsprosessflyt hvis du vil at alle skal behandle kundeforespørsler på samme måte, eller krever at ansatte skaffer godkjenning for en faktura før de sender en ordre.        | Designer for forretningsprosessflyt        |
|Arbeidsflyt     |  Arbeidsflyter automatiserer forretningsprosesser uten brukergrensesnitt. Designere bruker arbeidsflyter til å starte automatisering som ikke krever noen form for brukermedvirkning.       | Arbeidsflytutforming        |
|Handlinger    |  Handlinger er en prosesstype som manuelt starter handlinger, inkludert egendefinerte handlinger, direkte fra en arbeidsflyt.       |  Prosessutforming       |
|Forretningsregel     | Brukes til å bruke regel- eller anbefalingslogikk i et skjema, for eksempel for å angi feltkrav, skjule felt eller validere data. Appkonstruktører bruker et enkelt grensesnitt for å implementere og vedlikeholde regler som endres og brukes ofte.         |  Designer for forretningsregel       |
|Flow     | Flow er en skybasert tjeneste som gjør det mulig å opprette automatiske arbeidsflyter mellom apper og tjenester for å bli varslet, synkronisere filer, samle inn data og mye mer.        | Microsoft Flow        |

![Designere for arbeidsflyt, handling og forrretningsprosessflyt](media/model-driven-app-overview/designer-mash.png)

Mer informasjon: [Bruke forretningslogikk i en modelldrevet app](guide-staff-through-common-tasks-processes.md)

## <a name="visualizations"></a>Visualiseringer
Avgjør hvilken type datavisualiseringer og rapportering appen får tilgjengelig.


|Komponent  |Beskrivelse  |Designer  |
|---------|---------|---------|
|Diagram     | En enkel grafisk visualisering som kan vises i en visning, i et skjema eller legges til i et instrumentbord.        | Diagramutforming        |
|Instrumentbord     | Fungerer som en palett for én eller flere grafiske visualiseringer som gir en oversikt over forretningsdata du kan samhandle med.        | Instrumentbordutforming        |
|Innebygd Power BI     | Legg til innebygde Power BI-fliser og -instrumentbord i appen. Power BI er en skybasert tjeneste som inneholder forretningsinnsikt.        |  Kombinasjon av diagramutforming, instrumentbordutforming og Power BI       |

![Eksempel på instrumentbord](media/model-driven-app-overview/dashboard-designer.png)

## <a name="advanced-model-driven-app-making"></a>Avansert konstruksjon av modelldrevne apper
Løsningsutforskeren er et omfattende verktøy som brukes for avansert konstruksjon av modelldrevne apper. I løsningsutforskeren kan du navigere gjennom et hierarki som består av alle appkomponentene, ved hjelp av navigasjonsruten på venstre side i verktøyet.

![Løsningsutforsker](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Hvis du vil åpne løsningsutforskeren, kan du velge **Modelldrevet** i den venstre ruten i [!INCLUDE [powerapps](../../includes/powerapps.md)].

  ![Velge Modelldrevet](media/model-driven-app-overview/app-type-picker-mod.png)

Deretter velger du **Avansert**-kategorien.

Mer informasjon: [Avansert apputvikling og -tilpassing](advanced-navigation.md)

## <a name="related-topics"></a>Beslektede emner

[Validere og publisere en modelldrevet app](validate-app.md)

[Dele en modelldrevet app](share-model-driven-app.md)
