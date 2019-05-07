---
title: Referanse for e-post-skjermen malen for lerretsapper | Microsoft Docs
description: Forstå detaljene for hvordan e-post-skjermen malen for lerret-apper fungerer i PowerApps
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/31/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8f77fe1194ace2f8cb5abeb3f9657cc76aab263a
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61538828"
ms.PowerAppsDecimalTransform: true
---
# <a name="reference-information-about-the-email-screen-template-for-canvas-apps"></a>Referanseinformasjon om e-post-skjermen malen for lerretsapper

Forstå hvordan hver betydelige kontroll i malen e-post-skjermen, bidrar til skjermens overordnede standardfunksjonaliteten for lerret-apper i PowerApps. Dette dypdykket noe presenterer formler for virkemåte og verdiene i andre egenskaper som bestemmer hvordan kontrollene svare på inndata fra brukeren. Hvis en på høyt nivå gjennomgang av denne skjermen standard funksjonalitet, kan du se den [oversikt over e-post-skjermen](email-screen-overview.md).

Dette emnet uthever noen viktige kontroller og forklarer uttrykk eller formler til hvilke ulike egenskaper (slik som **elementer** og **OnSelect**) av disse kontrollene er angitt:

* [Tekstboks for søk](#text-search-box)
* [Legg til ikon](#add-icon)
* [Personer Bla gjennom-galleriet](#people-browse-gallery)
* [E-personer galleriet](#email-people-gallery) (+ underordnede kontroller)
* [Post-ikonet](#mail-icon)

## <a name="prerequisite"></a>Forutsetning

Kjennskap til hvordan du legger til og konfigurerer skjermbilder og andre kontroller som du [oppretter en app i PowerApps](../data-platform-create-app-scratch.md).

## <a name="text-search-box"></a>Boks for tekstsøk

   ![TextSearchBox kontroll](media/email-screen/email-search-box.png)

Flere andre kontroller i skjermen har en avhengighet på den **tekstsøk** kontroll:

* Hvis en bruker starter å skrive inn tekst, **PeopleBrowseGallery** vises.
* Hvis en bruker skriver ut en gyldig e-postadresse, **AddIcon** vises.
* Når en bruker velger en person i **PeopleBrowseGallery**, search innholdet tilbakestilles.

## <a name="add-icon"></a>Legg til-ikon

   ![AddIcon kontroll](media/email-screen/email-add-icon.png)

Den **Legg til ikonet** kontrollen kan brukere av appen å legge til personer som ikke finnes i deres organisasjon i mottakers listen over e-postmeldingen skrevet.

* Egenskap: **Synlig**<br>
    Verdi: Logikk for å vise kontrollen bare når en bruker skriver inn en gyldig e-postadresse i søkeboksen:

    ```powerapps-comma
    !IsBlank( TextSearchBox.Text ) &&
        IsMatch( TextSearchBox.Text; Match.Email ) &&
        Not( Trim( TextSearchBox.Text ) in MyPeople.UserPrincipalName )
    ```
  Linje for linje, den foregående kodeblokk sier at den **Legg til ikonet** kontroll, vises bare hvis:

    * **TextSearchBox** inneholder tekst.
    * Teksten i **TextSearchBox** er en gyldig e-postadresse.
    * Teksten i **TextSearchBox** ikke allerede finnes i den **MyPeople** samling.

* Egenskap: **OnSelect**<br>
    Verdi: Hvis du velger dette legger til gyldige e-postadressen til den **MyPeople** samling. Denne samlingen brukes av skjermen som listen over mottakere:

    ```powerapps-comma
    Collect( MyPeople;
        { 
            DisplayName: TextSearchBox.Text; 
            UserPrincipalName: TextSearchBox.Text; 
            Mail: TextSearchBox.Text
        }
    );;
    Reset( TextSearchBox )
    ```
  
  Denne kodeblokk legger til en rad i den **MyPeople** samling og fyller ut tre felt med teksten i **TextSearchBox**. Disse tre feltene er **DisplayName**, **UserPrincipalName**, og **e-post**. Deretter tilbakestiller innholdet i **TextSearchBox**.

## <a name="people-browse-gallery"></a>Personer Bla gjennom-galleriet

   ![PeopleBrowseGallery kontroll](media/email-screen/email-browse-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: Topp 15 resultatene av søketeksten ble skrevet inn i den **TextSearchBox** kontroll:
    
    ```powerapps-comma
    If( !IsBlank( Trim(TextSearchBox.Text ) ); 
        'Office365Users'.SearchUser( {searchTerm: Trim( TextSearchBox.Text ); top: 15} )
    )
    ```

  Elementene i dette galleriet fylles som søkeresultater fra den [Office365.SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) operasjonen. Operasjonen tar teksten `Trim(TextSearchBox)` som søket term og returnerer resultatene topp 15 som er basert på dette søket.
  
  **TextSearchBox** er pakket i en `Trim()` funksjonen fordi et bruker-Søk etter mellomrom er ugyldig. Den `Office365Users.SearchUser` operasjonen er pakket i en `If(!IsBlank(Trim(TextSearchBox.Text)) ... )` -funksjonen, som betyr at operasjonen er utført bare hvis søkeboksen inneholder brukerangitt tekst. Dette forbedrer ytelsen. 

### <a name="people-browse-gallery-title-control"></a>Personer Bla gjennom galleriet tittel kontroll

   ![PeopleBrowseGallery tittel kontroll](media/email-screen/email-browse-gall-title.png)

* Egenskap: **Tekst**<br>
    Verdi: `ThisItem.DisplayName`

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

   * Sett den **_selectedUser** variabel som skal det merkede elementet.
   * Tilbakestiller søketermen i **TextSearchBox**.
   * Legger til det valgte elementet til den **MyPeople** samling, en samling av alle de valgte brukerne som e postskjermen bruker som et sett med mottakere.

## <a name="email-people-gallery"></a>E-personer galleri

   ![EmailPeopleGallery kontroll](media/email-screen/email-people-gall.png)

* Egenskap: **Elementer**<br>
    Verdi: `MyPeople`

  Dette er samlingen av personer initialisert eller legges til ved å velge den **PeopleBrowseGallery tittel** kontroll.

* Egenskap: **Høyde**<br>
    Verdi: Logikk for å angi høyden, basert på hvor mange elementer for øyeblikket i galleriet:

    ```powerapps-comma
    Min( 
        ( EmailPeopleGallery.TemplateHeight + EmailPeopleGallery.TemplatePadding * 2) *
            RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2; 0 );
        304
    )
    ```

  Høyden på dette galleriet Justerer hvor mange elementer i galleriet, med en maksimal høyde for 304.
  
  Det tar `TemplateHeight + TemplatePadding * 2` som totalt høyden på en enkelt rad med **EmailPeopleGallery**, deretter multipliserer verdien med antall rader. Siden `WrapCount = 2`, antall rader som SANN er `RoundUp(CountRows(EmailPeopleGallery.AllItems) / 2; 0)`.

* Egenskap: **ShowScrollbar**<br>
    Verdi: `EmailPeopleGallery.Height >= 304`
  
  Når høyden på galleriet når 304, er rullefeltet synlig.

### <a name="email-people-gallery-title-control"></a>E-personer galleri tittel kontroll

   ![EmailPeopleGallery tittel kontroll](media/email-screen/email-people-gall-text.png)

* Egenskap: **OnSelect**<br>
    Verdi: `Set(_selectedUser; ThisItem)`

  Sett den **_selectedUser** variabel som skal det valgte elementet i **EmailPeopleGallery**.

### <a name="email-people-gallery-iconremove-control"></a>E-personer iconRemove gallerikontroll

   ![MonthDayGallery tittel kontroll](media/email-screen/email-people-gall-delete.png)

* Egenskap: **OnSelect**<br>
    Verdi: `Remove( MyPeople; LookUp( MyPeople; UserPrincipalName = ThisItem.UserPrincipalName ) )`

  Slår opp posten i den **MyPeople** samling, der **UserPrincipalName** samsvarer med den **UserPrincipalName** av det valgte elementet og fjerner som registrerer fra den samling.

## <a name="mail-icon"></a>Post-ikonet

* Egenskap: **OnSelect**<br>
    Verdi: Logikk for å sende brukerens e-postmeldingen:

    ```powerapps-comma
    Set( _emailRecipientString; Concat( MyPeople; Mail & ";" ) );;
    'Office365'.SendEmail( _emailRecipientString; 
        TextEmailSubject.Text;  
        TextEmailMessage.Text; 
        { Importance:"Normal" }
    );;
    Reset( TextEmailSubject );;
    Reset( TextEmailMessage );;
    Clear( MyPeople )
    ```

  Sende en e-postmelding krever en adskilt med semikolon streng med e-postadresser. I foregående kode:
  1. Den første kodelinjen tar den **e-post** feltet fra alle radene i den **MyPeople** samling, setter dem sammen til en enkelt streng med e-postadresser atskilt med semikolon, og angir den **_ emailRecipientString** variabelen til strengverdien.

  1. Den bruker deretter den [Office365.SendEmail](https://docs.microsoft.com/connectors/office365/#sendemail) operasjonen til å sende e-postmeldingen til mottakerne.
    Operasjonen har tre nødvendige parametere, **til**, **emne**, og **brødtekst**, og en valgfri parameter--**viktighet**. Disse er i foregående kode **_emailRecipientString**, **TextEmailSubject**. Tekst, **TextEmailMessage**. Tekst, og **Normal**, henholdsvis.
  1. Til slutt, tilbakestilles den **TextEmailSubject** og **TextEmailMessage** kontrollerer og fjerner den **MyPeople** samling.

* Egenskap: **DisplayMode**<br>
    Verdi: `If( Len( Trim( TextEmailSubject.Text ) ) > 0 && !IsEmpty( MyPeople ); DisplayMode.Edit; DisplayMode.Disabled )` Emnelinjen for e-post må ha for en e-post som skal sendes, tekst og mottakeren (**MyPeople**) samlingen kan ikke være tom.

## <a name="next-steps"></a>Neste trinn

* [Finn ut mer om denne skjermen](./email-screen-overview.md)
* [Finn ut mer om Office 365 Outlook connector i PowerApps](../connections/connection-office365-outlook.md)
* [Finn ut mer om Office 365-brukere-kobling i PowerApps](../connections/connection-office365-users.md)
