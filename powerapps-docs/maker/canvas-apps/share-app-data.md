---
title: Å dele Excel-filer som brukes av en app | Microsoft Docs
description: Dele Excel-filer i Dropbox, OneDrive og Google Drive. Brukere kan redigere og vise filer og mapper.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/16/2016
ms.author: jamesol
ms.openlocfilehash: 78423a1f1594e69a40cc4b81123217f960b61879
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014999"
---
# <a name="share-excel-data-used-by-your-app"></a>Å dele Excel-data som brukes av appen
Du kan dele Excel-data med appbrukerne i en [skykonto](connections/cloud-storage-blob-connections.md), for eksempel OneDrive.

Du kan for eksempel opprette en app som viser navn og telefonnumre til gruppen for kundestøtte i firmaet. Informasjonen er lagret i et Excel-regneark, som du plasserer i en mappe i Dropbox. Du kan deretter dele mappen med appbrukere, slik at de kan se navnene og telefonnumrene.

Du må dele dataene, slik at brukere kan kjøre og endre appen. Brukere som ikke har fått delingstillatelsene, ser ikke dataene i Excel-filen.

Dette emnet viser hvordan du deler data i et Excel-regneark ved hjelp av Dropbox, OneDrive og Google Drive. Hvis du vil opprette en app som viser data fra en Excel-fil, kan du se [Opprette en app fra et sett med data](get-started-create-from-data.md).

## <a name="share-data-in-dropbox"></a>Å dele data i Dropbox
1. Logg på Dropbox med samme konto som du brukte til å opprette en tilkobling fra PowerApps til Dropbox.
2. Velg mappen som inneholder Excel-filen, og velg deretter **Del**:  
   
    ![Del-kommandoen](./media/share-app-data/dropbox-share.png)
3. Skriv inn e-postadressene som appbrukerne logger på Dropbox med, i dialogboksen.  
   
    ![Å dele på Dropbox](./media/share-app-data/dropbox-perms.png)
4. Hvis appbrukerne kommer til å legge til, endre eller slette data i appen, velger du **Kan redigere**. Ellers velger du **Kan vise**.
5. Velg **Del**.

Hvis du vil ha mer informasjon, kan du se [Dele mapper i Dropbox](https://www.dropbox.com/en/help/19).

## <a name="share-data-in-onedrive"></a>Å dele data i OneDrive
1. Logg på OneDrive med samme konto som du brukte til å opprette en tilkobling fra PowerApps til OneDrive.
2. Velg mappen som inneholder filen, og velg deretter **Del**:  
   
    ![Del-kommandoen](./media/share-app-data/onedrive-share.png)
   
    > [!NOTE]
   > Del selve filen og ikke mappen som inneholder filen i OneDrive for Business.
3. I dialogboksen velger du **E-post**.
   
    ![Del via e-post](./media/share-app-data/onedrive-email.png)
4. Angi e-postadressene som appbrukerne logger seg på OneDrive med, og velg deretter **Del**.  
   
    ![Å angi en bruker](./media/share-app-data/onedrive-perms.png)

Hvis du vil ha mer informasjon, kan du se [Dele OneDrive-filer og -mapper](https://support.office.com/article/Share-OneDrive-files-and-folders-and-change-permissions-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

## <a name="share-data-in-google-drive"></a>Å dele data i Google Drive
1. Logg på Google Drive med samme konto som du brukte til å opprette en tilkobling fra PowerApps til Google Drive.
2. Høyreklikk på mappen som inneholder Excel-filen, og velg deretter **Del**.  
   
    ![Del-kommandoen](./media/share-app-data/googledrive-share.png)
3. Skriv inn e-postadressene som appbrukerne logger på Google Drive med, i dialogboksen:  
   
    ![Å angi en bruker](./media/share-app-data/googledrive-perms.png)
4. Hvis appbrukerne kommer til å legge til, endre eller slette data i appen, velger du **Kan redigere** i listen over tillatelser. Ellers velger du **Kan vise**.
5. Velg **Ferdig**.

Hvis du vil ha mer informasjon, kan du se [Dele Google Drive-filer og -mapper](https://support.google.com/drive/answer/2494822).

### <a name="known-limitations"></a>Kjente begrensninger
Hvis du vil ha informasjon om hvordan du deler Excel-data innad i organisasjonen, kan du [se gjennom disse begrensningene](connections/cloud-storage-blob-connections.md#known-limitations).

