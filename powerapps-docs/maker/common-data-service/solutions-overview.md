---
title: Arbeid med løsninger i PowerApps | MicrosoftDocs
description: Lær hvordan løsninger er fordelt
ms.custom: ''
ms.date: 06/21/2018
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
ms.assetid: ece68f5f-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
ms.openlocfilehash: 47fb64e650da2f3e1a9e0cf523060cf7d9f5a03b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691592"
---
<a name="BKMK_Solutions"></a>   
# <a name="solutions-overview"></a>Oversikt over løsninger  

 Det finnes løsninger slik at en modelldrevet app kan kjøpes, deles eller ellers transporteres fra én organisasjon til en annen. Du kan få løsninger fra [AppSource](https://appsource.microsoft.com/) eller fra en uavhengig programvareleverandør (ISV). En løsning er en fil som du kan importere til et miljø som en app, eller for å bruke som et sett med tilpassinger for en eksisterende app.  
  
Mer informasjon: [Hvitbok: mønstre og prinsipper for løsningsbyggere](http://go.microsoft.com/fwlink/p/?LinkID=533946)  
  
> [!NOTE]
>  Hvis du er en uavhengig programvareleverandør som oppretter en app som du vil distribuere, må du bruke løsninger. Hvis du vil ha mer informasjon om hvordan du bruker løsninger, se [Pakke- og distribueringsutvidelser ved hjelp av løsninger](https://msdn.microsoft.com/library/gg334530.aspx).  
  
 Her er det du trenger å vite om løsninger hvis du bare er interessert i å opprette PowerApps-apper for organisasjoner eller tilpasse Dynamics 365:  
  
-   Det å lage løsninger er valgfritt. Du kan bygge eller tilpasse apper direkte i PowerApps-miljøet uten noen gang å lage en løsning.  
  
-   Når du tilpasser PowerApps-miljøet direkte, arbeider du med en spesiell løsning kalt **Common Data Services Default Solution**. Denne løsningen inneholder alle komponentene i systemet.  
  
-   Du kan eksportere standardløsningen for å opprette en sikkerhetskopi av tilpassingene du har definert i organisasjonen. Det er lurt å ha om det verste skulle skje.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="solution-components"></a>Løsningskomponenter  
 En løsningskomponent representerer noe som du potensielt kan tilpasse. Alt som kan inkluderes i en løsning er en løsningskomponent. Følgende er en liste over løsningskomponentene som du kan vise i en løsning:  
  
-   Programbånd  

-   App 
  
-   Artikkelmal  
  
-   Forretningsregel  
  
-   Diagram  
  
-   Tilkoblingsrolle  
  
-   Kontraktsmal  
 
-   Egendefinert kontroll
  
-   Instrumentbord  
  
-   E-postmal  
  
-   Enhet  
  
-   Enhetsrelasjon  
  
-   Felt  
  
-   Feltsikkerhetsprofil  
  
-   Skjema  
  
-   Utskriftsflettingsmal  
  
-   Melding  
  
-   Alternativsett  
  
-   Plugin-modulsamling  
  
-   Prosess  
  
-   Behandlingstrinn for SDK-melding  
  
-   Sikkerhetsrolle  
  
-   Endepunkt for tjeneste  
  
-   Områdekart  

-   Dataleverandør for virtuell enhet

-   Datakilde for virtuell enhet
  
-   Nettressurs  
  
 De fleste løsningskomponentene er nestet i andre løsningskomponenter. En enhet inneholder for eksempel skjemaer, visninger, diagrammer, felter, enhetsrelasjoner, meldinger og forretningsregler. Hver av disse løsningskomponentene krever at en enhet finnes. Et felt kan ikke ekistere utenfor en enhet. Vi sier at feltet er avhengig av enheten. Det er faktisk dobbelt så mange typer for løsningskomponenter enn det som vises i listen ovenfor, men de fleste av dem er ikke synlig i programmet.  
  
 Formålet med å ha løsningskomponentene, er å holde oversikt over alle begrensninger på hva som kan tilpasses ved hjelp av forvaltede egenskaper, og alle løsningsavhengighetene, slik at det kan eksporteres, importeres og slettes uten å forlate noe.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Forvaltede og uadministrerte løsninger  
 En **forvaltet** løsning kan avinstalleres når den er importert. Alle komponentene i den løsningen fjernes ved å avinstallere løsningen.  
  
 Når du importerer en **uadministrert** løsning, legger du til alle komponentene i denne løsningen til standardløsningen. Du kan ikke fjerne komponentene ved å avinstallere løsningen.  
  
 Når du importerer en **uadministrerte** løsning, som inneholder løsningskomponentene som du allerede har tilpasset, blir tilpassingene overskrevet av tilpassingene i den uadministrerte løsningen. Du kan ikke angre dette.  
  
> [!IMPORTANT]
>  Installer en uadministrert løsning bare hvis du vil legge til alle komponentene i standardløsningen, og overskriv eventuelle eksisterende tilpassinger.  
  
 Selv om du ikke har tenkt på å distribuere løsningen din, kan du opprette og bruke en ikke-administrert løsning har en egen visning som bare inneholder de delene av programmet som du har tilpasset. Når du tilpasser noe, må du bare legge det til den uadministrerte løsningen som du opprettet.  
  
 Du kan bare eksportere standardløsningen som en uadministrert løsning.  
  
 Hvis du vil opprette en **administrert** løsning, kan du velge alternativet for administrert løsning når du eksporterer løsningen. Hvis du oppretter en administrert løsning, kan du importere den tilbake til den samme organisasjonen som du brukte til å opprette den. Du kan bare importere den til en annen organisasjon.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Hvordan løsninger brukes  
 Alle løsninger evalueres som lag for å bestemme hva appen skal gjøre. Følgende diagram viser hvordan administrerte og uadministrerte løsninger blir evaluert, og hvordan endringer i dem vises i organisasjonen.  
  
 ![Laginndeling for løsning](media/solution-layering.png "Laginndeling for løsning")  
  
 Starter fra bunnen og arbeider til toppen:  
  
 **Systemløsning**  
 Systemløsningen er som en administrert løsning, som hver organisasjon har. Systemløsningen er definisjonen på alle ferdige komponenter i systemet.  
  
 **Administrerte løsninger**  
 Administrerte løsninger kan endre løsningskomponentene for systemet, og legge til nye komponenter. Hvis flere administrerte løsninger er installert, vil den første som blir installert være under den administrerte løsningen som blir installert senere. Dette betyr at den andre løsningen som er installert, kan tilpasse den som ble installert først. Når to administrerte løsningene har motstridende definisjoner, er den generelle regelen at «den siste vinner». Hvis du avinstallerer en administrert løsning, trer den administrerte løsningen under i kraft. Hvis du avinstallerer alle administrerte løsninger, blir standardvirkemåten som er definert i systemløsningen tatt i bruk.  
  
 **Ubehandlede tilpassinger**  
 Ubehandlede tilpassinger er eventuelle endringer du har gjort i organisasjonen gjennom en ubehandlet løsning. Systemløsningen definerer hva du kan eller kan ikke tilpasse ved hjelp av forvaltede egenskaper. Utgivere av administrerte løsninger har samme muligheten til å begrense muligheten til å tilpasse løsningskomponenter for deg, som de legger til i løsningen. Du kan tilpasse noen av løsningskomponentene som ikke har forvaltede egenskaper som hindrer tilpassing av dem.  
  
 **Programfunksjonalitet**  
 Dette er hva du faktisk ser i organisasjonen. Standardløsningen for systemet, pluss alle administrerte løsninger, i tillegg til eventuelle uadministrerte tilpassinger du har brukt.  
  
<a name="BKMK_ManagedProperties"></a>   
### <a name="managed-properties"></a>Forvaltede egenskaper  
 Noen komponenter kan ikke tilpasses. Disse komponentene i systemløsningen har metadata som hindrer tilpassing av dem. Disse kalles **forvaltede egenskaper**. Utgiveren av en administrert løsning kan også angi forvaltede egenskapene til å hindre deg tilpassing av løsningene på måter som de ikke vil at du skal.  
  
<a name="BKMK_Dependencies"></a>   
### <a name="solution-dependencies"></a>Løsningsavhengigheter  
 På grunn av måten administrerte løsninger er lagdelt på, kan noen administrerte løsninger være avhengige av løsningskomponentene i andre administrerte løsninger. Noen løsningsutgivere vil dra nytte av dette for å bygge løsninger som moduler. Du må kanskje installere en «grunnleggende» administrert løsning først, og deretter installere en annen administrert løsning som vil tilpasse komponentene i den grunnleggende administrerte løsningen ytterligere. Den andre administrerte løsningen avhenger av løsningskomponenter som er en del av den første løsningen.  
  
 Systemet sporer disse avhengighetene mellom løsninger. Hvis du prøver å installere en løsning som krever en grunnleggende løsning som ikke er installert, vil du ikke kunne installere løsningen. Du får en melding om at løsningen krever at en annen løsning er installert først. På samme måte, på grunn av avhengighetene, kan ikke den grunnleggende løsningen avinstalleres mens en løsning som avhenger av den fremdeles blir installert. Du må avinstallere den avhengige løsningen før du kan avinstallere den grunnleggende løsningen.  
  
  
## <a name="next-steps"></a>Neste trinn  
[Importer, oppdater og eksporter løsninger](import-update-export-solutions.md) <br/>
[Gå til en bestemt løsning](navigate-specific-solution.md)
 
