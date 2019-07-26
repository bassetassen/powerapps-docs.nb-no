---
title: Opprett en rapport ved hjelp av rapport vei viseren | Microsoft Docs
description: Opprett en rapport ved hjelp av rapport vei viseren i PowerApps
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
ms.openlocfilehash: 0f953c44d81742baca39058cd68180ca63833eb6
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420287"
---
# <a name="create-a-report-using-the-report-wizard"></a>Opprett en rapport med rapportveiviseren


Bruk rapport vei viseren til å opprette rapporter med diagrammer og tabeller som gjør det enkelt å analysere dataene. 

Alle rapporter som er opprettet ved hjelp av rapport vei viseren, er hente BAS ert rapporter. Vær oppmerksom på at alle rapporter som er generert med rapport vei viseren, skrives ut i liggende modus.

## <a name="create-a-new-report"></a>Opprett en ny rapport

1. Velg rapporter-området fra navigasjons ruten til venstre.  
2. Velg **ny**på kommando linjen.

    > [!div class="mx-imgBorder"]
    > ![Opprett en ny rapport](media/newreport.png "Opprett en ny rapport")
  
3. En **rapport: den nye rapport** skjermen vises. For **rapport typen** lar rapporten standard valg til, rapport **vei viser** og velge **rapport vei viser** knappen. 

    > [!div class="mx-imgBorder"]
    > ![Rapport vei viser](media/report_wizard.png "Rapport vei viser skjerm")
  
4. Behold standard valgene i den neste skjermen, og velg deretter **neste**.
 
    > [!div class="mx-imgBorder"]
    > ![Rapport vei viser](media/report_wizard_1.png "Rapport vei viser skjerm")
   
4. Skriv inn et navn på rapporten på **rapport egenskaper** -skjermen, og velg deretter posten som skal tas med i rapporten, og velg deretter **neste**.
 
    > [!div class="mx-imgBorder"]
    > ![Skjerm for rapport egenskaper](media/report_wizard_2.png "Skjerm for rapport egenskaper")
  
5.  På **Select-postene som skal inkluderes i rapport** skjermen, velger du filtrene for å bestemme hvilke poster som skal inkluderes i rapporten. Hvis du for eksempel bare vil se resultater for poster som er endret de siste 60 dagene, kan du angi dette filteret i dette skjerm bildet. Hvis du ikke vil at dataene skal filtreres, velger du **Fjern**.

    > [!div class="mx-imgBorder"]
    > ![Velg poster som skal inkluderes i rapporten *](media/report_wizard_3.png "Velg poster som skal inkluderes i rapporten")
  
6. Velg oppsettet til rapporten, på **Plasser ut felt** -skjermen. Velg **Klikk her for å legge til en gruppering** og Velg hvordan du vil at dataene skal grupperes.

    > [!div class="mx-imgBorder"]
    > ![Utform felt](media/report_wizard_4.png "Utform felt")

7. Velg **oppførings typen** og **kolonnen** for dataene du vil ha gruppert i rapporten. Når du er ferdig med valgene dine, velger du **OK**.

    > [!div class="mx-imgBorder"]
    > ![dialog boksen Legg til gruppering](media/report_wizard_5.png "Legg til gruppering-skjerm")
  
8. Velg **Klikk her for å legge til en kolonne** i kolonner med data som er relatert til oppførings typen du valgte i forrige trinn.  

    > [!div class="mx-imgBorder"]
    > ![Legg til gruppering-skjerm](media/report_wizard_6.png "Legg til gruppering-skjerm")

9. På **Legg til kolonne** -skjermen velger du dataene du vil vise for kolonnen, og deretter velger du **OK**. 

    > [!div class="mx-imgBorder"]
    > ![Legg til kolonne-skjerm](media/report_wizard_7.png "Legg til kolonne-skjerm")
  
10. Gjenta det forrige trinnet for eventuelle andre kolonner du vil legge til. Når du er ferdig, kan du Slect **neste**på **Plasser ut felt** -skjermen.
 
    > [!div class="mx-imgBorder"]
    > ![Legg til mer kolonne-skjerm](media/report_wizard_8.png "Legg til mer kolonne-skjerm")
  
11. Velg hvordan du vil formatere rapporten, og velg deretter **neste**i **Format rapport** skjermen.
 
    > [!div class="mx-imgBorder"]
    > ![Formater rapport](media/report_wizard_9.png "Formater rapport skjerm bilde")

12. Se gjennom sammendraget av rapporten, og velg **neste** , og velg deretter **Fullfør**. Nå kan du se denne rapporten i listen over rapport i systemet.

    > [!div class="mx-imgBorder"]
    > ![Vis rapport](media/report_wizard_10.png "Vis rapporten")

### <a name="see-also"></a>Se også
[Arbeide med rapporter](work-with-reports.md) 

[Legg til en eksisterende rapport](add-existing-report.md)

[Rediger rapport filter](edit-report-filter.md)

[Feilsøke problemer med data som ikke vises i en rapport](troubleshoot-reports.md)


