---
title: Eksporter til et statisk Excel-regneark i en modell drevet app | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 82d14f70bbdcd9faddc467636db255f0b512830e
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/19/2019
ms.locfileid: "61544825"
---
# <a name="export-to-an-excel-static-worksheet"></a>Eksporter til et statisk regne ark i Excel

Når du vil presentere informasjon om dataene i appen din til en person som ikke har tilgang til appen, eller hvis du har data som ikke endres ofte, bør du vurdere å eksportere appdataene til et statisk regne ark i Office Excel.

Du kan eksportere opptil 100 000 poster om gangen. En modell drevet app viser som standard opptil 50 poster per side. Velg **side** pilene nederst i listen for å vise eventuelle ekstra sider.  
  
## <a name="export-data-to-an-excel-static-worksheet"></a>Eksporter data til et statisk regne ark i Excel  
Du kan ha mulighet til å eksportere data til et statisk Excel-regneark i alle oppførings typer. Men i noen tilfeller kan formatet være eldre, eller dataene er kanskje ikke filtrert etter det du ser i appen.  
  
1. Åpne en liste med oppføringer i appen, Velg pilen til høyre for **Eksporter til Excel**, og velg deretter **statisk regne ark (bare side)** .  
  
2. Som standard inkluderer et eksportert regne ark feltene som vises i listen, ved hjelp av samme felt rekkefølge, sortering og felt bredder. Hvis du vil gjøre endringer i Kol onnene i en avansert søk-visning, velger du **Rediger kolonner**. 
  
3. Velg **Lagre** , og deretter lagrer du XLSX-filen. Noter plasseringen der du lagret filen.  
  
   > [!NOTE]
   > Hvis du skal redigere data filen senere, anbefales det at du lagrer filen før du åpner den. Hvis ikke, kan det hende du får følgende feil melding: **Excel kan ikke åpne eller lagre flere dokumenter fordi det ikke er nok tilgjengelig minne eller disk plass.**  
   > 
   > Hvis du vil løse problemet, gjør du følgende:  
   > 
   > 1. Åpne Excel og gå til **fil** > **Alternativer** > **klarerings senter** > **Innstillinger Center innstillinger** > **beskyttet visning**.  
   > 2.  Fjern alle tre elementer i **beskyttet visning**.  
   > 3.  Velg **OK** >  **.**  
   > 
   > Vi anbefaler likevel sterkt at du lagrer og åpner data filen i stedet for å deaktivere beskyttet visning, noe som kan føre til at data maskinen blir utsatt for risiko.  


4. Åpne Excel, og åpne deretter XLSX-filen du lagret i forrige trinn.  
  
   Som standard inkluderer et eksportert regne ark feltene som vises i listen, ved hjelp av samme felt rekkefølge, sortering og felt bredder.  
  
## <a name="tips"></a>Tips  
  
- Du kan sende et statisk eksportert regne ark til alle eller lagre det i en delt fil. Alle som åpner filen, vil se alle dataene i filen.
  
- Du kan ikke endre Kol onnene for en system visning, for eksempel **alle aktive kontoer**. Du må enten tilpasse visningen, som krever system administrator eller sikkerhets rollen for systemtilpasser, eller du kan bruke Avansert søk til å opprette din egen visning basert på gjeldende visning.  
    
- I modell drevne apper eksporteres valuta verdier til Excel som tall. Ater du har fullført eksporten, kan du se hjelpeemnet «Vis tall som valuta» for å formatere dataene som valuta.
  
- Dato-og klokkeslett verdiene som du ser i appen, vises bare som dato når du eksporterer filen til Excel, men cellen faktisk viser både datoen og klokkeslettet.  
  
- Hvis du skal gjøre endringer og importere data filen tilbake til appen, må du huske at feltene sikret, beregnet og kompositt (for eksempel fullstendig navn) er skrivebeskyttet og ikke kan importeres til appen. Du kan redigere disse feltene i Excel, men når du importerer dataene tilbake til appen, blir ikke disse feltene oppdatert. Hvis du vil oppdatere disse feltene, for eksempel navnet på en kontakt, anbefales det at du bruker denne visningen til å eksportere dataene, oppdatere dem i Excel og importere dem tilbake til appen for endringer.  
  

