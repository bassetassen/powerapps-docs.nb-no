---
title: Referanse for e-post-skjerm malen for lerreter | Microsoft Docs
description: Forstå detaljer om hvordan malen for e-postskjermen for lerret apps fungerer i PowerApps
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/31/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7663668b77c6f8186ef54c3182230fa843f86577
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995703"
---
# <a name="reference-information-about-the-email-screen-template-for-canvas-apps"></a>Referanse informasjon om malen for e-post-skjermen for lerret apper

For å få en lerret-app i PowerApps kan du forstå hvordan hver betydelig kontroll i e-post-skjerm malen bidrar til skjermens generelle standard funksjon. Denne dype forhandlingen presenterer virke måte formlene og verdiene til andre egenskaper som bestemmer hvordan kontrollene svarer på bruker inn data. Hvis du vil ha en høy nivå diskusjon av denne skjermens standard funksjon, kan du se [Oversikt over e-post skjermen](email-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykkene eller formlene som ulike egenskaper (for eksempel **elementer** og **OnSelect**) til disse kontrollene er angitt for:

* [Tekst søkeboks](#text-search-box)
* [Legg til ikon](#add-icon)
* [Galleri for personer-bla gjennom](#people-browse-gallery)
* [E-postpersonens Galleri](#email-people-gallery) (+ underordnede kontroller)
* [E-postikon](#mail-icon)

## <a name="prerequisite"></a>Nødvendig

Kjennskap til hvordan du legger til og konfigurerer skjermer og andre kontroller mens du [oppretter en app i powerapps](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Boks for tekstsøk

   ![TextSearchBox-kontroll](media/email-screen/email-search-box.png)

Flere andre kontroller på skjermen har en avhengighet på **tekst søk Box** -kontrollen:

* Hvis en bruker begynner å skrive inn tekst, vises **PeopleBrowseGallery** .
* Hvis en bruker skriver inn en gyldig e-postadresse, vises **AddIcon** .
* Når en bruker velger en person i **PeopleBrowseGallery**, tilbakestilles søke innholdet.

## <a name="add-icon"></a>Legg til-ikon

   ![AddIcon-kontroll](media/email-screen/email-add-icon.png)

Med **Legg til ikon** -kontrollen kan App-brukere legge til personer som ikke finnes i organisasjonen, i mottaker listen til e-postmeldingen som er opprettet.

* Gjelder **Tydelig**<br>
    Revaluer Logikk for å vise kontrollen bare når en bruker skriver inn en gyldig e-postadresse i søke boksen:

    ```powerapps-dot
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text, Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```
  Linje for linje, sier den foregående kode blokken at **Legg til ikon** -kontrollen bare vil være synlig hvis:

    * **TextSearchBox** inneholder tekst.
    * Teksten i **TextSearchBox** er en gyldig e-postadresse.
    * Teksten i **TextSearchBox** finnes ikke allerede i **MyPeople** -samlingen.

* Gjelder **OnSelect**<br>
    Revaluer Hvis du velger dette, legges det til en gyldig e-postadresse i **MyPeople** -samlingen. Denne samlingen brukes av skjermen som mottaker liste:

    ```powerapps-dot
    Collect( MyPeople,
        { 
            DisplayName: TextSearchBox.Text, 
            UserPrincipalName: TextSearchBox.Text, 
            Mail: TextSearchBox.Text
        }
    );
    Reset( TextSearchBox )
    ```
  
  Denne kode blokken legger til en rad i **MyPeople** -samlingen og fyller tre felter med teksten i **TextSearchBox**. Disse tre feltene er **DisplayName**, **userPrincipalName**og **e-post**. Deretter tilbakestiller den innholdet i **TextSearchBox**.

## <a name="people-browse-gallery"></a>Galleri for personer-bla gjennom

   ![PeopleBrowseGallery-kontroll](media/email-screen/email-browse-gall.png)

* Gjelder **Elementene**<br>
    Revaluer De 15 høyeste søke resultatene for søke teksten som skrives inn i **TextSearchBox** -kontrollen:
    
    ```powerapps-dot
    If( !IsBlank( Trim(TextSearchBox.Text ) ), 
        'Office365Users'.SearchUser( {searchTerm: Trim( TextSearchBox.Text ), top: 15} )
    )
    ```

  Elementene i dette galleriet er fylt ut av søke resultater fra [office365. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -operasjonen. Operasjonen tar teksten i `Trim(TextSearchBox)` som søke ordet og returnerer de 15 høyeste resultatene basert på søket.
  
  **TextSearchBox** er pakket i en `Trim()`-funksjon fordi en bruker søker etter mellomrom er ugyldig. @No__t-0-operasjonen brytes i en `If(!IsBlank(Trim(TextSearchBox.Text)) ... )`-funksjon, noe som betyr at operasjonen utføres bare hvis søke boksen inneholder brukerangitt tekst. Dette forbedrer ytelsen. 

### <a name="people-browse-gallery-title-control"></a>Person bla gjennom Galleri tittel kontroll

   ![PeopleBrowseGallery tittel-kontroll](media/email-screen/email-browse-gall-title.png)

* Gjelder **Tekst**<br>
    Verdi: `ThisItem.DisplayName`

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

   * Angir **_selectedUser** -variabelen til det valgte elementet.
   * Tilbakestiller søke ordet i **TextSearchBox**.
   * Legger til det valgte elementet i **MyPeople** -samlingen, en samling av alle de valgte brukerne som e-postskjermen bruker som et sett med mottakere.

## <a name="email-people-gallery"></a>E-postgalleri for person

   ![EmailPeopleGallery-kontroll](media/email-screen/email-people-gall.png)

* Gjelder **Elementene**<br>
    Verdi: `MyPeople`

  Dette er samlingen av personer som er initialisert eller lagt til ved å velge **PeopleBrowseGallery title** -kontrollen.

* Gjelder **Høyden**<br>
    Revaluer Logikk for å angi høyden, basert på antallet elementer som for øyeblikket er i galleriet:

    ```powerapps-dot
    Min( 
        ( EmailPeopleGallery.TemplateHeight + EmailPeopleGallery.TemplatePadding * 2) *
            RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0 ),
        304
    )
    ```

  Høyden på dette galleriet justerer etter antall elementer i galleriet, med en maksimums høyde på 304.
  
  Den tar `TemplateHeight + TemplatePadding * 2` som den totale høyden for en enkelt rad med **EmailPeopleGallery**, og multipliserer den deretter etter antall rader. Siden `WrapCount = 2`, er antallet sanne rader `RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2, 0)`.

* Gjelder **ShowScrollbar**<br>
    Verdi: `EmailPeopleGallery.Height >= 304`
  
  Når høyden på galleriet når 304, vises rulle feltet.

### <a name="email-people-gallery-title-control"></a>Tittel kontroll for e-postpersonens galleri

   ![EmailPeopleGallery tittel-kontroll](media/email-screen/email-people-gall-text.png)

* Gjelder **OnSelect**<br>
    Verdi: `Set(_selectedUser, ThisItem)`

  Angir **_selectedUser** -variabelen til elementet som er valgt i **EmailPeopleGallery**.

### <a name="email-people-gallery-iconremove-control"></a>IconRemove-kontroll for e-postperson galleri

   ![MonthDayGallery tittel-kontroll](media/email-screen/email-people-gall-delete.png)

* Gjelder **OnSelect**<br>
    Verdi: `Remove( MyPeople, LookUp( MyPeople, UserPrincipalName = ThisItem.UserPrincipalName ) )`

  Slår opp posten i **MyPeople** -samlingen, der **userPrincipalName** Sams varer med **userPrincipalName** for det valgte elementet, og fjerner denne posten fra samlingen.

## <a name="mail-icon"></a>E-postikon

* Gjelder **OnSelect**<br>
    Revaluer Logikk for å sende brukerens e-postmelding:

    ```powerapps-dot
    Set( _emailRecipientString, Concat( MyPeople, Mail & ";" ) );
    'Office365'.SendEmail( _emailRecipientString, 
        TextEmailSubject.Text,  
        TextEmailMessage.Text, 
        { Importance:"Normal" }
    );
    Reset( TextEmailSubject );
    Reset( TextEmailMessage );
    Clear( MyPeople )
    ```

  Sending av en e-postmelding krever en semikolondelt streng med e-postadresser. I foregående kode:
  1. Den første kode linjen tar **e** -postfeltet fra alle radene i **MyPeople** -samlingen, kjeder dem inn i én enkelt streng med e-postadresser atskilt med semikolon, og angir **_emailRecipientString** -variabelen til strengen revaluer.

  1. Deretter brukes [office365. sende mail](https://docs.microsoft.com/connectors/office365/#sendemail) -operasjonen til å sende e-postmeldingen til mottakerne.
    Operasjonen har tre nødvendige parametere, **til**, **Emne**og **brød tekst**, og én valg fri parameter –**viktighet**. I den foregående koden er disse **_emailRecipientString**, **TextEmailSubject**. Text, **TextEmailMessage**. Henholdsvis tekst og **Normal**.
  1. Til slutt tilbakestiller den **TextEmailSubject** -og **TextEmailMessage** -kontrollen og fjerner **MyPeople** -samlingen.

* Gjelder **Display Mode**<br>
    Revaluer `If( Len( Trim( TextEmailSubject.Text ) ) > 0 && !IsEmpty( MyPeople ), DisplayMode.Edit, DisplayMode.Disabled )` Hvis du vil sende en e-postmelding, må Emne linjen for e-posten ha tekst, og mottakeren (**MyPeople**)-samlingen kan ikke være tom.

## <a name="next-steps"></a>Neste trinn

* [Lær mer om denne skjermen](./email-screen-overview.md)
* [Finn ut mer om Office 365 Outlook Connector i PowerApps](../connections/connection-office365-outlook.md)
* [Les mer om Office 365 brukere-koblingen i PowerApps](../connections/connection-office365-users.md)
