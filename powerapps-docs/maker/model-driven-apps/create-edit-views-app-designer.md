---
title: Opprette og redigere offentlige visninger eller systemvisninger for modelldrevne apper ved hjelp av apputforming med PowerApps | MicrosoftDocs
description: Finn ut hvordan du oppretter eller redigerer visninger ved hjelp av apputforming
keywords: ''
ms.date: 05/24/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 666ab3f3-abda-468c-b248-3a0b410286b0
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 1
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-and-edit-public-or-system-model-driven-app-views-by-using-the-app-designer"></a>Opplæring: Opprette og redigere offentlige visninger eller systemvisninger for modelldrevne apper ved hjelp av apputforming

I denne opplæringen skal du kan utføre flere oppgaver som kreves for å arbeide med visninger, for eksempel å opprette en fellsvisning, legge til en eksisterende visning i en app og endre kolonner, filtre og sorteringsrekkefølge for en visning.

I PowerApps definerer visninger hvordan oppføringer for en bestemt enhet vises. En visning definerer følgende:
-  Kolonnene (attributter) som skal vises
-  Bredden på kolonnene
-  Hvordan oppføringene sorteres som standard
-  Hvilke filtre som brukes til å fastsette oppføringene som vises i listen som standard

Vanligvis klassifiseres visninger inn i tre typer:
- **Personlig:** Individuelle brukere kan opprette personlige visninger i henhold til deres personlige krav. Disse visningene er bare synlige for brukeren som opprettet dem, og alle de ønsker å dele dem med. 
- **Offentlig:** Som appfremstiller kan du opprette og redigere offentlige visninger i samsvar med de organisatoriske kravene. Disse visningene er tilgjengelige i visningsvelgeren, og du kan bruke dem i delrutenett i et skjema eller som en liste på et instrumentbord.
- **System:** Som appfremstiller kan du også endre systemvisninger i samsvar med kravene i organisasjonen din. Dette er spesialvisninger som programmet er avhengig av. De finnes for systemenheter eller opprettes automatisk når du oppretter egendefinerte enheter. Disse visningene er tilgjengelige for noen eller alle brukere, avhengig av tillatelsene.

Mer informasjon: [Forstå visninger](create-edit-views.md)

## <a name="create-a-public-view-in-powerapps"></a>Opprette en fellesvisning i PowerApps
Som appfremstiller kan du opprette og redigere offentlige visninger ved hjelp av PowerApps.
1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  


    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Visninger**-kategorien. 

3. Velg **Legg til visning** på verktøylinjen. 

4. Angi et navn og eventuelt en beskrivelse i dialogboksen **Vis egenskaper**, og velg deretter **OK**. 
    
5. I redigeringsprogrammet for visning velger du **Legg til kolonner** for å legge til flere kolonner som skal vises i visningen. Mer informasjon: [Legge til en kolonne i visningen](#add-a-column-to-your-view)
6. Velg **Rediger filtervilkår** for å endre filtrering på følgende måter: 
    -  Bruke filtervilkår for å begrense dataene som vises i visningen. Mer informasjon: [Definere filterkriterier](#define-filter-criteria). 
    - Gruppere filtrene ved hjelp av alternativene **OG** eller **ELLER** og begrense dataene som vises i visningen, ytterligere. Mer informasjon: [Gruppere flere filtre](#group-multiple-filters)
7. Velg **Konfigurer sortering** for å endre rekkefølgen på dataene ved å konfigurere primær og sekundær sorteringsrekkefølge for kolonner. Mer informasjon: [Angi primær og sekundær sorteringsrekkefølge for kolonner](#set-primary-and-secondary-sort-order-for-columns)
8. (Valgfritt) Konfigurere kolonnebredden: 
  
    a. Velg en kolonne. Kategorien **Egenskaper** åpnes.
    
    b. Konfigurer **Angi bredde** med kolonnebredden du ønsker.
    
    > [!NOTE]
    > Kolonnebreddeverdien er fra 25 til 300 piksler.
9. (Valgfritt) Endre rekkefølgen på kolonnene ved å dra en kolonne til plasseringen du vil flytte den til. 

    Du skal se en visuelle indikator når du holder kolonnen over en posisjon den kan flyttes til.

    ![Endre rekkefølgen på kolonner](media/ViewAppDesigner_ReorderColumn.png "Endre rekkefølgen på kolonner i en visning")

    > [!NOTE]
    > Du kan også endre kolonnerekkefølgen ved hjelp av hurtigtaster. Klipp ut kolonnen ved å velge Ctrl + X, velg en kolonne, og lim deretter inn ved å velge Ctrl + V. Kolonnen flyttes til høyre for den valgte kolonnen.
10. (Valgfritt) Legg ved et ikon eller en fil i en kolonne for å skille den fra andre kolonner under kjøretid. Mer informasjon: [Definere en webressurs](#define-a-web-resource)
11. Visningen **Lagre og lukk**. 
12. Velg **Publiser** for å gjøre visningen tilgjengelig for andre brukere i organisasjonen. 
   

## <a name="open-and-add-a-view-in-the-app-designer"></a>Åpne og legge til en visning i apputformingen

Fremgangsmåten nedenfor forklarer hvordan du åpner og legger til en visning i apputformingen.
1. I løsningsutforskeren velger du **Apper** og deretter velger du appen du vil åpne i apputformingen. 

2. I delen **Enhetsvisning** velger du **Visninger**.

    I dette eksemplet har vi valgt **Visninger** fra **Forretningsforbindelse**-enheten.

    ![Apputformingvisning](media/ViewAppDesigner_AccountAppDesignerView.png "Apputformingvisning av forretningsforbindelsesenheten")

3. Hvis du vil legge til en visning, velger du den ved hjelp av visningstyper, for eksempel offentlig, avansert søk, tilknyttet og oppslag. Visningen legges automatisk til i **Visninger**-listen.

    > [!NOTE]
    > Visninger vises basert på enheten som du har valgt. Når du for eksempel velger **Forretningsforbindelse**, vises visninger som er relatert til enheten Forretningsforbindelse.

Mer informasjon om apputformingen: [Utforme egendefinerte forretningsapper ved hjelp av apputformingen](design-custom-business-apps-using-app-designer.md)


## <a name="add-a-column-to-your-view"></a>Legge til en kolonne i visningen
Visninger viser oppføringer i en tabell som inneholder kolonner og rader. Hver rad er en oppføring, og feltene som du viser fra oppføringen, fastsattes av kolonnene du legger til i visningen.

1. I apputformingen, i kategorien **Komponenter**, velger du **Kolonneattributter**-listen for **Hovedenhet** eller **Relatert enhet**.

    ![Legge til en kolonne](media/ViewAppDesigner_AddColumn.png "Legge til en kolonne i visningen") 

2. Fra listen velger du attributtet du vil ha, og drar det til kolonneoverskriften. Du kan også legge til attributtet ved å dobbeltklikke det.
3. Gjenta trinn 2 til du har lagt til alle attributtene du ønsker skal vises i visningen.

Når du legger til attributter, kan du dra dem til en hvilken som helst posisjon mellom eksisterende kolonneoverskrifter. Du kan også flytte kolonnene rundt når du har lagt dem til i visningen.


## <a name="define-filter-criteria"></a>Definere filterkriterier
Du kan angi filtervilkår slik at bare et delsett av-oppføringene vises i en visning. Når en bruker åpner visningen, vises bare oppføringene som oppfyller de definerte filtervilkårene. Du kan velge felt fra både hovedenheter og relaterte enheter å filtrere etter.
1. I apputformingen utvider du delen **Filtervilkår**.
   
    ![Angi filtervilkår](media/ViewAppDesigner_FilterCriteria.png "Angi filtervilkår") 

2. Velg **Legg til filter**.
3. Velg et attributt fra rullegardinlisten i den første kolonnen. 
4. Velg en operator fra rullegardinlisten i den andre kolonnen.

    ![Angi operator for filtervilkår](media/ViewAppDesigner_FilterCriteriaOption.png "Angi operator for filtervilkår")

5. Angi en verdi du vil filtrere etter, i den tredje kolonnen.

Du kan filtrere dataene etter attributtene for relaterte enheter i tillegg til hovedenheten. 

1. I kategorien **Komponenter** velger du **Kolonneattributter**-listen for **Relatert enhet**, velger pil ned for **Velg en enhet** i det øverste feltet, og velger deretter ønsket enhet.

    Dette vil legge til en egen del.

2. Gjenta trinn 2 til 5 fra forrige fremgangsmåte.

Mer informasjon: [Opprette og redigere relasjoner mellom enheter](../common-data-service/create-edit-entity-relationships.md)

## <a name="group-multiple-filters"></a>Gruppere flere filtre
Du kan legge til flere filtre i visningen hvis du vil filtrere oppføringer ved hjelp av mer enn ett felt. 

1. Velg filtrene du vil gruppere.
    ![Angi gruppefilter](media/ViewAppDesigner_GroupFilter.png "Angi gruppefilter")
2. Velg Gruppe OG eller Gruppe ELLER for å gruppere filtrene.
    ![Gruppefiltervalg](media/ViewAppDesigner_GroupFilterSelection.png "Velge et gruppefilter") Når du velger **Gruppe OG**, vises bare oppføringer som oppfyller begge vilkårene, i visningen. Når du velger **Gruppe ELLER**, vises oppføringer som oppfyller noen av filtervilkårene. Hvis du for eksempel vil vise bare oppføringer som har prioriteten Høy eller Normal og statusen Aktiv, velger du **Gruppe OG**.

Hvis du vil fjerne filteret fra en gruppe, velger du gruppen og deretter **Del opp gruppe**. 

## <a name="set-primary-and-secondary-sort-order-for-columns"></a>Angi primær og sekundær sorteringsrekkefølge for kolonner
Når du har åpnet en visning, sorteres oppføringene som vises, i rekkefølgen du definerte da du opprettet visningen.   Oppføringene sorteres som standard etter den første kolonnen i en visning når det ikke er valgt noen sorteringsrekkefølge. Du kan velge å sortere etter én enkelt kolonne, eller du kan velge å sortere etter to kolonner – én primær og én sekundær. Når visningen er åpnet, sorteres oppføringene først etter kolonnen du vil bruke for primær sorteringsrekkefølge og deretter etter kolonnen du vil bruke for sekundær sorteringsrekkefølge. 

> [!NOTE]
> Du kan bare angi primær og sekundær sorteringsrekkefølge for kolonneattributter du har lagt til fra hovedenheten.

1. Velg kolonnen du vil bruke for sortering.
2. Velg pil ned, og velg deretter **Primær sortering** eller **Sekundær sortering**.
 
    ![Sortere oppføring](media/ViewAppDesigner_SortRecords.png "Sortere oppføringer basert på primær og sekundær sorteringsrekkefølge") 

Hvis du fjerner kolonnen som du valgte for primær sorteringsrekkefølge, blir kolonnen du valgte for sekundær sorteringsrekkefølge, primær.

## <a name="define-a-web-resource"></a>Definere en webressurs
Angi en webressurs for skripttypen for tilknytning til en kolonne i visningen. Disse skriptene bidrar til å vise ikoner for kolonner.

1. Velg kolonnen du vil legge til en webressurs i.
2. I kategorien **Egenskaper** velger du **Avansert**.
3. I **Webressurs**-rullegardinlisten velger du webressursen du vil bruke.
4. Skriv inn et funksjonsnavn i **Funksjonsnavn**-boksen.

## <a name="edit-a-public-or-system-view"></a>Redigere en offentlig visning eller systemvisning
Du kan endre måten en offentlig visning eller systemvisning vises på, ved å legge til, konfigurere eller fjerne kolonner.
1. I **Visninger**-listen for en enhet velger du pil ned for **Vis referanseliste** ![Rullegardinliste](media/DownArrow.png "Rullegardinlistepil").
    ![Redigere visning](media/ViewAppDesigner_EditView.png "Redigere en offentlig visning eller systemvisning")
2. Ved siden av visningen du vil redigere, velger du **Åpne visningsutforming** ![Åpne visningsutforming](media/dynamics365-open-designer.png "Åpne visningsutforming"). 

    Visningen åpnes i visningsutformingen. 

Når du redigerer en offentlig visning eller systemvisning, må du lagre og publisere endringene for at de skal vises i programmet.


## <a name="community-tools"></a>Fellesskapsverktøy
**View Layout Replicator** og **View Designer** er verktøy som XrmToolbox-fellesskapet utviklet for Dynamics 365 Customer Engagement.

Mer informasjon: [Utviklerverktøy](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools).

> [!NOTE]
> Disse verktøyene leveres av XrmToolBox og støttes ikke av Microsoft. Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com/). 

### <a name="next-steps"></a>Neste trinn
[Opprette 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én)](../common-data-service/create-edit-1n-relationships.md)
