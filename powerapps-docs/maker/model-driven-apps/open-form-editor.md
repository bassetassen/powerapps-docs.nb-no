---
title: Åpne skjemaredigeringsprogrammet for modelldrevne apper i PowerApps | MicrosoftDocs
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="open-the-model-driven-app-form-editor"></a>Åpne skjemaredigeringsprogrammet for modelldrevne apper 
Skjemaredigeringsprogrammet er der du utformer skjemaer ved å legge til komponenter, for eksempel deler, kategorier, felt og kontroller, på lerettet i skjemaredigeringsprogrammet. I dette emnet kan du lære om flere ulike måter for å få tilgang til skjemaredigeringsprogrammet.
 
Hvis du oppretter nye løsningskomponenter i når du redigerer skjemaet, for eksempel webressurser, vil navnene på komponentene bruke tilpassingsprefikset for løsningsutgiver for standardløsningen, og disse komponentene inkluderes bare i standardløsningen. Hvis du vil at alle nye løsningskomponenter skal inkluderes i en bestemt uadministrert løsning, bør du åpne skjemaredigeringsprogrammet gjennom den uadministrerte løsningen.  

## <a name="access-the-form-editor-from-the-powerapps-site"></a>Få tilgang til skjemaredigeringsprogrammet fra PowerApps-nettstedet

1. Logg på [PowerApps](https://web.powerapps.com/). 

2. Velg **Modelldrevet** > **Data** > **Enheter** > og velg deretter enheten du vil bruke, for eksempel forretningsforbindelsesenheten. 

3. Velg kategorien **Skjemaer**, og åpne deretter skjemaet som du ønsker, for eksempel hovedskjemaet **Forretningsforbindelse**.

## <a name="access-the-form-editor-from-solution-explorer"></a>Åpne skjemaredigeringsprogrammet fra løsningsutforskeren
  
1.  Åpne [løsningsutforskeren](advanced-navigation.md#solution-explorer).
  
2.  Vis **Enheter** under **Komponenter**, vis deretter ønsket enhet, og klikk **Skjemaer**.  
  
3.  Klikk i listen over skjemaer for å åpne skjemaet du vil redigere.  
  

## <a name="access-the-form-editor-through-the-command-bar-within-a-model-driven-app"></a>Åpne skjemaredigeringsprogrammet via kommandolinjen i en modelldrevet app 
  
1.  Åpne en oppføring  
  
2.  Hvis det finnes flere hovedskjemaer for enheten, må du kontrollere at skjemaet er den du vil redigere. Hvis ikke, bruker du skjemavelgeren til å velge skjemaet du vil redigere.  
  
3.  Velg **Flere kommandoer**-knappen ![Flere kommandoer-knappen i Avtaleaktivitet](media/more-commands.gif "Flere kommandoer-knappen i Avtaleaktivitet").  
  
4.  Velg **Skjemaredigeringsprogram**.  

## <a name="access-the-form-editor-from-within-dynamics-365-customer-engagement"></a>Åpne skjemaredigeringsprogrammet fra Dynamics 365 Customer Engagement
  
 Du får tilgang til skjemaredigeringsprogrammet i Dynamics 365 Customer Engagement via kommandolinjen eller båndet, avhengig av enheten. Begge metodene åpner skjemaet i konteksten for standardløsningen. 

## <a name="access-the-form-editor-for-an-unmanaged-solution"></a>Åpne skjemaredigeringsprogrammet for en uadministrert løsning  
  
1.  Åpne [Løsninger](advanced-navigation.md#solutions).  
  
2.  Dobbeltklikk den uadministrerte løsningen du vil arbeide med.  
  
3.  Finn enheten med skjemaet du vil redigere. Hvis enheten ikke finnes, må den legges til. Mer informasjon: [Legge til en enhet i en uadministrert løsning](#add-an-entity-to-an-unmanaged-solution) 
  
### <a name="add-an-entity-to-an-unmanaged-solution"></a>Legge til en enhet i en uadministrert løsning  
  
1.  Klikk **Enheter**-noden, og klikk **Legg til eksisterende** på verktøylinjen over listen.  
  
2.  Klikk enheten du vil legge til, i dialogboksen **Klikk løsningskomponenter** med **Komponenttype**-velgeren satt til **Enhet**, og klikk **OK**.  
  
3.  Hvis dialogboksen **Mangler obligatoriske komponenter** vises, kan du klikke **Nei, ikke ta med nødvendige komponenter** hvis du ikke har til hensikt å eksportere denne uadministrerte løsningen til et annet miljø. Hvis du velger ikke å inkludere manglende obligatoriske komponenter på dette tidspunktet, kan du legge dem til senere. Du blir varslet på nytt hvis du eksporterer løsningen senere.  
  
5.  I løsningsutforskeren viser du enheten som inneholder skjemaet du vil redigere, og velger **Skjemaer**.  
  
6.  Dobbeltklikk i listen over skjemaer for å åpne skjemaet du vil redigere.  

## <a name="next-steps"></a>Neste trinn

[Opprette og utforme skjemaer](create-design-forms.md)
