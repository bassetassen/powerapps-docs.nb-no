---
title: Legge til et felt i et modelldrevet appskjema i PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: 29499887-6e7b-44a1-86a7-eaad33f3075d
caps.latest.revision: 30
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-a-field-to-a-model-driven-app-form"></a>Legge til et felt i et modelldrevet appskjema 

Hvis et PowerApps-skjema for en standardenhet ikke oppfyller forretningskravene til organisasjonen, kan du tilpasse skjemaet ved å endre eksisterende felt eller ved å legge til nye felt. Selv om det kan være enklere å redigere eksisterende felt i et skjema, er noen ganger det bedre å legge til et felt for å løse et bestemt forretningsscenario.

I dette emnet legger du til et felt i et skjema.   
  
1.  På [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-området velger du **Modelldrevet** (nederst til venstre i navigasjonsruten).  

    ![Modelldrevet utformingsmodus](../model-driven-apps/media/model-driven-switch.png)

    > [!IMPORTANT]
    > "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  

3.  I listen åpner du et skjema av typen **Hoved** for å redigere det.  
  
4.  Klikk inndelingen i skjemaet der du vil legge til et felt, og deretter går du til **Feltutforsker**-ruten og dobbeltklikker feltet du vil legge til i skjemaet.  
  
    > [!TIP]
    >  Når du legger til et felt for alternativsett i skjemaet, kan rullegardinlisten som inneholder alternativsettverdier bare vise to verdier. Brukere må rulle for å se flere verdier i listen. Hvis du vil vise flere enn to verdier uten at brukere må rulle, legger du til én eller flere **avstandskontroller** nedenfor feltet for alternativsett i skjemaet. Hver **avstandskontroll** gir et mellomrom for én ekstra alternativsettverdi. Hvis du for eksempel vil vise fire verdier i rullegardinlisten uten rulling, legger du til to **avstandskontroller** nedenfor alternativsettfeltet i skjemaet.  
  
5.  Slik forhåndsviser du hovedskjemaet og prøver ut hvordan hendelser fungerer:  
  
    1.  Klikk **Forhåndsvisning** i kategorien **Hjem**, og velg deretter **Opprett skjema**, **Oppdater skjema** eller **Skrivebeskyttet skjema**.  
  
    2.  Du lukker forhåndsvisningsskjemaet ved å klikke på **Lukk**.  
  
    3.  Hvis du vil publisere tilpassinger for skjemaet som du redigerer, klikker du **Publiser** når skjemaet er åpent.  
  
6.  Når du er ferdig med å redigere skjemaet, klikker du **Lagre og lukk**.  
  
7. Hvis du vil publisere tilpassinger for alle upubliserte komponentene samtidig, klikker du **Fil** og klikker deretter **Publiser alle tilpassinger**.  
  
> [!NOTE]
>  Publisering av tilpassinger kan forstyrre den ordinære driften av systemet.. Vi anbefaler at du publiserer når det i minst mulig grad vil forstyrre brukerne.  
  
## <a name="next-steps"></a>Neste trinn  
 
 [Opprette og utforme skjemaer](create-design-forms.md)
