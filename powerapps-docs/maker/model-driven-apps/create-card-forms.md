---
title: Opprette et kortskjema med PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter og bruker kortskjemaer i PowerApps
keywords: ''
ms.date: 03/05/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-card-form"></a>Opprett et kortskjema
Kortskjemaer brukes i visninger for Enhetlig grensesnitt-apper. Kortskjemaer er utformet for å vise informasjon i et komprimert format som passer for mobile enheter. For eksempel definerer standard kortskjema for visningen Mine aktive forretningsforbindelser informasjonen som vises for hver forretningsforbindelsesoppføring. 

> [!div class="mx-imgBorder"] 
> ![](media/account-cardform-for-myactiveaccounts-view.png "Kortskjema for forretningsforbindelse for visningen Mine aktive forretningsforbindelser")

Selv om kortskjemaer kan opprettes og redigeres på samme måte som andre skjematyper, legges kortskjemaer til i apper på en annen måte. I stedet for å legge til et skjema som en appkomponent legges egendefinerte kortskjemaer til i visninger ved hjelp av kontrollen **Skrivebeskyttet rutenett**. 

## <a name="create-a-card-form"></a>Opprett et kortskjema
1. For opprette et kortskjema logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). 
2. Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.
3. På verktøylinjen velger du **Legg til skjema**, og deretter veler du **Kortskjema**. Du kan også åpne en eksisterende **Skjematype** som er et **Kort**-skjema for å redigere.
4. Legg til ønskede felt. Vi anbefaler at du begrenser antall felt, slik at skjemaet vises riktig på små skjermer. 
5. Velg **Lagre**, og velg deretter **Publiser**. 

## <a name="add-a-card-form-to-a-view"></a>Legge til et kortskjema i en visning 
1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2. Utvid **Data**, velg enheten du vil bruke, og velg deretter **Visninger**-kategorien.
3. Velg visningen du vil bruke, og velg deretter **Bytt til vanlig**.
4. Velg **Egendefinerte kontroller** fra **Vanlige oppgaver**-ruten.
5. Velg **Legg til kontroll**, og fra listen over kontroller velger du **Skrivebeskyttet rutenett**, og deretter velger du **Legg til**.

   > [!NOTE]
   > Det finnes to skrivebeskyttede rutenettkontroller. Standard skrivebeskyttet rutenettkontroll som heter **Skrivebeskyttet rutenett (standard)** støtter ikke egendefinerte kortskjemaer. 

6. Fra **Skrivebeskyttet rutenett**-egenskapssiden konfigurerer du følgende egenskaper, og deretter velger du **OK**. 
   - **Kortskjema**. Velg blyantikonet ![Rediger kontrollegenskaper](media/ccf-pencil-icon.png), og velg deretter kortskjemaet du vil vise i visningen. Som standard er hovedenheten som er tilknyttet visningen, allerede valgt, men du kan endre den. 
   - **Virkemåte for dynamisk tilpassing**. Hvis du vil endre om kortskjemaet skal vises med endret størrelse, velger du blyantikonet ![Rediger kontrollegenskaper](media/ccf-pencil-icon.png). Mer informasjon: [Tillat at rutenettet tilpasses dynamisk til liste](specify-properties-for-unified-interface-apps.md#allow-grid-to-reflow-into-list)  
   - Velg klienttypene, **Web**, **Telefon** eller **Nettbrett**, der du vil at kontrollen **Skrivebeskyttet** skal vises.

     ![Skrivebeskyttet rutenett for kortskjema](media/read-only-grid-for-cardform.png)

7. Velg **OK** for å lukke egenskapssiden **Egendefinerte kontroller**. 
8. Velg **Lagre og lukk** på verktøylinjen for vanlig visningsutforming. 

## <a name="see-also"></a>Se også
[Bruke egendefinerte kontroller for datavisualiseringer i modelldrevne apper](use-custom-controls-data-visualizations.md)



