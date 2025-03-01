---
title: En oversikt over tilkoblinger til Office 365-brukere | Microsoft Docs
description: Slik kobler man til Office 365-brukere, går gjennom noen eksempler og ser alle funksjonene
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/07/2016
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: da6c30cc824f5bb6cf1f661d332831223c37d5b8
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993893"
---
# <a name="connect-to-office-365-users-connection-from-powerapps"></a>Å koble til Office 365-brukere fra PowerApps
![Office 365-brukere](./media/connection-office365-users/office365icon.png)

Med Office 365-brukere får du tilgang til brukerprofiler i organisasjonen som bruker Office 365-kontoen din. Du kan utføre en rekke handlinger som å hente profilen, en profil fra en annen bruker, lederen til en bruker eller direkte rapporter.

Du kan vise denne informasjonen i en etikett i appen. Du kan vise én funksjon, flere funksjoner, eller til og med kombinere forskjellige funksjoner. Du kan for eksempel opprette et uttrykk som kombinerer Brukernavn og Telefonnummer, og deretter vise denne informasjonen i appen.

Dette emnet viser deg hvordan du legger til Office 365-brukere som en tilkobling, som en datakilde i appen, og hvordan du bruker disse dataene i Galleri-kontrollen.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="add-a-connection"></a>Å legge til en tilkobling
1. [Legg til en datatilkobling](../add-data-connection.md), og velg **Office 365-brukere**:  

    ![Å koble til Office 365](./media/connection-office365-users/add-office.png)
2. Velg **Koble til**, og hvis du blir bedt om å logge på, angir du jobbkontoen din.

Tilkoblingen til Office 365-brukere er opprettet og lagt til i appen din. Den er nå klar til å brukes.

## <a name="use-the-connection-in-your-app"></a>Slik bruker man tilkoblingen i appen
### <a name="show-information-about-the-current-user"></a>Å vise informasjon om gjeldende bruker
1. Velg **Etikett** på menyen **Sett inn**
2. Du angir **[Tekst](../controls/properties-core.md)** -egenskapen i funksjonsfeltet til én av følgende formler:

   `Office365Users.MyProfile().City`  
   `Office365Users.MyProfile().CompanyName`  
   `Office365Users.MyProfile().Country`  
   `Office365Users.MyProfile().Department`  
   `Office365Users.MyProfile().DisplayName`  
   `Office365Users.MyProfile().GivenName`  
   `Office365Users.MyProfile().Id`  
   `Office365Users.MyProfile().JobTitle`  
   `Office365Users.MyProfile().Mail`  
   `Office365Users.MyProfile().MailNickname`  
   `Office365Users.MyProfile().mobilePhone`  
   `Office365Users.MyProfile().OfficeLocation`  
   `Office365Users.MyProfile().PostalCode`  
   `Office365Users.MyProfile().Surname`  
   `Office365Users.MyProfile().TelephoneNumber`  
   `Office365Users.MyProfile().UserPrincipalName`  
   `Office365Users.MyProfile().AccountEnabled`  
   `Office365Users.MyProfile().BusinessPhones`

Etiketten viser informasjonen du oppgav om den gjeldende brukeren.

### <a name="show-information-about-another-user"></a>Å vise informasjon om en annen bruker
1. Velg **Tekst** på **Sett inn**-menyen, og velg **Tekstinndata**. Endre navnet til **InfoAbout**:  

    ![Å gi en kontroll et nytt navn](./media/connection-office365-users/renameinfoabout.png)
2. Skriv eller lim inn en e-postadresse til en bruker i organisasjonen i **InfoAbout**. Skriv for eksempel inn *yourName*@*yourCompany.com*.
3. Legg til en **Etikett** (**Sett inn**-meny), og angi **[Tekst](../controls/properties-core.md)** -egenskapen til én av følgende formler:

   * Slik viser du informasjon om en annen bruker:  

     `Office365Users.UserProfile(InfoAbout.Text).City`  
     `Office365Users.UserProfile(InfoAbout.Text).CompanyName`  
     `Office365Users.UserProfile(InfoAbout.Text).Country`  
     `Office365Users.UserProfile(InfoAbout.Text).Department`  
     `Office365Users.UserProfile(InfoAbout.Text).DisplayName`  
     `Office365Users.UserProfile(InfoAbout.Text).GivenName`  
     `Office365Users.UserProfile(InfoAbout.Text).Id`  
     `Office365Users.UserProfile(InfoAbout.Text).JobTitle`  
     `Office365Users.UserProfile(InfoAbout.Text).Mail`  
     `Office365Users.UserProfile(InfoAbout.Text).MailNickname`  
     `Office365Users.UserProfile(InfoAbout.Text).mobilePhone`  
     `Office365Users.UserProfile(InfoAbout.Text).OfficeLocation`  
     `Office365Users.UserProfile(InfoAbout.Text).PostalCode`  
     `Office365Users.UserProfile(InfoAbout.Text).Surname`  
     `Office365Users.UserProfile(InfoAbout.Text).TelephoneNumber`  
     `Office365Users.UserProfile(InfoAbout.Text).UserPrincipalName`  
     `Office365Users.UserProfile(InfoAbout.Text).AccountEnabled`  
     `Office365Users.UserProfile(InfoAbout.Text).BusinessPhones`

   * Slik viser du informasjon om en leder til en annen bruker:  

     `Office365Users.Manager(InfoAbout.Text).City`  
     `Office365Users.Manager(InfoAbout.Text).CompanyName`  
     `Office365Users.Manager(InfoAbout.Text).Country`  
     `Office365Users.Manager(InfoAbout.Text).Department`  
     `Office365Users.Manager(InfoAbout.Text).DisplayName`  
     `Office365Users.Manager(InfoAbout.Text).GivenName`  
     `Office365Users.Manager(InfoAbout.Text).Id`  
     `Office365Users.Manager(InfoAbout.Text).JobTitle`  
     `Office365Users.Manager(InfoAbout.Text).Mail`  
     `Office365Users.Manager(InfoAbout.Text).MailNickname`  
     `Office365Users.Manager(InfoAbout.Text).mobilePhone`  
     `Office365Users.Manager(InfoAbout.Text).OfficeLocation`  
     `Office365Users.Manager(InfoAbout.Text).PostalCode`  
     `Office365Users.Manager(InfoAbout.Text).Surname`  
     `Office365Users.Manager(InfoAbout.Text).TelephoneNumber`  
     `Office365Users.Manager(InfoAbout.Text).UserPrincipalName`  
     `Office365Users.Manager(InfoAbout.Text).AccountEnabled`  
     `Office365Users.Manager(InfoAbout.Text).BusinessPhones`

Etiketten viser informasjonen du oppgav om brukeren som ble angitt, eller lederen til den brukeren.

> [!NOTE]
> Hvis du utvikler en app basert på en enhet i Common Data Service, kan du angi en bruker basert på ID i stedet for e-postadresse.

Du kan for eksempel [opprette en app automatisk](../data-platform-create-app.md), legge til en skjerm som inneholder en **Etikett**-kontroll, og angi kontrollens **Tekst**-egenskap til denne formelen:
<br>**Office365Users.UserProfile(BrowseGallery1.Selected.CreatedByUser).DisplayName**

Hvis du oppretter en kontakt og velger kontakten i bla gjennom-skjermen i appen, viser **Etikett**-kontrollen visningsnavnet ditt.

### <a name="show-the-direct-reports-of-another-user"></a>Å vise direkterapporter for en annen bruker
1. Legg til en **Tekstinndata**-kontroll (**Sett inn**-meny > **Tekst**), og endre navnet til **InfoAbout**.
2. Oppgi e-postadresse til en bruker i organisasjonen i **InfoAbout**. Du kan for eksempel oppgi *yourManagersName*@*yourCompany.com*
3. Legg til et **Med tekst**-galleri (**Sett inn**-meny > **Galleri**), og angi **[Elementer](../controls/properties-core.md)** -egenskapen til følgende formel:

    `Office365Users.DirectReports(InfoAbout.Text)`

    Galleriet viser informasjon om direkterapportene for brukeren du oppgav.

    Når galleriet er valgt, viser den høyre ruten alternativene for galleriet.
4. Velg **JobTitle** i den andre listen. Velg **DisplayName** i den tredje listen. Galleriet er oppdatert til å vise disse verdiene.  

> [!NOTE]
> Den første boksen er en bildekontroll. Hvis du ikke har et bilde, kan du slette bildekontrollen og legge til en etikett i stedet. [Å legge til og konfigurere kontroller](../add-configure-controls.md) er en god ressurs.

### <a name="search-for-users"></a>Å søke etter brukere
1. Legg til en **Tekstinndata**-kontroll (**Sett inn**-meny > **Tekst**), og endre navnet til **SearchTerm**. Oppgi et navn du vil søke etter. Angi for eksempel fornavnet ditt.
2. Legg til et **Med tekst**-galleri (**Sett inn**-meny > **Galleri**), og angi **[Elementer](../controls/properties-core.md)** -egenskapen til følgende formel:

    `Office365Users.SearchUser({searchTerm: SearchTerm.Text})`

    Galleriet viser brukere hvis navn inneholder søketeksten du oppgav.

    Når galleriet er valgt, viser den høyre ruten alternativene for galleriet.
3. Velg **E-post** i den andre listen. Velg **DisplayName** i den tredje listen.

    Den andre og tredje etiketten i galleriet oppdateres.

## <a name="view-the-available-functions"></a>Å vise de tilgjengelige funksjonene
Denne tilkoblingen har følgende funksjoner:

| Funksjonsnavn | Beskrivelse |
| --- | --- |
| [DirectReports](connection-office365-users.md#directreports) |Returnerer direkte rapportene for den angitte brukeren. |
| [Leder](connection-office365-users.md#manager) |Henter bruker profilen for lederen av den angitte brukeren. |
| [MyProfile](connection-office365-users.md#myprofile) |Henter profilen for gjeldende bruker. |
| [SearchUser](connection-office365-users.md#searchuser) |Henter søke resultater for bruker profiler. |
| [UserProfile](connection-office365-users.md#userprofile) |Henter en bestemt bruker profil. |

### <a name="myprofile"></a>MyProfile
Hent min profil: Henter profilen for gjeldende bruker.

#### <a name="input-properties"></a>Inndataegenskaper
Ingen.

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Type | Beskrivelse |
| --- | --- | --- |
| Nummer | streng |Brukerens post sted. |
| CompanyName | streng |Brukerens firma. |
| Land | streng |Brukerens land. |
| Avdeling |streng |Brukerens avdeling. |
| DisplayName |streng |Visningsnavnet til brukeren. |
| GivenName |streng |Fornavnet til brukeren. |
| ID |streng |Bruker-ID. |
| JobTitle |streng |Brukerens stilling. |
| Utsendelse |streng |E-post-ID-en til brukeren. |
| MailNickname |streng |Kallenavnet til brukeren. |
| mobilePhone | streng |Brukerens mobil telefon. |
| OfficeLocation | streng |Office-plassering for bruker.|
| Kontrollen | streng |Post nummeret til brukeren.|
| Etternavn |streng |Etternavnet til brukeren. |
| TelephoneNumber |streng |Telefonnummeret til brukeren. |
| UserPrincipalName |streng |Brukers hovednavn. |
| AccountEnabled |boolsk |Kontoaktivert flagg. |
| BusinessPhones | streng |Telefon numre til brukerens firma.|

### <a name="userprofile"></a>UserProfile
Hent bruker profil: Henter en bestemt bruker profil.

#### <a name="input-properties"></a>Inndataegenskaper

| navn | Datatype | Krevde | Beskrivelse |
| --- | --- | --- | --- |
| ID |streng |ja |Brukerhovednavn eller e-post-ID. |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Type | Beskrivelse |
| --- | --- | --- |
| Nummer | streng |Brukerens post sted. |
| CompanyName | streng |Brukerens firma. |
| Land | streng |Brukerens land. |
| Avdeling |streng |Brukerens avdeling. |
| DisplayName |streng |Visningsnavnet til brukeren. |
| GivenName |streng |Fornavnet til brukeren. |
| ID |streng |Bruker-ID. |
| JobTitle |streng |Brukerens stilling. |
| Utsendelse |streng |E-post-ID-en til brukeren. |
| MailNickname |streng |Kallenavnet til brukeren. |
| Etternavn |streng |Etternavnet til brukeren. |
| TelephoneNumber |streng |Telefonnummeret til brukeren. |
| UserPrincipalName |streng |Brukers hovednavn. |
| AccountEnabled |boolsk |Kontoaktivert flagg. |
| BusinessPhones | streng |Telefon numre til brukerens firma.|

### <a name="manager"></a>Leder
Hent overordnet: Henter bruker profilen for lederen av den angitte brukeren.

#### <a name="input-properties"></a>Inndataegenskaper

| navn | Datatype | Krevde | Beskrivelse |
| --- | --- | --- | --- |
| ID |streng |ja |Brukerhovednavn eller e-post-ID. |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Type | Beskrivelse |
| --- | --- | --- |
| Nummer | streng |Brukerens post sted. |
| CompanyName | streng |Brukerens firma. |
| Land | streng |Brukerens land. |
| Avdeling |streng |Brukerens avdeling. |
| DisplayName |streng |Visningsnavnet til brukeren. |
| GivenName |streng |Fornavnet til brukeren. |
| ID |streng |Bruker-ID. |
| JobTitle |streng |Brukerens stilling. |
| Utsendelse |streng |E-post-ID-en til brukeren. |
| MailNickname |streng |Kallenavnet til brukeren. |
| mobilePhone | streng |Brukerens mobil telefon. |
| OfficeLocation | streng |Office-plassering for bruker.|
| Kontrollen | streng |Post nummeret til brukeren.|
| Etternavn |streng |Etternavnet til brukeren. |
| TelephoneNumber |streng |Telefonnummeret til brukeren. |
| UserPrincipalName |streng |Brukers hovednavn. |
| AccountEnabled |boolsk |Kontoaktivert flagg. |
| BusinessPhones | streng |Telefon numre til brukerens firma.|

### <a name="directreports"></a>DirectReports
Hent direkte rapporter: Hent direkte rapporter.

#### <a name="input-properties"></a>Inndataegenskaper

| navn | Datatype | Krevde | Beskrivelse |
| --- | --- | --- | --- |
| ID |streng |ja |Brukerhovednavn eller e-post-ID. |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Type | Beskrivelse |
| --- | --- | --- |
| Nummer | streng |Brukerens post sted. |
| CompanyName | streng |Brukerens firma. |
| Land | streng |Brukerens land. |
| Avdeling |streng |Brukerens avdeling. |
| DisplayName |streng |Visningsnavnet til brukeren. |
| GivenName |streng |Fornavnet til brukeren. |
| ID |streng |Bruker-ID. |
| JobTitle |streng |Brukerens stilling. |
| Utsendelse |streng |E-post-ID-en til brukeren. |
| MailNickname |streng |Kallenavnet til brukeren. |
| mobilePhone | streng |Brukerens mobil telefon. |
| OfficeLocation | streng |Office-plassering for bruker.|
| Kontrollen | streng |Post nummeret til brukeren.|
| Etternavn |streng |Etternavnet til brukeren. |
| TelephoneNumber |streng |Telefonnummeret til brukeren. |
| UserPrincipalName |streng |Brukers hovednavn. |
| AccountEnabled |boolsk |Kontoaktivert flagg. |
| BusinessPhones | streng |Telefon numre til brukerens firma.|

### <a name="searchuser"></a>SearchUser
Søk etter brukere: Henter søke resultater for bruker profiler.

#### <a name="input-properties"></a>Inndataegenskaper

| navn | Datatype | Krevde | Beskrivelse |
| --- | --- | --- | --- |
| searchTerm |streng |nei |Søkestreng. Gjelder for: visnings navn, for navn, etter navnet, e-post, e-postkallenavn og brukerhovednavn. |

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Type | Beskrivelse |
| --- | --- | --- |
| Nummer | streng |Brukerens post sted. |
| CompanyName | streng |Brukerens firma. |
| Land | streng |Brukerens land. |
| Avdeling |streng |Brukerens avdeling. |
| DisplayName |streng |Visningsnavnet til brukeren. |
| GivenName |streng |Fornavnet til brukeren. |
| ID |streng |Bruker-ID. |
| JobTitle |streng |Brukerens stilling. |
| Utsendelse |streng |E-post-ID-en til brukeren. |
| MailNickname |streng |Kallenavnet til brukeren. |
| mobilePhone | streng |Brukerens mobil telefon. |
| OfficeLocation | streng |Office-plassering for bruker.|
| Kontrollen | streng |Post nummeret til brukeren.|
| Etternavn |streng |Etternavnet til brukeren. |
| TelephoneNumber |streng |Telefonnummeret til brukeren. |
| UserPrincipalName |streng |Brukers hovednavn. |
| AccountEnabled |boolsk |Kontoaktivert flagg. |
| BusinessPhones | streng |Telefon numre til brukerens firma.|

## <a name="helpful-links"></a>Nyttige koblinger
* Se alle [tilgjengelige tilkoblinger](../connections-list.md).
* Finn ut hvordan du [legger til tilkoblinger](../add-manage-connections.md) i appene dine.

