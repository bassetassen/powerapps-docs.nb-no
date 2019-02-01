---
title: Bruke løsninger i PowerApps | MicrosoftDocs
description: Finn ut hvordan du bruker løsninger til å opprette eller tilpasse apper
ms.custom: ''
ms.date: 10/29/2018
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
ms.assetid: 72bacfbb-96a3-4daa-88ff-11bdaaac9a3d
caps.latest.revision: 57
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-solutions-in-powerapps"></a>Bruke løsninger i PowerApps

 Du kan vise en liste over løsninger i PowerApps ved å velge **Løsninger** i den venstre navigasjonsruten. Deretter kan du velge en løsning for å vise alle komponentene. 
 
> [!div class="mx-imgBorder"]  
> ![Demo-løsning med alle komponenter](media/solution-all-items-list.PNG "Demo-løsning med alle komponenter")  
 
> [!NOTE]
>  Løsningsopplevelsen er bare tilgjengelig på Internett og for miljøversjon 9.1.0.267 og senere. Hvis du vil kontrollere versjonen, kan du gå til [...administrasjonssenteret for PowerApps](https://admin.powerapps.com/)> **Miljøer** > velg miljøet > kategorien **Detaljer**. For miljøer med tidligere versjon åpnes en valgt løsning i den klassiske opplevelsen.  
 
 Du kan bla gjennom alle komponentene i en løsning ved å rulle gjennom elementene. Hvis det finnes flere enn 100 elementer i listen, kan du velge **Last de neste 100 varene** for å se mer. 
 
> [!div class="mx-imgBorder"]  
> ![Last inn flere komponenter](media/load-more.PNG "Last inn flere komponenter")  

 ## <a name="search-and-filter-in-a-solution"></a>Søke og filtrere i en løsning
 
 Du kan også søke etter en bestemt komponent etter navn. 
 
> [!div class="mx-imgBorder"]  
> ![Søk etter komponent](media/solution-search-box.png "Søk etter komponent")  
 
 Eller du kan filtrere alle elementene i listen etter komponenttypen.
  
> [!div class="mx-imgBorder"]  
> ![Filtrer komponent etter type](media/solution-filter.PNG "Filtrer komponent etter type")  
 
 ## <a name="contextual-commands"></a>Kontekstbaserte kommandoer
 
 Når du velger hver komponent, vil handlingene som er tilgjengelige i kommandolinjen, endres avhengig av typen komponent du har valgt, og hvorvidt løsningen er standardløsningen eller en administrert løsning. 
 
> [!div class="mx-imgBorder"]  
> ![Komponentspesifikke kommandoer](media/component-commands.png "Komponentspesifikke kommandoer")  
 
 Når du ikke velger en komponent, viser kommandolinjen handlinger som gjelder selve løsningen. 
 
> [!div class="mx-imgBorder"]  
> ![Løsningsspesifikke kommandoer](media/solution-commands.PNG "Løsningsspesifikke kommandoer")  
 
 ## <a name="create-components-in-a-solution"></a>Opprette komponenter i en løsning
 Med løsninger som er uadministrert eller standard, kan du bruke **Ny**-kommandoen til å lage ulike typer komponenter. Dermed kommer du til en annen opprettingsopplevelse avhengig av hvilken komponent du velger. Når du har opprettet komponenten, legges den til i løsningen. 
 
> [!div class="mx-imgBorder"]  
> ![Opprett ny komponent i en løsning](media/solution-new-component.PNG "Opprett ny komponent i en løsning")  
 
 ## <a name="add-an-existing-component-to-a-solution"></a>Legg til eksisterende komponent i en løsning
 
 Med uadministrerte løsninger som ikke er standardløsningen, kan du bruke kommandoen **Legg til eksisterende** for å hente komponenter som ikke allerede finnes i løsningen.  
 
> [!div class="mx-imgBorder"]  
> ![Legg til eksisterende komponent i en løsning](media/solution-add-existing-component.PNG "Legg til eksisterende komponent i en løsning")  
  
 Med administrerte løsninger blir ingen kommandoer tilgjengelige, og du vil se meldingen nedenfor. Du må finne komponenten i løsningen kalt **standardløsning**, og prøve å redigere den der eller legge den til i en annen uadministrert løsning som du har opprettet. Komponenten kan kanskje ikke tilpasses. Mer informasjon: [Forvaltede egenskaper](solutions-overview.md#managed-properties)

> [!div class="mx-imgBorder"]  
> ![Administrert løsning](media/managed-solution.PNG "Administrert løsning")  

 Mange av tilpassingene du vil gjøre, omfatter enheter. Du kan bruke **Enhet**-filteret for å vise en liste over alle enheter i gjeldende løsning som kan tilpasses på et eller annet vis. Når du driller ned i en enhet, kan du se komponentene som er en del av enheten, som vist med enheten for forretningsforbindelsen i følgende skjermbilde. 
 
> [!NOTE]
>  Når du for øyeblikket legger til en eksisterende enhet i en løsning, legger systemet automatisk til alle komponentene som er en del av enheten i løsningen. Hvis dette ikke er det du ønsker, kan du bruke kommandoen **Bytt til klassisk** for å navigere til den klassiske opplevelsen og legge til bare komponenter som du ønsker. <!-- We will soon improve this experience from PowerApps and allow you to select only the specific component(s) under entity that you want to add into a solution. -->
  
> [!div class="mx-imgBorder"]  
> ![Demo-løsning som viser utvidet enhet for forretningsforbindelse](media/solution-entity-account.png "Demo-løsning som viser utvidet enhet for forretningsforbindelse")  

## <a name="classic-solution-explorer"></a>Klassisk løsningsutforsker

Du kan vise den klassiske løsningsutforskeren i PowerApps ved å velge **Løsninger** i den venstre navigasjonsruten, og deretter velge **Bytt til klassisk** i kommandolinjen. Klassisk løsningsutforsker er den som tidligere var tilgjengelig gjennom **Innstillinger > Avanserte tilpassinger**-området i PowerApps. Hvis du er en Dynamics 365 for Customer Engagement-bruker, kan du bruke den klassiske løsningsutforskeren til å arbeide med løsninger.  

## <a name="known-limitations"></a>Kjente begrensninger

- Sletting eller fjerning av en administrert løsning sletter ikke lerretappen i PowerApps.
- Egendefinerte koblinger er ikke tilgjengelig i en løsning.
- Lerretapper må åpnes etter en løsning er importert for å oppdatere tilkoblinger.
- Når du legger til en eksisterende SDK-samling, vises den ikke i løsningen. 
- Hvis en lerretapp er pakket i en administrert løsning, kan den fremdeles redigeres i målmiljøet.
- Avhengigheter er ikke tilgjengelig for lerretapper.
- Når du sletter en administrert løsning, rulles det ikke tilbake til en annen lerretappversjon. 
-   Lerretapptilgang (CRUD og sikkerhet) administreres helt i PowerApps og ikke Common Data Service for Apps (CDS)-databasen.
-   CDS API-er for å kalle lerretapper blokkeres og returnerer ikke noe. 
-   Lerretapper som er opprettet i en løsning, kan ikke deles som medeier til en AAD-sikkerhetsgruppe.
-   Lerretapper vil ikke vises i den klassiske løsningsutforskeren.
-   Eksisterende lerretapper er ikke løsningsavhengige. 

 For mer informasjon om tilpassing av individuelle komponenter i en løsning, kan du se følgende emner:  
  
-   For tilpassinger av enheter, enhetsrelasjoner, felt og meldinger, se [Metadata](create-edit-metadata.md).  
  
-   For enhetsskjemaer se [Skjemaer](../model-driven-apps/create-design-forms.md).  
  
-   For prosesser kan du se [Prosesser](../model-driven-apps/guide-staff-through-common-tasks-processes.md).  
  
-   For forretningsregler kan du se [Forretningsregler](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md).  
