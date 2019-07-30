---
title: Rediger standard filteret for en rapport | Microsoft Docs
description: Rediger standardfilteret for en rapport
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
ms.openlocfilehash: 53e4f2fc61bb72b4c3fc6fed188b513641c2034d
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420218"
---
# <a name="edit-the-default-filter-of-a-report"></a>Rediger standardfilteret for en rapport

Når en rapport er en SQL Server Reporting Services-rapport, er aktivert for forbruks filtrering og har et standard filter, kan du endre standard filteret for å vise dataene du forventer å se i rapporten. Dette filteret brukes hver gang en bruker kjører rapporten.

1. Velg rapporter-området fra venstre navigasjons rute
2. Velg en rapport, og velg **Rediger standard filter**på commbar-linjen.

     > [!div class="mx-imgBorder"]
     > ![Rediger standard rapport filter](media/edit_filter.png "Rediger standard rapport filter")
  
3. Endre filter vilkårene.  
  
   Vilkårene er gruppert etter oppførings typer som du kan bruke i filteret, for eksempel **kontoer** eller **kontakter**.  
  
   ### <a name="to-edit-an-existing-row"></a>Slik redigerer du en eksisterende rad
   1. Velg spørrings relasjonelle operatoren og velg en operator, eller velg den understrekede verdien, og angi en ny verdi.  
  
   2. Velg spørrings relasjonelle operatoren, og velg en operator.  
  
   Slik legger du til en vilkår-rad:  

   1.  Velg **Velg**, og angi feltet du vil filtrere etter.  

   2.  Velg spørrings relasjonelle operatoren, og velg en operator.  

   3.  Velg **Angi verdi**, og skriv inn en verdi du vil filtrere på. For noen verdier kan du merke av for **Merk eller endre verdiene for dette feltet** . Klikk på ellipse-![knappen](media/ellipsis-button.png " for å åpne") dialog boksen **Velg verdier** , og Velg verdien du vil bruke.  

   ### <a name="to-group-criteria"></a>Til gruppe vilkår
   Du må velge to eller flere rader for samme posttype. Rader med felt verdier fra forskjellige oppførings typer, for eksempel oppførings typer for **konto** og **kontakt** , kan imidlertid ikke grupperes.  

   1.  For hver rad du vil gruppere, velger du **Alternativer-menyen** for denne raden i detaljert modus, og deretter velger du **Velg rad**.  

   2.  Velg **gruppe og** eller **gruppe eller**på filter-verktøylinjen.  

   3.  Hvis du vil fjerne en rad fra en gruppe, velger du **Alternativer-menyen** for denne raden, og deretter velger du **Slett**.  

   4.  Hvis du vil velge en gruppe, velger du **Alternativer-menyen** for denne gruppen, og deretter velger du **Velg gruppe**.  

   5.  Hvis du vil legge til en vilkårs setning i en gruppe, velger du **Alternativer-menyen** for gruppen, velger **Legg til setning**, og deretter velger du feltet, spørrings relasjonelle operatoren og verdien.  

   6.  Hvis du vil fjerne merkingen av en gruppe som allerede er valgt, velger du **Alternativer-menyen** for denne gruppen, og deretter velger du Opphev **valg av gruppe**.  

   7.  Hvis du vil dele opp en gruppe, velger du **Alternativer-menyen** for denne gruppen, og deretter velger du **del opp gruppe**.  

   8.  Hvis du vil endre en **gruppe og** gruppe til en **gruppe eller** gruppe, eller en **gruppe eller** gruppe til en **gruppe og** gruppe, velger du **Alternativer-menyen** for denne gruppen, og deretter velger du **endre til eller** eller **endre til og**.  

   > [!TIP]
   > - Hvis du vil fjerne alle vilkår og begynne på nytt, velger du **Fjern**på filter-verktøy linjen, og velger deretter **Bekreft**.  
   > - Hvis du vil slette en rad, velger du **Alternativer-menyen** for denne raden, og deretter velger du **Slett**.  
  
4. Når du er ferdig, velger du **Lagre standard filter**.



### <a name="see-also"></a>Se også
[Arbeide med rapporter](work-with-reports.md) 

[Å opprette en rapport ved hjelp av rapport vei viseren](create-report-with-wizard.md)

[Legg til en eksisterende rapport](add-existing-report.md)

[Feilsøke problemer med data som ikke vises i en rapport](troubleshoot-reports.md)

