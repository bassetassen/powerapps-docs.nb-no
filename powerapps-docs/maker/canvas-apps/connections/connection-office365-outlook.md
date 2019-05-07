---
title: Oversikt over Office 365-tilkoblingen | Microsoft Docs
description: Referanseinformasjon med eksempler for Office 365 Outlook-tilkobling til PowerApps
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/20/2017
ms.author: lanced
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4f22f55b3c64d38cc274b0b69d8e7799c1a24f60
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61545399"
ms.PowerAppsDecimalTransform: true
---
# <a name="connect-to-office-365-outlook-from-powerapps"></a>Å koble til Office 365 Outlook fra PowerApps
![Office 365 Outlook](./media/connection-office365-outlook/office365icon.png)

Hvis du kobler til Office 365 Outlook, kan du vise, sende, slette og svare på e-postmeldinger, i tillegg til å utføre andre oppgaver.

Du kan legge til kontroller for å utføre disse funksjonene i appen. Du kan for eksempel legge til **Tekstinndata**-kontroller for å spørre etter mottakeren, emnet og brødteksten i e-postmeldingen, og legge til en **Knapp**-kontroll for å sende e-postmeldingen.

Dette emnet viser deg hvordan du legger til Office 365 Outlook som en tilkobling, som en datakilde i appen, og hvordan du bruker disse dataene i forskjellige kontroller.

> [!IMPORTANT]
> I skrivende stund støtter ikke kalenderfunksjonen gjentakende hendelser.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-office-365-outlook"></a>Slik kobler du til Office 365 Outlook
1. [Legg til en datatilkobling](../add-data-connection.md), og velg **Office 365 Outlook**:  
   
    ![Slik kobler du til Office 365](./media/connection-office365-outlook/add-office.png)
2. Velg **Koble til**, og hvis du blir bedt om å logge på, skriver du inn jobbkontoen din.

Office 365 Outlook-tilkoblingen er opprettet og lagt til i appen din. Den er nå klar til å brukes.

## <a name="show-messages"></a>Å hente meldinger
1. Velg **Galleri** på **Sett inn**-menyen, og velg deretter en **Tekstgalleri**-kontroll.
2. Angi **[Items](../controls/properties-core.md)**-egenskapen til følgende formel:  
   
    `Office365.GetEmails({fetchOnlyUnread:false})`
   
    Gallerikontrollen fylles automatisk med noen av e-postmeldingene dine.
3. Angi **Text**-egenskapen for den første etiketten til `ThisItem.From`, i galleriet. Angi den andre etiketten til `ThisItem.Subject`. Angi den tredje etiketten til `ThisItem.Body`. Du kan også endre størrelsen på etikettene.
   
    Galleriet fylles automatisk med de nye egenskapene.
4. Denne funksjonen har flere valgfrie parametere tilgjengelig. Angi **Items**-egenskapen for galleriet til en av følgende formler:
   
    `Office365.GetEmails({fetchOnlyUnread:false})`  
    `Office365.GetEmails({fetchOnlyUnread:false; top:2})`  
    `Office365.GetEmails({folderPath:"Sent Items"; fetchOnlyUnread:false; top:2})`  
    `Office365.GetEmails({folderPath:"Sent Items"; fetchOnlyUnread:false; top:2; searchQuery:"powerapps"})`  
    `Office365.GetEmails({folderPath:"Deleted Items"; fetchOnlyUnread:false; top:2; skip:3})`

## <a name="send-a-message"></a>Sending av en melding
1. Velg **Tekst** på **Sett inn**-menyen, og velg deretter **Tekstinndata**.
2. Gjenta det forrige trinnet to ganger til, slik at du har tre bokser, og ordne dem deretter i en kolonne:  
   
    ![Tre bokser i en kolonne](./media/connection-office365-outlook/threetextinput.png)
3. Navngi kontrollene på nytt til:  
   
   * **inputTo**
   * **inputSubject**
   * **inputBody**
4. Velg **Kontroller** på **Sett inn**-menyen, og velg **Knapp**. Angi **[OnSelect](../controls/properties-core.md)**-egenskapen til følgende formel:  
   
    `Office365.SendEmail(inputTo.Text; inputSubject.Text; inputBody.Text)`
5. Flytt knappen slik at den vises under alle de andre kontrollene, og angi **[Text](../controls/properties-core.md)**-egenskapen til **Send e-postmelding**.
6. Trykk på F5, eller velg forhåndsvisningsknappen (![Forhåndsvisningsknapp](./media/connection-office365-outlook/preview.png)). Skriv inn gyldig e-postadresse i **inputTo**, og skriv inn det du ønsker i de to andre **Tekstinndata**-kontrollene.
7. Velg **Send e-postmelding** for å sende meldingen. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="send-a-message-with-an-attachment"></a>Sending av en melding med et vedlegg
Du kan for eksempel opprette en app der brukeren tar bilder ved hjelp av enhetens kamera og deretter sender dem som vedlegg. Brukere kan også legge til mange andre filtyper til en e-postapp.

Hvis du vil legge til et vedlegg i en melding, følger du trinnene i forrige del, men legg til en parameter for å angi et vedlegg (når du angir **OnSelect**-egenskapen for knappen). Denne parameteren er strukturert som en tabell der du kan angi opptil tre egenskaper for hvert vedlegg:

* navn
* ContentBytes
* @odata.type

> [!NOTE]
> Du kan angi @odata.type-egenskapen for bare ett vedlegg, og du kan angi den til en tom streng.

I dette eksemplet blir et bilde sendt som **file1.jpg**:

`Office365.SendEmail(inputTo.Text; inputSubject.Text; inputBody.Text; {Attachments:Table({Name:"file1.jpg"; ContentBytes:Camera1.Photo; '@odata.type':""})})`

I dette eksemplet blir en lydfil sendt i tillegg til bildet:

`Office365.SendEmail(inputTo.Text; inputSubject.Text; inputBody.Text; {Attachments:Table({Name:"file1.jpg"; ContentBytes:Camera1.Photo; '@odata.type':""}; {Name:"AudioFile"; ContentBytes:microphone1.audio })})`

## <a name="delete-a-message"></a>Sletting av en melding
1. Velg **Galleri** på **Sett inn**-menyen, og velg deretter en **Tekstgalleri**-kontroll.
2. Angi **[Items](../controls/properties-core.md)**-egenskapen til følgende formel:  
   
    `Office365.GetEmails({fetchOnlyUnread:false})`
   
    Gallerikontrollen fylles automatisk med noen av e-postmeldingene dine.
3. Angi **Text**-egenskapen for den første etiketten til `ThisItem.Id`, i galleriet. Angi den andre etiketten til `ThisItem.Subject`. Angi den tredje etiketten til `ThisItem.Body`.
4. Velg den første etiketten i galleriet, og gi den det nye navnet **EmailID**:
   
    ![Gi et nytt navn til den første etiketten](./media/connection-office365-outlook/renameheading.png)
5. Velg den tredje etiketten i galleriet, og legg til en **Knapp** (**Sett inn**-menyen). Angi knappens **OnSelect**-egenskap til følgende formel:  
   
    `Office365.DeleteEmail(EmailID.Text)`
6. Trykk på F5, eller velg forhåndsvisningsknappen (![Forhåndsvisningsknapp](./media/connection-office365-outlook/preview.png)). Velg en av e-postmeldingene i galleriet, og klikk på knappen. 
    
    > [!NOTE]
    > Dette sletter den valgte e-postmeldingen fra innboksen din. Så, velg fornuftig.
7. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="mark-a-message-as-read"></a>Slik merker du en melding som lest
Denne delen bruker de samme kontrollene som [Sletting av en melding](connection-office365-outlook.md#delete-a-message).

1. Angi knappens **OnSelect**-egenskap til følgende formel:  
   
    `Office365.MarkAsRead(EmailID.Text)`
2. Trykk på F5, eller velg forhåndsvisningsknappen (![Forhåndsvisningsknapp](./media/connection-office365-outlook/preview.png)). Velg en av de uleste e-postmeldingene, og klikk deretter på knappen.
3. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="helpful-links"></a>Nyttige koblinger
* Du kan gå til [Office 365 Outlook-referanse](https://docs.microsoft.com/connectors/office365connector/) for å få en liste over alle funksjoner og tilhørende parametere.
* Se alle [tilgjengelige tilkoblinger](../connections-list.md).  
* Finn ut hvordan du [behandler tilkoblingene dine](../add-manage-connections.md).

