---
title: Eksporter til en Excel-pivottabell i modell drevne PowerApp | MicrosoftDocs
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
ms.openlocfilehash: 90cf377f10a99dbcece1e5f556cb50e678099744
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/19/2019
ms.locfileid: "61544986"
---
# <a name="export-to-an-excel-pivottable"></a>Eksporter til en Excel-pivottabell


Du kan eksportere AppData til en Office Excel-pivottabell for å se mønstre og trender i data. En Excel-pivottabell er en flott metode for å summere, analysere, utforske og presentere app-dataene dine. Du kan eksportere opptil 100 000 poster om gangen.  
  

## <a name="export-data-to-an-excel-pivottable"></a>Eksporter data til en Excel-pivottabell  
Alternativet for å eksportere data til en Excel-pivottabell er ikke tilgjengelig i alle oppførings typer. Hvis du ikke ser alternativet, er det ikke tilgjengelig for den oppføringen.  
  
1. Åpne en liste med oppføringer i appen, Velg pilen til høyre for **Eksporter til Excel**, og velg deretter **Dynamisk pivottabell**.  
  
2. Velg Kol onne innstillingene i dialog boksen **Velg kolonner for pivot Excel** , og velg deretter **Eksporter**.  
  
   Som standard inkluderer **felt listen** for pivottabellen bare felt som vises i **Select columns for pivot Excel** -listen.  
  
3. Velg **Lagre** , og deretter lagrer du XLSX-filen. Noter plasseringen der du lagret filen.  
  
   > [!NOTE]
   > Hvis du skal redigere data filen senere, anbefales det at du lagrer filen før du åpner den. Hvis ikke, kan det hende du får følgende feil melding: **Excel kan ikke åpne eller lagre flere dokumenter fordi det ikke er nok tilgjengelig minne eller disk plass.**  
   > 
   > Slik løser du problemet:  
   > 
   > 1. Åpne Excel og gå til **fil** > **Alternativer** > **klarerings senter**.  
   > 2. Velg **Innstillinger for klarerings senter** , og velg deretter **beskyttet visning**.  
   > 3. Under **beskyttet visning**fjerner du merket i avmerkings boksene for alle tre elementene.  
   > 4. Velg **OK** >  **.**  
   > 
   > Vi anbefaler likevel sterkt at du lagrer og åpner data filen i stedet for å deaktivere beskyttet visning, noe som kan føre til at data maskinen blir utsatt for risiko.  
  
4. Åpne Excel, og åpne deretter XLSX-filen du lagret i forrige trinn.  
  
5. Hvis du ser sikkerhets advarsel **eksterne data tilkoblinger er deaktivert**, velger du **Aktiver innhold**.  
  
6. Hvis du vil oppdatere data i filen, velger du **Oppdater fra powerapps**på **data** -fanen.  
  
7. Dra feltene fra felt listen for pivottabellen til pivottabellen. Se Hjelp for Excel hvis du vil ha mer informasjon.  
  
## <a name="tips"></a>Tips  
  
- I PowerApps eksporteres valuta verdier til Excel som tall. Når du har fullført eksporten, kan du se hjelpeemnet «Vis tall som valuta» for å formatere dataene som valuta.
  
- Dato-og klokkeslett verdiene som du ser i appen, vises bare som dato når du eksporterer filen til Excel, men cellen faktisk viser både datoen og klokkeslettet.  
  
- Hvis du skal gjøre endringer og importere data filen tilbake til appen, må du huske at feltene sikret, beregnet og kompositt (for eksempel fullstendig navn) er skrivebeskyttet og ikke kan importeres til appen. Du kan redigere disse feltene i Excel, men når du importerer dataene tilbake til appen, blir ikke disse feltene oppdatert. Hvis du vil oppdatere disse feltene, for eksempel navnet på en kontakt, anbefales det at du bruker denne visningen til å eksportere dataene, oppdatere dem i Excel og importere dem tilbake til appen for endringer.  
  
 
