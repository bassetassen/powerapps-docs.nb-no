---
title: Eksporter til et dynamisk regne ark i Excel i modell drevne Powerapps | MicrosoftDocs
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
ms.openlocfilehash: 804deaf9f12d4c73abbfd8f414f27307fe5aa7d6
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/19/2019
ms.locfileid: "63318749"
---
# <a name="export-to-an-excel-dynamic-worksheet"></a>Eksporter til et dynamisk regne ark i Excel

Eksporter appdataene dine til et Office Excel-regneark slik at brukere kan få den nyeste informasjonen. Tenk deg at administrerende direktør for bedriften din får den kritiske informasjonen de trenger, uten å måtte navigere i en app, men i stedet bare å åpne Excel-koblingen på skrive bordet. Du kan eksportere opptil 100 000 poster om gangen.    
  
## <a name="export-data-to-an-excel-dynamic-worksheet"></a>Eksporter data til et dynamisk regne ark i Excel  

Du kan ikke eksportere data til et dynamisk regne ark i Excel for alle oppførings typer. Hvis du ikke ser alternativet, er det ikke tilgjengelig for den oppføringen.  
  
1. Åpne en liste over poster i appen, og velg pilen til høyre for **Eksporter til Excel**. 
  
2. Velg **dynamisk regne ark**.  
  
3. I dialog boksen **Velg kolonner for dynamisk Excel** velger du Kol onne innstillinger, og deretter velger du **Eksporter**.  
  
4. Velg **Lagre** , og deretter lagrer du XLSX-filen. Noter plasseringen der du lagret filen.  
  
   > [!NOTE]
   > Hvis du skal redigere data filen senere, anbefales det at du lagrer filen før du åpner den. Hvis ikke, kan det hende du får følgende feil melding: **Excel kan ikke åpne eller lagre flere dokumenter fordi det ikke er nok tilgjengelig minne eller disk plass.**  
   > 
   > Slik løser du problemet:  
   > 
   >    1. Åpne Excel og gå til **fil** > **Alternativer** > **klarerings senter** **Innstillinger Center innstillinger** > **beskyttet visning**.  
   >    2. Fjern alle tre elementer i **beskyttet visning**.  
   >    3. Velg **OK** >  **.**  
   >     
   >    Vi anbefaler likevel sterkt at du lagrer og åpner data filen i stedet for å deaktivere beskyttet visning, noe som kan føre til at data maskinen blir utsatt for risiko.  
  
5. Åpne Excel, og åpne deretter XLSX-filen du lagret i forrige trinn.  
  
6. Hvis du ser sikkerhets advarsel **eksterne data tilkoblinger er deaktivert**, velger du **Aktiver innhold**.  
  
7. Hvis du vil oppdatere data i filen, velger du **Oppdater fra powerapps**på **data** -fanen.  
  
   > [!NOTE]
   > Hvis du har et telefon nummer som starter med **+** eller **–** (for eksempel + 1-123-456-7890), vil telefon nummer feltet ikke vise nummeret riktig når du oppdaterer det dynamiske regne arket.   
   >
   > Hvis du vil unngå problemet, kan du bruke et mellomrom eller parenteser **()** på følgende måte: + 1 123-456-7890 eller + 1 (123)-456-7890.  
  
## <a name="tips"></a>Tips  
  
- Du kan sende en dynamisk Excel-fil eller lagre den som en delt fil hvis mottakerne er i samme domene som deg. Når mottakerne åpner den dynamiske filen, ser de dataene de har tillatelse til å vise i appen, slik at dataene de ser, kan være forskjellige fra det du ser.  
  
- Noen system visninger, for eksempel kontoer: Ingen kampanje aktiviteter de siste 3 månedene kan bare eksporteres til et statisk Excel-regneark.  
  
- I PowerApps eksporteres valuta verdier til Excel som tall. Hvis du vil formatere dataene som valuta etter at du har fullført eksporten, kan du se hjelpeemnet «Vis tall som valuta».

- Dato-og klokkeslett verdiene som du ser i appen, vises bare som dato når du eksporterer filen til Excel, men cellen faktisk viser både datoen og klokkeslettet.  
  
- Hvis du skal gjøre endringer og importere data filen tilbake til appen, må du huske at feltene sikret, beregnet og kompositt (for eksempel fullstendig navn) er skrivebeskyttet og ikke kan importeres til appen. Du kan redigere disse feltene i Excel, men når du importerer dataene tilbake til appen, blir ikke disse feltene oppdatert. Hvis du vil oppdatere disse feltene, for eksempel navnet på en kontakt, anbefales det at du bruker denne visningen til å eksportere dataene, oppdatere dem i Excel og importere dem tilbake til appen for endringer.  
 

