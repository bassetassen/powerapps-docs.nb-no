---
title: Arbeid med løsninger i PowerApps | MicrosoftDocs
description: Lær hvordan løsninger er fordelt
ms.custom: ''
ms.date: 01/28/2019
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: da6b44c4755fa42d6e946cfe5955bba0e78b91c2
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "65038609"
---
# <a name="solutions-overview"></a>Oversikt over løsninger  

  I PowerApps brukes løsninger til å transportere apper og komponenter fra et miljø til et annet, eller til å bruke et sett med tilpassinger på eksisterende apper. En løsning kan inneholde både en eller flere apper og komponenter som enheter, alternativsett osv.  Du kan få en løsning fra [AppSource](https://appsource.microsoft.com/) eller fra en uavhengig programvareleverandør (ISV).
  
Mer informasjon: [Hvitbok: Livssyklusadministrasjon for løsninger](https://www.microsoft.com/en-us/download/details.aspx?id=57777)  
  
> [!NOTE]
>  Hvis du er en uavhengig programvareleverandør som oppretter en app som du vil distribuere, må du bruke løsninger. Hvis du vil ha mer informasjon om å bruke løsninger, kan du se [Veiledning for utviklere: Innføring i løsninger](/powerapps/developer/common-data-service/introduction-solutions).  
  
 Her er det du trenger å vite om løsninger hvis du er interessert i å opprette PowerApps-apper for organisasjoner eller tilpasse Dynamics 365 for Customer Engagement-apper:  
  
-   Det å lage løsninger er valgfritt. Du kan bygge eller tilpasse apper direkte i PowerApps-miljøet uten noen gang å lage en løsning.  
  
-   Når du tilpasser PowerApps-miljøet direkte uten å opprette noen løsning, bruker du en spesiell løsning kalt **Common Data Services standardløsning**. Denne løsningen inneholder alle tilpassingene du lager i PowerApps-miljøet ditt.  
  
-   Det finnes en annen spesiell løsning kalt **standardløsningen**. Denne løsningen inneholder alle komponentene i systemet ditt, enten de er opprettet av deg eller andre. Du kan eksportere **standardløsningen** for å opprette en sikkerhetskopi av tilpassingene du har definert i organisasjonen din. Dette er en god vane for å sikkerhetskopiere endringer i tilfelle av et verst tenkelig scenario.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="components"></a>Komponenter  
 En komponent representerer noe du potensielt kan tilpasse. Alt som kan inkluderes i en løsning, er en komponent. Dette er en liste over komponentene du kan vise i en løsning:  
  
-   Programbånd  
  
-   Artikkelmal  
  
-   Forretningsregel  

-   Lerretsapp 
  
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

-   Flyt
  
-   Skjema  
  
-   Utskriftsflettingsmal  
  
-   Melding  

-   Modelldrevet app
  
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
  
 Noen komponenter er nestet i andre komponenter. En enhet inneholder for eksempel skjemaer, visninger, diagrammer, felter, enhetsrelasjoner, meldinger og forretningsregler. Hver av disse komponentene krever en enhet for å eksistere. Et felt kan ikke ekistere utenfor en enhet. Vi sier at feltet er avhengig av enheten. Det finnes faktisk dobbelt så mange typer komponenter som vises i den foregående listen, men de fleste er ikke nestet i andre komponenter og er ikke synlige i appen.  
  
 Formålet med å ha komponenter er å holde oversikt over enhver begrensning på hva som kan tilpasses ved hjelp av forvaltede egenskaper og alle avhengighetene, slik at det kan eksporteres, importeres og (i forvaltede løsninger) slettes uten å la noe være igjen.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Forvaltede og uadministrerte løsninger  
 Det finnes **administrerte** og **uadministrerte** løsninger. En **administrert** løsning kan ikke endres og kan avinstalleres etter at den er importert. Alle komponentene i den løsningen fjernes ved å avinstallere løsningen.  
  
 Når du importerer en **uadministrert** løsning, legger du til alle komponentene fra den løsningen i miljøet ditt. Du kan ikke fjerne komponentene ved å avinstallere løsningen.  
  
 Når du importerer en **uadministrert** løsning som inneholder komponenter du allerede har tilpasset, blir tilpassingene dine overskrevet av tilpassingene i den importerte uadministrerte løsningen. Du kan ikke angre dette.  
  
> [!IMPORTANT]
>  Bare installer en uadministrert løsning hvis du vil legge til alle komponentene i miljøet ditt og overskrive alle eksisterende tilpassinger.  
  
 Selv om du ikke har tenkt å distribuere appene eller tilpassingene dine, kan det være at du vil opprette og bruke en uadministrert løsning for å få en egen visning som bare inneholder de delene av appen som du har tilpasset. Når du tilpasser noe, må du bare legge det til den uadministrerte løsningen som du opprettet.  
  
 Du kan bare eksportere **standardløsningen** som en uadministrert løsning.  
  
 For å opprette en **administrert** løsning velger du **Som administrert**-alternativet når du eksporterer løsningen. Hvis du oppretter en administrert løsning, kan du ikke importere den tilbake til det samme miljøet du brukte til å opprette den i. Du kan bare importere den til et annet miljø.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Hvordan løsninger brukes  
 Alle løsninger evalueres som lag for å bestemme hva appen skal gjøre. Dette diagrammet viser hvordan administrerte og uadministrerte løsninger evalueres, og hvordan endringer i dem vil se ut i miljøet ditt.  
  
 ![Laginndeling for løsning](media/solution-layering.png "Laginndeling for løsning")  
  
 Starter fra bunnen og arbeider til toppen:  
  
 **Systemløsning**  
 Systemløsningen er som en administrert løsning som alle miljøer har. Systemløsningen er definisjonen på alle ferdige komponenter i systemet.  
  
 **Administrerte løsninger**  
 Administrerte løsninger kan endre løsningskomponentene for systemet, og legge til nye komponenter. Hvis flere administrerte løsninger er installert, vil den første som blir installert være under den administrerte løsningen som blir installert senere. Dette betyr at den andre løsningen som er installert, kan tilpasse den som ble installert først. Når to administrerte løsningene har motstridende definisjoner, er den generelle regelen at «den siste vinner». Hvis du avinstallerer en administrert løsning, trer den administrerte løsningen under i kraft. Hvis du avinstallerer alle administrerte løsninger, blir standardvirkemåten som er definert i systemløsningen tatt i bruk.  
  
 **Ubehandlede tilpassinger**  
 Uadministrerte tilpassinger er enhver endring du har gjort i miljøet ditt gjennom en uadministrert løsning. Systemløsningen definerer hva du kan eller kan ikke tilpasse ved hjelp av forvaltede egenskaper. Utgivere av administrerte løsninger har samme muligheten til å begrense muligheten til å tilpasse løsningskomponenter for deg, som de legger til i løsningen. Du kan tilpasse noen av løsningskomponentene som ikke har forvaltede egenskaper som hindrer tilpassing av dem.  
  
 **Programfunksjonalitet**  
 Dette er det du faktisk ser i miljøet. Standardløsningen for systemet, pluss alle administrerte løsninger, i tillegg til eventuelle uadministrerte tilpassinger du har brukt.  
  
<a name="BKMK_ManagedProperties"></a>   
### <a name="managed-properties"></a>Forvaltede egenskaper  
 Noen komponenter kan ikke tilpasses. Disse komponentene i systemløsningen har metadata som hindrer tilpassing av dem. Disse kalles **forvaltede egenskaper**. Utgiveren av en administrert løsning kan også angi forvaltede egenskapene til å hindre deg tilpassing av løsningene på måter som de ikke vil at du skal.  
  
<a name="BKMK_Dependencies"></a>   
### <a name="solution-dependencies"></a>Løsningsavhengigheter  
 På grunn av måten administrerte løsninger er lagdelt på, kan noen administrerte løsninger være avhengige av løsningskomponentene i andre administrerte løsninger. Noen løsningsutgivere vil dra nytte av dette for å bygge løsninger som er modulære. Du må kanskje installere en «grunnleggende» administrert løsning først, og deretter installere en annen administrert løsning som vil tilpasse komponentene i den grunnleggende administrerte løsningen ytterligere. Den andre administrerte løsningen avhenger av løsningskomponenter som er en del av den første løsningen.  
  
 Systemet sporer disse avhengighetene mellom løsninger. Hvis du prøver å installere en løsning som krever en grunnleggende løsning som ikke er installert, vil du ikke kunne installere løsningen. Du får en melding om at løsningen krever at en annen løsning er installert først. På samme måte, på grunn av avhengighetene, kan ikke den grunnleggende løsningen avinstalleres mens en løsning som avhenger av den fremdeles blir installert. Du må avinstallere den avhengige løsningen før du kan avinstallere den grunnleggende løsningen.  
  
  
## <a name="next-steps"></a>Neste trinn  
[Importer, oppdater og eksporter løsninger](import-update-export-solutions.md) <br/>
[Gå til en bestemt løsning](navigate-specific-solution.md)
 
