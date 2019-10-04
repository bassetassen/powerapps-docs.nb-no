---
title: Vis profil kortet for en kontakt eller bruker | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 67441e506ba2715a9994f6b81cd08426e37e0fc8
ms.sourcegitcommit: 7c46e7ce889e2f1c5352ed2e705b0bb8968f2a89
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/04/2019
ms.locfileid: "71950914"
---
# <a name="view-the-profile-card-for-a-contact-or-user"></a>Vis profil kortet for en kontakt eller bruker

Bruk profil kortet til å få rask informasjon om en kontakt eller bruker. Når du velger et kontakt-eller bruker felt i modell drevne apper i Dynamics 365, for eksempel Dynamics 365 Sales og Dynamics 365 Customer Service, kan du finne informasjon relatert til dem på profil kortet. Hvis du vil ha mer informasjon om profil kort, kan du se [profil kort i Office 365](https://support.office.com/en-us/article/Profile-cards-in-Office-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501).

> [!NOTE]
>  - Profil kort er tilgjengelig for **kontakten** og **brukeren** heten. Hvis du vil ha mer informasjon, kan du se [aktivere profil kortet (for administratorer)](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/enable-profile-card).
>  - Profil kortet i Common Data Service vises ikke hvis multi-Factor Authentication er aktivert for kontor Delve-tjenesten i Azure Active Directory.

## <a name="view-a-contacts-profile"></a>Vis profilen til en kontakt

1.  Gå til **Aktiviteter**.
2.  Velg en eksisterende aktivitet, eller Opprett en ny.
3.  Beveg pekeren over **kall til** -feltet når det er en kontakt post. 

Du kan vise informasjon om den innebygde kontakten, som inkluderer kontakt bilde, navn, tittel og konto.

4. Hvis du vil vise flere detaljer, velger du **Vis mer** for å utvide kontaktens profil.
 
    > [!div class="mx-imgBorder"] 
    > ![Vis detaljer for kontakt profil kort](media/profile1.png "Vis kontakt profil kort informasjon")
   
 ## <a name="view-a-users-profile"></a>Vis en brukers profil
 
1.  Gå til **kontoer**.
2.  Velg en forretnings forbindelses oppføring.
3.  Beveg pekeren over eier feltet når det har en bruker oppføring. Du kan vise detaljene for den innebygde brukeren.
4.  Hvis du vil vise flere detaljer som e-post og delte filer med brukeren, velger du **Vis mer** for å utvide kontaktens profil.
 
    > [!div class="mx-imgBorder"] 
    > ![Vis detaljer om bruker profil kort](media/profile2.png "Vis informasjon om Utvid bruker profil kort")


 ## <a name="faqs"></a>Stil
 
### <a name="where-can-i-see-profile-cards-in-dynamics-365"></a>Hvor kan jeg se profil kort i Dynamics 365?
Du kan se på kontakt-og bruker oppføringer i profil kort. Du kan bare vise dem når de er i et oppslag.

### <a name="where-is-information-shown-in-the-profile-card-coming-from"></a>Hvor kommer informasjon fra profil kortet fra?
Informasjonen som vises på kontakt profil kortet hentes fra Common Data Service (og ikke Microsoft Exchange). Dette betyr at kontakt opplysningene kommer fra Dynamics 365.

Informasjonen som vises på bruker profil kortet hentes fra Office 365 (Azure Active Directory). Hvis du vil ha mer informasjon, kan du se [profil kort i Office 365 (administrator del)](https://support.office.com/en-us/article/Profile-cards-in-Office-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501).

### <a name="how-can-i-customize-the-fields-shown-on-the-profile-card"></a>Hvordan kan jeg tilpasse feltene som vises på profil kortet?
Listen over felt som vises på profil kortet, er for øyeblikket ikke åpnet for tilpasning.

### <a name="why-is-the-start-chat-option-on-the-profile-card-disabled-greyed-out"></a>Hvorfor er alternativet **Start chat** på profil kortet deaktivert (nedtonet)?
**Start chat** , og alternativene for å **sende e-post** på profil kortet, åpner standard direkte meldinger og e-postapper. Alternativet **Start chat** er aktivert hvis personen du prøver å kontakte i det samme Azure Active Directory miljøet, som du eller er en sammenslått kontakt.


  
