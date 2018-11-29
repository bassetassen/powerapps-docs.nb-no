---
title: Validere og publisere en modelldrevet app ved hjelp av apputforming | MicrosoftDocs
description: Finn ut hvordan du validerer og publiserer en modelldrevet app
keywords: ''
ms.date: 06/08/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 5a9ec120-9ddc-4d92-b48c-0fee8c57d3c3
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 10
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="validate-and-publish-a-model-driven-app-using-the-app-designer"></a>Validere og publisere en modelldrevet app ved hjelp av apputforming

Valider en app for å se etter anleggsmiddelavhengigheter som kreves for at appen skal fungere, men som ennå ikke lagt til i appen. Etter en vellykket validering publiserer du appen. 
  
Du har for eksempel lagt til et instrumentbord for Customer Service-ytelse i appen, som bruker diagrammer som Saksblanding (etter prioritet) eller Saksavslutningstrend etter dag som du ikke har lagt til. Når du validerer denne appen, får du en liste over alle manglende, nødvendige ressurser.  
  
Når du validerer appen, viser apputformingslerretet detaljer om aktivaene som mangler.  
  
1.  Velg **Valider** i utformingen.  
  
     Et statusfelt vises, som angir om appen har feil eller advarsler. Varsellinjen viser advarsler for eksempel når en enhet ikke har noen skjemaer eller visninger, eller nå appen ikke inneholder noen komponenter. En feil kan vises hvis et områdekart ikke er konfigurert for appen. Du kan publisere en app uten å løse advarsler, men du må rette feilene før du kan publisere den.  
  
     ![Systemfelt som viser advarsler i appen](media/app-designer-warning-notification.png "Systemfelt som viser advarsler i appen")  
  
     Apputformingen viser også et varselsymbol med antall avhengigheter i hver artefakt eller aktivaflis som mangler en nødvendig ressurs.  
  
     ![Advarsel om manglende komponent på apputformingsflisen](media/warning--button-on-app-designer-tile.png "Advarsel om manglende komponent på apputformingsflisen")  
  
2.  Hvis du vil legge til de nødvendige ressursene, velger kategorien **Nødvendig** til høyre på lerretet. Kategorien **Nødvendig** vises når det er minst én nødvendig ressurs som mangler i appen.  
  
     Kategorien viser en liste over nødvendige komponenter.  
  
     ![Nødvendig-fane som viser en liste over manglende komponenter i appen](media/app-designer-required-components-tab.png "Nødvendig-fane som viser en liste over manglende komponenter i appen")  
  
3.  Velg ressursene du vil legge til, og velg deretter **Legg til avhengigheter**. Når du legger til en nødvendig ressurs, reduseres antallet på flisen der du la til ressursen.  
  
    > [!NOTE]
    >  Hvis det kreves en felles nødvendig ressurs på tvers av ulike appkomponenter, for eksempel et skjema som er nødvendig for et instrumentbord og en enhet, og du legger til aktuelle anleggsmidlet bare én gang fra avhengighetstreet for instrumentbordet, reduseres antallet avhengigheter på bare instrumentbordflisen, men ikke på enhetsflisen. Avhengigheten vil imidlertid bli løst for begge.  
    >   
    >  Velg knappen **Last ned de nyeste avhengighetene** ![Knappen Last ned de nyeste avhengighetene i apputformingen](media/app-designer-get-latest-dependencies.png "Knappen Last ned de nyeste avhengighetene i apputformingen"), eller velg **Valider** på nytt for å hente det siste settet med avhengigheter. Disse knappene vises bare når du har lagret appen.  
  
     Velg **Skjul avhengigheter** hvis du ikke vil legge til nødvendige komponenter som er foreslått. Uløste advarsler vises på nytt når du åpner appen i apputformingen og velger **Valider** eller klikker knappen **Last ned de nyeste avhengighetene** ![Knappen Last ned de nyeste avhengighetene i apputformingen](media/app-designer-get-latest-dependencies.png "Knappen Last ned de nyeste avhengighetene i apputformingen").  
  
    > [!NOTE]
    >  Hvis du skjuler avhengigheter nå og senere ønsker å eksportere denne appen, vil du se alle disse avhengighetene på nytt.  
  
## <a name="publish-an-app-using-the-app-designer"></a>Publisere en app med apputformingen

Publiser en app for å gjøre den tilgjengelige for brukerne.  
  
 Når du har lagt til komponenter, validert og lagret appen, velger du **Publiser** på kommandolinjen. Du kan også publisere appen fra appflisen på [Mine apper](advanced-navigation.md#apps)-siden. I visningen **Apper som redigeres** går du til nedre høyre hjørne av appflisen du vil publisere, velger **Flere alternativer**-knappen (**...**), og velger deretter **Publiser**.  
  
 Statusen for appen endres til Publisert. Du kan se dette i øvre høyre hjørne av apputformingen. Appen flyttes fra visningen **Apper som redigeres** til visningen **Publiserte apper**, og publiseringsdatoen vises i apptittelen.  
  
> [!NOTE]
> - Hvis appen har en valideringsfeil, vil du se feilen på en varslingslinje. Du kan ikke publisere appen før du løser problemet.  
> - Du kan ikke publisere en app før du lagrer den.  

## <a name="next-steps"></a>Neste trinn  
[Dele en modelldrevet app med PowerApps](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app) <br/>
 [Kjør en modelldrevet app på en mobilenhet](https://docs.microsoft.com/powerapps/user/run-app-client-model-driven)   
 
