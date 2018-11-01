---
title: Arbeide med løsninger i PowerApps | MicrosoftDocs
description: Finn ut hvordan løsninger distribueres
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

<a name="BKMK_Solutions"></a>   
# <a name="solutions-overview"></a>Løsningsoversikt  

 Løsninger finnes slik at en modelldrevet app kan kjøpes, deles eller ellers transporteres fra én organisasjon til en annen. Du kan få løsninger fra [AppSource](https://appsource.microsoft.com/) eller fra en uavhengig programvareleverandør (ISV). En løsning er en fil du kan importere til et miljø som en app eller for å bruke et sett med tilpassinger på en eksisterende app.  
  
Mer informasjon: [Teknisk beskrivelse: Mønstre og prinsipper for systembyggere](http://go.microsoft.com/fwlink/p/?LinkID=533946)  
  
> [!NOTE]
>  Hvis du er en ISV som lager en app du vil distribuere, må du bruke løsninger. Hvis du vil ha mer informasjon om hvordan du bruker løsninger, kan du se [Pakke og distribuere utvidelser ved hjelp av løsninger](https://msdn.microsoft.com/library/gg334530.aspx).  
  
 Hvis du bare vil opprette PowerApps-apper for organisasjonsbruk eller tilpassing av Dynamics 365, trenger du vite følgende om løsninger:  
  
-   Det er valgfritt å lage løsninger. Du kan bygge eller tilpasse apper i PowerApps-miljøet direkte uten noen gang å opprette en løsning.  
  
-   Når du tilpasser et PowerApps-miljø direkte, arbeider du med en spesiell løsning kalt **Common Data Services-standardløsningen**. Denne løsningen inneholder alle komponentene i systemet.  
  
-   Du kan eksportere din standardløsning for å opprette en sikkerhetskopi av tilpasningene du har definert i organisasjonen. Det er lurt å ha i et verste tilfelle-scenario.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="solution-components"></a>Løsningskomponenter  
 En løsningskomponent representerer noe som du potensielt kan tilpasse. Alt som kan inkluderes i en løsning, er en løsningskomponent. Følgende er en liste over løsningskomponenter som du kan vise i en løsning:  
  
-   Programbånd  

-   App 
  
-   Artikkelmal  
  
-   Forretningsregel  
  
-   Diagram  
  
-   Tilkoblingsrolle  
  
-   Kontraktmal  
 
-   Tilpasset kontroll
  
-   Instrumentbord  
  
-   E-postmal  
  
-   Entity  
  
-   Enhetsrelasjon  
  
-   Felt  
  
-   Sikkerhetsprofil for felt  
  
-   Skjema  
  
-   Mal for utskriftsfletting  
  
-   Melding  
  
-   Alternativsett  
  
-   Plugin-modulsamling  
  
-   Prosess  
  
-   Behandlingstrinn for SDK-meldingen  
  
-   Sikkerhetsrolle  
  
-   Serviceendepunkt  
  
-   Områdekart  

-   Dataleverandør for virtuelle enheter

-   Datakilde for virtuelle enheter
  
-   Webressurs  
  
 De fleste løsningskomponenter er nestet i andre løsningskomponenter. En enhet inneholder for eksempel skjemaer, visninger, diagrammer, felt, enhetsrelasjoner, meldinger og forretningsregler. Hver av disse løsningskomponentene krever at en enhet finnes. Et felt kan ikke eksistere utenfor en enhet. Vi sier at feltet er avhengig av enheten. Det er faktisk to ganger så mange typer løsningskomponenter som vist i listen ovenfor, men de fleste av dem er ikke synlige i programmet.  
  
 Formålet med å ha løsningskomponenter er å holde oversikt over alle begrensninger på hva som kan tilpasses ved hjelp av Forvaltede egenskaper og alle løsningsavhengighetene, slik at den kan eksporteres, importeres og (i administrerte løsninger) slettes uten å etterlate noe.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Administrerte og uadministrerte løsninger  
 En **administrert** løsning kan avinstalleres når den er importert. Alle komponentene i denne løsningen fjernes ved å avinstallere løsningen.  
  
 Når du importerer en **ubehandlet** løsning, legger du til alle komponentene i denne løsningen i standardløsningen din. Du kan ikke fjerne komponentene ved å avinstallere løsningen.  
  
 Når du importerer en **uadministrert** løsning som inneholder løsningskomponenter som du allerede har tilpasset, vil tilpasningene bli overskrevet av tilpasningene i den uadministrerte løsningen. Du kan ikke angre dette.  
  
> [!IMPORTANT]
>  Installer en uadministrert løsning bare hvis du vil legge til alle komponentene i standardløsningen din og overskrive alle eksisterende tilpassinger.  
  
 Selv om du ikke planlegger å distribuere din løsning, bør du opprette og bruke en uadministrert løsning for å ha en egen visning som bare inneholder de delene av programmet som du har tilpasset. Når du tilpasser noe, legger du det bare til i den uadministrerte løsningen du har opprettet.  
  
 Du kan bare eksportere standardløsningen som en uadministrert løsning.  
  
 Når du skal opprette en **administrert** løsning, velger du alternativet for administrert løsning når du eksporterer løsningen. Hvis du oppretter en administrert løsning, kan du ikke importere den tilbake til den samme organisasjonen du brukte til å opprette den. Du kan bare importere den til en annen organisasjon.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Hvordan løsninger tas i bruk  
 Alle løsninger blir evaluert som lag for å bestemme hva appen faktisk skal gjøre. Følgende diagram viser hvordan administrerte og uadministrerte løsninger blir evaluert og hvordan endringer i dem vises i organisasjonen.  
  
 ![Løsningslag](media/solution-layering.png "Løsningslag")  
  
 Start fra bunnen, og arbeid deg oppover til toppen:  
  
 **Systemløsning**  
 Systemløsningen er som en administrert løsning som hver organisasjon har. Systemløsningen er definisjonen av alle de medfølgende komponentene i systemet.  
  
 **Administrerte løsninger**  
 Administrerte løsninger kan endre systemløsningskomponenter og legge til nye komponenter. Hvis flere administrerte løsninger blir installert, er den første som blir installert, under den administrerte løsningen som blir installert senere. Dette betyr at den andre installerte løsningen kan tilpasse den som er installert før den. Når to administrerte løsninger har motstridende definisjoner, er den generelle regelen "Den siste vinner". Hvis du avinstallerer en administrert løsning, trer den administrerte løsningen under den i kraft. Hvis du avinstallerer alle administrerte løsninger, brukes standardvirkemåten som er definert i systemløsningen.  
  
 **Uadministrerte tilpassinger**  
 Uadministrerte tilpassinger er alle endringer du har gjort i organisasjonen ved hjelp av en uadministrert løsning. Systemløsningen definerer hva du kan og ikke kan tilpasse ved hjelp av forvaltede egenskaper. Utgivere av administrerte løsninger har samme mulighet til å begrense muligheten til å tilpasse løsningskomponenter som de legger til i løsningen. Du kan tilpasse løsningskomponentene som ikke har forvaltede egenskaper som hindrer deg i å tilpasse dem.  
  
 **Programmets virkemåte**  
 Dette er hva som faktisk vises i organisasjonen. Standardsystemløsningen pluss alle administrerte løsninger pluss eventuelle uadministrerte tilpassinger som du har brukt.  
  
<a name="BKMK_ManagedProperties"></a>   
### <a name="managed-properties"></a>Forvaltede egenskaper  
 Enkelte komponenter kan ikke tilpasses. Disse komponentene i systemløsningen har metadata som hindrer deg fra å tilpasse dem. Disse kalles **forvaltede egenskaper**. Utgiverne administrerte løsninger kan også angi de forvaltede egenskapene for å hindre deg fra å tilpasse løsningen på måter de ikke vil at du skal.  
  
<a name="BKMK_Dependencies"></a>   
### <a name="solution-dependencies"></a>Løsningsavhengigheter  
 På grunn av måten administrerte løsninger er i lag på kan noen administrerte løsninger være avhengige av løsningskomponenter i andre administrerte løsninger. Noen løsningsutgivere vil dra nytte av dette for å bygge løsninger som modulære. Du må kanskje installere en "grunnleggende" administrert løsning først, og deretter kan du installere en annen administrert som vil videre tilpasse komponentene i den grunnleggende administrerte løsningen. Den andre administrerte løsningen er avhengig av løsningskomponenter som er en del av den første løsningen.  
  
 Systemet sporer disse avhengighetene mellom løsninger. Hvis du prøver å installere en løsning som krever en grunnleggende løsning som ikke er installert, kan du ikke installere løsningen. Du får en melding om at løsningen krever at en annen løsning installeres først. På grunn av avhengigheter, kan du på samme måte ikke avinstallere den grunnleggende løsningen mens en løsning som avhenger av den, fremdeles er installert. Du må avinstallere den avhengige løsningen før du kan avinstallere den grunnleggende løsningen.  
  
  
## <a name="next-steps"></a>Neste trinn  
[Importere, oppdatere og eksportere løsninger](import-update-export-solutions.md) <br/>
[Gå til en bestemt løsning](navigate-specific-solution.md)
 
