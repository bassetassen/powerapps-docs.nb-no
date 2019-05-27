---
title: Opprett en relasjon mellom SharePoint-lister via et oppslagsfelt i en lerretsapp | Microsoft Docs
description: Opprett en relasjon mellom SharePoint-lister i PowerApps via et oppslagsfelt i en lerretsapp.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/20/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8b7b718564ec62d9a7fa2ca78d52727831635c1c
ms.sourcegitcommit: dd74c98f48587730466e6669fc94da250d5c631e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 05/26/2019
ms.locfileid: "66224945"
---
# <a name="how-to-link-sharepoint-lists-using-a-lookup-field-in-powerapps"></a>Slik kobler du sammen SharePoint-lister ved hjelp av et oppslagsfelt i PowerApps

Denne opplæringen tar for seg hvordan du kan koble sammen to SharePoint-lister med et oppslagsfelt i en lerretsapp.

## <a name="overview"></a>Oversikt

SharePoint inneholder to typer oppslagsfelt:

* **Oppslag**: koblinger til en annen liste. Eksempelvis kan en *ordre*-liste kan ha et oppslagsfelt som er koblet til kunder i en *kunde*-liste
* **Valg**: å klikke eller trykke på feltet viser en liten meny med elementer du kan velge blant.

I denne opplæringen bygger du en app som bruker disse typene oppslagsfelt.

### <a name="why-use-a-lookup-field"></a>Fordeler ved å bruke et oppslagsfelt

Data i en virksomhet er store og komplekse. Data i en SharePoint-liste er ofte knyttet til data i en annen liste. Oppslagsfelt er den primære måten slike forretningsdata samles på.

Du kan for eksempel ha en **ordre**-liste som har et oppslagsfelt som er koblet til en **kunde**-liste for å vise hvilken kunde som la inn ordren. Med oppslagsfeltet i **ordre**-listen kan du også få andre data fra **kunde**-listen. Du kan også bruke et oppslagsfelt til å koble **ordre**-listen til en **produkt**-liste og hente frem informasjonen du trenger om produktet som er bestilt, for eksempel produktbilder, spesifikasjoner, produsentdetaljer og så videre.

### <a name="what-are-choice-fields-used-for"></a>Hva brukes Valg-felt til?
**Valg**-felt brukes for svært kort lister, men i stedet for faktisk å opprette en egen liste, tar du med listeverdiene i en liten meny som vises når du klikker eller trykker på **Valg**-feltet, og du velger én av verdiene.

Eksempler er koder for kundestatus, produkttilgjengelighet, statuskoder – i prinsippet alle fikserte lister som er relativt korte. Disse dataene kan faktisk implementeres som separate lister, og deretter bruker du **Oppslag**-feltet for å koble dem. Det er imidlertid vanligvis enklere og raskere å implementere dem som **Valg**-felt.

## <a name="create-the-lists-in-sharepoint"></a>Å opprette listene i SharePoint
I denne opplæringen kobler du sammen to egendefinerte SharePoint-lister, **Aktiva** og **RepairShop**. **Aktiva**-listen brukes til å spore maskinvareutstyr i en gruppe. Siden maskinvare blir ødelagt fra tid til annen, bruker vi **RepairShop**-listen for å spore lokale butikker som kan løse problemet.

### <a name="the-lookup-fields-used-in-this-example"></a>Oppslagsfeltet som er brukt i dette eksemplet
**RepairShop**-listen bruker *ContactEmail*-feltet for å identifisere butikken. Denne listen er definert først, slik at hver rad i **Aktiva**-listen har noe å peke til.

**Aktiva**-listen har to oppslagsfelt:

* ett kalt *RepairShop*, av typen **oppslag**, som bruker e-postadresser til å peke til oppføringer i **RepairShop**-listen;
* ett kalt *AssetType*, av typen **Valg**, som viser hvilke typer maskinvare dette aktivumet kan være.

Du skal mest sannsynlig definere flere felt, avhengig av informasjonen du trenger å spore.

### <a name="define-the-repairshop-list-and-add-data"></a>Å definere RepairShop-listen og legge til data
Du gjør dette først, slik at når du legger til data til **Aktiva**-listen, er **RepairShop**-oppføringer tilgjengelige for deg fra *Assets.RepairShop*-oppslagsfeltet, slik at du kan velge dem der.

1. På SharePoint-området kan du opprette en ny **RepairShop**-liste.

    ![](./media/sharepoint-lookup-fields/new-list.png)

2. Legg til et *ContactEmail*-felt av typen **Enkeltlinje med tekst**.

    ![](./media/sharepoint-lookup-fields/add-email-field.png)

3. Legg til eventuelle andre felt du trenger.

4. Klikk eller trykk på **+ Ny** for å skrive inn eksempeldata i listen, minst 3 rader med ulike *ContactEmail*-verdier. Når et aktivum må repareres, velger du én av disse.

    ![](./media/sharepoint-lookup-fields/add-repair-shops.png)

### <a name="define-the-assets-list"></a>Å definere aktiva-listen
1. På SharePoint-området kan du opprette en ny **Aktiva**-liste.

2. Klikk eller trykk på plusstegnet, og velg **Mer**.

    ![](./media/sharepoint-lookup-fields/choose-more-type.png)

3. Legg til et *AssetType*-felt av typen **Valg**, og fyll inn verdiene du vil skal vises i valg-menyen i tekstboksen **Skriv inn hvert valg på en egen linje**. Klikk eller trykk så på **OK**.

    ![](./media/sharepoint-lookup-fields/define-choice-column.png)

4. Start å legge til et annet felt, akkurat som i trinn 2: Klikk eller trykk på plusstegnet, og velg **Mer**.

5. Legg til et *RepairShop*-felt av typen **Oppslag**, velg **RepairShop** fra tekstboksen **Hent informasjon fra**, og velg *ContactEmail* fra tekstboksen **I denne kolonnen**. Klikk eller trykk så på **OK**.

    ![](./media/sharepoint-lookup-fields/setup-lookup-column.png)

6. Legg til flere felt du vil bruke.

## <a name="create-an-app-from-the-assets-list"></a>Opprett en app fra listen over aktiva
Du bruker denne appen til å legge til data i **Aktiva**-listen.

1. [Logg deg på PowerApps Studio](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Hvis du er ny med PowerApps, [kan du registrere deg gratis](https://powerapps.microsoft.com) ved hjelp av organisasjons-e-postadressen din.

2. Klikk eller trykk på **Ny** i **Fil**-menyen (langs venstre kant), og klikk eller trykk deretter på **SharePoint**.

    ![](./media/sharepoint-lookup-fields/create-app.png)

1. Velg SharePoint-området fra **Nylig brukte områder**-listen eller skriv inn områdets nettadresse direkte i tekstboksen. Klikk eller trykk på **GÅ TIL**.

    ![](./media/sharepoint-lookup-fields/choose-sharepoint-site.png)

1. Velg hovedlisten fra SharePoint-området, i dette eksemplet **Aktiva**. Klikk eller trykk på **Koble til**-knappen i nedre høyre hjørne.

    ![](./media/sharepoint-lookup-fields/choose-main-list.png)


## <a name="add-data-to-the-assets-list"></a>Å legge til data til Aktiva-listen
Du kan nå kjøre appen og se hvordan skjermbildet Vis detaljer ser ut for oppslagsfeltene.

1. Trykk på F5, eller velg Forhåndsvisning ( ![](./media/sharepoint-lookup-fields/preview.png) ).

2. Klikk eller trykk på **+**-symbolet øverst til høyre for å legge til en oppføring.

3. Angi en **tittel** for aktivumet.

4. Klikk eller trykk på rullegardinpilen **AssetType**. Verdiene som vises, er de du angav da du opprettet dette feltet. Velg én av oppføringene.

    ![](./media/sharepoint-lookup-fields/fill-asset-type-3.png)

5. Klikk eller trykk på rullegardinpilen **RepairShop**. Velg én av oppføringene.

    ![](./media/sharepoint-lookup-fields/fill-repair-shop-3.png)

6. Øverst til høyre klikker eller trykker du på merket for dette alternativet hvis du vil lagre den nye posten.

7. (valgfritt) Gjenta denne fremgangsmåten for å legge til så mange elementer i listen som du ønsker.

8. Trykk på ESC for å gå tilbake til standardarbeidsområdet.

## <a name="for-more-information"></a>For mer informasjon
* [Introduksjon av støtte for oppslag og en ny eksempelapp](https://powerapps.microsoft.com/blog/support-for-lookups/)
* [Ytelse, Oppdater-knappen, ForAll og flere feltoppslag](https://powerapps.microsoft.com/blog/performance-refresh-forall-multiple-field-lookups-531/)
* [Å generere en app ved hjelp av en Common Data Service-database](data-platform-create-app.md)
* [Å opprette en app fra grunnen av ved hjelp av en Common Data Service-database](data-platform-create-app-scratch.md)
