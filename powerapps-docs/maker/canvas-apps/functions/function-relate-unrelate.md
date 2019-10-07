---
title: Relater og ikke Relater funksjoner | Microsoft Docs
description: Referanse informasjon, inkludert syntaks og et eksempel, for funksjonene relate og unrelater i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/22/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d8ba0cef60b268caafb57e18ae80a522905ba45b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992754"
---
# <a name="relate-and-unrelate-functions-in-powerapps"></a>Relater og ikke Relater funksjoner i PowerApps

Relater og ikke Relater poster med to enheter gjennom en én-til-mange-eller mange-til-mange-relasjon.

## <a name="description"></a>Beskrivelse

**Relater** -funksjonen kobler to poster gjennom en én-til-mange-eller mange-til-mange-relasjon i Common data service. **Unrelater** -funksjonen reverserer prosessen og fjerner koblingen.

For én-til-mange-relasjoner har mange-enheten et sekundær nøkkel felt som peker til en post i den ene enheten. **Relater** angir at dette feltet skal peke til en bestemt post for den ene enheten, mens dette feltet **er** *tomt*. Hvis feltet allerede er angitt når **Relaten** kalles, går den eksisterende koblingen tapt til fordel for den nye koblingen. Du kan også angi dette feltet ved hjelp av [**patch**](function-patch.md) -funksjonen eller en **[redigerings skjema](../controls/control-form-detail.md)** -kontroll. du trenger ikke bruke **Relater** -funksjonen.

For mange-til-mange-relasjoner, opprettholder systemet som kobler sammen postene en skjult Sammenkoblings tabell. Du har ikke tilgang til denne Sammenkoblings tabellen direkte. den kan bare leses gjennom en én-til-mange-projeksjon og angis gjennom funksjonene **Relates** og **unrelater** . Verken relatert enhet har en sekundær nøkkel.

Dataene for enheten som du angir i det første argumentet, oppdateres for å gjenspeile endringen, men dataene for enheten som du angir i det andre argumentet, kan ikke endres. Dataene må oppdateres manuelt med **[oppdaterings](function-refresh.md)** funksjonen for å vise resultatet av operasjonen.

Disse funksjonene oppretter eller sletter aldri en post. De er bare relatert til eller opphever relaterte to poster som allerede finnes.

Du kan bare bruke disse funksjonene i [formler for virke måte](../working-with-formulas-in-depth.md).

> [!NOTE]
> Disse funksjonene er en del av en forhånds visnings funksjon, og virke måten er bare tilgjengelig når funksjonen **Relasjons data, alternativ sett og andre nye funksjoner for CDer** er aktivert. Dette er en innstilling på en app-nivå som er aktivert som standard for nye apper. Hvis du vil finne denne funksjons bryte ren, åpner du **fil** -menyen, velger **App-innstillinger**, og deretter velger du **Avanserte innstillinger**. Vi setter stor pris på dine tilbakemeldinger – fortell oss hva du synes i [forumet for PowerApps-fellesskapet](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

## <a name="syntax"></a>Syntaks

**Relater**( *Entity1RelatedTable*, *Entity2Record* )

* *Entity1RelatedTable* – obligatorisk. Hvis du vil ha en oversikt over *Entity1*, er tabellen med *Entity2* -poster relatert gjennom en én-til-mange-eller mange-til-mange-relasjon.
* *Entity2Record* – obligatorisk. *Entity2* -posten som skal legges til i relasjonen.

Ikke **Relater**( *Entity1RelatedTable*, *Entity2Record* )

* *Entity1RelatedTable* – obligatorisk. Hvis du vil ha en oversikt over *Entity1*, er tabellen med *Entity2* -poster relatert gjennom en én-til-mange-eller mange-til-mange-relasjon.
* *Entity2Record* – obligatorisk. *Entity2* -posten som skal fjernes fra relasjonen.

## <a name="examples"></a>Eksempler

Vurder en **produkt** enhet med følgende relasjoner som vist i [powerapps-portalen for enhets visning](../../common-data-service/create-edit-entities-portal.md):

| Visnings navn for relasjon | Relatert enhet | Relasjons type |
| --- | --- |
| Produkt reservasjon | Reservasjon | Én-til-mange |
| Produkt @no__t – 0 kontakt | Kontakt | Mange-til-mange |

**Produkter** og **reservasjoner** er knyttet til en én-til-mange-relasjon.  Hvis du vil relatere den første posten i **reservasjons** enheten med første post i **produkt** enheten:

`Relate( First( Products ).Reservations, First( Reservations ) )`

Slik fjerner du relasjonen mellom disse postene:

`Unrelate( First( Products ).Reservations, First( Reservations ) )`

Vi kunne ikke opprette eller fjerne en post, men bare relasjonen mellom postene ble endret.

**Produkter** og **kontakter** er relatert via en mange-til-mange-relasjon.  Hvis du vil relatere den første posten i **kontakter** -enheten med første post i **produkt** enheten:

`Relate( First( Products ).Contacts, First( Contacts ) )`

Ettersom mange-til-mange-relasjoner er symmetrisk, kan vi også ha gjort dette i motsatt retning:

`Relate( First( Contacts ).Products, First( Products ) )`

Slik fjerner du relasjonen mellom disse postene:

`Unrelate( First( Products ).Contacts, First( Contacts ) )`

eller

`Unrelate( First( Contacts ).Products, First( Products ) )`

Denne Fremgangs måten følger nøyaktig disse operasjonene på disse enhetene ved bruk av en app med **Galleri** -og **kombinasjons boks** kontroller for å velge de involverte oppføringene.

Disse eksemplene avhenger av eksempel dataene som installeres i miljøet ditt. [Opprett et prøve miljø, inkludert eksempel data](../../model-driven-apps/overview-model-driven-samples.md#get-sample-apps) , eller [Legg til eksempel data i et eksisterende miljø](../../model-driven-apps/overview-model-driven-samples.md#install-or-uninstall-sample-data).

### <a name="one-to-many"></a>Én-til-mange

#### <a name="relate-function"></a>**Relater** , funksjon

Du oppretter først en enkel app for å vise og tilordne reservasjonene som er knyttet til et produkt, på nytt.

1. Opprett en [tavle-app fra Tom](../data-platform-create-app-scratch.md).

1. Velg **Datakilder** på **Vis**-fanen.

1. I **data** -ruten velger du **Legg til data kilde** > **Common data service** > -**produkter** > **Koble til**.  

    Produkt enheten er en del av eksempel dataene som er lastet inn ovenfor.

     ![Legg til produkter-enheten som en data kilde](media/function-relate-unrelate/products-connect.png)

1. Legg til en tom, loddrett **[Galleri](../controls/control-gallery.md)** -kontroll i **Sett inn** -fanen.

1. Kontroller at kontrollen du nettopp la til, heter **Gallery1**, og flytt og endre størrelsen på den for å fylle venstre side av skjermen.

1. Angi **elementer** -egenskapen for **Gallery1**til **produkter** og tilhørende **Oppsett** til **bilde og tittel**på **Egenskaper** -fanen.

    ![Konfigurer ProductsGallery](media/function-relate-unrelate/products-gallery.png)

1. Kontroller at **etikett** -kontrollen heter **Title1**i **Gallery1**, og angi deretter **tekst** -egenskapen til **ThisItem.name**.

    ![Konfigurer etiketten i Gallery1](media/function-relate-unrelate/products-title.png)

1. Velg skjermen for å unngå å sette inn det neste elementet i **Gallery1**.  Legg til en ny tom, loddrett **Galleri** -kontroll, og kontroller at den heter **gallery2**.

    **Gallery2** vil vise reservasjonene for det produktet brukeren velger i **Gallery1**.

1. Flytt og endre størrelse på **gallery2** for å fylle den øvre høyre delen av skjermen.

1. valg fritt Legg til den blå **etikett** -kontrollen over **gallery2**, som den neste grafikken viser.

1. Angi **elementer** -egenskapen for **gallery2** til Gallery1 i formel linjen **. valgte. reserveringer**.

    ![Konfigurer gallery2-elementer](media/function-relate-unrelate/reservations-gallery.png)

1. Angi **gallery2**- **oppsettet** til **Tittel**i egenskaper-ruten.

    ![Konfigurer gallery2-oppsett](media/function-relate-unrelate/reservations-gallery-right.png)

1. Legg til en **[kombinasjons boks](../controls/control-combo-box.md)** -kontroll i **gallery2**, kontroller at den heter **ComboBox1**, og flytt og endre størrelsen på den for å unngå å blokkere de andre kontrollene i **gallery2**.

1. Angi **elementer** -egenskapen for **ComboBox1**til **produkter**på **Egenskaper** -fanen.

    ![Angi elementer-egenskap til produkter](media/function-relate-unrelate/reservations-combo-right.png)

1. Rull ned i **Egenskaper** -fanen, og angi **ComboBox1**-egenskapen **Tillat valg av flere elementer** **.**

    ![Angi Tillat sammensatt merket område](media/function-relate-unrelate/reservations-singleselect-right.png)

1. Angi **DefaultSelectedItems** -egenskapen for **ComboBox1**til ThisItem på formel linjen. **"produkt reservasjon"** .

    ![Angi DefaultSelectedItems for ReserveCombo](media/function-relate-unrelate/reservations-combo.png)

1. I **gallery2**angir du **NextArrow2**s **OnSelect** -egenskap til denne formelen:

    ```powerapps-dot
    Relate( ComboBox1.Selected.Reservations, ThisItem )
    ```

    Når brukeren velger dette ikonet, endres gjeldende reservasjon til produktet som brukeren valgte i **ComboBox1**.

    ![Konfigurer NextArrow2](media/function-relate-unrelate/reservations-relate.png)

1. Trykk på F5 for å teste appen i forhånds visnings modus.

Med denne appen kan brukeren flytte en reservasjon fra ett produkt til et annet. For en reservasjon på ett produkt kan brukeren velge et annet produkt i **ComboBox1** , og deretter velge **NextArrow2** for å endre reservasjonen.

![Demonstrere relatert-funksjonen i én-til-mange-app](media/function-relate-unrelate/reservations-reassign.gif)

#### <a name="unrelate-function"></a>**Avrelater** funksjon

På dette tidspunktet kan du flytte relasjonen fra én post til en annen, men du kan ikke fjerne relasjonen helt. Du kan bruke **unrelater** -funksjonen til å koble fra en reservasjons post fra et hvilket som helst produkt.

1. Velg **Datakilder** på **Vis**-fanen.

1. I **data** -ruten velger du **Legg til data kilde** > **Common Data Service**@no__t – 4**reservasjoner** > **Koble til**.

1. I **gallery2**kan du angi **OnSelect** -formelen for **NextArrow2** til denne formelen:

    ```powerapps-dot
    If( IsBlank( ComboBox1.Selected ),
        Unrelate( Gallery1.Selected.Reservations, ThisItem ),
        Relate( ComboBox1.Selected.Reservations, ThisItem )
    );
    Refresh( Reservations )
    ```
    ![Konfigurer høyre ikon](media/function-relate-unrelate/reservations-relate-unrelate.png)

1. Kopier **gallery2** til utklipp stav len ved å merke den og deretter trykke CTRL + C.

1. Lim inn et duplikat av **gallery2** på samme skjerm ved å trykke CTRL + V, og Flytt den deretter til den nedre høyre delen av skjermen.

1. valg fritt Hvis du har lagt til en etikett over **gallery2**, kan du gjenta de forrige to trinnene for etiketten.

1. Kontroller at duplikatet av **gallery2** heter **Gallery2_1**, og angi deretter **element** -egenskapen til denne formelen:

    ```powerapps-dot
    Filter( Reservations, IsBlank( 'Product Reservation' ) )
    ```

    Det vises en delegerings advarsel, men det er ikke noe med den lille data mengden i dette eksemplet.

    ![Angi elementer-egenskapen for Gallery2_1](media/function-relate-unrelate/reservations-lost.png)

Med disse endringene kan brukerne fjerne valget i **ComboBox1** for en kontakt hvis denne personen ikke har reservert et produkt. Kontakter som ikke har reservert et produkt, vises i **Gallery2_1** der brukere kan tilordne hver kontakt til et produkt.

   ![Demonstrere Relater og ikke Relater funksjoner i én-til-mange-app](media/function-relate-unrelate/reservations-lostandfound.gif)

### <a name="many-to-many"></a>Mange-til-mange

#### <a name="create-a-many-to-many-relationship"></a>Opprett en mange-til-mange-relasjon

Eksempel dataene inneholder ikke en mange-til-mange-relasjon, men du oppretter én mellom produktene heten og kontakt enheten. Brukere kan knytte hvert produkt til mer enn én kontakt og hver kontakt til mer enn ett produkt.

1. Fra [denne siden](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)velger du **data** i det venstre navigasjons feltet, og deretter velger du **enheter**.

    ![Åpne liste over enheter](media/function-relate-unrelate/entity-list.png)

1. Endre enhets filteret til å inkludere alle enheter.

    Som standard vises ikke eksempel enheter.

    ![Fjern enhets filter](media/function-relate-unrelate/entity-all.png)

1. Rull ned, åpne **produkt** entiteten og velg **relasjoner**.

    ![Relasjoner-fanen for produkt enheten](media/function-relate-unrelate/entity-relationships.png)

1. Velg **Legg til relasjon** > **mange-til-mange**.

    ![Legg til mange-til-mange-relasjoner](media/function-relate-unrelate/entity-manytomany.png)

1. Velg **kontakt** enhet for relasjonen.

    ![Velg kontakt enheten](media/function-relate-unrelate/entity-contact.png)

1. Velg **fullført** > **Lagre enhet**.

    ![Liste over relasjoner for produkt enheter](media/function-relate-unrelate/entity-done.png)

#### <a name="relate-and-unrelate-contacts-with-one-or-more-products"></a>Relater og ikke Relater kontakter til ett eller flere produkter

Du oppretter en annen app som ligner på den du opprettet tidligere i dette emnet, men den nye appen vil tilby en mange-til-mange-relasjon. Hver kontakt vil kunne reservere flere produkter i stedet for bare én.

1. Opprett **Gallery1** som den [første prosedyren](#one-to-many) i dette emnet beskriver, i en tom app for nett brett.

1. Legg til en ny tom, loddrett **Galleri** -kontroll, kontroller at den heter **gallery2**, og Flytt den til hjørnet øverst til høyre på skjermen.

    Senere i dette emnet vil du legge til en **kombinasjons boks** -kontroll under **gallery2**.

1. Angi **elementer** -egenskapen for **gallery2**til **Gallery1. selected. Contacts**i formel linjen.

    ![Konfigurer ContactsGallery](media/function-relate-unrelate/contacts-gallery.png)

1. På **Egenskaper** -fanen angir du **Oppsett** til **bilde og tittel**.

    ![Konfigurer ContactsGallery](media/function-relate-unrelate/contacts-gallery-right.png)

1. Kontroller at **etikett** -kontrollen heter **Title2**i **gallery2**, og angi deretter **tekst** -egenskapen til **ThisItem. fullstendig navn**.

    Ingen tekst vil vises i kontrollen før du er ferdig med denne prosedyren og tilordner en kontakt til et produkt.

    ![Vis kontakt navn](media/function-relate-unrelate/contacts-title.png)

1. Slett **NextArrow2**, sett inn et **Avbryt** -ikon, og kontroller at det har navnet **icon1**.

1. Angi **OnSelect** -egenskapen for **Avbryt** -ikonet til denne formelen: 

    ```powerapps-dot
    Unrelate( Gallery1.Selected.Contacts, ThisItem )
    ```

    ![Konfigurer Avbryt-ikon](media/function-relate-unrelate/contacts-unrelate.png)

1. Velg **Datakilder** på **Vis**-fanen.

1. I **data** -ruten velger du **Legg til data kilde** > **Common Data Service**@no__t – 4**kontakter** > **Koble til**.

1. Legg til en **kombinasjons boks** -kontroll under **gallery2**, kontroller at den heter **ComboBox1**, og angi deretter **element** -egenskapen til **kontakter**.

    ![Konfigurer element-egenskapen for kombinasjons boks](media/function-relate-unrelate/contacts-combo.png)

1. På **Egenskaper** - **fanen kan du**angi **Tillat sammensatt merket område** .

    ![Konfigurer egenskap for oppsett for kombinasjons boks](media/function-relate-unrelate/contacts-combo-right.png)

1. Sett inn et **Legg til** -ikon, og angi **OnSelect** -egenskapen til denne formelen: 

    ```powerapps-dot
    Relate( Gallery1.Selected.Contacts, ComboBox1.Selected )
    ```

    ![Konfigurer Legg til-ikon](media/function-relate-unrelate/contacts-relate.png)

Med denne appen kan brukere nå fritt relatere og ikke relatere et sett med kontakter til hvert produkt.

- Hvis du vil legge til en kontakt i et produkt, velger du kontakten i kombinasjons boksen nederst på skjermen, og deretter velger du **Legg til** -ikonet.
- Hvis du vil fjerne en kontakt fra et produkt, velger du **Avbryt** -ikonet for den kontakten.

    I motsetning til én-til-mange-relasjon, kan brukere knytte til den samme kontakten med flere produkter.

![Demonstrere Relater og ikke Relater funksjoner i mange-til-mange-apper](media/function-relate-unrelate/contacts-relate-unrelate.gif)

#### <a name="in-reverse-relate-and-unrelate-products-with-multiple-contacts"></a>Baklengs: Relater og å relatere produkter med flere kontakter

Mange-til-mange-relasjoner er symmetriske. Du kan utvide eksemplet for å legge til produkter i en kontakt, og deretter vende mellom de to skjerm bildene for å vise hvordan relasjonen vises fra hver retning.

1. Angi **OnVisible** -egenskapen for **Screen1** som skal **oppdateres (produkter)** .

    Når du oppdaterer en én-til-mange-eller mange-til-mange-relasjon, blir bare dataene i den første argument enheten for **relate** -eller **unrelater** -kallet oppdatert. Den andre må oppdateres manuelt Hvis du vil vende mellom skjermene i denne appen.

    ![Angi OnVisible-egenskapen til refresh-funksjonen](media/function-relate-unrelate/contacts-refresh.png)

1. Duplisert **Screen1**.

    Duplikatet får navnet **Screen1_1** og danner grunnlaget for å se på relasjonene fra kontakter-siden.

    ![Duplisere en skjerm](media/function-relate-unrelate/contacts-duplicate.png)

1. Hvis du vil opprette den omvendte visningen, endrer du disse formlene på kontrollene for **Screen1_1**:

    - Screen1_1. OnVisible = `Refresh( Contacts )`
    - Gallery1_1. Items = `Contacts`
    - Title1_1. text = `ThisItem.'Full Name'`
    - Label1_1. text = `"Selected Contact Products"`
    - Gallery2_1. Items = `Gallery1_1.Selected.Products`
    - Title2_1. text = `ThisItem.Name`
    - Icon1_1. OnSelect = `Unrelate( Gallery1_1.Selected.Products, ThisItem )`
    - ComboBox1_1. Items = `Products`
    - Icon2_1. OnSelect = `Relate( Gallery1_1.Selected.Products, ComboBox1_1.Selected )`

    Resultatet ser omtrent ut som det forrige skjerm bildet, men kommer til relasjonen fra **kontakter** -siden.

    ![Vis mange-til-mange-relasjoner som starter med kontakter](media/function-relate-unrelate/reverse-screen.png)

1. Sett inn et **pil ned** -ikon, og angi **OnSelect** -egenskapen til **Naviger (Screen1, ingen)** .  Gjør det samme på **Screen1** med formel **Naviger (Screen1_1, ingen)** .

    ![Legg til navigasjon mellom skjermer](media/function-relate-unrelate/reverse-navigate.png)

Med denne nye skjermen kan brukere legge til en kontakt i et produkt og deretter vende til en visning av kontakter og se det tilknyttede produktet. Relasjonene er symmetrisk og delt mellom de to skjerm bildene.

![Demonstrere mange-til-mange-relasjoner fra hver side](media/function-relate-unrelate/contacts-reverse.gif)
