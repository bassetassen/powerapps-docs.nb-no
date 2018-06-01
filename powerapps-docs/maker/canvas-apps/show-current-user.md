---
title: Å vise detaljer om gjeldende bruker | Microsoft Docs
description: Sett inn brukerfunksjonen for å vise navnet og e-postadressen til brukeren som er logget på i PowerApps
services: ''
suite: powerapps
documentationcenter: ''
author: lonu
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: lonu
ms.openlocfilehash: b337188360ba592d504a7364fdbeb3a2973b8ee0
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997402"
---
# <a name="show-information-about-a-powerapps-user"></a>Vis informasjon om en PowerApps-bruker
Brukerfunksjonen kan vise det fullstendige navnet, e-postadressen og bildet som er knyttet til brukeren som er logget på. Du kan bruke denne informasjonen til å automatisk fylle ut et skjema.

Du kan for eksempel bruke denne funksjonen til å:

* Opprette et «registreringsark» for brukere som ønsker å delta på opplæring, være frivillig ved arrangementer, besøke en kiosk med mer.
* Vise det fullstendige navnet på en app for personaladministrasjon.
* Angi en e-postadresse automatisk når du kontakter brukerstøtte.

I utgangspunktet kan du bruke denne hvor som helst hvor brukere kan dra nytte av et skjema eller etiketter som er automatisk utfylt

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="show-user-details"></a>Vis brukerdetaljer
1. Klikk eller trykk på **Media** på **Sett inn**-fanen, og klikk eller trykk deretter på **Bilde**.
   
   ![][2]
2. Angi **[Bilde](controls/properties-visual.md)**-egenskapen til denne formelen:
   <br>**User().Image**
   
    ![][3]
3. Klikk eller trykk på **Tekst** på **Sett inn**-fanen, og deretter klikker eller trykker du på **Etikett**:  
   
    ![][4]
4. Angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**User().FullName**
   
   ![][6]
   
   Når du gjør dette, fylles etiketten automatisk ut med hele navnet ditt. Flytt etiketten slik at den er under bildekontrollen, omtrent som følger:
   
   ![][5]
5. Legg til en annen etikett, og angi **[Tekst](controls/properties-core.md)**-egenskapen til denne formelen:
   <br>**User().Email**  
   
    ![][8]
   
    Når du gjør dette, fylles etiketten automatisk ut med e-postadressen din. Flytt etiketten slik at den er under den første etiketten, omtrent som følger:  
   
    ![][7]

[2]: ./media/show-current-user/add-image.png
[3]: ./media/show-current-user/imageproperty.png
[4]: ./media/show-current-user/insertlabel.png
[5]: ./media/show-current-user/label.png
[6]: ./media/show-current-user/textproperty.png
[7]: ./media/show-current-user/secondlabel.png
[8]: ./media/show-current-user/email.png
[9]: ./media/show-current-user/preview.png
