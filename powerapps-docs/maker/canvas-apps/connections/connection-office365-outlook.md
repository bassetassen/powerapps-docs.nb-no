---
title: Oversikt over Office 365-tilkoblingen | Microsoft Docs
description: Referanseinformasjon, inkludert eksempler for Office 365 Outlook-tilkobling til PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/20/2017
ms.author: archanan
ms.openlocfilehash: 2932e3145d38bd0b82c0c56882861e7976572c62
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996092"
---
# <a name="connect-to-office-365-outlook-from-powerapps"></a>Å koble til Office 365 Outlook fra PowerApps
![Office 365 Outlook](./media/connection-office365-outlook/office365icon.png)

Hvis du kobler til Office 365 Outlook, kan du, i tillegg å utføre andre oppgaver; vise, sende, slette og svare på e-postmeldinger.

Du kan legge til kontroller for å utføre disse funksjonene i appen. Du kan for eksempel legge til **Tekstinndata**-kontroller for å be om å få se mottakeren, emnet og brødteksten i e-postmeldingen, og egg til en **Knapp**-kontroll for å sende e-postmeldingen.

Dette emnet viser deg hvordan du legger til Office 365 Outlook som en tilkobling, som en datakilde i appen, og å bruke disse dataene i forskjellige kontroller.

> [!IMPORTANT]
> I skrivende stund vil ikke hendelser som gjentas støttes av kalenderfunksjonen.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-office-365-outlook"></a>Å koble til Office 365 Outlook
1. [Legg til en datatilkobling](../add-data-connection.md), og velg **Office 365 Outlook**:  
   
    ![Å koble til Office 365](./media/connection-office365-outlook/add-office.png)
2. Velg **Koble til**, og hvis du blir bedt om å logge på, angir du jobbkontoen din.

Office 365 Outlook-tilkobling er opprettet og lagt til appen din. Den er nå klar til å brukes.

## <a name="show-messages"></a>Å hente meldinger
1. I **Sett inn**-menyen velger du **Galleri**, og velger deretter en **Tekstgalleri**-kontroll.
2. Angi **[Elementer](../controls/properties-core.md)**-egenskapen til den følgende formelen:  
   
    `Office365.GetEmails({fetchOnlyUnread:false})`
   
    Galleri-kontrollen fylles automatisk med noen av e-postene dine.
3. I galleriet kan du angi **Tekst**-egenskapen for den første etiketten til `ThisItem.From`. Angi den andre etiketten til `ThisItem.Subject`. Angi den tredje etiketten til `ThisItem.Body`. Du kan også endre størrelsen på etikettene.
   
    Galleriet fylles automatisk med de nye egenskapene.
4. Denne funksjonen har flere valgfrie tilgjengelige parametere. Angi galleriets **Elementer**-egenskap til en av følgende formler:
   
    `Office365.GetEmails({fetchOnlyUnread:false})`  
    `Office365.GetEmails({fetchOnlyUnread:false, top:2})`  
    `Office365.GetEmails({folderPath:"Sent Items", fetchOnlyUnread:false, top:2})`  
    `Office365.GetEmails({folderPath:"Sent Items", fetchOnlyUnread:false, top:2, searchQuery:"powerapps"})`  
    `Office365.GetEmails({folderPath:"Deleted Items", fetchOnlyUnread:false, top:2, skip:3})`

## <a name="send-a-message"></a>Å sende en melding
1. Velg **Tekst** på **Sett inn**-menyen, og velg **Tekstinndata**.
2. Gjenta det forrige trinnet to ganger slik at du har tre bokser, og ordne dem deretter i en kolonne:  
   
    ![Tre bokser i en kolonne](./media/connection-office365-outlook/threetextinput.png)
3. Navngi kontrollene på nytt til:  
   
   * **inputTo**
   * **inputSubject**
   * **inputBody**
4. Velg **Kontroller** på **Sett inn**-menyen, og velg **Knapp**. Angi knappens **[OnSelect](../controls/properties-core.md)**-egenskap til følgende formel:  
   
    `Office365.SendEmail(inputTo.Text, inputSubject.Text, inputBody.Text)`
5. Flytt knappen slik at den vises under alle de andre kontrollene, og angi **[Tekst](../controls/properties-core.md)**-egenskapen til **«Send e-post»**.
6. Trykk på F5, eller velg ![forhåndsvisningsknappen](./media/connection-office365-outlook/preview.png). Skriv inn gyldig e-postadresse i **inputTo**, og skriv inn det du ønsker i de to andre **Tekstinndata**-kontrollene.
7. Velg **Send e-post** for å sende meldingen. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="send-a-message-with-an-attachment"></a>Sende en melding med et vedlegg
Du kan for eksempel opprette en app der brukeren tar bilder ved hjelp av enhetens kamera og sender dem som vedlegg. Brukere kan også legge til mange andre filtyper til en e-postapp.

Hvis du vil legge til et vedlegg i en melding, følger du trinnene i forrige del, men legger til et parameter for å angi et vedlegg (når du angir **OnSelect**-egenskapen for knappen). Denne parameteren er strukturert som en tabell der du kan angi opptil tre egenskaper for hvert vedlegg:

* Navn
* ContentBytes
* @odata.type

> [!NOTE]
> Du kan angi @odata.type-egenskapen for bare ett vedlegg, og du kan sette den til en tom streng.

I dette eksemplet blir et bilde sendt som **file1.jpg**:

`Office365.SendEmail(inputTo.Text, inputSubject.Text, inputBody.Text, {Attachments:Table({Name:"file1.jpg", ContentBytes:Camera1.Photo, '@odata.type':""})})`

I dette eksemplet blir en lydfil sendt i tillegg til bildet:

`Office365.SendEmail(inputTo.Text, inputSubject.Text, inputBody.Text, {Attachments:Table({Name:"file1.jpg", ContentBytes:Camera1.Photo, '@odata.type':""}, {Name:"AudioFile", ContentBytes:microphone1.audio })})`

## <a name="delete-a-message"></a>Å slette en melding
1. I **Sett inn**-menyen velger du **Galleri**, og velger deretter en **Tekstgalleri**-kontroll.
2. Angi **[Elementer](../controls/properties-core.md)**-egenskapen til den følgende formelen:  
   
    `Office365.GetEmails({fetchOnlyUnread:false})`
   
    Galleri-kontrollen fylles automatisk med noen av e-postene dine.
3. I galleriet kan du angi **Tekst**-egenskapen for den første etiketten til `ThisItem.Id`. Angi den andre etiketten til `ThisItem.Subject`. Angi den tredje etiketten til `ThisItem.Body`.
4. Velg den første etiketten i galleriet, og gi den det nye navnet **EmailID**:
   
    ![Gi et nytt navn til den første etiketten](./media/connection-office365-outlook/renameheading.png)
5. Velg den tredje etiketten i galleriet, og legg til **knapp** (**Sett inn**-menyen). Angi knappens **OnSelect**-egenskap til følgende formel:  
   
    `Office365.DeleteEmail(EmailID.Text)`
6. Trykk F5, eller velg forhåndsvisningsknappen (![Forhåndsvisning-knapp](./media/connection-office365-outlook/preview.png)). Velg ett av e-postmeldingene i galleriet, og klikk på knappen. 
    
    > [!NOTE]
    > Dette sletter den valgte e-posten fra innboksen din. Så, velg fornuftig.
7. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="mark-a-message-as-read"></a>Å merke en melding som lest
Denne delen bruker de samme kontrollene som [Å slette en melding](connection-office365-outlook.md#delete-a-message).

1. Angi knappens **OnSelect**-egenskap til følgende formel:  
   
    `Office365.MarkAsRead(EmailID.Text)`
2. Trykk F5, eller velg forhåndsvisningsknappen (![Forhåndsvisning-knapp](./media/connection-office365-outlook/preview.png)). Velg ett av de uleste e-postmeldingene, og klikk deretter på knappen.
3. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="helpful-links"></a>Nyttige koblinger
* Se [Office 365 Outlook-referanse](https://docs.microsoft.com/connectors/office365connector/), for å få en liste over alle funksjonene og deres parametre.
* Se alle [tilgjengelige tilkoblinger](../connections-list.md).  
* Finn ut hvordan du [behandler tilkoblingene](../add-manage-connections.md).

