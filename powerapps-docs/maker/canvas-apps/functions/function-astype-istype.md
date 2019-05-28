---
title: Funksjonene AsType og IsType i lerretsapper | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempel for funksjonene AsType og IsType i lerretsapper
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 999653159f838e840f7f569aa9953633a6a70065
ms.sourcegitcommit: 93096dfa1aadba77159db1e5922f3d5528eecb7a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/21/2019
ms.locfileid: "65986323"
ms.PowerAppsDecimalTransform: true
---
# <a name="astype-and-istype-functions-in-canvas-apps"></a>Funksjonene AsType og IsType i lerretsapper

Kontrollerer en postreferanse for en bestemt enhet (**IsType**) og behandler referansen som en bestemt type (**AsType**).

## <a name="description"></a>Beskrivelse

Les [forstå posten referanser og polymorfisk oppslag](../working-with-references.md) for en innføring i bredere og mer informasjon.

Et oppslagsfelt refererer vanligvis til poster i en bestemt enhet. Siden enhetstypen er godt etablert, får du tilgang til feltene i oppslaget ved hjelp av en enkel prikk notasjon. For eksempel **første (kontoer). " Primary Contact'. ' Fullt navn '** går fra den **kontoer** enheten til den **hovedkontakt** posten i den **kontakter** enhets- og trekker ut den **fullt navn**  felt.

Common Data Service støtter også polymorfisk oppslagsfelt, som kan referere til poster fra et sett med enheter, som i disse eksemplene.

| Oppslagsfelt | Kan referere til |
|--------------|--------------|
| **Eier** | **Brukere** eller **grupper** |
| **Kunde** | **Kontoer** eller **kontakter** |
| **Angående** | **Kontoer**, **kontakter**, **kunnskapsartikler**og så videre. |

<!--note from editor: Change "Knowledge Articles" to "Knowledge Base articles" if that is what is being referenced.   -->

Lerretsapp formler, kan du bruke post referanser til å arbeide med polymorfisk oppslag. Fordi en postreferanse kan referere til ulike enheter, kan du ikke vet hvilke felt du vil være tilgjengelig når du skriver en formel. Den *. Feltet* notasjon er ikke tilgjengelig. Disse formlene må tilpasses til postene som appen oppstår når den kjøres.

Den **IsType** funksjonen tester om en postreferanse refererer til en bestemt enhet-type. Funksjonen returnerer en boolsk SANN eller USANN.

Den **AsType** funksjonen behandler en post referanse som en bestemt enhetstype, noen ganger kalt *"casting"*. Du kan bruke resultatet som om den var en post for enheten og, på nytt, bruker den *. Feltet* notasjon for å få tilgang til alle feltene i oppføringen. Det oppstår en feil hvis referansen er ikke av en bestemt type.

Bruk disse funksjonene sammen for å teste først enhetstypen for en post og behandle den som en oppføring av denne typen slik at feltene er tilgjengelige:

```powerapps-comma
If( IsType( First( Accounts ).Owner; Users );
    AsType( First( Accounts ).Owner; Users ).'Full Name';
    AsType( First( Accounts ).Owner; Teams ).'Team Name'
)
```

Du trenger disse funksjonene bare hvis du har tilgang til feltene i en postreferanse. Du kan for eksempel bruke posten referanser i den [ **Filter** ](function-filter-lookup.md) fungere uten **IsType** eller **AsType**:

```powerapps-comma
Filter( Accounts; Owner = First( Users ) )
```

På samme måte kan du bruke posten referanser med den [ **Patch** ](function-patch.md) funksjonen:

```powerapps-comma
Patch( Accounts; First( Accounts ); { Owner: First( Teams ) } )
```  

Hvis den brukes i en postkontekst som, slik som i en [ **galleriet** ](../controls/control-gallery.md) eller [ **redigeringsskjema** ](../controls/control-form-detail.md) kontroll, må du kanskje bruke den [global tvetydighetsoperatoren](operators.md#disambiguation-operator) å referere til enhetstypen. For eksempel denne formelen vil gjelde for et galleri som viser en liste med kontakter der **firmanavn** er en **kunden** oppslag:

```powerapps-comma
If( IsType( ThisItem.'Company Name'; [@Accounts] );
    AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
    AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
)
```

For begge funksjonene, kan du angi hvilken type gjennom navnet på datakilden som er koblet til enheten. For formelen som skal fungere, må du også legge til en datakilde i appen for alle typer som du vil teste eller endre. Du må for eksempel legge til den **brukere** enhet som en datakilde Hvis du vil bruke **IsType** og **AsType** med en **eieren** oppslag og poster fra denne enheten. Du kan legge til bare datakilder som du faktisk bruker i appen; Du trenger ikke å legge til alle enhetene som kan referere til et oppslag.

Hvis posten referansen er *tom*, **IsType** returnerer USANN, og **AsType** returnerer *tom*. Alle feltene i en *tom* post blir *tom*.

## <a name="syntax"></a>Syntaks

**AsType**( *RecordReference*; *EntityType* )

- *RecordReference* – obligatorisk. En postreferanse, ofte et oppslagsfelt som kan referere til en post i en av flere enheter.
- *EntityType* – obligatorisk. Den bestemte enheten for som skal testes.

**IsType**( *RecordReference*; *EntityType* )

- *RecordReference* – obligatorisk. En postreferanse, ofte et oppslagsfelt som kan referere til en post i en av flere enheter.
- *EntityType* – obligatorisk. Bestemte enheten som posten som skal brukes.

## <a name="example"></a>Eksempel

[Forstå posten referanser og polymorfisk oppslag](../working-with-references.md) inneholder omfattende eksempler.

1. Opprette et tomt lerret-app for nettbrett.

1. På den **Vis** fanen og velge **datakilder**, og legg deretter til den **kontakter** og **kontoer** enheter som datakilder.
    > [!div class="mx-imgBorder"]
    > ![Tom app med to datakilder: forretningsforbindelser og kontakter](media/function-astype-istype/contacts-add-datasources.png)

1. Sett inn en **galleriet** kontroll med en **tomt, loddrett** retning.

    > [!div class="mx-imgBorder"]
    > ![Sett inn en galleri-kontroll med et tomt loddrett oppsett](media/function-astype-istype/contacts-customer-gallery.png)

1. På den **Egenskaper** fanen nær høyre side av skjermen, angi galleriets **elementer** egenskapen til **kontakter**.

    > [!div class="mx-imgBorder"]
    > ![Sett av elementer til kontakter i Egenskaper-ruten](media/function-astype-istype/contacts-customer-datasource.png)

1. Angi galleriets oppsett **tittel og undertittel**.

    > [!div class="mx-imgBorder"]
    > ![Åpne velgeren for oppsett fra Egenskaper-ruten](media/function-astype-istype/contacts-customer-layout.png)

    > [!div class="mx-imgBorder"]
    > ![Angi oppsett til tittel og undertittel](media/function-astype-istype/contacts-customer-flyout.png)

1. I den **Data** ruten, åpne det **Title1** listen, og velg deretter **fullt navn**.

    > [!div class="mx-imgBorder"]
    > ![Verdi for tittel](media/function-astype-istype/contacts-customer-title.png)

1. Velg den **Subtitle1** etikettkontroll.

    > [!div class="mx-imgBorder"]
    > ![Verdi for undertittel](media/function-astype-istype/contacts-customer-subtitle.png)

1. Angi den **tekst** -egenskapen for **Subtitle1** til denne formelen:

    ```powerapps-comma
    If( IsBlank( ThisItem.'Company Name' ); "--";
        IsType( ThisItem.'Company Name'; [@Accounts] );
            "Account: " & AsType( ThisItem.'Company Name'; [@Accounts] ).'Account Name';
        "Contact: " & AsType( ThisItem.'Company Name'; [@Contacts] ).'Full Name'
    )
    ```

    > [!div class="mx-imgBorder"]
    > ![Skjermen er nå fullført som viser kontoer og kontakter intermixed i galleriet](media/function-astype-istype/contacts-customer-complete.png)

    Undertittelen i galleriet viser disse verdiene:
    - "--" Hvis den **'Firmanavn'** er *tom*.
    - «Konto: «og deretter den **kontonavn** feltet fra den **kontoer** enhet hvis den **firmanavn** feltet refererer til en konto.
    - «Kontakt: «og deretter den **fullt navn** feltet fra den **kontakter** enhet hvis den **firmanavn** feltet refererer til en kontakt.

    Resultatene kan være forskjellig fra de som finnes i dette emnet fordi den bruker eksempeldata som ble endret for å vise flere typer resultater.
