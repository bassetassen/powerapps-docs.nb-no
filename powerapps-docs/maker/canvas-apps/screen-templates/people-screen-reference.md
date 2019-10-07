---
title: Referanse til personer-skjerm malen | Microsoft Docs
description: Få informasjon om hvordan malen for personer-skjermen for lerret apps fungerer i PowerApps
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 1/2/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0a1626583300e6fe696415a91de68ff08596f081
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71989397"
---
# <a name="reference-information-about-the-people-screen-template-for-canvas-apps"></a>Referanse informasjon om malen for personer-skjermen for lerret apper

For å få en lerret-app i PowerApps kan du forstå hvordan hver omfattende kontroll i personer-skjerm-malen bidrar til skjermens generelle standard funksjon. Denne dype Fremgangs måten presenterer virke måte formler og verdiene til andre egenskaper som bestemmer hvordan kontrollene svarer på bruker inn data. Hvis du vil ha en høy nivå diskusjon av denne skjermens standard funksjon, kan du se [Oversikt over personer-skjermen](people-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykkene eller formlene som ulike egenskaper (for eksempel **elementer** og **OnSelect**) til disse kontrollene er angitt for:

* [Tekst søkeboks](#text-search-box)
* [Bruker-Browse-Galleri](#user-browse-gallery) (+ underordnede kontroller)
* [Personer lagt til galleri](#people-added-gallery) (+ underordnede kontroller)

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Boks for tekstsøk

![TextSearchBox-kontroll](media/people-screen/people-search-box.png)

Et par andre kontroller samhandler eller har en avhengighet på tekst søk-boksen:

* Hvis en bruker begynner å skrive inn tekst, blir **UserBrowseGallery** synlig.
* Når en bruker velger en person i **UserBrowseGallery**, tilbakestilles søke innholdet.

## <a name="user-browse-gallery"></a>Galleri for bruker visning

![UserBrowseGallery-kontroll](media/people-screen/people-browse-gall.png)

* Gjelder **Elementene**<br>
    Revaluer Logikk for å slå opp brukere når brukeren begynner å skrive:
    
    ```powerapps-dot
    If( !IsBlank( Trim( TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser(
            {
                searchTerm: Trim( TextSearchBox.Text ), 
                top: 15
            }
        )
    )
    ```
    
Elementene i dette galleriet er fylt ut av søke resultater fra [office365. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -operasjonen. Operasjonen tar teksten i `Trim(TextSearchBox)` som søke ordet og returnerer de 15 høyeste resultatene basert på søket. **TextSearchBox** er pakket i en `Trim()`-funksjon fordi en bruker søker etter mellomrom er ugyldig.

@No__t-0-operasjonen brytes i en `If(!IsBlank(Trim(TextSearchBox.Text)) ... )`-funksjon fordi du bare trenger å kalle operasjonen når søke boksen inneholder brukerangitt tekst. Dette forbedrer ytelsen.

### <a name="userbrowsegallery-title-control"></a>UserBrowseGallery tittel-kontroll

![UserBrowseGallery tittel-kontroll](media/people-screen/people-browse-gall-title.png)

* Gjelder **Tekst**<br>Verdi: `ThisItem.DisplayName`

  Viser personens visnings navn fra Office 365-profilen.

* Gjelder **OnSelect**<br>
    Revaluer Kode for å legge til brukeren i en samling på en app-nivå, og velg deretter brukeren:

    ```powerapps-dot
    Concurrent(
        Set( _selectedUser, ThisItem ),
        Reset( TextSearchBox ),
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ), 
            Collect( MyPeople, ThisItem )
        )
    )
    ```
Hvis du velger denne kontrollen, vil tre ting samtidig:

   * Angir den **\_selectedUser-** variabelen til det valgte elementet.
   * Tilbakestiller søke ordet i **TextSearchBox**.
   * Legger til det valgte elementet i **MyPeople** -samlingen, en samling av alle personene som appen bruker har valgt.

### <a name="userbrowsegallery-profileimage-control"></a>UserBrowseGallery ProfileImage-kontroll

![UserBrowseGallery ProfileImage-kontroll](media/people-screen/people-browse-gall-image.png)

* Gjelder **Bilde**<br>
    Revaluer Logikk for å hente brukerens profil bilde.

    ```powerapps-dot
    If( !IsBlank( ThisItem.Id ) && 
            'Office365Users'.UserPhotoMetadata( ThisItem.Id ).HasPhoto,
        'Office365Users'.UserPhoto( ThisItem.Id )
    )
    ```

**Bilde** kontrollen henter brukerens bilde med [Office365Users. UserPhoto](https://docs.microsoft.com/connectors/office365users/#get-user-photo--v1-) -operasjonen. Men før du gjør det, ser det etter to ting:
  
   * Om ID-feltet er tomt eller ikke tomt. Dette hindrer at **bilde** -kontrollen prøver å hente et bruker bilde før galleriet er fylt ut med søke resultater.
   * Om brukeren har et bilde (med [Office365Users. UserPhotoMetadata](https://docs.microsoft.com/connectors/office365users/#get-user-photo-metadata) -operasjonen). Dette hindrer at oppslaget på @no__t 0 returnerer et unntak hvis brukeren ikke har et profil bilde.

Vær oppmerksom på at hvis et bilde ikke hentes, er **bilde** kontrollen tom, og **iconUser** -kontrollen vises i stedet.

## <a name="people-added-gallery"></a>Personer-lagt til galleri

![PeopleAddedGallery-kontroll](media/people-screen/people-people-gall.png)

* Gjelder **Elementene**<br>
    Verdi: `MyPeople`

Dette er samlingen av personer som er initialisert eller lagt til ved å velge **UserBrowseGallery title** -kontrollen.

### <a name="peopleaddedgallery-title-control"></a>PeopleAddedGallery tittel-kontroll

![PeopleAddedGallery tittel-kontroll](media/people-screen/people-people-gall-title.png)

* Gjelder **OnSelect**<br>
    Verdi: `Set( _selectedUser, ThisItem )`

Angir **_selectedUser** -variabelen til elementet som er valgt i **EmailPeopleGallery**.

### <a name="peopleaddedgallery-iconremove-control"></a>PeopleAddedGallery iconRemove-kontroll

![PeopleAddedGallery iconRemove-kontroll](media/people-screen/people-people-gall-delete.png)

* Gjelder **OnSelect**<br>
    Verdi: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

Slår opp posten i **MyPeople** -samlingen, der **userPrincipalName** Sams varer med **userPrincipalName** for det valgte elementet, og fjerner deretter posten fra samlingen.

## <a name="next-steps"></a>Neste trinn

* [Les mer om dette skjerm bildet](./people-screen-overview.md).
* [Les mer om Office 365 Outlook Connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om koblingen til Office 365-brukere](../connections/connection-office365-users.md).
