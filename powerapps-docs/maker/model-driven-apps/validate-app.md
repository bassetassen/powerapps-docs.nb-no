---
title: Valider og publiser en modelldrevet app ved hjelp av apputforming | MicrosoftDocs
description: Lær hvordan du validerer og publiser en modelldrevet app
keywords: ''
ms.date: 06/08/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 5a9ec120-9ddc-4d92-b48c-0fee8c57d3c3
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 10
topic-status: Drafting
ms.openlocfilehash: e3802ef423e7012974c24311c36b78cd56f8ed06
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693728"
---
# <a name="validate-and-publish-a-model-driven-app-using-the-app-designer"></a>Valider og publiser en modelldrevet app ved hjelp av apputforming

Valider en app for å se etter ressursavhengigheter som kreves for at appen skal fungere, men som ennå ikke har blitt lagt til appen. Etter en vellykket validering, kan du publisere appen. 
  
Hvis du for eksempel har lagt til et instrumentbord for Customer Service Performance i appen, som bruker diagrammer som for eksempel Saksblanding (etter prioritet) eller Saksavslutningstrend (etter dag) som du ikke har lagt til. Når du validerer denne appen, får du en liste over alle nødvendige ressurser som mangler.  
  
Når du validerer appen, viser apputforming-lerretet detaljer om ressursene som ikke finnes.  
  
1.  Velg **Valider** i apputforming.  
  
     En varslingslinje vises, med informasjon om appen har feil eller advarsler. Varslingslinjen viser advarsler i tilfeller der en enhet for eksempel ikke har noen skjemaer eller visninger, eller appen ikke inneholder noen komponenter. En feil vises kanskje hvis et områdekart ikke er konfigurert for appen. Du kan publisere en app uten å håndtere advarsler, men feil må rettes før du kan publisere.  
  
     ![Varslingsrad viser advarsler i appen](media/app-designer-warning-notification.png "Varslingsrad viser advarsler i appen")  
  
     Apputforming viser også et advarselsymbol med antall avhengigheter på hver artefakt- eller ressursflis som mangler en nødvendig ressurs.  
  
     ![Advarsel om manglende komponent på apputformingsflisen](media/warning--button-on-app-designer-tile.png "Advarsel om manglende komponent på apputformingsflisen")  
  
2.  Hvis du vil legge til de nødvendige ressursene, kan du velge **Nødvendig**-fanen på høyre side av lerretet. **Nødvendig**-fanen er synlig når minst én nødvendig ressurs mangler i appen.  
  
     Fanen viser en liste over nødvendige komponenter.  
  
     ![Nødvendig-fane som viser en liste over manglende komponenter i appen](media/app-designer-required-components-tab.png "Nødvendig-fane som viser en liste over manglende komponenter i appen")  
  
3.  Velg ressursen du vil legge til, og velg deretter **Legg til avhengigheter**. Når du legger til en påkrevd ressurs, reduseres antallet på flisen der du har lagt til ressursen.  
  
    > [!NOTE]
    >  Hvis det kreves en felles ressurs på tvers av de forskjellige komponentene i appen – for eksempel et skjema er nødvendig for et instrumentbord og en enhet – og du legger til denne ressursen bare én gang fra avhengighetstreet på instrumentbordet, reduseres avhengigshetsantallet bare på instrumentbordflisen, men ikke på enhetsflisen. Avhengigheten vil imidlertid løses for begge.  
    >   
    >  Velg **Få nyeste avhengigheter** ![Få nyeste avhengigheter-knappen i apputforming](media/app-designer-get-latest-dependencies.png "Få nyeste avhengigheter-knappen i apputforming") eller velg  **Valider** på nytt for å få det nyeste settet av avhengigheter. Du ser bare disse knappene når du har lagret appen.  
  
     Velg **Skjul avhengigheter** hvis du ikke vil legge til de foreslåtte nødvendige komponentene. Uløste advarsler vises på nytt når du åpner appen i apputforming og velger **Valider** eller **Få nyeste avhengigheter** ![Få nyeste avhengigheter-knappen i apputforming ](media/app-designer-get-latest-dependencies.png "Få nyeste avhengigheter-knappen i apputforming").  
  
    > [!NOTE]
    >  Hvis du skjuler avhengigheter nå og ønsker å eksportere denne appen senere, vises alle disse avhengighetene på nytt.  
  
## <a name="publish-an-app-using-the-app-designer"></a>Publiser en app ved hjelp av apputforming

Publiser en app for å gjøre den tilgjengelig for brukere.  
  
 Når du har lagt til komponenter, validert og lagret appen, velger du **Publiser** på kommandolinjen. Du kan også publisere appen fra app-flisen på [Mine apper](advanced-navigation.md#my-apps)-siden. I visningen **Apper som redigeres** nederst til høyre i appflisen du vil publisere, velger du **Flere alternativer**-knappen (**...** ), og velger deretter **Publiser**.  
  
 Appstatusen endres til Publisert. Du kan se dette øverst til høyre i apputforming. Appen flyttes fra visningen **Apper som redigeres** til **Publiserte apper**-visningen, og publiseringsdatoen vises på appflisen.  
  
> [!NOTE]
> - Hvis appen din har valideringsfeil, ser du feilen på varslingslinjen. Du vil ikke kunne publisere appen før du har løst feilen.  
> - Du kan ikke publisere en app før du lagrer den.  

## <a name="next-steps"></a>Neste trinn  
[Del en modelldrevet app med PowerApps](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app) <br/>
 [Å kjøre en modelldreven app på en mobil enhet](https://docs.microsoft.com/powerapps/user/run-app-client-model-driven)   
 
