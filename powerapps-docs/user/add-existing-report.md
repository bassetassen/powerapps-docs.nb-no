---
title: Legg til en rapport fra eksterne PowerApps | Microsoft Docs
description: Legg til en rapport fra eksterne PowerApps
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 06/27/2019
ms.author: mkaur
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 24faa77b454cf3324e4b7277c94c6cd364aec9a9
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420172"
---
# <a name="add-a-report-from-outside-powerapps"></a>Legg til en rapport fra eksterne PowerApps

Hvis du har opprettet en egen definert rapport utenfor systemet, kan du enkelt legge den til i PowerApps.

Hvis du vil ha informasjon om hvordan du oppretter en egen definert rapport, kan du se [veiledning for rapportering og analyse](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/analytics/get-started-writing-reports).

1. Velg rapporter-området fra navigasjons ruten til venstre. 
2. Velg **ny**på kommando linjen.
  
   **Legg til en fil som er opprettet i et annet program**  
  
   1. Velg **eksisterende fil**i **rapport type** -boksen i **kilde** inndelingen.  
   
     > [!div class="mx-imgBorder"]
     > ![Legg til en eksisterende rapport](media/add_existing_report.png "Legg til en eksisterende rapport")
  
   2. Skriv inn banen og fil navnet til filen som skal legges til, i **fil plassering** -boksen, eller velg **Bla gjennom** for å finne filen. 
   
      Du kan laste opp mange andre filtyper, for eksempel en Excel-fil, men for å kjøre som en SQL Server Reporting Services rapport eller rapport vei viser opprettet rapport, må filen være en. RDL-fil. Hvis du vil ha mer informasjon, kan du se [rapport skrive miljø ved hjelp av SQL Server data verktøy](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/analytics/report-writing-environment-using-sql-server-data-tools).
  
      -ELLER  
  
   **Å legge til en kobling til en nettside**  
  
   1.  Velg **Koble til nettside**i **rapport type** -boksen i **kilde** inndelingen.  
  
   2.  Skriv inn Netta dressen til Netts IDen i **URL-** boksen nett side.  
  
3. Angi egenskapene for rapporten.
  
   1.  Angi et meningsfylt navn og en beskrivelse for rapporten i **detaljer** -delen.  
  
   2.  Tekst boksen **overordnet rapport** viser overordnet rapport for gjeldende rapport, hvis den finnes.  
  
   3. **Kategorier**. Merk av for **Velg eller endre verdiene for dette feltet** ![ellipse](media/ellipsis-button.png "") , knapp for uttrykks knapp, og angi deretter kategoriene som skal inkluderes i denne rapporten.  
  
   4. **Relaterte oppførings typer**. Hvis du vil at rapporten skal vises i rapporter-listen på en side for bestemte oppførings typer, velger du **Velg eller endre verdiene for feltet for** uttrykks knapp for ![ellipse](media/ellipsis-button.png "") , og deretter velger du oppførings typer.  
  
   5. **Vises i**. Hvis du vil angi hvor rapporter skal vises, velger du **Velg eller endre verdiene for feltet for** ![ellipse](media/ellipsis-button.png "") , knapp for uttrykks knapp, og deretter velger du ett eller flere av alternativene.  
  
        Hvis ingen verdier er valgt, vil rapporten ikke være synlig for slutt brukerne.  
  
4. Velg **Lagre** eller **Lagre og Lukk**.  




### <a name="see-also"></a>Se også
[Arbeide med rapporter](work-with-reports.md) 

[Å opprette en rapport ved hjelp av rapport vei viseren](create-report-with-wizard.md)

[Rediger rapport filter](edit-report-filter.md)

[Feilsøke problemer med data som ikke vises i en rapport](troubleshoot-reports.md)
