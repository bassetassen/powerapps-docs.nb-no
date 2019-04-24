---
title: Oversikt over tilkoblingen for skylagring | Microsoft Docs
description: Se hvordan du kobler til en konto for lagring i skyen og viser Excel-data i appen din
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 07/12/2016
ms.author: lanced
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 10a6178c63495b929eb6e5885ded9394b31a11ef
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61546075"
---
# <a name="connect-to-cloud-storage-from-powerapps"></a>Å koble til lagring i skyen fra PowerApps
PowerApps tilbyr flere tilkoblinger for lagring i skyen. Ved hjelp av noen av disse tilkoblingene kan du lagre en Excel-fil og bruke informasjonen i den i hele appen. Disse tilkoblingene omfatter:  

| **Azure Blob** | **Box** | **Dropbox** | **Google Drive** | **OneDrive** | **OneDrive<br>for Business** |
| --- | --- | --- | --- | --- | --- |
| ![Ikon](./media/cloud-storage-blob-connections/blobicon.png) |![API-ikon][boxicon] |![API-ikon][dropboxicon] |![API-ikon][googledriveicon] |![API-ikon][onedriveicon] |![API-ikon][onedriveforbusinessicon] |

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

* En Excel-fil med dataene [formatert som en tabell](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664):
  
  1. Åpne Excel-filen, og velg deretter en celle i dataene du vil bruke.
  2. Velg **Tabell** på **Sett inn**-fanen.
  3. Merk av for **Tabellen har overskrifter** i dialogboksen **Lagre som tabell**, og velg deretter **OK**.
  4. Lagre endringene.

## <a name="connect-to-the-cloud-storage-connection"></a>Å koble til tilkoblingen for skylagring
1. Utvid **Behandle**på [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og velg **Tilkoblinger**:  
   
    ![Å velge tilkoblinger](./media/cloud-storage-blob-connections/connections.png)
2. Velg **Ny tilkobling**, og velg tilkoblingen din for skylagring. Velg for eksempel **OneDrive**.
3. Du blir bedt om brukernavn og passord i kontoen for skylagring. Angi dette, og velg deretter **Logg på**:  
    ![Å angi brukernavn og passord](./media/cloud-storage-blob-connections/signin.png)
   
    Når du er logget på, er denne tilkoblingen klar til å brukes i appene dine.
4. Klikk eller trykk på **Datakilder** i appen, på **Vis**-fanen på båndet. Klikk eller trykk på **Legg til en datakilde** i den høyre ruten, klikk eller trykk så på skylagringstilkoblingen, og velg deretter Excel-tabellen.
5. Velg **Koble til**.
   
    Nå er tabellen oppført som en datakilde:
   
    ![Å velge Excel-tabellen](./media/cloud-storage-blob-connections/selecttable.png)
   
    > [!NOTE]
   > Husk at Excel-dataene må være formatert som en tabell.

## <a name="using-the-excel-data-in-your-app"></a>Å bruke Excel-data i appen
1. Velg **Galleri** på **Sett inn**-fanen, og velg deretter en **Med tekst**-gallerikontroll.
2. Angi **[Elementer](../controls/properties-core.md)**-egenskapen for galleriet i Excel-tabellen. Hvis Excel-tabellen eksempelvis heter **Tabell1**, angir du den som Tabell1:  
   
    ![Elementegenskaper](./media/cloud-storage-blob-connections/itemsproperty.png)  
   
    Galleriet er automatisk oppdatert med informasjon fra Excel-tabellen.
3. Velg andre eller tredje **etikett**-kontroll i galleriet. **Tekst**-egenskapen vises som standard med andre og tredje etiketter automatisk satt til `ThisItem.something`. Du kan angi disse etikettene til hvilke som helst kolonner i tabellen.
   
    I eksemplet nedenfor er den andre etiketten satt til `ThisItem.Name`, og den tredje etiketten er satt til `ThisItem.Notes`:  
   
    ![Andre etikett](./media/cloud-storage-blob-connections/items-secondtextbox.png)  
   
    ![Tredje etikett](./media/cloud-storage-blob-connections/items-thirdtextbox.png)  
   
    Eksempelutdata:  
    ![Andre og tredje etiketter](./media/cloud-storage-blob-connections/secondthirdtextboxes.png)
   
> [!NOTE]
> Den første boksen er en bildekontroll. Hvis du ikke har et bilde i Excel-tabellen, kan du slette bildekontrollen og legge til en etikett i stedet. [Å legge til og konfigurere kontroller](../add-configure-controls.md) er en god ressurs.

[Å forstå tabeller og poster](../working-with-tables.md) gir mer informasjon og noen eksempler.  

## <a name="sharing-your-app"></a>Å dele appen
Du kan dele [appen](../share-app.md), [ressursene](../share-app-resources.md) som for eksempel koblinger og [dataene](../share-app-data.md) med andre i organisasjonen.

Hvis du deler en mappe i Dropbox, må den delte mappen være knyttet til brukerens Dropbox-konto.

Det finnes [visse begrensninger](#sharing-excel-tables) med koblinger som involverer Excel-filer.

## <a name="known-limitations"></a>Kjente begrensninger
Hvis **Datatypen støttes ikke** eller **Ikke formatert som en tabell** vises når du prøver å bruke en Excel-tilkobling i appen [, formaterer du dataene som en tabell](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664).

Hvis Excel-dataene inneholder en beregnet kolonne, kan du ikke bruke den til å bygge en app, og du kan ikke legge til dataene til en eksisterende app.

### <a name="sharing-excel-tables"></a>Å dele Excel-tabeller
Slik deler du dataene i en Excel-fil:

* I OneDrive for Business kan du dele selve filen.
* I OneDrive deler du mappen som inneholder filen, og angir filbaner (ikke nettadresser) for alle medier.
* I Dropbox eller Google Drive kan du dele enten filen eller mappen.

## <a name="helpful-links"></a>Nyttige koblinger
Se alle [tilgjengelige tilkoblinger](../connections-list.md).  
Finn ut hvordan du [legger til tilkoblinger](../add-manage-connections.md) og [legger til en datakilde](../add-data-connection.md) til appene dine.  
[Forstå tabeller og poster](../working-with-tables.md) med datakilder i tabellform.  
Noen ekstra galleriressurser inkluderer [Vis en liste over elementer](../add-gallery.md) og [Vis bilder og tekst i et galleri](../show-images-text-gallery-sort-filter.md).

<!--Icon references-->
[boxicon]: ./media/cloud-storage-blob-connections/boxicon.png
[dropboxicon]: ./media/cloud-storage-blob-connections/dropboxicon.png
[googledriveicon]: ./media/cloud-storage-blob-connections/googledriveicon.png
[onedriveicon]: ./media/cloud-storage-blob-connections/onedriveicon.png
[onedriveforbusinessicon]: ./media/cloud-storage-blob-connections/onedriveforbusinessicon.png
