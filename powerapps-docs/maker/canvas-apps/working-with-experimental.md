---
title: Forhåndsvisnings- og eksperimentelle funksjoner | Microsoft Docs
description: Test og begynn å bruke nye funksjoner.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/16/2018
ms.author: gregli
ms.openlocfilehash: d976a81603d48d72ecb2dc7c279b59d0e70800eb
ms.sourcegitcommit: b9fa569153924af9815db45d52c04e764ddb7fa2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/17/2018
ms.locfileid: "39094831"
---
# <a name="understand-experimental-and-preview-features-in-powerapps"></a>Forhåndsvisnings- og eksperimentelle funksjoner i PowerApps

Vi foretar endringer og legger til funksjoner i hver utgave, slik at PowerApps er et verktøy som er best mulig tilpasset dine behov. Vi vil videreutvikle produktet.  

Vi tar bakoverkompatibilitet på alvor. Alle endringer eller forbedringer kan imidlertid føre til utilsiktede bivirkninger, og det kan hende appen ikke virker helt som den gjorde tidligere.

For å hjelpe med å balansere forbedringer mot påvirkning på eksisterende apper, fører vi større funksjoner gjennom trinnvise faser. Denne artikkelen beskriver denne prosessen og hvordan du kan kontrollere eksponeringen for funksjoner som er under utvikling.

## <a name="feature-roll-out-stages"></a>Funksjonsutrullingsfaser

Funksjonene går gjennom tre faser på vei mot å bli offisielle deler av produktet:

1. **Eksperimentell**: Arbeid med denne funksjonen pågår. Ikke stol på den ennå, ettersom den kan komme til å gjennomgå betydelige endringer.
1. **Forhåndsvisning**: Denne funksjonen er nesten ferdig og er stabil. Begynn å overføre eksisterende apper til den nå.
1. **Lansert**: Denne funksjonen er ferdig. Alle appene har aktivert denne funksjonen, og du kan ikke slå den av.

I hver fase stiger antallet personer som bruker funksjonen, noe som hjelper oss med å validere at funksjonen er det du trenger, og at vi ikke introduserer utilsiktede bivirkninger.

**Tilbakemeldingen din er viktig for denne prosessen.**  Publiser tilbakemeldingen din i [Fellesskapsforumet for PowerApps](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).

Hvor lenge forblir en funksjon i hver fase? Dette varierer fra funksjon til funksjon. Vi ser på mange faktorer, for eksempel hvor mange apper som bruker funksjonen, antall rapporterte problemer, og hvor raskt det er behov for funksjonen. Funksjoner kan forbli i samme fase i flere uker og opptil mange måneder.

Denne tabellen kan hjelpe deg med å avgjøre hvor du skal begynne: 

| Fase | Når skal jeg bruke det? | Kan jeg trygt bruke den? | Er den aktivert som standard for nye apper? | 
|----|----|----|-----|------|
| **Eksperimentell** | Hvis du er blant de første til å ta den i bruk, ser noe nyttig, og vil hjelpe med å teste funksjonen. | Nei.  Eksperimentelle funksjoner kan endres radikalt eller forsvinne fullstendig når som helst. | Nei. Du må eksplisitt registrere deg for å få funksjonen.  |  
| **Forhåndsvisning** | Nye apper inkluderer denne funksjonen automatisk.  Begynn å aktivere og teste i eksisterende apper, for denne funksjonen slås snart på for disse også. | Ja. Denne funksjonen er på god vei til å bli en permanent del av produktet.  | Ja. Du bør slå den av hvis det oppstår et problem.  Rapporter problemer. Dette er hovedårsaken til at funksjonen er i Forhåndsvisning. | 
| **Lansert** (vises ikke lenger i **Avanserte innstillinger**) | Alle apper har denne funksjonen. | Ja. | Ja.  De fleste kan ikke deaktiveres.  |  

Mot slutten av forhåndsvisningen kan det hende vi aktiverer funksjonen for alle appene én gang, og vi merker den til å være i **endelig validering**.  Denne endringen gir flest mulig en siste sjanse til å prøve ut funksjonen mens de kan fremdeles kan slå den av. Hyppig tilbakemelding er viktig i denne perioden fordi funksjonen blir fullstendig lansert i neste fase, og du kan ikke slå den av.  

## <a name="documentation"></a>Dokumentasjon

Hvor finner jeg informasjon om disse funksjonene?  Vi behandler forhåndsvisningsfunksjoner som ferdige funksjoner, og du kan finne ut mer om dem på samme måte som du gjør med andre produktfunksjoner: 
- [PowerApps-dokumentasjon](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/getting-started). Vi gir grunnleggende informasjon om den nye funksjonen: fordelene, hvordan du kommer i gang og referanseinformasjon.
- [Fellesskapsforum for PowerApps](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).  Andre utforsker den nye funksjonen sammen med deg. Lær av deres erfaringer, og del dine egne.
- [PowerApps-blogg](https://powerapps.microsoft.com/en-us/blog/).  Ofte, men ikke alltid, følger et blogginnlegg med en ny funksjon.

Eksperimentelle funksjoner er forskjellige.  Arbeid med funksjonene pågår, og vi anser dem ikke som ferdige. Den korte beskrivelsen i **Appinnstillinger**-ruten (se nedenfor) kan være den eneste informasjonen om dem. Eksperimentelle funksjoner vises vanligvis ikke i dokumentasjonen. Fellesskapsforumet er sannsynligvis den beste kilden til informasjon.  I noen tilfeller beskriver et tidlig blogginnlegg funksjonen.  Hvis du ikke finner nok informasjon, kan du stille spørsmål i foraene eller vente på at funksjonene skal gå videre til Forhåndsvisningsfasen.

## <a name="controlling-which-features-are-enabled"></a>Å kontrollere hvilke funksjoner som er aktivert

Forhåndsvisnings- og eksperimentelle funksjoner er oppført i appens **Avanserte innstillinger**.  Velg **Fil**-menyen fra appen, velg **Appinnstillinger**, og velg deretter **Avanserte innstillinger**. Rull ned til inndelingene **Forhåndsvisningsfunksjoner** og **Eksperimentelle funksjoner**:

![](media/working-with-experimental/advanced-settings.png)

Hver funksjon har en veksleknapp.  **Av** betyr at funksjonen er deaktivert.  Å ha alle bryterne slått av er grunnlinjen og den sikreste måten å kjøre appen på.

I noen tilfeller må du kanskje lukke og åpne appen på nytt når du har endret en innstilling.  Funksjonsbeskrivelsen bør angi når du må utføre dette trinnet.

Øverst i **Avanserte innstillinger**-panelet finner du innstillinger for fullstendig lanserte funksjoner, som ikke er i forhåndsvisning eller eksperimentelle, og som du kan stole fullt og helt på. 

Disse innstillingene er spesifikke for hver app. Hvis du endrer veksleknappen, er det bare appen som er åpen som påvirkes. Hvis du oppretter en app, går disse bryterne tilbake til standardinnstillingene for appen.
