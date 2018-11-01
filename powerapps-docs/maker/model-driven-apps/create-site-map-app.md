---
title: Opprette et områdekart for modelldrevet app for en app i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter et områdekart for appen
keywords: ''
ms.date: 05/29/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 2461bd71-6cb4-46b7-8d1f-6a0aa3dca809
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 18
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-model-driven-app-site-map-for-an-app-using-the-site-map-designer"></a>Opplæring: Opprette et områdekart for modelldrevet app for en app ved hjelp av områdekartutformingen

Du kan utføre flere områdekartoppgaver i denne opplæringen, for eksempel opprette et nytt områdekart og legge til et område, en gruppe og et underområde.

Områdekart definerer navigasjonen for appen din. Du kan opprette et områdekart for appen din på en enkel måte ved hjelp av flisbasert områdekartutforming. Bruk utformingsverktøyet til å dra og slippe komponenter på utforminglerretet, forhåndsvise arbeidet og publisere områdekartet umiddelbart. Systemtilpassere eller brukere med nødvendige rettigheter kan raskt lage områdekart for apper.  
  
Områdekartutformingen lar deg også definere område-, underområde- eller gruppetitler på språkene som støttes av miljøet.  
  
Det finnes et standard områdekart. Du kan redigere dette områdekartet eller konfigurere områdekart for nye apper ved hjelp av områdekartutformingen. Områdekartutformingen er integrert med apputformingen.  

## <a name="prerequisites"></a>Forhåndskrav
Sørg for at du har sikkerhetsrollen som systemansvarlig eller systemtilpasser eller tilsvarende tillatelser.  Brukere med følgende rettigheter kan også opprette apper:  
-   Opprettings-, lese- og skriverettigheter på appenheten  
-   Lese- og skriverettigheter på tilpassingsenheten  
-   Leserettigheter på løsningsenheten

Du kan vise eller angi disse rettighetene i kategorien **Tilpassing** for en sikkerhetsrolle.
  
## <a name="create-a-site-map-for-an-app"></a>Opprette et områdekart for en app  
  
1. På apputformingslerretet, i **Områdekart**-området, velger du **Åpne områdekartutforming** ![Knappen Åpne områdekartutforming](media/dynamics365-open-designer.PNG "Knappen Åpne områdekartutforming").  
  
     Områdekartutformingen åpnes med et lerret automatisk fylt ut med ett område, én gruppe og ett underområde. Velg område-, gruppe- eller underområdeflisen for å endre egenskapene.  
  
    > [!NOTE]
    >  Når du velger **Åpne områdekartutforming**-knappen ![Åpne områdekartutforming-knappen](media/dynamics365-open-designer.PNG "Åpne områdekartutforming-knappen") fra apputformingslerretet, opprettes automatisk et nytt områdekart (hvis ikke det finnes noe eksisterende områdekart) med samme navn som appnavnet og med samme unike navn som det unike navnet på appen. 

   ![Velge områdekart](media/app-designer-sitemap-location.png "Velge et områdekart") 
  
2.  [Legge til et område i områdekartet](create-site-map-app.md#bkmk_AddArea).  
  
3.  [Legg til en gruppe i områdekartet](create-site-map-app.md#bkmk_AddGroup).  
  
4.  [Legg til et underområde i en gruppe i områdekartet](create-site-map-app.md#bkmk_AddSubarea).  
  
5.  Velg **Lagre**.  
  
    > [!NOTE]
    >  Det nye områdekartet knyttes til appen når du går tilbake til apputformingen og velger **Lagre**. Når et områdekart er konfigurert, vises **Konfigurert** i flisen for områdekartet. Hvis ikke vises **Ikke konfigurert** i flisen.  Hvis du åpner områdekartutformingen fra apputformingen og konfigurerer et nytt områdekart, men lukker nettleseren før du knytter områdekartet til appen, knyttes områdekartet automatisk til appen neste gang du åpner apputformingen, basert på det unike appnavnet.  
  
6.  Velg **Publiser**.  
  
## <a name="edit-the-default-site-map"></a>Redigere standard områdekart 

 Ditt miljø leveres med et standard områdekart.  
  
1. Åpne løsningsutforskeren.  
  
2. Velg **Klientutvidelser** under **Komponenter** i løsningsvinduet.  

3. Velg **Legg til eksisterende** > **Områdekart** på komponentverktøylinjen.

4. I listen over løsningskomponenter velger du områdekartet kalt **Områdekart**, og deretter **OK**.
  
5.  Dobbeltklikk for å velge områdekartet du la til, som har visningsnavnet **Områdekart** og tilstanden **Administrert**. Du kan også velge områdekartet og velge **Rediger** på handlingsverktøylinjen.  
  
     Områdekartet åpnes i områdekartutformingen.  
  
6.  [Legge til et område i områdekartet](create-site-map-app.md#bkmk_AddArea).  
  
7.  [Legg til en gruppe i områdekartet](create-site-map-app.md#bkmk_AddGroup).  
  
8.  [Legg til et underområde i en gruppe i områdekartet](create-site-map-app.md#bkmk_AddSubarea).  
  
9. Velg **Lagre**.  
  
10. Velg **Publiser**.  
  
<a name="bkmk_AddArea"></a>   
## <a name="add-an-area-to-the-site-map"></a>Legge til et område i områdekartet  
  
1.  Velg **Legg til**-knappen ![Legg til-knappen i utformingen](media/dynamics365-designer-addbutton.PNG "Legg til-knappen i utformingen") på lerretet for områdekartutforming, og velg deretter **Område**.  
  
     eller  
  
     Fra kategorien **Komponenter** drar og slipper du **Område**-flisen til den tomme boksen på lerretet. Du vil se den tomme boksen når du flytter flisen til riktig sted på lerretet.  
  
2.  Velg området du nettopp la til. Du vil se kategorien **Egenskaper** uthevet i ruten til høyre for lerretet.  
  
3.  Legg til eller rediger egenskaper for området.  
  
     Gjør følgende under **Generelt**:  
  
    - **TIttel**: Angi tittelen for området på originalspråket for organisasjonen.  
  
    - **Ikon**: Et standardprogramikon velges. Velg et annet ikon for området i listen over webressurser som er tilgjengelige i løsningen.  
  
    - **ID**: En unik ID genereres automatisk, men du kan angi en annen om ønskelig. Vi anbefaler at du bruker den angitte ID-en fordi hvis ID-en du angir, ikke er unik, kan brukere få en feil når du bruker appen, eller du kan få en feil når du importerer en løsning som inneholder dette områdekartet.  
  
    - **Vis grupper**: Merk av for denne avmerkingsboksen for å vise grupper med underområder i navigasjonsruten.  
  
     Gjør følgende under **Avansert**:  
  
    - **Flere titler**: Hvis organisasjonen bruker flere språk, velger du et språk (Nasjonal innstilling) for tittelen, skriver inn tittelen, og velger deretter **Legg til** ![Legg til-knappen i områdekartutforming](media/add-icon-sitemap-designer.png "Legg til-knappen i områdekartutforming"). Du kan opprette, redigere eller slette titler på så mange språk som organisasjonen din bruker. Du kan imidlertid bare ha én tittel per språk.  
  
    - **Flere beskrivelser**: Hvis organisasjonen bruker flere språk, velger du et språk for beskrivelsen, skriver inn beskrivelsen, og velger deretter **Legg til** ![Legg til-knappen i områdekartutforming](media/add-icon-sitemap-designer.png "Legg til-knappen i områdekartutforming"). Du kan opprette, redigere eller slette beskrivelser på så mange språk som organisasjonen din bruker. Du kan imidlertid bare ha én beskrivelse per språk.  
  
    - **URL-adresse**: Skriv inn URL-adressen som skal gjengis for Dynamics 365 for Outlook-mappen som representerer området.  
  
<a name="bkmk_AddGroup"></a>   
## <a name="add-a-group-to-the-site-map"></a>Legg til en gruppe i områdekartet  
  
1.  Velg området du vil legge til gruppen i, på lerretet for områdekartutformingen.  
2.  Velg **Legg til** ![Legg til-knappen i utformingen](media/dynamics365-designer-addbutton.PNG "Legg til-knappen i utformingen"), og velg deretter **Gruppe**.  
  
     eller  
  
     Fra kategorien **Komponenter** drar og slipper du **Gruppe**-flisen til en tom boks under **Område** på lerretet. Du vil se den tomme boksen når du flytter flisen til riktig sted på lerretet.  
  
3.  Velg gruppen du nettopp la til.  
  
4.  Legg til eller rediger gruppeegenskaper i kategorien **Egenskaper**:  
  
     Gjør følgende under **Generelt**:  
  
    - **TIttel**: Angi tittelen for gruppen på originalspråket for organisasjonen.  
  
    - **ID**: En unik ID genereres automatisk. Angi en annen hvis det er nødvendig. Vi anbefaler at du bruker den automatiske ID-en fordi hvis ID-en du angir, ikke er unik, kan det oppstå en feil når du importerer en løsning som inneholder dette områdekartet.  
  
     Gjør følgende under **Avansert**:  
  
    - **Flere titler**: Hvis organisasjonen bruker flere språk, velger du et språk (nasjonal innstilling) for tittelen, skriver inn tittelen for gruppen, og velger deretter **Legg til** ![Legg til-knappen i områdekartutforming](media/add-icon-sitemap-designer.png "Legg til-knappen i områdekartutforming"). Du kan opprette, redigere eller slette titler på så mange språk som organisasjonen din bruker. Du kan imidlertid bare ha én tittel per språk.  
  
    - **Flere beskrivelser**: Hvis organisasjonen bruker flere språk, velger du et språk for beskrivelsen, skriver inn beskrivelsen for gruppen, og velger deretter **Legg til** ![Legg til-knappen i områdekartutforming](media/add-icon-sitemap-designer.png "Legg til-knappen i områdekartutforming"). Du kan opprette, redigere eller slette beskrivelser på så mange språk som organisasjonen din bruker. Du kan imidlertid bare ha én beskrivelse per språk.  
  
    - **URL-adresse**: Skriv inn URL-adressen som skal gjengis for Dynamics 365 for Outlook-mappen som representerer gruppen.  
  
    - **Angi som profil**: Merk av for denne avmerkingsboksen for å angi om denne gruppen representerer en profil som kan velges av en bruker, for arbeidsområdet. Gruppen som er angitt som en profil som kan velges av en bruker, gjøres tilgjengelig som alternativer under personlige alternativer. Dette gjelder bare for grupper i området **Arbeidsområde**.  
  
<a name="bkmk_AddSubarea"></a>   
## <a name="add-a-subarea-to-a-group-in-the-site-map"></a>Legg til et underområde i en gruppe i områdekartet  
  
1.  Velg **Legg til**-knappen ![Legg til-knappen i utformingen](media/dynamics365-designer-addbutton.PNG "Legg til-knappen i utformingen") på lerretet for områdekartutforming, og velg deretter **Underområde**.  
  
     eller  
  
     Fra kategorien **Komponenter** drar og slipper du **Underområde**-flisen til en tom boks under **Gruppe**-delen på lerretet. Du vil se den tomme boksen når du flytter flisen til riktig sted på lerretet.  
  
2.  Velg underområdet du nettopp la til.  
  
3.  Legg til eller rediger underområdeegenskaper i kategorien **Egenskaper**:  
  
     Gjør følgende under **Generelt**:  
  
    - **Type**: Velg om underområdet du legger til, er et instrumentbord, en enhet, en webressurs eller URL-adresse.  
  
    - **Enhet**: Velg enheten som underområdet er for. Dette feltet er deaktivert hvis typen underområde er en annen enn **Enhet** i **Type**-rullegardinlisten.  
  
    - **URL-adresse**: Angi en URL-adresse for hovedsiden i programmet som skal vises når dette underområdet velges. Dette feltet er deaktivert hvis du har valgt **Enhet** i **Type** -rullegardinlisten.  
  
    - **Standard instrumentbord**: Velg standard instrumentbord som skal vises for dette underområdet. Dette feltet er deaktivert hvis du ikke har valgt **Instrumentbord** i **Type**-rullegardinlisten.  
  
    - **TIttel**: Angi tittelen for underområdet på originalspråket for organisasjonen.  
  
    - **Ikon**: Et standardprogramikon velges. Velg et annet ikon for underområdet i listen over webressurser som er tilgjengelige i løsningen.  
  
    - **ID**. En unik ID genereres automatisk. Angi en annen unik ID hvis det er nødvendig.  
  
    - **Parameteroverføring**. Merk av i denne avmerkingsboksen for å sende informasjon om organisasjonen og språkkonteksten til URL-adressen. Det er bare merket av for denne avmerkingsboksen når underområdetypen er en webressurs eller et URL-adressebasert underområde.  
  
     Gjør følgende under **Avansert**:  
 
    - **Rettigheter**: Dette definerer om et underområde vises basert på rettighetene som er tilgjengelige i sikkerhetsroller tilordnet brukeren. Velg navnet på enheten for å kontrollere rettighetene og deretter merke av for å tilordne tilgangsrettigheter. 
  
    - **Flere titler**: Hvis organisasjonen bruker flere språk, velger du et språk for tittelen, angir tittelen for underområdet, og velger deretter **Legg til**. Du kan opprette, redigere eller slette titler på så mange språk som organisasjonen din bruker. Du kan imidlertid bare ha én tittel per språk.  
  
    - **Flere beskrivelser**: Hvis organisasjonen bruker flere språk, velger du et språk for beskrivelsen, angir beskrivelsen for underområdet, og velger deretter **Legg til**. Du kan opprette, redigere eller slette beskrivelser på så mange språk som organisasjonen din bruker. Du kan imidlertid bare ha én beskrivelse per språk.  
  
    - **SKU-er**: Velg versjonene av Dynamics 365 customer engagement som viser dette underområdet.  
  
    - **Klient**: Velg hvilken type klient som viser dette underområdet.  
  
    - **Outlook-snarvei**: Velg ikonet for å vise Dynamics 365 for Outlook.  
  
    - **Tilgjengelighet i frakoblet modus**: Merk av i denne avmerkingsboksen for å gjøre dette underområdet tilgjengelig for brukere når de er frakoblet i Dynamics 365 for Outlook.  
  
## <a name="organize-areas-groups-and-subareas"></a>Organisere områder, grupper og underområder  
 Du kan organisere områdene, gruppene og underområdene dine ved å dra dem til nye plasseringer. En beholder vises der du kan slippe flisene. Her er noen ting du kan gjøre:  
  
-   Flytte et underområde til en ny plassering innenfor samme gruppe eller en annen gruppe under det samme området.  
  
-   Flytte et underområde til en ny plassering innenfor en gruppe under et annet område.  
  
-   Flytte en gruppe til en ny plassering innenfor det samme området.  
  
-   Flytte en gruppe til en ny plassering i et annet område.  
  
-   Flytte et område til en ny plassering.  
  
## <a name="clone-a-component-in-a-site-map"></a>Klone en komponent i et områdekart  
 Hvis du vil lage en kopi av en eksisterende komponent, velger du komponenten og deretter **Klon**.  Alle detaljer for den klonede komponenten er de samme som basiskomponenten bortsett fra ID og tittel. ID-en genereres tilfeldig. 
  
 Når du kloner et område, legges det klonede området til, til høyre for det merkede området. Når du kloner en gruppe, legges den klonede gruppen til, til høyre for den merkede gruppen. Når du kloner et underområde, legges det klonede underområdet til, under det merkede underområdet.  
  
## <a name="delete-an-area-group-or-subarea-from-a-site-map"></a>Slette et område, en gruppe eller et underområde fra et områdekart  
 Hvis du vil slette en komponent i et områdekart, velger du komponentflisen og deretter **Slett** på verktøylinjen. Når du sletter et område, slettes også alle grupper og underområder i området. På samme måte, når du sletter en gruppe, slettes gruppen og underområdene i denne.  
  
## <a name="clients-supported"></a>Klienter som støttes  
 Følgende tabell beskriver klientene som støttes for ulike områdekart.  
 
|Områdekart|Klienter som støttes|  
|---------------|-----------------------|  
|Nye apper| Enhetlig grensesnitt og Dynamics 365 Customer Engagement-webappen |  
|Områdekart for den egendefinerte Dynamics 365-appen | Dynamics 365 customer engagement-webappen og Dynamics 365 for Outlook |  
|Standard forretningsapper (Sales, Sales-hub, Customer Service, Customer Service-hub, Field Service, Project Service Automation)| Dynamics 365 Customer Engagement-webappen og Enhetlig grensesnitt|  
 
  
### <a name="next-steps"></a>Neste trinn  
 [Opprette eller redigere en app](create-edit-app.md)   
 [Legge til eller redigere appkomponenter](add-edit-app-components.md)
