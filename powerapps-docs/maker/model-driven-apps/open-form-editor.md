---
title: Åpne det modelldrevne redigeringsprogrammet for appskjemaer i PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 8478a07a-c697-4784-874b-36958eb4f95d
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: e0fe15df88fccbaee3c13a344416a434e1f92923
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691144"
---
# <a name="open-the-model-driven-app-form-editor"></a>Åpne det modelldrevne redigeringsprogrammet for appskjemaer 
Skjemaredigeringsprogrammet er der du utformer skjemaer ved å slippe komponenter, for eksempel inndelinger, faner, felt og kontroller, til lerretet for skjemaredigeringsprogrammet. I dette emnet finner du ut flere ulike måter å få tilgang til skjemaredigeringsprogrammet på.
 
Hvis du oppretter eventuelle nye løsningskomponenter mens du holder på å redigere skjemaet, for eksempel nettressurser, bruker navnene på komponentene tilpassingsprefikset for løsningsutgiveren for standardløsningen, og disse komponentene inkluderes bare i standardløsningen. Hvis du vil at eventuelle nye løsningskomponenter skal inkluderes i en bestemt ikke-administrert løsning, bør du åpne skjemaredigeringsprogrammet via den ikke-administrerte løsningen.  

## <a name="access-the-form-editor-from-the-powerapps-site"></a>Gå til skjemaredigeringsprogrammet fra PowerApps-nettstedet

1. Logg deg på [PowerApps](https://web.powerapps.com/). 

2. Velg **modelldrevne** > **Data** > **-enheter** > og velg deretter enheten du ønsker, for eksempel kontoenheten. 

3. Velg **Skjemaer**-fanen, og åpne deretter skjemaet du vil ha, for eksempel **Konto**-hovedskjemaet.

## <a name="access-the-form-editor-from-solution-explorer"></a>Gå til skjemaredigeringsprogrammet fra løsningsutforsker
  
1.  Åpne [løsningsutforsker](advanced-navigation.md#solution-explorer).
  
2.  Utvid **Enheter** under **Komponenter**, og deretter enheten du vil ha, og klikk på **Skjemaer**.  
  
3.  Klikk på skjemaet du vil redigere, i listen over skjemaer.  
  

## <a name="access-the-form-editor-through-the-command-bar-within-a-model-driven-app"></a>Gå til skjemaredigeringsprogrammet via kommandolinjen i en modelldrevet app 
  
1.  Åpne en post.  
  
2.  Hvis det finnes flere hovedskjemaer for enheten, må du kontrollere at skjemaet er det du vil redigere. Hvis ikke det er det, kan du bruke skjemavelgeren til å velge skjemaet du vil redigere.  
  
3.  Velg **Flere kommandoer**-knappen ![Flere kommandoer-knappen i Avtaleaktivitet](media/more-commands.gif "Flere kommandoer-knappen i Avtaleaktivitet").  
  
4.  Velg **skjemaredigeringsprogram**.  

## <a name="access-the-form-editor-from-within-dynamics-365-customer-engagement"></a>Gå til skjemaredigeringsprogrammet fra Dynamics 365 Customer Engagement
  
 Du kan gå til skjemaredigeringsprogrammet i Dynamics 365 Customer Engagement via kommandolinjen eller båndet, avhengig av enheten. Begge disse metodene vil åpne skjemaet i konteksten til standardløsningen. 

## <a name="access-the-form-editor-for-an-unmanaged-solution"></a>Gå til skjemaredigeringsprogrammet for en ikke-administrert løsning  
  
1.  Åpne [Løsninger](advanced-navigation.md#solutions).  
  
2.  Dobbeltklikk på de ikke-administrerte løsningene du vil arbeide med.  
  
3.  Finn enheten med skjemaet du vil redigere. Hvis ikke enheten er der, må du legge den til. Mer informasjon: [Legg til en enhet i en ikke-administrert løsning](#add-an-entity-to-an-unmanaged-solution) 
  
### <a name="add-an-entity-to-an-unmanaged-solution"></a>Legg til en enhet i en ikke-administrert løsning  
  
1.  Velg **Enheter**-noden, og klikk på **Legg til eksisterende** i verktøylinjen over listen.  
  
2.  Velg enheten du vil legge til, og klikk på **OK** i dialogboksen **Velg løsningskomponenter** med **komponenttype**-velgeren angitt som **Enhet**.  
  
3.  Hvis dialogboksen **Manglende nødvendige komponenter** vises, kan du klikke på **Nei, ikke inkluder nødvendige komponenter** hvis du ikke har tenkt å eksportere den ikke-administrerte løsningen til et annet miljø. Hvis du velger ikke å inkludere manglende nødvendige komponenter på dette tidspunktet, kan du legge dem til senere. Du blir varslet på nytt hvis du eksporterer denne løsningen i fremtiden.  
  
5.  Utvid enheten med skjemaet du vil redigere, i løsningsutforsker, og velg **Skjemaer**.  
  
6.  Dobbeltklikk på skjemaet du vil redigere, i listen over skjemaer.  

## <a name="next-steps"></a>Neste trinn

[Opprette og utforme skjemaer](create-design-forms.md)
