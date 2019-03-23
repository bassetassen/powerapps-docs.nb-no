---
title: Relatert og Unrelate functions | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempel for funksjonene relatere og Unrelate i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/22/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4b2c6b9518e987ef17f2ff2b50987568c8a0b69f
ms.sourcegitcommit: 5b2b70c3fc7bcba5647d505a79276bbaad31c610
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356774"
---
# <a name="relate-and-unrelate-functions-in-powerapps"></a>Relatert og Unrelate i PowerApps

Relatert og unrelate postene i to enheter via en én-til-mange eller mange-til-mange-relasjon.

## <a name="description"></a>Beskrivelse

Den **relatere** funksjonen forbinder to poster via en én-til-mange eller mange-til-mange-relasjon i Common Data Service. Den **Unrelate** funksjonen reverserer prosessen og fjerner koblingen.

For én-til-mange-relasjoner, har mange enheten har et felt for sekundærnøkkel som peker til en post i én enhet. **Relatert** angir dette feltet til å peke til en bestemt post for én enhet, mens **Unrelate** gir dette feltet *tom*. Hvis feltet allerede er angitt når **relatere** er kalt, den eksisterende koblingen går tapt til fordel for den nye koblingen. Du kan også angi dette feltet ved hjelp av den [ **Patch** ](function-patch.md) funksjon eller en **[redigeringsskjema](../controls/control-form-detail.md)** kontroll; du må ikke bruke den **relatere**  funksjonen.

For mange-til-mange-relasjoner opprettholder systemet som er koblet postene en skjult join-tabell. Du får ikke tilgang til denne tabellen sammenføyning direkte. den kan lese bare gjennom en én-til-mange-projeksjon og angis via den **relatere** og **Unrelate** funksjoner. Ingen relaterte enheten har en sekundærnøkkel.

Dataene for enheten som du angir i det første argumentet oppdateres for å gjenspeile endringen, men vil ikke dataene for enheten som du angir i det andre argumentet. Må dataene være manuelt oppdatert med den **[Oppdater](function-refresh.md)** funksjonen for å vise resultatet av operasjonen.

Disse funksjonene aldri opprette eller slette en post. De bare relatere eller unrelate to poster som allerede finnes.

Du kan bruke disse funksjonene bare i [formler for virkemåte](../working-with-formulas-in-depth.md).

> [!NOTE]
> Disse funksjonene er en del av en funksjon i testversjon, og virkemåten er bare tilgjengelig når den **relasjonsdata, alternativsett og andre nye funksjoner for CDS** funksjonen er aktivert. Dette er en innstilling for app-nivå som er aktivert som standard for nye apper. Du finner denne funksjonsbryteren, kan du åpne den **filen** menyen velger **appinnstillinger**, og velg deretter **avanserte innstillinger**. Vi setter stor pris på dine tilbakemeldinger – fortell oss hva du synes i [forumet for PowerApps-fellesskapet](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

## <a name="syntax"></a>Syntaks

**Relatert**( *Entity1RelatedTable*, *Entity2Record* )

* *Entity1RelatedTable* – obligatorisk. For en post i *Entity1*, tabellen med *Entity2* poster som er relatert via en én-til-mange eller mange-til-mange-relasjon.
* *Entity2Record* – obligatorisk. Den *Entity2* post for å legge til i relasjonen.

**Unrelate**( *Entity1RelatedTable*, *Entity2Record* )

* *Entity1RelatedTable* – obligatorisk. For en post i *Entity1*, tabellen med *Entity2* poster som er relatert via en én-til-mange eller mange-til-mange-relasjon.
* *Entity2Record* – obligatorisk. Den *Entity2* post som skal fjernes fra relasjonen.

## <a name="examples"></a>Eksempler

Vurder en **produkter** enhet med følgende relasjonene som vist i den [PowerApps-portalen enhet viewer](../../common-data-service/create-edit-entities-portal.md):

| Visningsnavn for relasjon | Relatert enhet | Relasjonstype |
| --- | --- |
| Produkt-reservasjon | Reservasjon | Én-til-mange |
| Produktet &harr; kontakt | Kontakt | Mange-til-mange |

**Produkter** og **reservasjoner** er relatert via en én-til-mange relasjon.  Til å relatere den første posten i den **reservasjoner** enhet med den første posten i den **produkter** enhet:

`Relate( First( Products ).Reservations, First( Reservations ) )`

Fjerne relasjonen mellom disse oppføringene:

`Unrelate( First( Products ).Reservations, First( Reservations ) )`

Aldri vi opprettet, eller fjern eller en post, bare relasjonen mellom poster ble endret.

**Produkter** og **kontakter** er relatert via en mange-til-mange relasjon.  Til å relatere den første posten i den **kontakter** enhet med den første posten i den **produkter** enhet:

`Relate( First( Products ).Contacts, First( Contacts ) )`

Som mange-til-mange-relasjoner er symmetrisk, vi kan også har gjort dette i motsatt retning:

`Relate( First( Contacts ).Products, First( Products ) )`

Fjerne relasjonen mellom disse oppføringene:

`Unrelate( First( Products ).Contacts, First( Contacts ) )`

eller:

`Unrelate( First( Contacts ).Products, First( Products ) )`

Gå gjennom de følger samsvarer nøyaktig disse operasjonene på disse enhetene ved hjelp av en app med **galleriet** og **kombinasjonsboks** kontroller for å velge poster som er involvert.

Disse eksemplene, avhenger av eksempeldataene som installeres i miljøet ditt. Enten [opprette et prøveversjonsmiljø inkludert eksempeldata](../../model-driven-apps/overview-model-driven-samples.md#get-sample-apps) eller [legge til eksempeldata til en eksisterende miljø](../../model-driven-apps/overview-model-driven-samples.md#install-or-uninstall-sample-data).

### <a name="one-to-many"></a>Én-til-mange

#### <a name="relate-function"></a>**Relatert** funksjonen

Først oppretter du en enkel app for å vise og tilordne reservasjoner som er knyttet til et produkt.

1. Opprett en [nettbrettapp fra tom](../data-platform-create-app-scratch.md).

1. På den **Vis** fanen og velge **datakilder**.

1. I den **Data** ruten velger **Legg til datakilde** > **Common Data Service-** > **produkter**  >  **Koble**.  

    Produkter enheten er en del av data i eksemplet ovenfor er lastet inn.

     ![Legg til produkter som en datakilde](media/function-relate-unrelate/products-connect.png)

1. På den **Sett inn** fanen, Legg til en tom loddrett **[galleriet](../controls/control-gallery.md)** kontroll.

1. Sikre at kontrollen du nettopp la til heter **Gallery1**, og deretter flytte og endre størrelsen på den for å fylle til venstre på skjermen.

1. På den **Egenskaper** fanen, angir **Gallery1**'s **elementer** egenskapen til **produkter** og **oppsett** til **Bilde og tittel**.

    ![Konfigurer ProductsGallery](media/function-relate-unrelate/products-gallery.png)

1. I **Gallery1**, forsikre deg om at den **etikett** kontrollen heter **Title1**, og deretter angi dens **tekst** egenskapen til  **ThisItem.Name**.

    ![Konfigurere etiketten i Gallery1](media/function-relate-unrelate/products-title.png)

1. Velg skjermen for å unngå å sette inn det neste elementet i **Gallery1**.  Legg til en andre tom loddrett **galleriet** kontroll, og sikre at den heter **Gallery2**.

    **Gallery2** viser reservasjonene for uansett hvilket produkt som brukeren velger i **Gallery1**.

1. Flytte og endre størrelse på **Gallery2** til å fylle øverst til høyre på skjermen.

1. (valgfritt) Legg til blå **etikett** kontroll over **Gallery2**, som viser neste grafikken.

1. I formellinjen, kan du angi den **elementer** -egenskapen for **Gallery2** til **Gallery1.Selected.Reservations**.

    ![Konfigurer Gallery2 elementer](media/function-relate-unrelate/reservations-gallery.png)

1. I Egenskaper-ruten kan du angi **Gallery2**'s **oppsett** til **tittel**.

    ![Konfigurer Gallery2 oppsett](media/function-relate-unrelate/reservations-gallery-right.png)

1. I **Gallery2**, legge til en **[kombinasjonsboks](../controls/control-combo-box.md)** kontroll, må du kontrollere at den heter **ComboBox1**, og deretter flytte og endre størrelsen på den for å unngå blokkerer den andre kontroller i **Gallery2**.

1. På den **Egenskaper** fanen, angir **ComboBox1**'s **elementer** egenskapen til **produkter**.

    ![Angi elementer-egenskapen til produkter](media/function-relate-unrelate/reservations-combo-right.png)

1. Rull nedover i den **Egenskaper** fanen og angi **ComboBox1**'s **Tillat flere valg** egenskapen til **av**.

    ![Sett Tillat flere valg til av.](media/function-relate-unrelate/reservations-singleselect-right.png)

1. I formellinjen, kan du angi **ComboBox1**'s **DefaultSelectedItems** egenskapen til **ThisItem. 'Produktet reservasjon'**.

    ![Set DefaultSelectedItems for ReserveCombo](media/function-relate-unrelate/reservations-combo.png)

1. I **Gallery2**, kan du angi **NextArrow2**'s **OnSelect** egenskapen til denne formelen:

    ```powerapps-dot
    Relate( ComboBox1.Selected.Reservations, ThisItem )
    ```

    Når brukeren velger dette ikonet, gjeldende reservasjonen endres til produktet som brukeren har valgt i **ComboBox1**.

    ![Konfigurer NextArrow2](media/function-relate-unrelate/reservations-relate.png)

1. Trykk F5 for å teste appen i forhåndsvisningsmodus.

Med denne appen, kan brukeren flytte en reservasjon fra ett produkt til en annen. For en reservasjon på ett produkt, kan brukeren velge et annet produkt i **ComboBox1** og velg deretter **NextArrow2** til å endre denne reservering.

![Demonstrere relatere-funksjonen i én-til-mange-app](media/function-relate-unrelate/reservations-reassign.gif)

#### <a name="unrelate-function"></a>**Unrelate** funksjonen

Nå kan du flytte relasjonen fra én post til en annen, men du kan ikke fjerne relasjonen helt. Du kan bruke den **Unrelate** funksjonen til å koble en reservering-post fra et produkt.

1. På den **Vis** fanen og velge **datakilder**.

1. I den **Data** ruten velger **Legg til datakilde** > **Common Data Service-** > **reservasjoner**  >  **Koble**.

1. I **Gallery2**, kan du angi den **OnSelect** formel for **NextArrow2** til denne formelen:

    ```powerapps-dot
    If( IsBlank( ComboBox1.Selected ),
        Unrelate( Gallery1.Selected.Reservations, ThisItem ),
        Relate( ComboBox1.Selected.Reservations, ThisItem )
    );
    Refresh( Reservations )
    ```
    ![Konfigurer høyre-ikon](media/function-relate-unrelate/reservations-relate-unrelate.png)

1. Kopier **Gallery2** til utklippstavlen ved å merke den og deretter trykke Ctrl-C.

1. Lim inn et duplikat av **Gallery2** til det samme skjermbildet ved å trykke på Ctrl + V for, og deretter flytte den til nederst til høyre på skjermen.

1. (valgfritt) Hvis du har lagt til en etikett som er over **Gallery2**, Gjenta de forrige to trinnene for denne etiketten.

1. Forsikre deg om at duplikat av **Gallery2** heter **Gallery2_1**, og deretter angi dens **elementer** egenskapen til denne formelen:

    ```powerapps-dot
    Filter( Reservations, IsBlank( 'Product Reservation' ) )
    ```

    En delegeringsadvarsel vises, men det vil ikke noe å si med små mengden data i dette eksemplet.

    ![Angi Items-egenskapen for Gallery2_1](media/function-relate-unrelate/reservations-lost.png)

Med disse endringene, kan brukere oppheve merkingen i **ComboBox1** for en kontakt hvis vedkommende ikke har reservert et produkt. Kontakter som ikke har reservert et produkt vises i **Gallery2_1** der brukere kan tilordne hver kontakt til et produkt.

   ![Demonstrerer relatere og Unrelate funksjoner i én-til-mange-app](media/function-relate-unrelate/reservations-lostandfound.gif)

### <a name="many-to-many"></a>Mange-til-mange

#### <a name="create-a-many-to-many-relationship"></a>Opprette en mange-til-mange-relasjon

Eksempeldataene inkluderer ikke en mange-til-mange-relasjon, men du vil opprette en mellom produkter-enhet og kontakter-enheten. Brukere kan relateres hvert produkt til mer enn én kontakt og hver kontakt til mer enn ett produkt.

1. Fra [denne siden](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), og velg **Data** i navigasjonsruten til venstre, og velg deretter **enheter**.

    ![Åpne listen over enheter](media/function-relate-unrelate/entity-list.png)

1. Endre enhet for å inkludere alle enheter.

    Eksempel på enhetene vises ikke som standard.

    ![Fjern filter for enhet](media/function-relate-unrelate/entity-all.png)

1. Rull ned, åpne det **produktet** enhet, og velg **relasjoner**.

    ![Relasjoner-kategorien for selve produktenheten](media/function-relate-unrelate/entity-relationships.png)

1. Velg **Legg til relasjon** > **mange-til-mange**.

    ![Legg til mange-til-mange-relasjon](media/function-relate-unrelate/entity-manytomany.png)

1. Velg den **kontakt** enhet for relasjonen.

    ![Velg kontaktenheten](media/function-relate-unrelate/entity-contact.png)

1. Velg **ferdig** > **lagre enhet**.

    ![Liste over relasjoner for produkter-enhet](media/function-relate-unrelate/entity-done.png)

#### <a name="relate-and-unrelate-contacts-with-one-or-more-products"></a>Relatert og unrelate kontakter med ett eller flere produkter

Oppretter du en annen app som ligner på det du opprettet tidligere i dette emnet, men den nye appen vil tilby en mange-til-mange-relasjon. Hver kontakt vil kunne reservere flere produkter i stedet for bare én.

1. I en tom app for nettbrett, kan du opprette **Gallery1** som den [første prosedyren](#one-to-many) i dette emnet beskriver.

1. Legg til et annet tomt loddrett **galleriet** kontroll, må du kontrollere at den heter **Gallery2**, og deretter flytte den til øverst i høyre hjørne på skjermen.

    Senere i dette emnet, skal du legge til en **kombinasjonsboks** kontroll **Gallery2**.

1. I formellinjen, kan du angi **Gallery2**'s **elementer** egenskapen til **Gallery1.Selected.Contacts**.

    ![Konfigurer ContactsGallery](media/function-relate-unrelate/contacts-gallery.png)

1. På den **Egenskaper** fanen, angir **oppsett** til **bilde og tittel**.

    ![Konfigurer ContactsGallery](media/function-relate-unrelate/contacts-gallery-right.png)

1. I **Gallery2**, forsikre deg om at den **etikett** kontrollen heter **Tittel2**, og deretter angi dens **tekst** egenskapen til  **ThisItem. 'Fullt navn'**.

    Ingen teksten vises i kontrollen før du er ferdig med denne prosedyren, og tilordne en kontakt til et produkt.

    ![Vis kontaktnavn](media/function-relate-unrelate/contacts-title.png)

1. Slett **NextArrow2**, sette inn en **Avbryt** ikonet, og sikre at den heter **icon1**.

1. Angi den **Avbryt** ikonets **OnSelect** egenskapen til denne formelen: 

    ```powerapps-dot
    Unrelate( Gallery1.Selected.Contacts, ThisItem )
    ```

    ![Konfigurer Avbryt-ikon](media/function-relate-unrelate/contacts-unrelate.png)

1. På den **Vis** fanen og velge **datakilder**.

1. I den **Data** ruten velger **Legg til datakilde** > **Common Data Service-** > **kontakter**  >  **Koble**.

1. Under **Gallery2**, legge til en **kombinasjonsboks** kontroll, må du kontrollere at den heter **ComboBox1**, og deretter angi dens **elementer** egenskapen til **Kontakter**.

    ![Konfigurer kombinasjonsboks for Items-egenskapen](media/function-relate-unrelate/contacts-combo.png)

1. På den **Egenskaper** fanen, angir **Tillat flere valg** til **av**.

    ![Konfigurer kombinasjonsboksen oppsett egenskapen](media/function-relate-unrelate/contacts-combo-right.png)

1. Sett inn en **Legg til** -ikonet, og angi dens **OnSelect** egenskapen til denne formelen: 

    ```powerapps-dot
    Relate( Gallery1.Selected.Contacts, ComboBox1.Selected )
    ```

    ![Konfigurer Add-ikon](media/function-relate-unrelate/contacts-relate.png)

Med denne appen kan brukere nå fritt relatere og unrelate et sett med kontakter til hvert produkt.

- Hvis du vil legge til en kontakt i et produkt, velger kontakten i kombinasjonsboksen nederst på skjermen, og velg deretter den **Legg til** ikonet.
- Hvis du vil fjerne en kontakt fra et produkt, velg den **Avbryt** ikonet for kontakten.

    I motsetning til én-til-mange, en mange-til-mange-relasjon, tillater brukere å knytte samme kontakt med flere produkter.

![Demonstrerer relatere og Unrelate funksjoner i mange-til-mange-app](media/function-relate-unrelate/contacts-relate-unrelate.gif)

#### <a name="in-reverse-relate-and-unrelate-products-with-multiple-contacts"></a>I omvendt rekkefølge: relatere og unrelate produkter med flere kontakter

Mange-til-mange-relasjoner er symmetrisk. Du kan utvide eksemplet for å legge til produkter til en kontakt og deretter vender mellom de to skjermbildene for å vise hvordan relasjonen vises fra begge retninger.

1. Angi den **OnVisible** -egenskapen for **Screen1** til **Oppdater (produkter)**.

    Når du oppdaterer en én-til-mange eller mange-til-mange-relasjon, bare dataene i den første argumentet enheten på den **relatere** eller **Unrelate** kall oppdateres. Andre må oppdateres manuelt hvis du vil skal vendes mellom skjermene av denne appen.

    ![Angi OnVisible-egenskapen til Forny-funksjonen](media/function-relate-unrelate/contacts-refresh.png)

1. Duplisert **Screen1**.

    Dupliserte skal navngis **Screen1_1** og danner grunnlaget for å se på relasjonene fra kontakter-siden.

    ![Duplisere en skjerm](media/function-relate-unrelate/contacts-duplicate.png)

1. Hvis du vil opprette snudd visningen, kan du endre disse formlene på kontrollene til **Screen1_1**:

    - Screen1_1.OnVisible = `Refresh( Contacts )`
    - Gallery1_1.items = `Contacts`
    - Title1_1.Text = `ThisItem.'Full Name'`
    - Label1_1.Text = `"Selected Contact Products"`
    - Gallery2_1.items = `Gallery1_1.Selected.Products`
    - Title2_1.Text = `ThisItem.Name`
    - Icon1_1.OnSelect = `Unrelate( Gallery1_1.Selected.Products, ThisItem )`
    - ComboBox1_1.Items = `Products`
    - Icon2_1.OnSelect = `Relate( Gallery1_1.Selected.Products, ComboBox1_1.Selected )`

    Resultatet vil se omtrent på forrige skjermbilde, men kommer på relasjonen fra den **kontakter** side.

    ![Vis mange-til-mange-relasjon fra og med kontakter](media/function-relate-unrelate/reverse-screen.png)

1. Sett inn en **piler ovenfra og ned** ikon og sett den **OnSelect** egenskapen til **Navigate (Screen1, None)**.  Gjør samme på **Screen1** med formelen **Navigate (Screen1_1, None)**.

    ![Legge til navigasjon mellom skjermer](media/function-relate-unrelate/reverse-navigate.png)

Med denne nye skjermen kan kan brukere legge til en kontakt i et produkt og deretter Bla til en visning av kontakter og se det tilknyttede produktet. Relasjonene er symmetrisk og delt mellom de to skjermbildene.

![Vise mange-til-mange-relasjon fra hver side](media/function-relate-unrelate/contacts-reverse.gif)
