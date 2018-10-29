---
title: Endre prefiks for løsningsutgiver | MicrosoftDocs
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: ece684h8-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
ms.openlocfilehash: 5881dd6742dd441d135768d3a96fd36dbef9e700
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693840"
---
# <a name="change-the-solution-publisher-prefix"></a>Endre prefiks for løsningsutgiver

Hver tilpasning du gjør er en del av en løsning. Hver løsning har en utgiver. Løsningen du vil arbeide med i PowerApps, blir som standard **Common Data Services-standardløsningen** som er tilknyttet **CDS standardutgiver**.

Standardprefikset for tilpassing tilordnes tilfeldig for denne utgiveren, og kan for eksempel være `cr8a3`. Dette betyr at navnet på alle nye metadataelementer som opprettes for organisasjonen din, har dette foran navnene som brukes til å identifisere elementene unikt. Hvis du oppretter en ny enhet med navnet **Dyr**, blir det unike navnet som brukes av CDS for apper, være `cr8a3_animal`. Det samme gjelder for alle nye felt (attributter), relasjoner eller alternativsett-alternativer.

Med mindre du vil distribuere løsningen din slik at den er installert sammen med metadataelementer som ble opprettet for en annen løsningsutgiver, er det ikke viktig hva tilpassingsprefikset er. Det er ikke synlig for de fleste personer som bruker appene dine. Men det er synlig for utviklere og andre teknikere som gjør ting som for eksempel å bygge rapporter. Den gir en rask måte å forstå hvilken løsning som legges til elementet.

Derfor liker mange å endre prefikset for løsningsutgiveren, slik at det blir mer meningsfylt, spesielt når du viser metadataelementer som inkluderer elementer som er importert fra andre løsninger. 

> [!NOTE]
> Hvis du endrer prefikset for løsningsutgivere, bør du gjøre dette før du oppretter nye metadataelementer. Du kan ikke endre navnene på metadataelementer.
> Når du endrer prefiksverdien for tilpassing, må du bruke TAB for å flytte til det neste feltet. **Prefikset for alternativverdi** vil automatisk generere et tall som er basert på prefikset for tilpassing. Dette nummeret brukes når du legger til alternativer i alternativsett, og gir en indikator på hvilken løsning som ble brukt til å legge til alternativet. 

## <a name="change-the-solution-publisher-prefix-for-the-cds-default-publisher"></a>Endre prefiks for løsningsutgiver for CDS-standardutgiver  

 1. Velg **Modelldreven** nederst til venstre i PowerApps-portalen.
 2. Klikk på **Avansert** i navigasjonsruten til venstre for å åpne **Common Data Services-standardløsning**
 3. Velg **Informasjon**-området i navigasjonsruten til venstre i løsningsutforskeren.
 4. Klikk på **Utgiver**-koblingen for å åpne skjemaet **CDS-standardutgiver**.
 5. Rediger **Prefiks**-feltverdien til ønsket prefiks for tilpassing.
 6. Klikk på **Lagre og lukk**.
  
## <a name="change-the-solution-publisher-prefix-for-any-publisher"></a>Endre prefiks for løsningsutgiver for hvilken som helst utgiver

Personer som distribuerer løsningene sine, jobber vanligvis i en løsning som de oppretter, heller enn **Common Data Services-standardløsningen**. Prefiks for tilpassing angis vanligvis når de oppretter løsningen. Du kan endre prefikset for tilpassing for en annen ikke-administrert løsning som du arbeider med, ved å følge disse trinnene: 

 1. Velg **Modelldreven** nederst til venstre i PowerApps-portalen.
 2. Klikk på **Avansert** i navigasjonsruten til venstre for å åpne **Common Data Services-standardløsning**
 3. Rediger nettadressen på siden for å fjerne alt etter `dynamics.com` og laste inn siden.
 4. Naviger til **Innstillinger** > **Tilpassing** > **Tilpassinger**. 
 5. Klikk på **Utgivere**. Nå kan du se en liste over tilgjengelige utgivere.
 6. Klikk på utgiveren du vil redigere, for å åpne utgiverskjemaet.
 7. Rediger **Prefiks**-feltverdien til ønsket prefiks for tilpassing.
 6. Klikk på **Lagre og lukk**.
  