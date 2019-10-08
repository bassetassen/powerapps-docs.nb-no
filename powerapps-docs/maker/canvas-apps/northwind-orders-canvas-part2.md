---
title: Opprett et sammendrags skjema i et arbeidsom råde program | Microsoft Docs
description: Opprett et sammendrags skjema i en lerret-app for å administrere data for Gas tro nor delikat Esser
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/25/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d151249caebdb2a6f142943074a409bc626ff662
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995846"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-summary-form-in-a-canvas-app"></a>Opprett et sammendrags skjema i en lerret-app

Følg trinn vise instruksjoner for å opprette et sammendrags skjema i en lerret-app for å administrere fiktive data i databasen Gas tro nor delikat Esser. Dette emnet er en del av en serie som forklarer hvordan du bygger et forretnings program på relasjonelle data i Common Data Service. Du får best resultat ved å utforske disse emnene i denne rekkefølgen:

1. [Opprett et ordre Galleri](northwind-orders-canvas-part1.md).
2. Opprett et sammendrags skjema (**dette emnet**).
3. [Opprett et detalj Galleri](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> @no__t – 0Definition av skjerm områder @ no__t-1

## <a name="prerequisites"></a>Forutsetninger

1. [Installer databasen Gas tro nor delikat Esser](northwind-install.md).
1. Se gjennom [oversikten over lerretet](northwind-orders-canvas-overview.md) for Gas tro nor delikat Esser.
1. [Opprett ordens galleriet](northwind-orders-canvas-part1.md) selv, eller åpne **del nor ordrer (lerret) – Start deler 2-** appen, som allerede inneholder dette galleriet.

## <a name="add-a-title-bar"></a>Å legge til en tittellinje

Opprett en tittel linje øverst i appen, som vil inneholde handlings knapper ved slutten av dette emnet.

1. I **tre visning** -ruten velger du **Screen1** for å sikre at du ikke ved et uhell legger til en kontroll i rekkefølge galleriet:

    > [!div class="mx-imgBorder"]
    > ![Select Screen1 i tre visnings ruten @ no__t-1

1. Velg **etikett** på **Sett inn** -fanen for å sette inn en [**etikett**](controls/control-text-box.md) -kontroll:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Insert en etikett @ no__t-1

    Den nye etiketten skal bare vises én gang, over galleriet. Hvis det vises i hvert element i galleriet, sletter du den første forekomsten av etiketten, kontrollerer at skjermen er valgt (som foregående trinn beskriver), og deretter setter du inn etiketten på nytt.

1. Flytt og endre størrelsen på den nye etiketten for å dekke toppen av skjermen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Move og endre størrelsen på etiketten @ no__t-1

1. Dobbelt klikk på teksten til etiketten, og skriv deretter inn **Gastronor-ordrer**.

    Som et alternativ kan du endre **tekst** -egenskapen i formel linjen for å oppnå samme resultat:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Change teksten i tittel linjen @ no__t-1

1. Formater etiketten i **hjem** -fanen:
    - Øk skrift størrelsen til 24 punkt.
    - Gjør teksten fet.
    - Gjør teksten hvit.
    - Midt Still teksten.
    - Legg til et mørkt blått fyll i bakgrunnen.

    > [!div class="mx-imgBorder"]
    > Alternativer for @no__t – 0Formatting på hjem-fanen @ no__t-1

## <a name="add-an-edit-form-control"></a>Å legge til en redigerings skjema-kontroll

I denne delen kan du legge til kontroller for å vise et sammendrag av hvilken som helst rekkefølge brukeren velger i galleriet.

1. På **Sett inn** -fanen setter du inn en [**redigerings skjema**](controls/control-form-detail.md) -kontroll:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Add en redigerings skjema-kontroll @ no__t-1

    Som standard vises skjemaet i hjørnet øverst til venstre, der andre kontroller kan gjøre det vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Edit skjema kontroll i standard plassering @ no__t-1

1. Flytt og endre størrelsen på skjemaet for å dekke hjørnet øverst til høyre på skjermen under tittel linjen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Move og endre størrelsen på redigerings skjema-kontrollen @ no__t-1

1. Angi **DataSource** -egenskapen for skjemaet til denne verdien i formel linjen:

    ```powerapps-comma
    Orders
    ```

    > [!div class="mx-imgBorder"]
    > ![Set DataSource-egenskapen for redigerings skjema-kontrollen @ no__t-1

    Du kan angi den samme egenskapen i **Egenskaper** -fanen nær høyre kant, men denne tilnærmingen legger til felt som du ikke trenger i skjemaet. Hvis du bruker formel linjen, forblir skjemaet tomt.

## <a name="add-and-arrange-fields"></a>Legge til og ordne felt

1. Velg **Rediger felt** i **Egenskaper** -fanen nær høyre kant, og åpne **felt** -ruten:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Open felt-ruten @ no__t-1

1. Velg **Legg til felt**i **felt** -ruten, og merk deretter av for feltene **kunde** og **ansatt** .

    > [!div class="mx-imgBorder"]
    > @no__t – 0Add feltene for kunde og ansatt i redigerings skjema-kontrollen @ no__t-1

1. Rull ned til disse feltene vises, og Merk av i avmerkings boksene:

    - **Notater**
    - **Bestillings dato**
    - **Bestillings nummer**
    - **Bestillings status**
    - **Betalt dato**

    > [!div class="mx-imgBorder"]
    > @no__t – 0Add fem flere felt til redigerings skjema-kontrollen @ no__t-1

1. Nederst i **felt** -ruten velger du **Legg til**, og deretter lukker du **felt** -ruten.

    Skjemaet viser syv felt:

    > [!div class="mx-imgBorder"]
    > ![Edit skjema kontrollen viser syv felt @ no__t-1

    > [!NOTE]
    > Hvis et felt viser et rødt feil ikon, kan det ha oppstått et problem da data ble Hentet fra kilden. Hvis du vil løse feilen, kan du oppdatere dataene:
    >
    > 1. Velg **Datakilder** på **Vis**-fanen.
    > 1. Velg **data kilder**i **data** -ruten.
    > 1. Velg ellipsen (...) ved siden av **ordrer**, velg **Oppdater**, og lukk deretter **data** -ruten.
    >
    > Hvis kombinasjons boksen for kunden eller navnet på en ansatt fremdeles viser en feil, kan du kontrollere den **primære teksten** og **SearchField** i hver boks ved å merke den og deretter åpne **data** -ruten. For kunde-boksen må begge felt settes til **nwind_company**. For med arbeider-boksen må begge feltene settes til **nwind_lastname**.

1. Når skjemaet er valgt, endrer du antallet kolonner i skjemaet fra 3 til 12 i **Egenskaper** -fanen nær høyre kant.

    Dette trinnet gir fleksibilitet når du ordner feltene:

    > [!div class="mx-imgBorder"]
    > ![Change, antall kolonner i redigerings skjema-kontrollen @ no__t-1

    Mange grensesnitt utforminger er avhengige av 12 Kol onne oppsett fordi de kan ha plass til rader med 1, 2, 3, 4, 6 og 12 kontroller. I dette emnet skal du opprette rader som inneholder 1, 2 eller 4 kontroller.

1. Flytt og endre størrelse på feltene ved å dra i håndtakene, på samme måte som med andre kontroller, slik at hver rad inneholder disse data kortene i den angitte rekkefølgen:

    - Første rad: **Ordre nummer**, **ordre status**, **ordre dato**og **betalt dato**
    - Andre rad: **Kunde** og **ansatt**
    - Tredje rad: **Notater**

    > [!NOTE]
    > Det kan være enklere å utvide **notat**-, **kunde**-og **ansatt** data kortene før du ordner dem.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Move og endre størrelse på felt @ no__t-1

    Mer informasjon om hvordan du ordner felt i et skjema: [Forstå data skjema oppsett for lerret apper](working-with-form-layout.md).

## <a name="hide-time-controls"></a>Skjul tids kontroller

I dette eksemplet trenger du ikke klokkeslett delene av dato feltene, fordi dette nivået kan være distraherende for brukeren. Hvis du sletter dem, kan det hende at det oppstår problemer i formler som bruker disse kontrollene til å oppdatere dato verdier eller bestemme plasseringen til en annen kontroll i data kortet. I stedet skjuler du tids kontrollene ved å angi **Visible** -egenskapen.

1. Velg **bestillings dato** data kortet i **tre visnings** ruten.

    Kortet kan ha et annet navn, men det inneholder **ordre dato**.

1. Mens du holder nede SKIFT-tasten velger du kontrollene time, minutt og kolon-skille tegn i data kortet **for ordre dato** .

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select tids kontrollene i Order date Card @ no__t-1

1. Angi Controls **Visible** -egenskapen til **False**.

    Alle de valgte kontrollene forsvinner fra skjemaet:

    > [!div class="mx-imgBorder"]
    > ![Set synlig-egenskap til Usann. ](media/northwind-orders-canvas-part2/form-10.png)

1. Endre størrelsen på [**dato velger**](controls/control-date-picker.md) -kontrollen for å vise hele datoen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Resize dato velger-kontrollen @ no__t-1

    Deretter skal du gjenta de siste trinnene for feltet **betalt dato** .

1. I **tre visnings** ruten velger du tids kontrollene i data kortet **betalt dato** :

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select klokkeslett-kontroll i betalt dato kort @ no__t-1

1. Angi **Visible** -egenskapen for de valgte kontrollene til **Usann**:

    > [!div class="mx-imgBorder"]
    > ![Set synlig-egenskap til Usann. ](media/northwind-orders-canvas-part2/form-13.png)

1. Endre størrelsen på dato velgeren på kortet **betalt for dato** :

    > [!div class="mx-imgBorder"]
    > @no__t – 0Resize dato velger-kontrollen @ no__t-1

## <a name="connect-the-order-gallery"></a>Koble til ordre galleriet

1. I **tre visnings** ruten kan du skjule skjemaet for enklere å finne navnet på rekkefølge galleriet, og deretter kan du endre navn på det til **Gallery1**.

1. Angi **element** -egenskapen for sammendrags skjemaet til dette uttrykket:

    ```powerapps-comma
    Gallery1.Selected
    ```

    > [!div class="mx-imgBorder"]
    > ![Set for skjemaet @ no__t-1

    Skjemaet viser et sammendrag av hvilken ordre brukeren velger i listen.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select en ordre i listen for å vise oversikten i skjemaet @ no__t-1

## <a name="replace-a-data-card"></a>Bytt ut et data kort

**Ordre nummer** er en identifikator som Common data service tilordnes automatisk når du oppretter en post. Dette feltet har en [**tekst inn data**](controls/control-text-input.md) -kontroll som standard, men du erstatter den med en etikett slik at brukeren ikke kan redigere dette feltet.

1. Velg skjemaet, velg **Rediger felt** i **Egenskaper** -fanen nær høyre kant, og velg deretter feltet **ordre nummer** :

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select ordre nummer feltet @ no__t-1

1. Åpne **kontroll type** -listen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Open * * Control type * * *. liste @ no__t-1

1. Velg **visnings tekst** data kortet:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select * * visnings tekst * * data kort @ no__t-1

1. Lukk **felt** -ruten.

    Brukeren kan ikke lenger endre bestillings nummeret:

    > [!div class="mx-imgBorder"]
    > ![Order Number er skrivebeskyttet @ no__t-1

1. På **hjem** -fanen kan du endre skrift størrelsen for ordens tallet til 20 punkter, slik at feltet er enklere å finne:

    > [!div class="mx-imgBorder"]
    > ![Change for bestillings nummeret @ no__t-1

## <a name="use-a-many-to-one-relationship"></a>Bruk en mange-til-én-relasjon

**Orders** -enheten har en mange-til-én-relasjon med **ansatte** -enheten: hver ansatt kan opprette mange ordrer, men hver ordre kan bare tilordnes én ansatt. Når brukeren velger en ansatt i [**kombinasjons boks**](controls/control-combo-box.md) kontrollen, vil den **valgte** egenskapen gi den ansattes fullstendige post fra **ansatte** -enheten. Som et resultat av dette kan du konfigurere en [**bilde**](controls/control-image.md) -kontroll til å vise bildet av den ansatte brukeren velger i kombinasjons boksen.

1. Velg **ansatt** data kortet:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select data kortet for ansatte @ no__t-1

1. Lås opp data kortet i **Avansert** -fanen nær høyre kant, slik at du kan redigere formler som tidligere er skrivebeskyttet:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Unlock data kortet for ansatte @ no__t-1

1. Reduser bredden på kombinasjons boksen i data kortet for å få plass til bildet på den ansatte:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Resize kombinasjons boks kontrollen @ no__t-1

1. Velg **Media** > **bilde**på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Insert et bilde @ no__t-1

    Et bilde vises i data kortet, som utvides for å få plass til det:

    > [!div class="mx-imgBorder"]
    > 0Employee data kort med bilde kontroll @ no__t-1 @no__t

1. Endre størrelsen på bildet, og Flytt det til høyre for kombinasjons boksen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Move og endre størrelsen på bilde-kontrollen @ no__t-1

1. Angi **bilde** -egenskapen for bildet til denne formelen, og erstatt nummeret på slutten av DataCardValue om nødvendig:

    ```powerapps-comma
    DataCardValue7.Selected.Picture
    ```

    > [!div class="mx-imgBorder"]
    > ![Set image-egenskapen for bildet @ no__t-1

    Bildet av den valgte ansatte vises.

1. Mens du holder nede Alt-tasten velger du en annen ansatt i kombinasjons boksen for å bekrefte at bildet også endres.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Select en ansatt for å vise den ansattes bilde @ no__t-1

## <a name="add-a-save-icon"></a>Legg til et lagrings ikon

1. Velg **Screen1**i **tre visnings** ruten, og velg deretter **Sett inn** > -**ikoner** > **Sjekk**:

    > [!div class="mx-imgBorder"]
    > ![Insert for utsjekkings merke @ no__t-1

    [**Sjekk**](controls/control-shapes-icons.md) ikonet vises i øvre venstre hjørne som standard, der andre kontroller kan gjøre det vanskelig å finne ikonet:

    > [!div class="mx-imgBorder"]
    > ![Icon i standard plassering @ no__t-1

1. På **hjem** -fanen endrer du **farge** -egenskapen for ikonet til hvit, endrer størrelse på ikonet og flytter det nær høyre kant av tittel linjen:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Configure farge, størrelse og plassering for lagrings ikonet @ no__t-1

1. Kontroller at navnet på skjemaet er **Form1**i **tre visnings** ruten, og angi deretter **OnSelect** -egenskapen for ikonet til denne formelen:

    ```powerapps-comma
    SubmitForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set for OnSelect-egenskapen @ no__t-1

    Når brukeren velger ikonet, samler [**SubmitForm**](functions/function-form.md) -funksjonen alle endrede verdier i skjemaet og sender dem til data kilden. Punkter per time øverst på skjermen etter hvert som dataene sendes inn, og ordre galleriet gjenspeiler endringene etter at prosessen er fullført.

1. Angi **Display Mode** -egenskapen for ikonet til denne formelen:

    ```powerapps-comma
    If( Form1.Unsaved; DisplayMode.Edit; DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set ikonets Display Mode-egenskap @ no__t-1

    Hvis alle endringer i skjemaet er lagret, er ikonet deaktivert og vises i **DisabledColor**, som du angir neste.

1. Angi **DisabledColor** -egenskapen for ikonet til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Set ikonets DisabledColor-egenskap @ no__t-1

    Brukeren kan lagre endringer i en rekkefølge ved å velge avmerkings ikonet, som deretter er deaktivert og nedtonet til brukeren gjør en annen endring:

    > [!div class="mx-imgBorder"]
    > @no__t – 0saving endringer @ no__t-1

## <a name="add-a-cancel-icon"></a>Legg til et Avbryt-ikon

1. Velg **ikoner**@no__t – 2**Avbryt**på **Sett inn** -fanen:

    > [!div class="mx-imgBorder"]
    > ![Add Avbryt-ikon @ no__t-1

    Ikonet vises i hjørnet øverst til venstre som standard, der andre kontroller kan gjøre ikonet vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Cancel ikon i standard plassering @ no__t-1

1. Endre ikonets **farge** -egenskap til hvit i **hjem** -fanen, endre størrelsen på ikonet, og Flytt det til venstre for avmerkings ikonet:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Change farge, størrelse og plassering for Avbryt-ikonet @ no__t-1

1. Angi **OnSelect** -egenskapen for Avbryt-ikonet til denne formelen:

    ```powerapps-comma
    ResetForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set Avbryt-ikonets OnSelect-egenskap @ no__t-1

    [**Reset form**](functions/function-form.md) -funksjonen forkaster alle endringer i skjemaet, som returnerer den til sin opprinnelige tilstand.

1. Angi **Display Mode** -egenskapen for Avbryt-ikonet til denne formelen:

    ```powerapps-comma
    If( Form1.Unsaved Or Form1.Mode = FormMode.New; DisplayMode.Edit; DisplayMode.Disabled )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set Avbryt-ikonets Display Mode-egenskap @ no__t-1

    Denne formelen er litt forskjellig fra den som er merket for avmerkings ikonet. Avbryt-ikonet er deaktivert hvis alle endringene er lagret, eller skjemaet er i **ny** modus, som du aktiverer neste. I dette tilfellet, forkaster **reset form** den nye posten.

1. Angi **DisabledColor** -egenskapen for Avbryt-ikonet til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Set Avbryt-ikonets DisabledColor-egenskap @ no__t-1

    Brukeren kan avbryte endringer i en ordre, og kontroll-og avbrudds ikonene er deaktivert og nedtonet hvis alle endringene er lagret:

    > [!div class="mx-imgBorder"]
    > ![Saving og Annullerer endringer @ no__t-1

## <a name="add-an-add-icon"></a>Legg til et Legg til-ikon

1. På **Sett inn** -fanen velger du **ikoner** > **Legg til**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Insert et Legg til-ikon @ no__t-1

    **Legg til** -ikonet vises i øvre venstre hjørne som standard, der andre kontroller kan gjøre det vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Default plassering av Legg til-ikon @ no__t-1

1. Angi **farge** -egenskapen for Legg til-ikonet til hvit i **hjem** -fanen, endre størrelsen på ikonet, og Flytt det til venstre for Avbryt-ikonet:

    > [!div class="mx-imgBorder"]
    > ![Change farge, størrelse og plassering for Legg til-ikonet @ no__t-1

1. Angi **OnSelect** -egenskapen for Legg til-ikonet til denne formelen:

    ```powerapps-comma
    NewForm( Form1 )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set Add-ikonets OnSelect-egenskap @ no__t-1

    [**NewForm**](functions/function-form.md) -funksjonen viser en tom post i skjemaet.  

1. Angi **Display Mode** -egenskapen for Legg til-ikonet til denne formelen:

    ```powerapps-comma
    If( Form1.Unsaved Or Form1.Mode = FormMode.New; DisplayMode.Disabled; DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set Add-ikonets Display Mode-egenskap @ no__t-1

    Formelen deaktiverer Legg til-ikonet under disse betingelsene:

    - Brukeren gjør endringer, men lagrer eller avbryter dem ikke, noe som er den motsatte virke måten fra sjekk-og avbrudds ikonene.
    - Brukeren velger Legg til-ikonet, men gjør ingen endringer.

1. Angi **DisabledColor** -egenskapen for Legg til-ikonet til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Set Add-ikonets DisabledColor-egenskap @ no__t-1

    Brukeren kan opprette en ordre hvis de ikke gjør noen endringer, eller de lagrer eller avbryter eventuelle endringer som er gjort. (Hvis brukeren velger dette ikonet, kan de ikke velge det igjen før de gjør én eller flere endringer og deretter lagrer eller avbryter disse endringene):

    > [!div class="mx-imgBorder"]
    > @no__t – 0Create en ordre @ no__t-1

> [!NOTE]
> Hvis du oppretter og lagrer en ordre, kan det hende du må bla nedover i ordre galleriet for å vise den nye bestillingen. Den har ikke en total pris fordi du ikke har lagt til noen ordre detaljer ennå.

## <a name="add-a-trash-icon"></a>Legg til et papir kurv ikon

1. På **Sett inn** -fanen velger du **ikoner** > **papir kurv**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Insert et papir kurv ikon @ no__t-1

    **Papir kurv** ikonet vises i øvre venstre hjørne som standard, der andre kontroller kan gjøre det vanskelig å finne:

    > [!div class="mx-imgBorder"]
    > ![Default plassering av papir kurv ikonet @ no__t-1

1. På **hjem** -fanen kan du endre **farge** -egenskapen for papir kurven til hvit, endre størrelse på ikonet og flytte det til venstre for Legg til-ikonet:

    > [!div class="mx-imgBorder"]
    > @no__t – 0Change farge, størrelse og plassering for papir kurv ikonet @ no__t-1

1. Angi **OnSelect** -egenskapen for avfall-ikonet til denne formelen:

    ```powerapps-comma
    Remove( Orders; Gallery1.Selected )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set for OnSelect-egenskapen @ no__t-1

    [**Remove**](functions/function-remove-removeif.md) -funksjonen fjerner en post fra en data kilde. I denne formelen fjerner funksjonen posten som er valgt i ordre galleriet. Papir kurv ikonet vises nær sammendrags skjemaet (ikke i ordre galleriet) fordi skjemaet viser flere detaljer om posten, slik at brukeren enklere kan identifisere posten som formelen skal slette.

1. Angi **Display Mode** -egenskapen for avfall-ikonet til denne formelen:

    ```powerapps-comma
    If( Form1.Mode = FormMode.New; DisplayMode.Disabled; DisplayMode.Edit )
    ```

    > [!div class="mx-imgBorder"]
    > ![Set for Display Mode-egenskapen @ no__t-1

    Denne formelen deaktiverer papir kurv ikonet hvis brukeren oppretter en post. Før brukeren lagrer posten, har ikke **Remove** -funksjonen en post å slette.

1. Angi **DisabledColor** -egenskapen for avfall-ikonet til denne verdien:

    ```powerapps-comma
    Gray
    ```

    > [!div class="mx-imgBorder"]
    > ![Set for DisabledColor-egenskapen @ no__t-1

    Brukeren kan slette en ordre.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Deleting ordrer @ no__t-1

## <a name="summary"></a>Oversikt

Du har lagt til et skjema der brukeren kan vise og redigere et sammendrag av hver ordre i oppsummering, og du brukte disse elementene:

- Et skjema som viser data fra **Orders** -enheten: **Form1. DataSource =** `Orders`
- En tilkobling mellom skjemaet og ordre galleriet: **Form1. Item =** `Gallery1.Selected`
- En alternativ kontroll for feltet **for ordre nummer** : **Vis tekst**
- En mange-til-én-relasjon for å vise den ansattes bilde i data kortet for **ansatte** : `DataCardValue1.Selected.Picture`
- Et ikon for å lagre endringer i en rekkefølge: `SubmitForm( Form1 )`
- Et ikon for å avbryte endringer i en rekkefølge: `ResetForm( Form1 )`
- Et ikon for å opprette en ordre: `NewForm( Form1 )`
- Et ikon for å slette en ordre: `Remove( Orders; Gallery1.Selected )`

## <a name="next-step"></a>Neste trinn

I neste emne kan du legge til et annet galleri for å vise produktene i hver ordre, og du kan endre disse detaljene ved hjelp av [**patch**](functions/function-patch.md) -funksjonen.

> [!div class="nextstepaction"]
> [Opprett detalj galleriet](northwind-orders-canvas-part3.md)
