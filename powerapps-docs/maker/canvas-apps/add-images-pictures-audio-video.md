---
title: Bygge multimediafiler inn i en app og laste opp | Microsoft Docs
description: Vise multimediafiler i en app og laste dem opp til en datakilde
services: ''
suite: powerapps
documentationcenter: ''
author: karthik-1
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/12/2017
ms.author: sharik
ms.openlocfilehash: 75ec8131a4e9a4be796f06669d8d25ff559eaf69
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996477"
---
# <a name="using-multimedia-files-in-powerapps"></a>Bruke multimediafiler i PowerApps
Dette emnet forklarer hvordan du bygger inn multimediafiler i appen, laster opp pennetegninger til en datakilde og viser bilder fra en datakilde i appen. Datakilden som brukes i dette emnet er en Excel-fil i OneDrive for Business.

## <a name="prerequisites"></a>Forutsetninger
[Registrer deg](../signup-for-powerapps.md) for PowerApps, og [installer](http://aka.ms/powerappsinstall) den. Når du åpner PowerApps, logger du på med samme legitimasjon som du brukte til å registrere deg.

## <a name="add-media-from-a-file-or-the-cloud"></a>Legge til media fra en fil eller fra skyen
Du kan velge hvilken type mediafil du vil legge til (for eksempel bilder, video eller lyd).

1. Velg **Media** i fanen **Innhold**.

2. Under **Media** velger du **Bilder**, **Videoer** eller **Lyd**, og deretter velger du **Bla gjennom**:

    ![Bla gjennom media][1]

3. Velg filen du vil legge til, og velg deretter **Åpne**.

    Mappen **Bilder** på datamaskinen åpnes, og du kan velge et bilde fra denne eller navigere til en annen mappe.

4. Når du er ferdig å legge til filer, trykker du på Esc for å gå tilbake til standardarbeidsområdet.

5. Under fanen **Sett inn** velger du **Media**, og deretter velger du **Bilde**, **Video** eller **Lyd**:

    ![Velg mediatype][8]

6. Hvis du har lagt til en bildekontroll, angir du kontrollens **[Bilde](controls/properties-visual.md)**-egenskap til den filen du la til:  

    ![Angi bildeegenskap](./media/add-images-pictures-audio-video/imageproperty.png)

    > [!NOTE]
> Angi kun filnavnet, uten filtypen, i enkle anførselstegn.

7. Hvis du har lagt til en video- eller lydkontroll, angir du **Media**-egenskap for filen du la til:  

    ![Angi mediaegenskap](./media/add-images-pictures-audio-video/mediaproperty.png)

    > [!NOTE]
> Spill av en YouTube-video ved å angi **Media**-egenskapen til en videokontroll til den relevante URL-adressen, omsluttet av doble anførselstegn.

## <a name="add-media-from-azure-media-services"></a>Legge til media fra Azure Media Services
1. Logg på Azure Media Services-kontoen, last opp og publiser videoressursen via **AMS > Innstillinger > Ressurser**.

2. Kopier URL-adressen til videoen når den er publisert.

3. Legg til **Video**-kontrollen via **Sett inn > Media** i PowerApps.

4. Angi **Media**-egenskapen til den URL-adressen du kopierte.

    Som dette bildet viser, kan du velge hvilken som helst URL-adresse for direkteavspilling som støttes av Azure Media Services:

    ![Angi mediaegenskap](./media/add-images-pictures-audio-video/ams-with-powerapps.png)

## <a name="add-images-from-the-cloud-to-your-app"></a>Legge til bilder fra skyen til appen
I dette scenarioet lagrer du bilder i en konto for lagring i skyen, OneDrive for Business. Du bruker en Excel-tabell til å oppbevare banen til bildene, og du viser bildene i et gallerikontroll i appen.

Dette scenarioet bruker [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip), som inneholder noen .jpeg files.

> [!NOTE]
> Banen til disse bildene i Excel-filen må bruke skråstreker. Når PowerApps lagrer bildebaner i en Excel-tabell, bruker banen omvendte skråstreker. Hvis du bruker bildebaner fra en slik tabell, må du endre banene i Excel-tabellene slik at de bruker skråstreker i stedet for omvendte skråstreker. Ellers vil ikke bildene vises.  

1. Last ned [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) og pakk ut **Assets**-mappen på kontoen for lagring i skyen.

2. Endre navnet på **Assets**-mappen til **Assets_images**.

3. Opprett en tabell med én kolonne i et Excel-ark, og fyll inn følgende data:

    ![Tabell over jakker](./media/add-images-pictures-audio-video/jackets.png)

4. Gi tabellen navnet **Jakker**, og gi Excel-filen navnet **Assets.xlsx**.

5. Legg **Jakker**-tabellen til som en datakilde i appen.  

6. Legg til en **Kun bilde**-kontroll (fanen **Sett inn** > **Galleri**), og angi kontrollens **Elementer**-egenskap til `Jackets`:  

    ![Elementegenskaper](./media/add-images-pictures-audio-video/items-jackets.png)

    Galleriet oppdateres automatisk med bildene:  

    ![Jakkebilder](./media/add-images-pictures-audio-video/images.png)

    Når du angir **Elementer**-egenskapen, legges det automatisk til en kolonne med navnet **PowerAppsId** til i Excel-tabellen.

    I Excel-tabellen kan bildebanen også være URL-adressen til et bilde. Et eksempel er eksempelfilen [Flooring Estimates](http://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx). Du kan laste den ned til kontoen din for lagring i skyen, legge `FlooringEstimates`-tabellen til som en datakilde i appen og deretter angi gallerikontrollen til `FlooringEstimates`. Galleriet oppdateres automatisk med bildene.

## <a name="upload-pen-drawings-to-the-cloud"></a>Laste opp pennetegninger til skyen
I dette scenarioet lærer du hvordan du laster opp pennetegninger til datakilden, OneDrive for Business, og undersøke hvordan tegningene lagres der.

1. Åpne et Excel-ark, og legg **Bilde [bilde]** til i celle A1.

2. Opprett en tabell ved å gjøre følgende:    

   1. Velg celle A1.

   2. Velg **Tabell** på båndet **Sett inn**.

   3. Velg **Tabellen min har overskrifter**, og velg deretter **OK**.

       ![Opprette en tabell](./media/add-images-pictures-audio-video/create-table.png)

       Nå er Excel-filen i et tabellformat. Du finner mer informasjon om formatering av tabeller i Excel under [Formatere dataene som en tabell](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370).

   4. Gi tabellen navnet **Drawings**:

       ![Endre navnet på tabellen til Drawings](./media/add-images-pictures-audio-video/name-media-table.png)

3. Lagre Excel-filen på OneDrive for Business som **SavePen.xlsx**.

4. Opprett en [tom app](get-started-create-from-blank.md) i PowerApps.

5. I appen legger du til OneDrive for Business-kontoen som en [datakilde](add-data-connection.md):

   1. Klikk eller trykk på fanen **Vis**, og klikk eller trykk deretter på **Datakilder**.

       ![](./media/add-images-pictures-audio-video/choose-data-sources.png)

   2. Klikk eller trykk på **Legg til datakilde**, og klikk eller trykk på **OneDrive for Business**.

       ![](./media/add-images-pictures-audio-video/select-source.png)

   3. Klikk eller trykk på **SavePen.xlsx**.

   4. Velg tabellen **Drawings**, og klikk eller trykk deretter på **Koble til**.

       ![Koble til](./media/add-images-pictures-audio-video/savepen.png)  

       Nå er tabellen Tegninger oppført som en datakilde.

6. Velg **Tekst** på **Sett inn**-fanen, og velg **Penneinndata**.

7. Endre navnet på den nye kontrollen til **MyPen**:  

    ![Gi nytt navn](./media/add-images-pictures-audio-video/rename-mypen.png)

8. Legg til en **Knapp**-kontroll under fanen **Sett inn**, og angi **OnSelect**-egenskapen til denne formelen:

    **Patch(Drawings, Defaults(Drawings), {Image:MyPen.Image})**

9. Legg til en **Bildegalleri**-kontroll (fanen **Sett inn** > **Galleri**), og angi kontrollens **Elementer**-egenskap til `Drawings`. Gallerikontrollens **Bildegalleri**-egenskap angis automatisk til `ThisItem.Image`.

    Sett opp kontrollene slik at skjermbildet ser ut som det følgende:  

    ![Eksempel på skjermbilde](./media/add-images-pictures-audio-video/screen.png)

10. Trykk på F5, eller velg Forhåndsvisning ( ![Forhåndsvisning-knapp](./media/add-images-pictures-audio-video/preview.png) ).

11. Tegn noe i MyPen, og velg deretter knappen.

    Det første bildet i gallerikontrollen viser det du tegnet.

12. Legg til noe mer på tegningen, og velg knappen.

    Det andre bildet i gallerikontrollen viser det du tegnet.

13. Lukk forhåndsvisningsbildet ved å trykke på Esc.

    En mappe med navnet **SavePen_images** har blitt automatisk opprettet i kontoen din for lagring i skyen. Denne mappen inneholder de lagrede bildene, sammen med ID-ene for filnavnene til bildene. Det kan hende du må oppdatere nettleservinduet, for eksempel ved å trykke på F5, for å vise mappen.

    I **SavePen.xlsx** angir **Image**-kolonnen banen til de nye bildene.

### <a name="known-limitations"></a>Kjente begrensninger
Hvis du vil ha informasjon om hvordan du deler Excel-data innad i organisasjonen, kan du [se gjennom disse begrensningene](connections/cloud-storage-blob-connections.md#known-limitations).

## <a name="for-more-information"></a>For mer informasjon
Sørg for at du tester appen din på ulike plattformer, inkludert i [et nettleservindu](https://home.dynamics.com/) og på en telefon.

Hvis du vil ha mer informasjon om mer avanserte scenarioer som involverer opplasting av multimedia direkte til en annen datakilde, kan du se [profesjonelle tips for bildeopptak](https://powerapps.microsoft.com/blog/image-capture-pro-tips/) og [tilpassede koblinger for bildeopplasting](https://powerapps.microsoft.com/blog/custom-api-for-image-upload/).

Du kan også laste opp filer til en datakilde ved å bruke [Patch](functions/function-patch.md)-funksjonen.

[1]: ./media/add-images-pictures-audio-video/add-image-video-audio-file.png
[3]: ./media/add-images-pictures-audio-video/add-intro-sound.png
[4]: ./media/add-images-pictures-audio-video/add-picture.png
[5]: ./media/add-images-pictures-audio-video/camera-gallery.png
[6]: ./media/add-images-pictures-audio-video/audio-gallery.png
[7]: ./media/add-images-pictures-audio-video/pen-gallery.png
[8]: ./media/add-images-pictures-audio-video/mediaoptions.png
[9]: ./media/add-images-pictures-audio-video/imageproperty.png
[10]: ./media/add-images-pictures-audio-video/mediaproperty.png
[11]: ./media/add-images-pictures-audio-video/renamecamera.png
