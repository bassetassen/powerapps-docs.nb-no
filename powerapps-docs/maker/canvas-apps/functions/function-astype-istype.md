---
title: AsType-og IsType-funksjoner i lerret apper | Microsoft Docs
description: Referanse informasjon, inkludert syntaks, og et eksempel på funksjonene AsType og IsType i lerret-apper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0ecb30a5a452a6ee092ccf9bc9d47f6182ef60ab
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992991"
ms.PowerAppsDecimalTransform: true
---
# <a name="astype-and-istype-functions-in-canvas-apps"></a>AsType-og IsType-funksjoner i lerret apps

Kontrollerer en post referanse for en bestemt enhets type (**IsType**) og behandler referansen som en bestemt type (**AsType**).

## <a name="description"></a>Beskrivelse

Les [forståelse av post referanser og polymorfiske oppslag](../working-with-references.md) for å få mer informasjon.

Et oppslags felt refererer vanligvis til poster i en bestemt enhet. Ettersom enhets typen er godt opprettet, får du tilgang til feltene i oppslaget ved å bruke en enkel punktnotasjon. For eksempel for **navn (kontoer). ' Primær kontakt «.» Full navn-** ledere fra **kontoer** -enheten til den **primære kontakt** oppføringen i **kontakter** -enheten, og trekker ut det **fullstendige navne** feltet.

Common Data Service støtter også polymorfiske oppslags felt, som kan referere til poster fra et sett med enheter, som i disse eksemplene.

| Oppslags felt | Kan referere til |
|--------------|--------------|
| **Ren** | **Brukere** eller **team** |
| **Kunde** | **Forretnings forbindelser** eller **kontakt personer** |
| **Angående** | **Forretnings forbindelser**, **kontakter**, **kunnskaps artikler**og så videre. |

<!--note from editor: Change "Knowledge Articles" to "Knowledge Base articles" if that is what is being referenced.   -->

I et lerret kan du bruke post referanser til å arbeide med polymorfiske oppslag. Ettersom en post referanse kan referere til ulike enheter, vet du ikke hvilke felt som er tilgjengelige når du skriver en formel. *. NOTATION er* ikke tilgjengelig. Disse formlene må tilpasses postene som appen møter når de kjører.

**IsType** -funksjonen tester om en post referanse refererer til en bestemt enhets type. Funksjonen returnerer en boolsk sann eller USANN.

**AsType** -funksjonen behandler en post referanse som en bestemt enhets type, noen ganger kalt *endring*. Du kan bruke resultatet som om det var en post i enheten, og deretter bruke *. NOTATION for* å få tilgang til alle feltene i denne posten. Det oppstår en feil hvis referansen ikke er av den bestemte typen.

Bruk disse funksjonene sammen for å teste enhets typen for en post først, og behandle den deretter som en oppføring av denne typen, slik at feltene er tilgjengelige:

```powerapps-comma
If( IsType( First( Accounts ).Owner; Users );
    AsType( First( Accounts ).Owner; Users ).'Full Name';
    AsType( First( Accounts ).Owner; Teams ).'Team Name'
)
```

Du trenger bare disse funksjonene hvis du har tilgang til feltene i en post referanse. Du kan for eksempel bruke post referanser i [**filter**](function-filter-lookup.md) -funksjonen uten **IsType** eller **AsType**:

```powerapps-comma
Filter( Accounts; Owner = First( Users ) )
```

På samme måte kan du bruke post referanser med [**patch**](function-patch.md) -funksjonen:

```powerapps-comma
Patch( Accounts; First( Accounts ); { Owner: First( Teams ) } )
```  

Hvis det brukes i en post kontekst, for eksempel i et [**Galleri**](../controls/control-gallery.md) eller en [**redigerings skjema**](../controls/control-form-detail.md) -kontroll, må du kanskje bruke den [globale tvetydighets operatoren](operators.md#disambiguation-operator) til å referere til enhets typen. Denne formelen vil for eksempel være gyldig for et galleri som viser en liste over kontakter der **firma navn** er et **kunde** oppslag:

```powerapps-comma
If( IsType( ThisItem.'Company Name'; [@Accounts] );
    AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
    AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
)
```

For begge funksjoner angir du typen via navnet på data kilden som er koblet til enheten. Hvis formelen skal fungere, må du også legge til en data kilde i appen for alle typer du vil teste eller endre. Du må for eksempel legge til **brukerne** heten som en data kilde hvis du vil bruke **IsType** og **AsType** med et **eier** oppslag og poster fra denne enheten. Du kan bare legge til data kildene som du faktisk bruker i appen din. du trenger ikke å legge til alle enhetene som et oppslag kan referere til.

Hvis post referansen er *tom*, returnerer **IsType** USANN, og **AsType** returnerer *tom*. Alle felt i en *tom* post vil være *tomme*.

## <a name="syntax"></a>Syntaks

**AsType**( *RecordReference*; *EntityType* )

- *RecordReference* – obligatorisk. En post referanse, ofte et oppslags felt som kan referere til en post i en av flere enheter.
- *EntityType* – obligatorisk. Den bestemte enheten som skal testes.

**IsType**( *RecordReference*; *EntityType* )

- *RecordReference* – obligatorisk. En post referanse, ofte et oppslags felt som kan referere til en post i en av flere enheter.
- *EntityType* – obligatorisk. Den spesifikke enheten som posten skal brukes på.

## <a name="example"></a>Eksempel

[Forståelse av post referanser og polymorfiske oppslag](../working-with-references.md) inneholder omfattende eksempler.

1. Opprett et tomt lerret-program for nett brett.

1. Velg **data kilder**på **Vis** -fanen, og legg deretter til **kontaktene** og **konto** enhetene som data kilder.
    > [!div class="mx-imgBorder"]
    > ![Blank appen med to data kilder: kontoer og kontakter @ no__t-1

1. Sett inn en **Galleri** -kontroll med en **tom vertikal** retning.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Insert en Galleri kontroll med et tomt loddrett oppsett @ no__t-1

1. Angi **elementer** -egenskapen for galleriet til **kontakter**i **Egenskaper** -fanen nær høyre side av skjermen.

    > [!div class="mx-imgBorder"]
    > ![Set elementer til kontakter i egenskaper-ruten @ no__t-1

1. Angi oppsettet for galleriet til **Tittel og under tittel**.

    > [!div class="mx-imgBorder"]
    > @no__t – 0Open oppsett velgeren fra egenskaper-ruten @ no__t-1

    > [!div class="mx-imgBorder"]
    > ![Set oppsett til tittel og under tittel @ no__t-1

1. Åpne **Title1** -listen i **data** -ruten, og velg deretter **fullstendig navn**.

    > [!div class="mx-imgBorder"]
    > tittel verdi for ![Set @ no__t-1

1. Velg etikett-kontrollen for **Subtitle1** .

    > [!div class="mx-imgBorder"]
    > ![Set under tittel verdi @ no__t-1

1. Angi **tekst** -egenskapen for **Subtitle1** til denne formelen:

    ```powerapps-comma
    If( IsBlank( ThisItem.'Company Name' ); "--";
        IsType( ThisItem.'Company Name'; [@Accounts] );
            "Account: " & AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
        "Contact: " & AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Screen er nå ferdig med å vise kontoer og kontakter i Galleri @ no__t-1

    Under tittelen i galleriet vises disse verdiene:
    - «--» Hvis **firma navnet** er *tomt*.
    - «Konto:» og deretter **konto navn** -feltet fra **kontoer** -enheten Hvis **Firmanavn** -feltet refererer til en konto.
    - «Kontakt:» og deretter **fullt navn** -feltet fra **kontakter** -enheten Hvis **Firmanavn** -feltet viser til en kontakt.

    Resultatene kan være annerledes enn i dette emnet fordi det bruker eksempel data som ble endret til å vise flere typer resultater.
