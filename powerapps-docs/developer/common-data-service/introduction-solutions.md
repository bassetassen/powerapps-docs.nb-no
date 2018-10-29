---
title: Innføring i løsninger | Microsoft Docs
description: Lær hvordan løsninger brukes til å opprette modellapper.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: bcf89d9c52e1e277f65f7f02013885f30862aa56
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864983"
---
# <a name="introduction-to-solutions"></a>Innføring i løsninger

*Løsninger* er måten tilpassere og utviklere oppretter, pakker og vedlikeholder programvareenheter som utvider Common Data Service for apper. Appene for Dynamics 365 for Sales, Marketing og Customer Service består av løsninger. Tilpassere og utviklere distribuerer løsninger, slik at organisasjoner kan bruke Common Data Service for apper til å installere og avinstallere forretningsfunksjonalitet som er definert av løsningen.

Hver tilpassing du gjør til Common Data Service for apper, eller til en tidligere installert løsning, er en del av en løsning. Hver endring du tar i bruk, spores, og eventuelle avhengigheter kan beregnes. Når du eksporterer en administrert løsning, inneholder den alle endringene som har blitt tatt i bruk for løsningen. Alt dette lagres i en fil som du deretter kan importere til et annet miljø for Common Data Service for apper.

Hvis du har tenkt å transportere tilpasninger eller utvidelser mellom ulike miljøer for Common Data Service for apper, eller distribuere løsninger ved bruk av AppSource, må du forstå løsningsrammeverket.

## <a name="managed-and-unmanaged-solutions"></a>Administrerte og uadministrerte løsninger

Det finnes to typer løsninger: *administrerte* og *uadministrerte*.

En **administrert** løsning er en fullført løsning som er ment å bli distribuert og installert. 
- Du kan ikke redigere komponentene til en administrert løsning.
- Du kan ikke eksportere en administrert løsning.
- Du kan legge til uadministrerte tilpassinger i komponenter til en administrert løsning. Når du gjør dette, oppretter du en avhengighet mellom de uadministrerte tilpassingene og den administrerte løsningen. Når en avhengighet eksisterer, kan ikke den administrerte løsningen avinstalleres før du fjerner avhengigheten.
- Når du sletter en administrert løsning (avinstallerer), fjernes alle tilpassinger og utvidelser som følger med.

  > [!IMPORTANT]
  > Når du avinstallerer en administrert løsning, mister du følgende data: data lagret i egendefinerte enheter som er en del av den administrerte løsningen, og data lagret i egendefinerte attributter som er en del av den administrerte løsningen på andre enheter som ikke er en del av den administrerte løsningen.

En **uadministrert** løsning er fremdeles under utvikling eller er ikke ment å distribueres. 
- Du kan fortsette å legge til og fjerne komponenter mens en løsningen er uadministrert. 
- Du kan eksportere en uadministrert løsning for å transportere uadministrerte tilpassinger fra ett miljø til et annet.
- Når en uadministrert løsning slettes, slettes bare løsningsbeholderen for eventuelle tilpassinger inkludert i den. Alle de uadministrerte tilpassingene gjelder fortsatt og de tilhører standardløsningen. 
- Når den uadministrerte løsningen er fullført og du vil distribuere den, eksporterer du den som en administrert løsning.

  > [!NOTE]
  > Du kan ikke importere en administrert løsning i samme miljø som inneholder den opprinnelige uadministrerte løsningen. Hvis du vil teste en administrert løsning, må du importere den inn i en separat løsning.

## <a name="solution-publishers"></a>Løsningsutgivere

Hver løsning er koblet til en løsningsutgiver. Løsningsutgiveren har informasjon om hvordan du kontakter utgiveren, i tillegg til et tilpassingsprefiks. Standardverdien er `new`.

Når skjemaendringer inkluderes som en del av en løsning, legges tilpassingsprefikset til foran navnet på skjemaelementene. Denne verdien legges også til i eventuelle egendefinerte handlinger. Dette er nyttig fordi det tillater en enkel gjenkjenning av hvilken løsning som la til skjemaelementet eller den tilpassede handlingen. Det er ikke nødvendig at alle skjemaelementer og egendefinerte handlinger i en løsning bruker det samme tilpassingsprefikset, men det anbefales sterkt.

> [!IMPORTANT]
> Før du begynner å opprette en løsning, må du opprette en løsningsutgiverpost, og du må opprette en ny løsning som er koblet til den. Du må sørge for at tilpassingsprefikset representerer en verdi som gir mening for deg. 

Ditt valg av løsningsutgiver er viktig i tilfelle du ønsker å publisere en oppdatering til en løsning du har sendt. En oppdatering kan bare tas i bruk i en administrert løsning med den samme utgiveren som den opprinnelige administrerte løsningen. 

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Vedlikehold administrerte løsninger > Opprett administrerte løsningsoppdateringer](/dynamics365/customer-engagement/developer/maintain-managed-solutions#create-managed-solution-updates)

## <a name="create-a-solution-publisher-and-solution"></a>Opprett en løsningsutgiver og løsning 

Hvis du vil opprette en løsningsutgiver og løsning, må du navigere til tilpassingsområdet for Dynamics 365.

Fra[powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)

1. Velg *Rutemeny*-ikonet øverst til venstre.
2. Velg **Alle apper** i undermenyen.
3. Se etter **Dynamics 365 – egendefinert app**.
 Klikk på ellipsen (...) og velg **Fest denne appen**. Da blir det enklere å navigere til den neste gang.
4. Klikk på appen **Dynamics 365 – egendefinert app** og velg den.
5. Naviger til **Innstillinger** > **Tilpassing** > **Tilpassinger**.

Fra [home.dynamics.com](http://home.dynamics.com/)

1. Se etter flisen **Dynamics 365 – egendefinert** og klikk på den.
2. Naviger til **Innstillinger** > **Tilpassing** > **Tilpassinger**.

### <a name="create-a-solution-publisher"></a>Opprett en løsningsutgiver

1. Velg **Utgivere** fra tilpassingsområdet.
2. Klikk på **Ny**.
3. Skriv inn **visningsnavn** i utgiverskjemaet. En **Navn**-verdi blir generert basert på visningsnavnet. Du kan godta den genererte verdien eller angi en ny.
4. Angi tilpassingsprefikset som skal legges til i egendefinerte skjemaelementer du legger til når du utvikler løsningen, i **prefiks**-feltet. Standardverdien er `new`. Velg en verdi som representerer organisasjonen, og som hjelper folk med å identifisere hvilke installerte komponenter på systemet kom fra løsningen.
5. En **Prefiks for alternativverdi**-verdi blir generert basert på ditt valg av tilpassingsprefiks. Dette er en verdi som legges til verdier for alternativene for alternativsett, som legges til i attributter i løsningen. Denne verdien identifiserer eventuelle alternativer du legger til i løsningen.
6. I **Kontaktinformasjon**-inndelingen i skjemaet kan du legge til kontaktinformasjon du ønsker å oppgi for de som installerer løsningen.
7. Klikk på **Lagre og lukk** når du er ferdig.

### <a name="create-a-solution"></a>Opprett en løsning

1. Velg **Løsninger** fra tilpassingsområdet.
2. Klikk på **Ny**.
3. Skriv inn **visningsnavn** i løsningsskjemaet. En **Navn**-verdi blir generert basert på visningsnavnet. Du kan godta den genererte verdien eller angi en ny.
4. Slå opp utgiveren du opprettet i [Opprett en løsningsutgiver](#create-a-solution-publisher), i **Utgiver**-feltet.
5. Velg en riktig versjon for løsningen din, som 1.0.0.0., i **Versjon**-feltet.
6. Klikk på **Lagre** når du er ferdig.

> [!IMPORTANT]
> Når du oppretter en ny løsningskomponent som blir inkludert i løsningen, bruker du denne løsningen, eller du kan bruke en annen løsning som er knyttet til den samme løsningsutgiveren for å legge dem til.
> Løsningskomponentene opprettet i konteksten av en løsning som er knyttet til en annen løsningsutgiver, kan legges til denne løsningen, men det kan hende de har inkonsekvente verdisett for tilpassingsprefiks.

## <a name="solution-layering"></a>Løsningslag

Det er mulig at to installerte administrerte løsninger er motstridende, eller at tilpassinger som er tatt i bruk for miljøet kan overstyre en administrert løsning. Hvordan fungerer det?

Det fungerer fordi Common Data Service for apper evaluerer administrerte løsninger etter rekkefølgen de er installert, og eventuelle tilpassinger som ikke befinner seg i en administrert løsning, evalueres til slutt.

Det følgende diagrammet introduserer hvordan administrerte løsninger og uadministrerte tilpassinger samhandler for å kontrollere hva som er inkludert ved kjøring i programmet.

![Diagram som viser løsningslag](media/solution-layering.png)

Standardvirkemåten som er angitt i systemløsningen, overstyres eller legges til av administrerte løsninger i dette eksemplet. Eventuelle uadministrerte tilpassinger kan deretter overstyre eller legge til tilpassinger, som deretter er synlig i programmet.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Innføring i løsninger > Uadministrerte og administrerte løsninger](/dynamics365/customer-engagement/developer/introduction-solutions#managed-and-unmanaged-solutions)

## <a name="managed-properties"></a>Forvaltede egenskaper

Når du distribuerer en administrert løsning, kan alle som installerer løsningen inkludere sine egne uadministrerte tilpassinger i den. Disse uadministrerte tilpassingene kan deretter legges til i en løsning som de distribuerte som en administrert løsning, som avhenger av løsningen din. Men hva om du ikke ønsker at noen skal gjøre dette? Som utgiver av den administrerte løsningen, kan du bruke administrerte egenskaper til å deaktivere spesifikke tilpassinger for komponentene i den administrerte løsningen.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Bruk administrerte egenskaper](/dynamics365/customer-engagement/developer/use-managed-properties)

## <a name="modular-solutions"></a>Modulære løsninger

Du kan bruke løsningsrammeverket til å opprette et diskret sett av komponenter som gir et sett med funksjonaliteter. Hver administrerte løsning kan installeres og avinstalleres for å returnere kundens distribusjon til opprinnelig tilstand. Hver administrerte løsning du oppretter, kjører i tillegg til systemløsningen, og får tilgang til egenskapene til den underliggende løsningen.

Du kan også bygge administrerte løsninger som kjører i tillegg til andre løsninger, for å opprette et sett med funksjonaliteter som kan deles av ulike systemer. På denne måten kan du bygge og vedlikeholde en vanlig modul som en løsning for å støtte flere løsninger. På grunn av dette trenger du bare å installere løsningens som er riktig for dem, og du trenger ikke å inkludere den samme delte funksjonaliteten i hver løsning. Hvis du trenger å sende ut en oppdatering til en løsning som støtter flere løsninger, trenger du bare å oppdatere den vanlige modulen.

Kunder, systemimplementerere og andre programvareleverandører kan deretter bygge løsninger på toppen av løsningene dine for å oppnå de spesifikke tilpassingene de krever.

Når er sett med bedriftsfunksjonalitet er satt sammen av flere løsninger, kalles de pakker. Du kan bruke *Pakkedistributør* til å kombinere flere løsninger i én enkelt, installerbar enhet.

## <a name="deploy-solution-packages"></a>Distribuer løsningspakker

Bruk *Pakkedistributør* til å opprette et egendefinert installasjonsprogram for en pakke som kan inkludere 
- én eller flere løsningsfiler,
- flate filer eller eksporterte konfigurasjonsdatafiler, 
- egendefinert kode som kan kjøre før, samtidig eller etter at pakken distribueres.
- HTML-innhold som er spesifikk for pakken som kan vises i begynnelsen og mot slutten av distribusjonsprosessen. Dette kan være nyttig for å gi en beskrivelse av løsningene og filene som distribueres i pakken.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Opprett pakker for Dynamics 365 Pakkedistributør](/dynamics365/customer-engagement/developer/create-packages-package-deployer).

## <a name="team-development-of-solutions"></a>Teamutvikling av løsninger

En løsningsfil er en enkel binær fil som ikke kan gjennomgå kildekodekontroll eller teamutvikling. Flere utviklere kan ikke arbeide på de egendefinerte komponentene i løsningen.

*SolutionPackager*-verktøyet løser problemet med kildekodekontroll og teamutvikling for løsningsfiler. Dette verktøyet identifiserer individuelle komponenter i den komprimerte løsningsfilen, og pakker dem ut til individuelle filer. Verktøyet kan også gjenskape en løsningsfil ved å pakke filene som tidligere ble pakket ut. Dette gjør det mulig for flere personer å arbeide uavhengig på én enkelt løsning og pakke ut endringene til en felles plassering. Fordi hver komponent i løsningsfilen er delt opp i flere filer, blir det mulig å flette tilpassinger uten å overskrive tidligere endringer. Du kan også bruke SolutionPackager-verktøyet til å starte fra en automatisert byggingsprosess for å generere en komprimert løsningsfil fra tidligere utpakkede komponentfiler, uten å måtte ha en aktiv Dynamics 365-forekomst.

Hvis du vil ha mer informasjon, kan du se [Dynamics 365 Customer Engagement – Veiledning for utviklere: Løsningsverktøy for teamutvikling](/dynamics365/customer-engagement/developer/solution-tools-team-development)

### <a name="see-also"></a>Se også

[Common Data Service for apper – Oversikt for utviklere](overview.md)
