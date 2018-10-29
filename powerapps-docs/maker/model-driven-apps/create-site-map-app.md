---
title: Opprett et modelldrevet områdekart for en app i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter et områdekart for appen
keywords: ''
ms.date: 05/29/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 2461bd71-6cb4-46b7-8d1f-6a0aa3dca809
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 18
topic-status: Drafting
ms.openlocfilehash: 2c3f1f4f22df6ed8b4824f1942e3fd202362ea9d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39692539"
---
# <a name="tutorial-create-a-model-driven-app-site-map-for-an-app-using-the-site-map-designer"></a>Opplæring: Opprett et modelldrevet områdekart for en app ved bruk av utforming av områdekart

I denne opplæringen skal du utføre flere områdekartoppgaver som å opprette et nytt områdekart, og legge til område, gruppe og underområde.

Områdekart definerer navigasjonen for appen. Opprett et områdekart for appen på en enkel måte ved bruk av den flisbaserte utformingen av områdekart. Bruk utformingsprogrammet til å dra komponenter over på lerretet, forhåndsvise arbeidet, og umiddelbart publisere områdekartet. Systemtilpassere eller brukere med nødvendige tillatelser kan raskt opprette områdekart for apper.  
  
Med utformingen av områdekart kan du også definere området, underområdet eller gruppefliser på de språkene som støttes av miljøet.  
  
Et standard områdekart er tilgjengelig. Du kan redigere dette områdekartet eller konfigurere områdekart for nye apper ved bruk av utforming av områdekart. Utformingen av områdekart er integrert i apputforming.  

## <a name="prerequisites"></a>Forutsetninger
Kontroller at du har Systemansvarlig- eller Systemtilpasser-sikkerhetsrollen, eller tilsvarende tillatelser.  Enhver bruker med følgende rettigheter kan også opprette apper:  
-   Opprette, Lese og Skrive for appenheten  
-   Lese og Skrive for tilpassingsenheten  
-   Lese for løsningsenheten

Du kan også vise eller angi disse rettighetene på **Tilpassing**-fanen i en sikkerhetsrolle.
  
## <a name="create-a-site-map-for-an-app"></a>Opprett et områdekart for en app  
  
1. Velg **Åpne utforming av områdekart** ![knappen Åpne utforming av områdekart](media/dynamics365-open-designer.PNG "Åpne utforming av områdekart") på lerretet for apputforming, i **Områdekart**-området.  
  
     Utforming av områdekart åpner et lerret som er forhåndsutfylt med ett område, én gruppe og ett underområde. Velg område-, gruppe- eller underområdeflisen for å endre egenskapene.  
  
    > [!NOTE]
    >  Hvis du velger **Åpne utforming av områdekart** ![knappen Åpne utforming av områdekart](media/dynamics365-open-designer.PNG "knappen Åpne utforming av områdekart") fra lerretet for apputforming, oppretter automatisk et nytt områdekart (hvis det ikke allerede eksisterer et), og det nye områdekartet får samme navn og unike navn som appens navn og unike navn. 

   ![Velg områdekart](media/app-designer-sitemap-location.png "Velg et områdekart") 
  
2.  [Legg til et område i områdekartet](create-site-map-app.md#bkmk_AddArea).  
  
3.  [Legg til en gruppe i områdekartet](create-site-map-app.md#bkmk_AddGroup).  
  
4.  [Legg til et underområde i områdekartet](create-site-map-app.md#bkmk_AddSubarea).  
  
5.  Velg **Lagre**.  
  
    > [!NOTE]
    >  Det nye områdekartet tilknyttes med appen når du går tilbake til apputforming og velger **Lagre**. Når du har konfigurert et områdekart, vises **Konfigurert** på områdekartflisen. Ellers vises **Ikke konfigurert** på flisen.  Hvis du åpner utforming av områdekart fra apputforming og konfigurerer et nytt områdekart, men lukker nettleseren før du tilknyttet områdekartet med appen, tilknyttes områdekartet automatisk med appen nesten gang du åpner apputforming, basert på appens unike navn.  
  
6.  Velg **Publiser**.  
  
## <a name="edit-the-default-site-map"></a>Rediger standard områdekart 

 Miljøet inkluderer et standard områdekart.  
  
1. Åpne løsningutforsker.  
  
2. Velg **Klientutvidelser** under **Komponenter** i løsningsvinduet.  

3. Velg **Legg til eksisterende** > **Områdekart** på verktøylinjen for komponenten.

4. Velg områdekartet med navn **Områdekart** i listen over løsningskomponenter, og velg deretter **OK**.
  
5.  Dobbeltklikk for å velge områdekartet du la til med visningsnavnet **Områdekart**, og som befinner seg i **Behandlet**-tilstanden. Du kan også velge områdekartet, og deretter velge **Rediger** på verktøylinjen.  
  
     Områdekartet åpnes i utforming av områdekart.  
  
6.  [Legg til et område i områdekartet](create-site-map-app.md#bkmk_AddArea).  
  
7.  [Legg til en gruppe i områdekartet](create-site-map-app.md#bkmk_AddGroup).  
  
8.  [Legg til et underområde i områdekartet](create-site-map-app.md#bkmk_AddSubarea).  
  
9. Velg **Lagre**.  
  
10. Velg **Publiser**.  
  
<a name="bkmk_AddArea"></a>   
## <a name="add-an-area-to-the-site-map"></a>Legg til et område i områdekartet  
  
1.  Velg **Legg til** ![Legg til-knapp på utformeren](media/dynamics365-designer-addbutton.PNG "Legg til-knapp på utformeren") på lerretet for utforming av områdekart, og velg deretter **Område**.  
  
     eller  
  
     Dra **Område**-flisen til den tomme boksen på lerretet, fra **Komponenter**-fanen. Du ser den tomme boksen når du flytter flisen til riktig plass på lerretet.  
  
2.  Velg området du nettopp la til. Du ser **Egenskaper**-fanen uthevet i ruten til høyre for lerretet.  
  
3.  Legg til eller rediger egenskaper for området.  
  
     Gjør følgende under **Generelt**:  
  
    - **Tittel**: Skriv inn tittelen for området på originalspråket for organisasjonen.  
  
    - **Ikon**: Et standard programikon er valgt. Velg et annet ikon for området fra listen over nettressurser som er tilgjengelig i løsningen.  
  
    - **ID**: En unik ID genereres automatisk, men du kan skrive inn en ID manuelt hvis du ønsker det. Vi anbefaler at du bruker den angitte ID-en. Grunnen til det er at hvis ID-en du oppgir ikke er unik, kan brukerne få en feil når de prøver å bruke appen, eller du kan få en feil når du importerer en løsning som inneholder dette områdekartet.  
  
    - **Vis grupper**: Merk av for dette alternativet for å vise grupper tilhørende underområder i navigasjonsruten.  
  
     Gjør følgende under **Avansert**:  
  
    - **Flere titler**: Hvis organisasjonen bruker flere språk, velger du et språk (nasjonal innstilling) for tittelen, skriver inn tittelen, og velger deretter **Legg til** ![Legg til-knapp på utforming av områdekart](media/add-icon-sitemap-designer.png "Legg til-knapp på utforming av områdekart"). Du kan opprette, redigere eller slette titler for like mange språk som organisasjonen bruker. Du kan imidlertid bare ha én tittel per språk.  
  
    - **Flere beskrivelser**: Hvis organisasjonen bruker flere språk, velger du et språk for beskrivelsen, skriver inn beskrivelsen, og velger deretter **Legg til** ![Legg til-knapp på utforming av områdekart](media/add-icon-sitemap-designer.png "Legg til-knapp på utforming av områdekart"). Du kan opprette, redigere eller slette beskrivelser for like mange språk som organisasjonen bruker. Du kan imidlertid bare ha én beskrivelse per språk.  
  
    - **Nettadresse**: Angi nettadressen for Dynamics 365 for Outlook-mappen som representerer området.  
  
<a name="bkmk_AddGroup"></a>   
## <a name="add-a-group-to-the-site-map"></a>Legg til en gruppe i områdekartet  
  
1.  Velg området du ønsker å legge til i gruppen, på lerretet for utforming av områdekart.  
2.  Velg **Legg til** ![Legg til-knapp på utformeren](media/dynamics365-designer-addbutton.PNG "Legg til-knapp på utformeren"), og velg deretter **Grupper**.  
  
     eller  
  
     Dra **Gruppe**-flisen til en tom boks fra **Komponenter**-fanen, under **Område** på lerretet. Du ser den tomme boksen når du flytter flisen til riktig plass på lerretet.  
  
3.  Velg gruppen du nettopp la til.  
  
4.  Legg til eller rediger gruppeegenskapene på **Egenskaper**-fanen:  
  
     Gjør følgende under **Generelt**:  
  
    - **Tittel**: Skriv inn tittelen for gruppen på originalspråket for organisasjonen.  
  
    - **ID**: En unik ID genereres automatisk. Du kan oppgi en annen ID hvis du ønsker det. Vi anbefaler at du bruker den automatiske ID-en. Grunnen til det er at hvis ID-en du oppgir ikke er unik, kan du få en feil når du importerer en løsning som inneholder dette områdekartet.  
  
     Gjør følgende under **Avansert**:  
  
    - **Flere titler**: Hvis organisasjonen bruker flere språk, velger du et språk (nasjonal innstilling) for tittelen, skriver inn tittelen for gruppen, og velger deretter **Legg til** ![Legg til-knapp på utforming av områdekart](media/add-icon-sitemap-designer.png "Legg til-knapp på utforming av områdekart"). Du kan opprette, redigere eller slette titler for like mange språk som organisasjonen bruker. Du kan imidlertid bare ha én tittel per språk.  
  
    - **Flere beskrivelser**: Hvis organisasjonen bruker flere språk, velger du et språk for beskrivelsen, skriver inn beskrivelsen for gruppen, og velger deretter **Legg til** ![Legg til-knapp på utforming av områdekart](media/add-icon-sitemap-designer.png "Legg til-knapp på utforming av områdekart"). Du kan opprette, redigere eller slette beskrivelser for like mange språk som organisasjonen bruker. Du kan imidlertid bare ha én beskrivelse per språk.  
  
    - **Nettadresse**: Angi nettadressen for Dynamics 365 for Outlook-mappen som representerer gruppen.  
  
    - **Angi som profil**: Merk av for dette alternativet for å angi om gruppen representerer en profil for arbeidsplassen, som kan velges av brukeren. Gruppen som angis som profilen som kan velges av brukeren, gjøres tilgjengelig som alternativer i dine personlige alternativer. Dette gjelder bare for grupper i **Arbeidsplass**-området.  
  
<a name="bkmk_AddSubarea"></a>   
## <a name="add-a-subarea-to-a-group-in-the-site-map"></a>Legg til et underområde i områdekartet  
  
1.  Velg **Legg til** ![Legg til-knapp på utformeren](media/dynamics365-designer-addbutton.PNG "Legg til-knapp på utformeren") på lerretet for utforming av områdekart, og velg deretter **Underområde**.  
  
     eller  
  
     Dra **Underområde**-flisen til en tom boks fra **Komponenter**-fanen, under **Gruppe**-delen på lerretet. Du ser den tomme boksen når du flytter flisen til riktig plass på lerretet.  
  
2.  Velg underområdet du nettopp la til.  
  
3.  Legg til eller rediger egenskapene for underområdet på **Egenskaper**-fanen:  
  
     Gjør følgende under **Generelt**:  
  
    - **Type**: Velg om underområdet du legger til er et instrumentbord, en enhet, nettressurs eller nettadresse.  
  
    - **Enhet**: Velg enheten som underområdet gjelder for. Dette feltet er deaktivert hvis underområdetypen ikke er angitt som **Enhet** i **Type**-rullegardinlisten.  
  
    - **Nettadresse**: Angi en nettadresse for hovedsiden til programmet som skal vises, når dette underområdet er valgt. Dette feltet er deaktivert hvis du valgte **Enhet** i **Type**-rullegardinlisten.  
  
    - **Standardinstrumentbordet**: Velg standardinstrumentbordet som skal vises for dette underområdet. Dette feltet er deaktivert hvis du ikke valgte **Instrumentbord** i **Type**-rullegardinlisten.  
  
    - **Tittel**: Skriv inn tittelen for underområdet på originalspråket for organisasjonen.  
  
    - **Ikon**: Et standard programikon er valgt. Velg et annet ikon for underområdet fra listen over nettressurser som er tilgjengelig i løsningen.  
  
    - **ID**. En unik ID genereres automatisk. Du kan oppgi en annen unik ID hvis du ønsker det.  
  
    - **Parameteroverføring**. Velg denne boksen for å overføre informasjon om organisasjonen og språkkontekst til nettadressen. Dette alternativet er bare merket av når underområdetypen er en nettressurs eller et nettadressebasert underområde.  
  
     Gjør følgende under **Avansert**:  
 
    - **Rettigheter**: Dette definerer om et underområde vises basert på rettigheter som er tilgjengelig i sikkerhetsrollene som er tilordnet til brukeren. Velg navnet på enheten som du ønsker å kontrollere rettigheter for, og merk deretter av for å tilordne rettigheter. 
  
    - **Flere titler**: Hvis organisasjonen bruker flere språk, velger du språket for tittelen, skriver inn tittelen for underområdet, og velger deretter **Legg til**. Du kan opprette, redigere eller slette titler for like mange språk som organisasjonen bruker. Du kan imidlertid bare ha én tittel per språk.  
  
    - **Flere beskrivelser**: Hvis organisasjonen bruker flere språk, velger du språket for beskrivelsen, skriver inn beskrivelsen av underområdet, og velger deretter **Legg til**. Du kan opprette, redigere eller slette beskrivelser for like mange språk som organisasjonen bruker. Du kan imidlertid bare ha én beskrivelse per språk.  
  
    - **SKU-er**: Velg versjonene av Dynamics 365 Customer Engagement som viser dette underområdet.  
  
    - **Klient**: Velg klienttypen som viser dette underområdet.  
  
    - **Outlook-snarvei**: Velg ikonet som skal vises i Dynamics 365 for Outlook.  
  
    - **Frakoblet tilgjengelighet**: Merk av for dette alternativet hvis du vil gjøre dette underområdet tilgjengelig for brukerne, mens de er frakoblet når de bruker Dynamics 365 for Outlook.  
  
## <a name="organize-areas-groups-and-subareas"></a>Organiser områder, grupper og underområder  
 Du kan organisere områdene, gruppene og underområdene ved dra dem til nye plasseringer. En beholderboks der du drar over filene, vises. Dette er noe av det du kan gjøre:  
  
-   Flytt et underområde til en ny plassering i samme gruppe eller en annen gruppe under samme området.  
  
-   Flytt et underområde til en ny plassering i gruppen under et annet området.  
  
-   Flytt en gruppe til en ny plassering i samme område.  
  
-   Flytt en gruppe til en ny plassering i et annet område.  
  
-   Flytt et område til en ny plassering.  
  
## <a name="clone-a-component-in-a-site-map"></a>Klon en komponent i et områdekart  
 Hvis du vil ta en kopi av en eksisterende komponent, velger du komponenten, og velger deretter **Klon** på verktøylinjen.  Alle detaljene til den klonede komponenten er de samme som grunnkomponenten, bortsett fra ID-en og tittelen. ID-en genereres tilfeldig. 
  
 Når du kloner et område, blir det klonede området lagt til til høyre for det gjeldende merkede området. Når du kloner en gruppe, blir den klonede gruppen lagt til til høyre for den gjeldende merkede gruppen. Når du kloner et underområde, blir det klonede underområdet lagt til nedenfor det gjeldende merkede underområdet.  
  
## <a name="delete-an-area-group-or-subarea-from-a-site-map"></a>Slett en gruppe, et område eller underområde fra et områdekart  
 Hvis du vil slette en områdekartkomponent, velger du komponenttittelen, og velger deretter **Slett** på verktøylinjen. Når du sletter et område, slettes også alle gruppene og underområdene i det området. Når du sletter en gruppe, slettes også gruppen og underområdene i gruppen.  
  
## <a name="clients-supported"></a>Støttede klienter  
 Den følgende tabellen forklarer klientene som støttes for ulike områdekart.  
 
|Områdekart|Støttede klienter|  
|---------------|-----------------------|  
|Nye apper| Forenet grensesnitt og nettappen Dynamics 365 Customer Engagement |  
|Områdekart for Dynamics 365 – egendefinert app | Nettappen Dynamics 365 Customer Engagement og Dynamics 365 for Outlook |  
|Standard forretningsapper (Sales, Sales Hub, Customer Service, Customer Service Hub, Field Service, Project Service Automation)| Nettappen Dynamics 365 Customer Engagement og Forenet grensesnitt|  
 
  
### <a name="next-steps"></a>Neste trinn  
 [Opprett eller rediger en app](create-edit-app.md)   
 [Legg til eller rediger appkomponenter](add-edit-app-components.md)
