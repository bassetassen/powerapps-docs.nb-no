---
redirect_url: 'create-edit-entity-relationships#entity-relationship-behavior'
title: Atferd for enhetsrelasjon (Common Data Service) | Microsoft Docs
description: <Description>
ms.custom: ''
ms.date: 08/01/2018
ms.reviewer: ''
ms.service: powerapps
ms.topic: article
author: Mattp123
ms.author: matp
manager: kvivek
---
# <a name="entity-relationship-behavior"></a>Enhetsrelasjonsfunksjonalitet

Virkemåte for relaterte enheter er viktig fordi den sikrer dataintegritet og kan automatisere forretningsprosesser for selskapet.

## <a name="preserve-data-integrity"></a>Opprettholde dataintegritet

Noen enheter finnes for å støtte andre enheter. De har ingen mening på egen hånd. De har vanligvis et nødvendig oppslagsfelt for å koble til den primære enheten de støtter. Hva skal skje når hovedoppføringen slettes?

Du kan bruke relasjonsfunksjonaliteten for å definere dette i samsvar med reglene i bedriften din. To alternativer er:

- Hindre sletting av den primære enheten, slik at de relaterte enhetsoppføringene kan avstemmes, kanskje ved at man knytter dem til en annen hovedenhet.
- Tillate at de relaterte enhetene slettes automatisk med slettingen av hovedenhetsoppføringen.

Hvis den relaterte enheten ikke støtter en hovedenhet, kan du tillate at den primære enheten slettes, og verdien for oppslaget fjernes.

## <a name="automate-business-processes"></a>Automatisere forretningsprosesser
  
Anta at du har en ny selger, og du vil tilordne vedkommende en rekke eksisterende forretningsforbindelser som er tilordnet en annen selger. Hver forretningsforbindelsesoppføring kan ha en rekke tilknyttede oppgaveaktiviteter. Du kan enkelt finne de aktive forretningsforbindelsene du vil tilordne på nytt, og tilordne dem til den nye selgeren. Men hva skal skje med oppgaveaktivitetene som er knyttet til forretningsforbindelsene? Vil du åpne hver oppgave og avgjøre om den også skal tilordnes den nye selgeren? Sannsynligvis ikke. I stedet kan du la relasjonen automatisk bruke noen standardregler for deg. Disse reglene gjelder bare for oppgaveoppføringer som er knyttet til forretningsforbindelser som du tilordner på nytt. Alternativene er:  
  
- Tilordne alle aktive oppgaver på nytt.  
- Tilordne alle oppgaver på nytt. 
- Tilordne ingen av oppgavene på nytt.  
- Tilordne alle oppgaver på nytt som er tilordnet til den tidligere eieren av forretningsforbindelsen.  
  
Relasjonen kan styre hvordan handlingene som utføres på en oppføring for hovedenhetsoppføringen, overlapper ned til eventuelle relatert oppføringer.  

## <a name="behaviors"></a>Virkemåter

Det finnes flere typer virkemåter som kan brukes når bestemte handlinger forekommer.

|Virkemåte|Beskrivelse|
|--|--|
|**Overlapp aktive**|Utfør handlingen på alle aktive relatert enhetsoppføringer.|
|**Overlapp alle**|Utfør handlingen på alle relatert enhetsoppføringer.|
|**Overlapp ingen**|Ikke gjør noe.|
|**Fjern kobling**|Fjern oppslagsverdien for alle relaterte oppføringer.|
|**Begrens**|Hindre at hovedenhetsoppføringen slettes når det finnes relaterte enhetsoppføringer.|
|**Overlapp brukereide**|Utfør handlingen på alle relatert enhetsoppføringer som eies av samme bruker som hovedenhetsoppføringen.|

## <a name="actions"></a>Handlinger

Dette er handlinger som kan utløse enkelte virkemåter:

|Felt|Beskrivelse|Alternativer|
|--|--|--|
|**Tilordne**|Hva skal skje når hovedenhetsoppføringen tilordnes til noen andre?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Overordne på nytt**|Hva skal skje når oppslagsverdien for en relatert enhet i en overordnet relasjon endres?<br />Mer informasjon: [Overordnede enhetsrelasjoner](#parental-entity-relationships)|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Dele**|Hva skal skje når hovedenhetsoppføringen deles?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Slett**|Hva skal skje når hovedenhetsoppføringen slettes?|Overlapp alle<br />Fjern kobling<br />Begrens|
|**Oppheve deling**|Hva skal skje når delingen av en hovedenhetsoppføring oppheves?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Slå sammen**|Hva skal skje når en hovedenhetsoppføring slås sammen?|Overlapp alle<br />Overlapp ingen|
|**Visning av beregnet verdi**|Hva er ønsket virkemåte for visningen av beregnet verdi knyttet til denne relasjonen? |Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|


## <a name="parental-entity-relationships"></a>Overordnede enhetsrelasjoner

Hvert par med enheter som er kvalifiserte for en 1:N-relasjon, kan ha flere 1:N-relasjoner mellom dem. Vanligvis kan bare én av disse relasjonene anses som en overordnet enhetsrelasjon.

En overordnet enhetsrelasjon er en 1:N-enhetsrelasjon der ett av overlappingsalternativene i **Overordnet**-kolonnen i den følgende tabellen er sann.

|Handling|Overordnet|Ikke overordnet|  
|------------|--------------|------------------|  
|**Tilordne**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Slett**|Overlapp alle|Fjern kobling<br />Begrens|  
|**Overordne på nytt**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Dele**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Oppheve deling**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  

Hvis du for eksempel oppretter en ny egendefinert enhet og legger til en 1:N-enhetsrelasjon med forretningsforbindelsesenheten der den egendefinerte enheten er den relaterte enheten, kan du konfigurere handlingene for denne enhetsrelasjonen slik at den bruker alternativene i **Overordnet**-kolonnen. Hvis du senere legger til en ny 1:N-enhetsrelasjon med den egendefinerte enheten som den refererende enheten, kan du bare konfigurere handlingene for bruk av alternativene i **Ikke overordnet**-kolonnen.

Dette betyr vanligvis at for hvert enhetspar er det bare én overordnet relasjon. Det finnes enkelte tilfeller der oppslaget på den relaterte enheten kan tillate en relasjon til mer enn én type enhet.

For eksempel hvis en enhet har et kundeoppslag som kan referere til en kontakt- eller forretningsforbindelsesenhet. Det finnes to separate overordnede 1:N-enhetsrelasjoner.

En aktivitetsenhet har et lignende sett med overordnede enhetsrelasjoner for enheter som kan tilknyttes ved hjelp av oppslagsfeltet Angående.

<a name="BKMK_RelationshipBehaviorLimitations"></a>   

## <a name="limitations-on-behaviors-you-can-set"></a>Begrensninger for virkemåter som du kan angi
  
På grunn av overordnede relasjoner finnes det enkelte begrensninger som du bør ha i tankene når du definerer enhetsrelasjoner.  
  
- En egendefinert enhet kan ikke være hovedenhet i en relasjon med en relatert systemenhet som overlapper. Dette betyr at du ikke kan ha en relasjon med handling satt til **Overlapp alle**, **Overlapp aktive** eller **Overlapp brukereide** mellom en egendefinert hovedenhet og en relatert systemenhet.  
- Nye relasjoner kan ikke ha handling satt til **Overlapp alle**, **Overlapp aktiv** eller **Overlapp brukereide** hvis den relaterte enheten i relasjonen allerede finnes som en relatert enhet i en annen relasjon, som har en handling satt til **Overlapp alle**, **Overlapp aktiv** eller **Overlapp brukereide**. Dette hindrer relasjoner som har relasjoner med flere overordnede.  
