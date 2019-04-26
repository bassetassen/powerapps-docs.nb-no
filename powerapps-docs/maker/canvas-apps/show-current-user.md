---
title: Vis detaljer om den gjeldende brukeren i en lerretsapp | Microsoft Docs
description: Vis navnet og e-postadressen til brukeren som er pålogget i en lerretsapp i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/16/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 12a6cd6f3df6c83f39b08608e1057f5e31e7d46e
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "63319185"
---
# <a name="show-information-about-a-powerapps-user-in-a-canvas-app"></a>Vis informasjon om en PowerApps-bruker i en lerretsapp

Vis det fullstendige navnet, e-postadressen og bildet som er knyttet til brukeren som er pålogget i en lerretsapp i PowerApps. Du kan for eksempel bruke denne informasjonen til å fylle ut et skjema automatisk.

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
