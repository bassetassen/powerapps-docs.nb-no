---
title: Eksporter data til Excel i PowerApps | MicrosoftDocs
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
- D365CE
ms.openlocfilehash: 2c23b25c062bc5ac4be26132c63f4cc4a79c3fad
ms.sourcegitcommit: b3fd824cf0d540b964b729686b198c7ccf2c2174
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/21/2019
ms.locfileid: "67316864"
---
# <a name="export-data-to-excel"></a>Å eksportere data til Excel

Har du behov for å analysere dataene dine fra og konvertere disse dataene til handlings elementer som hjelper deg med å drive mer salg? Nå kan du gjøre dette når du eksporterer dataene til Excel eller Excel online. Det er heller ikke et problem å analysere store data sett fordi du kan eksportere opptil 100 000 rader med data.
  
Du kan velge å eksportere statiske regne ark eller dynamiske regne ark, som du kan importere tilbake til appen. Hvis du trenger mer avanserte funksjoner, kan du eksportere en dynamisk pivottabell, som gjør det veldig enkelt å organisere og oppsummere data.  
  
Du kan eksportere data til en standard Excel-fil som du kan bruke på alle enheter som telefon, nett brett eller skrive bords data maskin. Dataene eksporteres i samme format som du ser i appen. Teksten forblir tekst, tall vil være tall, og datoer vil være datoer. Når du eksporterer data fra appen til Excel, kan det imidlertid hende at noen celle formater endres. Tabellen nedenfor viser hvordan du kan se dataene i appene, og hvordan celle formatet endres når du eksporterer dataene til Excel.  
  
## <a name="cell-format-when-data-is-exported-from-model-driven-apps"></a>Celle format når data eksporteres fra modell drevne apper
  
| Data format i modell drevne apper |                                            Celle format i Excel                                             |
|----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            Tekst, ticker-symbol, telefon, alternativer angitt og oppslag            |                                                       Vis som tekst og alternativ sett blir rulle gardin liste                                                       |
|                                 E-post, URL-adresse                                 |                                                                        Vis generelt                                                                         |
|                                   Tall                                   |                                                             Viser som tall uten gruppe skille tegn                                                             |
|                                  Trianguleringsvalutaen                                  |                                                         Viser som tall og inkluderer ikke dollar tegn ($)                                                         |
|                          Bare dato og klokkeslett                          |                                                                       Viser som bare dato                                                                        |
|                       Beregnede og oppsamlede felt                        | Redigerbar i Excel, men kan ikke importeres tilbake til PowerApps |
|                               Sikrede felt                               | Redigerbar i Excel, men kan ikke importeres tilbake til PowerApps |
  
## <a name="see-which-type-of-export-works-best-for-you"></a>Se hvilken type eksport som fungerer best for deg  
  
|                                                                                                               Oppgave                                                                                                                |                                              få mer informasjon                                               |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
|   Foreta en *ad hoc-* eller *Hva hvis* -analyse uten å endre appdataene. Eller rask masse redigering til flere poster.   | [Eksporter til Excel online](export-to-excel-online.md) |
|                                                                   Få et øyeblikks bilde av dataene ved gjeldende data og tidspunkt, eller du vil dele dem med andre.                                                                    |           [Eksporter til et statisk regne ark i Excel](export-excel-static-worksheet.md)           |
| Få den mest oppdaterte informasjonen og være i stand til å oppdatere den i Excel og sammenligne det du ser i appen når som helst. |          [Eksporter til et dynamisk regne ark i Excel](export-excel-dynamic-worksheet.md)          |
|                                                                      Vis AppData i en pivottabell.                                                                      |                 [Eksporter til en Excel-pivottabell](export-excel-pivottable.md)                 |



Når du eksporterer data i Excel (. xlsx-format) og deretter legger til eller endrer kolonner, kan du ikke importere dataene tilbake til Dynamics 365. Dette støttes ikke for XLSX-filformatet.  
  
Hvis du bruker Excel 2010, kan du få denne feil meldingen når du eksporterer data fra konto området: 
 
`The file is corrupt and cannot be opened.`  
  
Feil meldingen vises på grunn av en innstilling i Excel. Gjør følgende for å løse problemet:  
  
1. Åpne Excel 2010.  
  
2. Gå til **fil** > **Alternativer**.  
  
3. Gå til**Innstillinger for klarerings senter**for klarerings **senter** > .  
  
4. Velg **beskyttet visning** , og fjern deretter merkene for de to første alternativene.  
  
5. Velg **OK** , og lukk deretter dialog boksen **Alternativer** .  
  

