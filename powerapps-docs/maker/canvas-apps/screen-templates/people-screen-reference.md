---
title: Personer-skjermen malreferansen | Microsoft Docs
description: Forstå detaljene for hvordan personer-skjermen malen for lerret-apper fungerer i PowerApps
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 1/2/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 09b92a1e2bc87ac6f4e2ec651aa67a845e0f07b1
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61540783"
ms.PowerAppsDecimalTransform: true
---
# <a name="reference-information-about-the-people-screen-template-for-canvas-apps"></a>Referanseinformasjon om personer-skjermen malen for lerretsapper

Forstå hvordan hver betydelige kontroll i malen personer skjerm bidrar til skjermens overordnede standardfunksjonaliteten for lerret-apper i PowerApps. Dette dypdykket noe presenterer formler for virkemåte og verdiene i andre egenskaper som bestemmer hvordan kontrollene svare på inndata fra brukeren. Hvis en på høyt nivå gjennomgang av denne skjermen standard funksjonalitet, kan du se den [personer-skjermen oversikt over](people-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykk eller formler til hvilke ulike egenskaper (slik som **elementer** og **OnSelect**) av disse kontrollene er angitt:

* [Tekstboks for søk](#text-search-box)
* [Bruker-Bla gjennom-galleriet](#user-browse-gallery) (+ underordnede kontroller)
* [Personer lagt til galleriet](#people-added-gallery) (+ underordnede kontroller)

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Boks for tekstsøk

![TextSearchBox kontroll](media/people-screen/people-search-box.png)

Et par andre kontroller samhandle eller har en avhengighet på tekstboksen for søk:

* Hvis en bruker starter å skrive inn tekst, **UserBrowseGallery** blir synlig.
* Når en bruker velger en person i **UserBrowseGallery**, search innholdet tilbakestilles.

## <a name="user-browse-gallery"></a>Bruker-Bla gjennom-galleriet

![UserBrowseGallery kontroll](media/people-screen/people-browse-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: Logikk for å slå opp brukere når brukeren starter å skrive inn:
    
    ```powerapps-comma
    If( !IsBlank( Trim( TextSearchBox.Text ) ); 
        'Office365Users'.SearchUser(
            {
                searchTerm: Trim( TextSearchBox.Text ); 
                top: 15
            }
        )
    )
    ```
    
Elementene i dette galleriet fylles som søkeresultater fra den [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) operasjonen. Operasjonen tar teksten `Trim(TextSearchBox)` som søket term og returnerer resultatene topp 15 som er basert på dette søket. **TextSearchBox** er pakket i en `Trim()` funksjonen fordi et bruker-Søk etter mellomrom er ugyldig.

Den `Office365Users.SearchUser` operasjonen er pakket i en `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` funksjonen, da du trenger bare å ringe operasjonen når søkeboksen inneholder brukerangitt tekst. Dette forbedrer ytelsen.

### <a name="userbrowsegallery-title-control"></a>UserBrowseGallery tittel kontroll

![UserBrowseGallery tittel kontroll](media/people-screen/people-browse-gall-title.png)

* Egenskap: **Tekst**<br>Verdi: `ThisItem.DisplayName`

  Viser personens visningsnavn fra deres Office 365-profilen.

* Egenskap: **OnSelect**<br>
    Verdi: Kode for å legge til brukeren i en samling med app-nivå, og velg deretter brukeren:

    ```powerapps-comma
    Concurrent(
        Set( _selectedUser; ThisItem );
        Reset( TextSearchBox );
        If( Not( ThisItem.UserPrincipalName in MyPeople.UserPrincipalName ); 
            Collect( MyPeople; ThisItem )
        )
    )
    ```
Å velge denne kontrollen har tre ting samtidig:

   * Sett den  **\_selectedUser** variabel som skal det merkede elementet.
   * Tilbakestiller søketermen i **TextSearchBox**.
   * Legger til det valgte elementet til den **MyPeople** samling, en samling av alle personene appbrukeren har valgt.

### <a name="userbrowsegallery-profileimage-control"></a>UserBrowseGallery ProfileImage-kontroll

![UserBrowseGallery ProfileImage-kontroll](media/people-screen/people-browse-gall-image.png)

* Egenskap: **Bilde**<br>
    Verdi: Logikk for å hente en brukers profilbilde.

    ```powerapps-comma
    If( !IsBlank( ThisItem.Id ) && 
            'Office365Users'.UserPhotoMetadata( ThisItem.Id ).HasPhoto;
        'Office365Users'.UserPhoto( ThisItem.Id )
    )
    ```

Den **bilde** kontrollen henter brukerens bilde med den [Office365Users.UserPhoto](https://docs.microsoft.com/connectors/office365users/#get-user-photo--v1-) operasjonen. Men før du gjør som, ser etter to ting:
  
   * Om ID-feltet er tomt eller ikke tomt. Dette hindrer at den **bilde** kontroll fra forsøk på å hente en Brukerfoto før galleriet har fylt ut med søkeresultater.
   * Angir om brukeren har et bilde (med den [Office365Users.UserPhotoMetadata](https://docs.microsoft.com/connectors/office365users/#get-user-photo-metadata) operasjonen). Dette hindrer at den `Office365Users.UserPhoto` lookup returnerer et unntak hvis brukeren ikke har en profilbilde.

Vær oppmerksom på at hvis et bilde ikke er hentet, **bilde** kontrollen er tom, og den **iconUser** kontrollen er synlig i stedet.

## <a name="people-added-gallery"></a>La personer til galleriet

![PeopleAddedGallery kontroll](media/people-screen/people-people-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: `MyPeople`

Dette er samlingen av personer initialisert eller legges til ved å velge den **UserBrowseGallery tittel** kontroll.

### <a name="peopleaddedgallery-title-control"></a>PeopleAddedGallery tittel kontroll

![PeopleAddedGallery tittel kontroll](media/people-screen/people-people-gall-title.png)

* Egenskap: **OnSelect**<br>
    Verdi: `Set( _selectedUser; ThisItem )`

Sett den **_selectedUser** variabel som skal det valgte elementet i **EmailPeopleGallery**.

### <a name="peopleaddedgallery-iconremove-control"></a>PeopleAddedGallery iconRemove kontroll

![PeopleAddedGallery iconRemove kontroll](media/people-screen/people-people-gall-delete.png)

* Egenskap: **OnSelect**<br>
    Verdi: `Remove( MyPeople; LookUp( MyPeople; UserPrincipalName = ThisItem.UserPrincipalName ) )`

Slår opp posten i den **MyPeople** samling, der **UserPrincipalName** samsvarer med den **UserPrincipalName** for det valgte elementet, og deretter fjerner som registrerer fra den samling.

## <a name="next-steps"></a>Neste trinn

* [Finn ut mer om denne skjermen](./people-screen-overview.md).
* [Finn ut mer om Office 365 Outlook connector](../connections/connection-office365-outlook.md).
* [Finn ut mer om Office 365-brukere connector](../connections/connection-office365-users.md).
