---
title: Legg til en tilkoblings rolle for å koble poster til hverandre | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 8/01/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: d824e76f6ffd5cc72f2f030f7009d3f4a140bf8a
ms.sourcegitcommit: d6b7f98b4ae011a753c1e72d7708f0f8dfbfb1fb
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/22/2019
ms.locfileid: "69896248"
---
# <a name="add-a-connection-role-to-link-records-to-each-other"></a>Legg til en tilkoblings rolle for å koble poster til hverandre

[!INCLUDE [cc-beta-prerelease-disclaimer](../includes/cc-beta-prerelease-disclaimer.md)]

Med tilkoblinger kan du enkelt knytte brukere, kontakter, tilbud, salgs ordrer og mange andre enhets poster med hverandre. Postene i tilknytningen kan tilordnes bestemte roller som bidrar til å definere formålet med relasjonen.

Det er en rask metode for å opprette flere tilkoblinger og roller for en bestemt post. En kontakt kan for eksempel ha mange relasjoner med andre kontakter, kontoer eller kontrakter. En kontakt kan spille en annen rolle i hver relasjon.

Tilkoblings roller er direkte knyttet til en tilkobling. Hvis du vil bruke en tilkoblings rolle, må du først legge til en tilkobling i oppføringen.

Før du kan legge til tilkoblings roller, må du aktivere administrator. Hvis du vil ha mer informasjon, kan du se [konfigurere tilkoblings roller](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/configure-connection-roles).

1. Hvis du vil legge til eller administrere tilkoblinger, velger du posten du vil administrere som en mulighet.  
2. Velg **relatert** -fanen, og velg deretter **tilkobling**. Dette åpner tilkoblings rute nettet med listen over tilkoblinger for oppføringen.

    > [!div class="mx-imgBorder"]
    > ![Legg til en ny tilkoblings rolle](media/connection1.png "Legg til en ny tilkoblings rolle") 

3. Velg **Koble** til, og velg deretter **til en annen** eller **til meg**.

    > [!div class="mx-imgBorder"]
    > ![Velg tilkoblings type](media/connection2.png "Velg tilkoblings type") 
  
4. Skriv inn eller Finn navnet på posten for tilkoblingen i **navn** -feltet.

5. Velg oppslags-ikonet på **som dette rolle** feltet, og velg deretter **ny tilkoblings rolle**. Du kan også bruke søket til å finne en eksisterende rolle som du vil knytte til tilkoblingen, og deretter velge **Lagre**.

    > [!div class="mx-imgBorder"]
    > ![Velg Ny tilkoblings rolle](media/connection3.png "Velg Ny tilkoblings rolle")  

    > [!NOTE]
    > Hvis du har angitt informasjon før du oppretter en ny tilkoblings rolle, vil det vises en advarsels dialog boks som spør om du vil kansellere og fortsette å arbeide med forbindelsen, eller for å gå videre og la den gjeldende posten være aktiv.

6. Hvis du vil opprette en ny tilkoblings rolle, skriver du inn et navn på skjerm bildet **ny tilkoblings rolle** og velger en **Kategori for tilkoblings rolle**.

    > [!div class="mx-imgBorder"]
    >  ![Legg til tilkoblings rolle kategori](media/connection4.png "Legg til tilkoblings rolle kategori") 

7. Når du er ferdig, velger du **lagre & Lukk**.

  
## <a name="manage-connection-roles"></a>Administrer tilkoblings roller

Hvis du vil administrere en tilkoblings rolle, velger du tilkoblings rollen fra en tilkoblings enhet. Dette åpner enhets posten for tilkoblings rollen.  Du kan redigere navnet, velge en kategori for tilkoblings rolle og legge til en beskrivelse.


   > [!div class="mx-imgBorder"]
   > ![Rediger tilkoblings rolle](media/connection7.png "Editconnection-rolle") 
  
Du kan også administrere tilkoblings rolle typene du vil knytte til tilkoblings rollen.

1. Åpne tilkoblings rollen, og velg deretter **Behandle oppførings type** på kommandoen. 

    > [!div class="mx-imgBorder"]
    > ![Rediger tilkoblings rolle](media/connection5.png "Editconnection-rolle") 
  

2. Dette åpner en liste over tilkoblings rolle typer som du kan legge til eller fjerne for denne tilkoblings rollen.

    > [!div class="mx-imgBorder"]
    > ![Administrer oppførings type](media/connection6.png "Administrer oppførings type") 


