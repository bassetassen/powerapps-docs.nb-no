---
title: Slik fungerer lerretsappskjemaer | Microsoft Docs
description: Legg til et skjema i en lerretsapp i PowerApps, slik at du kan samle inn og vise informasjon fra en datakilde.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/27/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 661f6710c8cec55868ccc9d67d0f83dd230f89c1
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42851741"
---
# <a name="understand-canvas-app-forms-in-microsoft-powerapps"></a>Slik fungerer lerretsappskjemaer i Microsoft PowerApps

Legg til tre typer kontroller i en lerretsapp, slik at brukeren kan bla gjennom etter en post, vise detaljer om denne posten og redigere eller opprette en post:

| Aktivitet | Kontroll | Beskrivelse |
| --- | --- | --- |
| **Å bla gjennom etter en post** |**[Galleri](controls/control-gallery.md)**-kontroll |Filtrer, sorter, søk og bla gjennom postene i en datakilde, og velg en bestemt post. Vis bare noen få felt fra hver post for å vise flere poster om gangen, selv på en liten skjerm. |
| **Å vise detaljene for en post** |**[Visningsskjema](controls/control-form-detail.md)**-kontroll |For en enkelt post, kan du vise mange av, eller alle felt i posten. |
| **Å redigere eller opprette en post** |**[Redigeringsskjema](controls/control-form-detail.md)**-kontroll |Oppdater ett eller flere felt i en enkelt post (eller opprett en post som starter med standardverdier), og lagre disse endringene tilbake til den underliggende datakilden. |

Sett hver kontroll på ulike skjermer for å gjøre dem enklere å skille fra hverandre:

![Bla gjennom, vise og redigere poster på tvers av tre skjermer](./media/working-with-forms/three-screens.png)

Som dette emnet beskriver, kan du kombinere disse kontrollene med formler for å lage den generelle brukeropplevelsen.

## <a name="prerequisites"></a>Forutsetninger

* [Registrer deg](../signup-for-powerapps.md) for PowerApps, og deretter [logger du deg på](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ved å angi samme legitimasjon som du brukte til å registrere deg.
* Finn ut hvordan du [konfigurerer en kontroll](add-configure-controls.md) i PowerApps.

## <a name="explore-a-generated-app"></a>Å utforske en generert app
PowerApps kan automatisk generere en app, basert på en datakilde angir. Hver app inneholder tre skjermer med kontrollene som er beskrevet tidligere, og formler som knytter dem sammen. Kjør disse ferdiglagde appene, tilpass dem til dine bestemte mål eller undersøk hvordan de fungerer, slik at du kan lære om nyttige konsepter som gjelder for dine egne apper. Undersøk skjermene, kontrollene og formlene som kjører en generert app i avsnittene nedenfor.  

### <a name="browse-screen"></a>Bla gjennom-skjerm
![Skjermkontroller for Bla gjennom](./media/working-with-forms/afd-browse-screen-basic.png)

Denne skjermen har følgende viktige formler:

| Kontroll | Støttet virkemåte | Formel |
| --- | --- | --- |
| **BrowseGallery1** |Vis poster fra **Aktiva**-datakilden. |**[Element](controls/properties-core.md)**-egenskapen i galleriet er angitt til en formel som er basert på **Aktiva**-datakilden. |
| **ImageNewItem1** |Vis **Rediger og opprett**-skjermen med hvert felt angitt til en standardverdi, slik at brukeren enkelt kan opprette en post. |Angi **[OnSelect](controls/properties-core.md)**-egenskapen til bildet til denne formelen:<br> **NewForm( EditForm1 );<br>Navigate( EditScreen1, None )** |
| **NextArrow1** (i galleriet) |Vis **Detaljer**-skjermen for å vise mange av, eller alle feltene i den valgte posten. |Angi **[OnSelect](controls/properties-core.md)**-egenskapen for pilen til denne formelen:<br>**Navigate( DetailScreen1, None )** |

Hovedkontrollen i denne skjermen, **BrowseGallery1**, dekker det meste av skjermområdet. Brukeren kan bla gjennom galleriet for å finne en bestemt post for å vise flere felt eller oppdatere dem.

Angi **[Items](controls/properties-core.md)**-egenskapen for et galleri til å vise poster fra en datakilde i den. Angi for eksempel egenskapen til **Aktiva** til å vise poster fra en datakilde med dette navnet.

> [!NOTE]
> I en generert app er **[Element](controls/properties-core.md)** angitt til en betydelig mer komplisert formel som standard, slik at brukeren kan sortere og søke etter poster. Senere i dette emnet finner du ut hvordan du utvikler formelen; det er for øyeblikket nok med en enklere versjon.

Brukeren kan opprette en post ved å velge +-tegnet over galleriet, i stedet for å finne enn post som skal vises eller redigeres. Opprett denne effekten ved å legge til en **[Bilde](controls/control-image.md)**-kontroll som viser et +-symbol i den, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:
<br>**NewForm( EditForm1 ); Navigate( EditScreen1, None )**

Denne formelen åpner **Rediger og opprett**-skjermen, som har en  **kontroll for [Redigeringsskjema](controls/control-form-detail.md)**, med tittelen **EditForm1**. Formelen bytter også skjemaet til **Ny**-modus, der skjemaet viser standardverdiene fra datakilden, slik at brukeren enkelt kan opprette en post fra grunnen av.

For å undersøke en kontroll som vises i **BrowseGallery1**, velger du kontrollen i den første delen av galleriet, som fungerer som en mal for alle andre deler. Velg for eksempel den midtre **[Etikett](controls/control-text-box.md)**-kontrollen på venstre side:

![Skjermkontroller for Bla gjennom](./media/working-with-forms/afd-browse-gallery-controls.png)

I dette eksemplet er kontrollens **[Tekst](controls/properties-core.md)**-egenskap angitt til **ThisItem.AssignedTo**, som er et felt i **Aktiva**-datakilden. **[Tekst](controls/properties-core.md)**-egenskapen for de andre tre **[Etikett](controls/control-text-box.md)**-kontrollene i galleriet er angitt til lignende formler, og hver kontroll viser ulike felt i datakilden.  

Velg **[Figur](controls/control-shapes-icons.md)**-kontrollen (pilen), og bekreft at **[OnSelect](controls/properties-core.md)**- egenskapen er angitt til denne formelen:
<br>**Navigate( DetailScreen1, None )**

Hvis brukeren finner en post i **BrowseGallery1**, kan han velge pilen for denne posten for å vise mer informasjon om den i **DetailScreen1**. Ved å velge en pil, endrer brukeren verdien for den **Selected**-egenskapen for **BrowseGallery1**. I denne appen bestemmer denne egenskapen hvilken post som vises, ikke bare i **DetailScreen1**, men også i **Rediger og opprett**-skjermen hvis brukeren bestemmer seg for å oppdatere posten.

### <a name="detail-screen"></a>Detaljskjerm
![Detaljskjermkontroller](./media/working-with-forms/afd-detail-screen-basic.png)

Denne skjermen har følgende viktige formler:

| Kontroll | Støttet virkemåte | Formel |
| --- | --- | --- |
| **DetailForm1** |Visning av en post i **Aktiva**-datakilden |Angi **[DataSource](controls/control-form-detail.md)**-egenskapen til **Aktiva**. |
| **DetailForm1** |Bestemmer hvilke poster som skal vises. I en generert app vises posten som brukeren har valgt i galleriet. |Angi **[Item](controls/control-form-detail.md)**-egenskapen til kontrollen til denne verdien:<br>**BrowseGallery1.Selected** |
| **[Kort](controls/control-card.md)**-kontroller |I en **[Visningsskjema](controls/control-form-detail.md)**-kontroll, vises ett enkelt felt i en post. |Angi **[DataField](controls/control-card.md)**-egenskapen til navnet på et felt, omsluttet av doble anførselstegn (for eksempel **"Name"**). |
| **ImageBackArrow1** |**BrowseScreen1** åpnes, når brukeren velger denne kontrollen. |Angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br>**Tilbake()** |
| **ImageDelete1** |Når brukeren velger denne kontrollen, slettes en post. |Angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br>**Remove( Assets, BrowseGallery1.Selected )** |
| **ImageEdit1** |Når brukeren velger denne kontrollen, åpnes **Rediger og opprett**-skjermen i gjeldende post. |Angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br>**Navigate( EditScreen1, None )** |

Øverst på skjermen er tre bilder plassert utenfor **DetailForm1** og fungerer som knapper. De bytter mellom de tre skjermene i appen.

**DetailForm1** dominerer denne skjermen og viser posten som brukeren har valgt i galleriet (fordi skjemaets **[Element](controls/control-form-detail.md)**-egenskap er angitt til  **BrowseGallery1.Selected**). **[DataSource](controls/control-form-detail.md)**-egenskapen for skjemaet gir også metadata om datakilden, for eksempel et brukervennlig visningsnavn for hvert felt.

**DetailForm1** inneholder en rekke **[Kort](controls/control-card.md)**-kontroller. Du kan velge enten selve **[Kort](controls/control-card.md)**-kontrollen, eller kontrollen den inneholder for å få mer informasjon.

![Detaljkort og kort-kontroller som er valgt i redigeringsopplevelsen](./media/working-with-forms/afd-detail-card-controls.png)

**[DataField](controls/control-card.md)**-egenskapen for en **[Kort](controls/control-card.md)**-kontroll bestemmer hvilke felt kortet viser. I dette tilfellet er den egenskapen angitt til **AssetID**. Kortet inneholder en **[Etikett](controls/control-text-box.md)**-kontroll, der **[Tekst](controls/properties-core.md)**-egenskapen er angitt til **Parent.Default**. Denne kontrollen viser **Standard**-verdien for kortet, som er angitt via **[DataField](controls/control-card.md)**-egenskapen.

**[Kort](controls/control-card.md)**-kontrollene låses som standard i en generert app. Når et kort er låst, er det enkelte egenskaper du ikke kan endre på, for eksempel **[DataField](controls/control-card.md)**, og formellinjen er ikke tilgjengelig for disse egenskapene. Denne begrensningen bidrar til å sikre at tilpasningene ikke bryter med den grunnleggende funksjonaliteten i den genererte appen. Du kan imidlertid endre noen egenskaper for et kort og de tilhørende kontrollene i ruten til høyre:

![Detaljskjermen med alternativer-ruten åpen](./media/working-with-forms/detail-screen-new.png)

Du kan velge hvilke felt som skal vises, i den høyre ruten, og i hvilken type kontroll hvert felt vises.

### <a name="editcreate-screen"></a>Rediger/Opprett-skjerm
![Kontroller for Rediger-skjerm](./media/working-with-forms/afd-edit-screen-basic.png)

Denne skjermen har følgende viktige formler:

| Kontroll | Støttet virkemåte | Formel |
| --- | --- | --- |
| **EditForm1** |Viser en post i **Aktiva**-datakilden. |Angi **[DataSource](controls/control-form-detail.md)**-egenskapen til **Aktiva**. |
| **EditForm1** |Bestemmer hvilke poster som skal vises. I en generert app vises posten som brukeren har valgt i **BrowseScreen1**. |Angi **[Item](controls/control-form-detail.md)**-egenskapen til denne verdien:<br>**BrowseGallery1.Selected** |
| **[Kort](controls/control-card.md)**-kontroller |I en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll blir kontroller gitt slik at brukeren kan redigere ett eller flere felt i en post. |Angi **[DataField](controls/control-card.md)**-egenskapen til navnet på et felt, omsluttet av doble anførselstegn (for eksempel **"Name"**). |
| **ImageCancel1** |Når brukeren velger denne kontrollen, forkastes endringene som pågår, og **Detaljer**-skjermen åpnes. |Angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br>**ResetForm( EditForm1 ); Back()** |
| **ImageAccept1** |Endringene sendes til datakilden, når brukeren velger denne kontrollen. |Angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br>**SubmitForm( EditForm1 )** |
| **EditForm1** |Hvis endringene blir godtatt, går det tilbake til forrige skjerm. |Angi **[ OnSuccess](controls/control-form-detail.md)**-egenskapen til denne formelen:<br>**Back()** |
| **EditForm1** |Forbli på den gjeldende skjermen slik at brukeren kan løse eventuelle problemer og prøve å sende på nytt, hvis endringene ikke blir godtatt. |La **[OnFailure](controls/control-form-detail.md)**-egenskapen stå tom. |
| **LblFormError1** |En feilmelding vises, hvis endringene ikke er godtatt. |Angi **[Item](controls/properties-core.md)**-egenskapen til denne verdien:<br>**EditForm1.Error** |

Som i **Detaljer**-skjermen, dominerer en skjemakontroll med tittelen **EditForm1** **Rediger og opprett**-skjermen. I tillegg er**[Element](controls/control-form-detail.md)**-egenskapen for **EditForm1** angitt til **BrowseGallery1.Selected**, slik at skjemaet viser posten som brukeren valgte i **BrowseScreen1**. Selv om **Detalj**-skjermen viser hvert felt i skrivebeskyttet visning, kan brukeren oppdatere verdien i ett eller flere felt ved hjelp av kontrollene i **EditForm1**. Den bruker også **[DataSource](controls/control-form-detail.md)**-egenskapen for å få tilgang til metadata om denne datakilden, for eksempel det brukervennlige visningsnavnet for hvert felt, og plasseringen der endringene skal lagres.

Hvis brukeren velger X-ikonet for å avbryte en oppdatering, forkaster **[ResetForm](functions/function-form.md)**-funksjonen alle ulagrede endringer, og **[Tilbake](functions/function-navigate.md)**-funksjonen åpner **Detaljer**-skjermen. Både **Detaljer**-skjermen og **Rediger og opprett**-skjermen viser den samme posten helt til brukeren velger et annet navn på **BrowseScreen1**. Feltene i posten forblir angitt til verdiene som sist ble lagret, ikke eventuelle endringer som brukeren har gjort, og deretter avbrutt.

Hvis brukeren endrer én eller flere verdier i skjemaet, og deretter velger avmerkingsikonet, sender **[SubmitForm](functions/function-form.md)**-funksjonen brukerens endringer til datakilden.

* Skjemaets **[OnSuccess](controls/control-form-detail.md)**-formel kjøres hvis endringene er lagret, og **Back()**-funksjonen åpner detaljerskjermen for å vise den oppdaterte posten.
* Skjemaets **[OnFailure](controls/control-form-detail.md)**-formel kjører hvis endringene ikke er lagret, men det endrer ikke noe fordi den er *tom*. **Rediger og opprett**-skjermen forblir åpen slik at brukeren kan avbryte endringene eller rette opp i feilen. **LblFormError1** viser en brukervennlig feilmelding, som skjemaets **Error**-egenskap er angitt til.

Som med en **[Visningsskjema](controls/control-form-detail.md)**-kontroll, inneholder en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll **[Kort](controls/control-card.md)**-kontroller som inneholder andre kontroller som viser ulike felt i en post:

![Redigeringskort og kort-kontroller som er valgt i redigeringsopplevelsen](./media/working-with-forms/afd-edit-card-controls.png)

I forrige bilde viser det valgte kortet **AssetID**-feltet som inneholder en **[Tekstinndata](controls/control-text-input.md)**-kontroll, slik at brukeren kan redigere verdien i feltet. (I motsetning til dette viser detaljskjermen det samme feltet i en **[Etikett](controls/control-text-box.md)**-kontroll som er skrivebeskyttet.) **[Tekstinndata](controls/control-text-input.md)**-kontrollen har en **[Standard](controls/properties-core.md)**-egenskap, som er angitt til **Parent.Default**. Hvis brukeren har opprettet en post i stedet for å redigere en, viser kontrollen en startverdi som brukeren kan endre for den nye posten.

Du kan vise eller skjule hvert kort, omorganisere eller konfigurere dem til å vise felt i forskjellige kontrolltyper, i den høyre ruten.

![Rediger-skjermen med alternativer-ruten åpen](./media/working-with-forms/edit-screen.png)

## <a name="build-an-app-from-scratch"></a>Å bygge en app fra grunnen av
Ved å forstå hvordan PowerApps genererer en app, kan du utvikle en selv, som bruker samme byggeblokker og formler som beskrevet tidligere i dette emnet.

## <a name="identify-test-data"></a>Å identifisere testdata
For å få mest mulig ut av dette emnet, kan du starte med en datakilde som du kan eksperimentere med. Den bør inneholde testdata som du kan lese og oppdatere uten problemer.

> [!NOTE]
> PowerApps erstatter mellomrommene med **«\_x0020\_»**, hvis du bruker en SharePoint-liste eller en Excel-tabell som inneholder kolonnenavn med mellomrom som datakilde. **Kolonnenavn** i SharePoint eller Excel, vil for eksempel vises som **Column_x0020_Name** i PowerApps når det vises i dataoppsettet, eller brukes i en formel.

For å følge resten av dette emnet nøyaktig, kan du lage en SharePoint-liste med navnet «Ice Cream» som inneholder disse dataene:

![SharePoint-liste for Ice Cream](./media/working-with-forms/sharepointlist-icecream.png)

* Opprett en app fra grunnen av, for telefoner, og [koble den til datakilden](add-data-connection.md).
  
    > [!NOTE]
  > Apper for nettbrett er svært like, men du vil kanskje ha et annet [skjermoppsett](#screen-design) for å få fullt utbytte av den ekstra skjermplassen.
  
    Eksemplene i resten av emnet er basert på en datakilde med navnet **Ice Cream**.

## <a name="browse-records"></a>Å bla gjennom poster
Få en informasjon raskt fra en post ved å finne den i et galleri på en Bla gjennom-skjerm.

1. Legg til et **Loddrett** galleri, og endre oppsettet til kun **Tittel**.
   
    ![Galleriet som er koblet til datakilden for Ice Cream](./media/working-with-forms/new-gallery.png)
2. Angi galleriets **[Element](controls/properties-core.md)**-egenskap til **Ice Cream**.
3. Angi **[Tekst](controls/properties-core.md)**-egenskapen for den første etiketten i galleriet til **ThisItem.Title**, hvis den er angitt til noe annet.
   
    Nå viser etiketten verdien i **Tittel**-feltet for hver post.
   
    ![Galleriet som er koblet til datakilden for Ice Cream](./media/working-with-forms/new-gallery-2.png)
4. Endre størrelse på galleriet for å fylle skjermen, og angi egenskapen for **[Malstørrelse](controls/control-gallery.md)** til **60**.
   
    Skjermen ligner dette eksemplet, som viser alle postene i datakilden:
   
    ![Galleriet som er koblet til datakilden for Ice Cream](./media/working-with-forms/new-gallery-icecream.png)

## <a name="view-details"></a>Se detaljene
Hvis galleriet ikke viser informasjonen du vil bruke, velger du pilen for en post for å åpne detaljerskjermen. En **[Visningsskjema](controls/control-form-detail.md)**-kontroll på denne skjermen viser flere felt, kanskje alle, for posten som du har valgt.

**[Visningsskjema](controls/control-form-detail.md)**-kontrollen bruker to egenskaper til å vise posten:

* **[DataSource](controls/control-form-detail.md)**-egenskapen.  Navnet på datakilden som inneholder posten. Denne egenskapen fyller det høyre panelet med felt, og bestemmer visningsnavnet og datatypen (streng, tall, dato og så videre) for hvert felt.  
* **[Item](controls/control-form-detail.md)**-egenskap.  Posten som du vil vise.  Denne egenskapen er ofte tilknyttet den **valgte** egenskapen for **[Galleri](controls/control-gallery.md)**-kontrollen, slik at brukeren kan velge en oppføring i **[Galleri](controls/control-gallery.md)**-kontrollen og deretter drille ned i denne posten.

Når **[DataSource](controls/control-form-detail.md)**-egenskapen er angitt, kan du legge til og fjerne felt via ruten til høyre og endre hvordan de vises.

På denne skjermen kan ikke brukere endre verdier i posten, verken med eller uten hensikt. **[Visningsskjema](controls/control-form-detail.md)**-kontrollen er en skrivebeskyttet kontroll, slik at den ikke kan endre en post.

For å legge til en **[Visningsskjema](controls/control-form-detail.md)**-kontroll gjør du følgende:

1. Legg til en skjerm, og legg deretter til en **[Visningsskjema](controls/control-form-detail.md)**-kontroll
2. Angi **[DataSource](controls/control-form-detail.md)**-egenskapen for skjema-kontrollen til **Ice Cream**.

Du kan velge feltene som skal vises på skjermen, og hvilken type kort som skal vises for hvert felt i ruten til høyre. Når du gjør endringer i ruten til høyre, er **[DataField](controls/control-card.md)**-egenskapen på hver **[Kort](controls/control-card.md)**-kontroll angitt til feltet som brukeren vil samhandle med. Skjermen bør ligne på dette eksemplet:

![Å vise skjema for Ice Cream-datakilden](./media/working-with-forms/ice-cream-new.png)

Til slutt må vi koble **[Visningsskjema](controls/control-form-detail.md)**-kontrollen til **[Galleri](controls/control-gallery.md)**-kontrollen, slik at vi kan se på detaljene for en bestemt post.  Så snart vi har angitt **[Element](controls/control-form-detail.md)**-egenskapen, vises den første posten fra galleriet i skjemaet vårt.

* Angi **[Item](controls/control-form-detail.md)**-egenskapen for **[Visningsskjema](controls/control-form-detail.md)**-kontrollen til **Gallery1.Selected**.
   
    Detaljene for det valgte elementet vises i skjemaet.
   
    ![Visningsskjema for Ice Cream-datakilden som er koblet til galleriet](./media/working-with-forms/view-form-select-coconut.png)

Bra!  Vi skal nå konsentrere oss om navigasjon: hvordan en bruker åpner detaljerskjermen fra galleriskjermen og galleriskjermen fra detaljerskjermen.

* Legg til en **[Knapp](controls/control-button.md)**-kontroll på skjermen, angi **[Text](controls/properties-core.md)**-egenskapen til **[Back](functions/function-navigate.md)**, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til **Back()**.
   
    Denne formelen gjør at brukeren vender tilbake til galleriet når han er ferdig med å vise detaljene.

    ![Visningsskjema for Ice Cream-datakilden med tilbake-knappen](./media/working-with-forms/viewform-icecream-back.png)

Nå skal vi gå tilbake til **[Galleri](controls/control-gallery.md)**-kontrollen og legge til navigasjon i detaljskjermen vår.

1. Bytt til den første skjermen, som er vert for **[Galleri](controls/control-gallery.md)**-kontrollen vår, og velg pilen i det første elementet i galleriet.

2. Angi **[OnSelect](controls/properties-core.md)**-egenskapen til figuren til denne formelen:
   <br>**Navigate( Screen2, None )**
   
    ![Visningsskjema for Ice Cream-datakilden med tilbake-knappen](./media/working-with-forms/gallery-icecream-nav-new.png)

3. Trykk på F5, og velg deretter en pil i galleriet for å vise detaljene for et element.

4. Velg **[Tilbake](functions/function-navigate.md)**-knappen for å gå tilbake til galleriet med produkter, og trykk deretter på Esc.

## <a name="editing-details"></a>Redigering av detaljer
Til slutt er den siste kjerneaktiviteten vår å endre innholdet i en post, som brukerne utfører i en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll.

**[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen bruker to egenskaper til å vise og redigere posten:

* **[DataSource](controls/control-form-detail.md)**-egenskapen.  Navnet på datakilden som inneholder posten.  Denne egenskapen fyller det høyre panelet med felt, og bestemmer visningsnavnet og datatypen (streng, tall, dato og så videre) for hvert felt, akkurat som med **[Visningsskjema](controls/control-form-detail.md)**-kontrollen. Denne egenskapen bestemmer også om hver feltverdi er gyldig, før de sendes til den underliggende datakilden.
* **[Item](controls/control-form-detail.md)**-egenskap.  Posten som skal redigeres, som ofte er knyttet til **Selected**-egenskapen for **[Galleri](controls/control-gallery.md)**-kontrollen. På den måten kan du velge en post i **[Galleri](controls/control-gallery.md)**-kontrollen, vise den i detaljskjermen og redigere den i **Redigere og opprett**-skjermen.

Hvis du vil legge til en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll, gjør du følgende:

1. Legg til en skjerm, legg til en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll, og angi deretter skjemaets**[DataSource](controls/control-form-detail.md)**-egenskap til **'Ice Cream'**.
2. Angi **[Item](controls/control-form-detail.md)**-egenskapen til **Gallery1.Selected**.

Nå kan du velge feltene som skal vises på skjermen. Du kan også velge hvilken type kort som skal vises for hvert felt. Når du gjør endringer i ruten til høyre angis **[DataField](controls/control-card.md)**-egenskapen for hver **[Kort](controls/control-card.md)**-kontroll til feltet brukeren skal samhandle med.  Skjermen bør ligne på dette eksemplet:

![Å vise skjema for Ice Cream-datakilden](./media/working-with-forms/icecream-edit.png)

Disse to egenskapene er de samme som egenskapene på **[Visningsskjema](controls/control-form-detail.md)**-kontrollen.  Og med disse alene, kan vi vise detaljene for en post.  

**[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen går videre ved å tilby **[SubmitForm](functions/function-form.md)**-funksjonen til å tilbakeskrive endringer til datakilden. Du bruker dette med en knapp eller bildekontroll, for å lagre en brukers endringer.

* Legg til en **[Knapp](controls/control-button.md)**-kontroll, angi **[Text](controls/properties-core.md)**-egenskapen til å vise **Lagre**, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br>
  **SubmitForm( Form1 )**

![Å redigere skjema for Ice Cream-datakilden](./media/working-with-forms/edit-icecream-save.png)

Slik legger du til navigering til og fra denne skjermen:

1. Legg til en ekstra **[Knapp](controls/control-button.md)**-kontroll, angi **[Text](controls/properties-core.md)**-egenskapen til å vise **Avbryt**, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen: <br>**ResetForm( Form1 ); Back()**
   
    Denne formelen forkaster eventuelle ulagrede endringer, og åpner den forrige skjermen.
   
    ![Å vise skjema for Ice Cream-datakilden](./media/working-with-forms/edit-icecream-cancel.png)
2. Angi **[OnSuccess](controls/control-form-detail.md)**-egenskapen for skjemaet til **Back()**.
   
    Når oppdateringene er lagret, åpnes forrige skjerm (i dette tilfellet detaljerskjermen) automatisk.
   
    ![Redigeringsskjema med en OnSuccess-regel lagt til](./media/working-with-forms/edit-icecream-onsuccess.png)
3. Legg til en knapp på **Visning**-skjermen, angi **[Text-](controls/properties-core.md)** egenskapen til å vise**Rediger**, og angi **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br> **Navigate( Screen3, None )**
   
    ![Visningsskjema med en Rediger-knapp lagt til](./media/working-with-forms/viewform-icecream-edit.png)

Du har laget en grunnleggende app med tre skjermer for å vise og skrive inn data.  Hvis du vil prøve den ut, viser du galleriskjermen og trykker deretter på F5 (eller velger fremoverpilen for Forhåndsvisning-knappen nær øvre venstre hjørne på skjermen). Den rosa prikken viser hvor brukeren klikker på skjermbildet for hvert trinn.

![Å prøve ut Ice Cream-appen](./media/working-with-forms/try-icecream.png)

## <a name="create-a-record"></a>Å opprette en post
Brukeren samhandler med det samme **Redigerings**-skjemaet for både oppdatering og oppretting av poster. Når brukeren ønsker å opprette en post, bytter **[NewForm](functions/function-form.md)**-funksjonen skjemaet til **Ny**-modus.

Når skjemaet er i **Ny**-modus, er verdien for hvert felt angitt til standardverdiene for datakilden. Posten som er angitt i skjemaets **[Element](controls/control-form-detail.md)**-egenskap, ignoreres.  

Når brukeren er klar til å lagre den nye posten, kjøres **[SubmitForm](functions/function-form.md)**. Når skjemaet er sendt, settes skjemaet tilbake i **Redigeringsmodus**.  

Legg til en **Ny**-knapp på den første skjermen:

1. Legg til en **[Knapp](controls/control-button.md)**-kontroll på skjermen med galleriet.
2. Angi knappens **[Text](controls/properties-core.md)**-egenskap til **New** og **[OnSelect](controls/properties-core.md)**-egenskapen til denne formelen:<br>
   **NewForm( Form1 ); Navigate( Screen3, None )**
   
    Denne formelen bytter **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen på **Screen3** til **Ny** modus og åpner skjermen slik at brukeren kan fylle ut skjemaet.

![Visningsskjema med en Rediger-knapp lagt til](./media/working-with-forms/gallery-icecream-new.png)

Når Rediger og opprett-skjermen åpnes, er skjemaet tomt og klart for at brukeren skal legge til et element. **[SubmitForm](functions/function-form.md)**-funksjonen sikrer at en post opprettes i stedet for å oppdateres, når brukeren velger **Lagre**-knappen. Hvis brukeren velger **Avbryt**-knappen, bytter **[ResetForm](functions/function-form.md)**-funksjonen skjemaet tilbake til **Redigerings**modus, og **[Back](functions/function-navigate.md)**-funksjonen åpner skjermen for å bla gjennom galleriet.

## <a name="delete-a-record"></a>Å slette en post
1. Legg til en knapp på **Visning** -skjermen, og angi **[Text](controls/properties-core.md)**-egenskapen til å vise **Slett**.
2. Angi **[OnSelect](controls/properties-core.md)**-egenskapen for knappen til denne formelen:
   <br>**Remove( 'Ice Cream', Gallery1.Selected ); Back()**
   
    ![Visningsskjema med en Rediger-knapp lagt til](./media/working-with-forms/viewform-icecream-remove.png)

## <a name="handling-errors"></a>Å håndtere feil
I denne appen oppstår det en feil når verdien i et felt ikke er gyldig, et obligatorisk felt er tomt, du er koblet fra nettverket, eller en rekke andre problemer dukker opp.  

Hvis **[SubmitForm](functions/function-form.md)** av en eller annen grunn mislykkes, inneholder **Error**-egenskapen for **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen en feilmelding som vises til brukeren. Brukeren bør være i stand til å løse problemet og sende inn endringen på nytt med denne informasjonen, eller han kan avbryte oppdateringen.

1. Legg til en **[Etikett](controls/control-text-box.md)**-kontroll på Rediger og opprett-skjermen, og flytt den til rett under **Lagre**-knappen. Det er lett å se eventuelle feil når brukeren velger denne kontrollen til å lagre endringer.

2. Angi **[Text](controls/properties-core.md)**-egenskapen for **[Etikett](controls/control-text-box.md)**-kontrollen til å vise **Form1.Error**.

    ![Visningsskjema med en Rediger-knapp lagt til](./media/working-with-forms/edit-icecream-error.png)

I en app som PowerApps genererer fra data, er **[AutoHeight](controls/control-text-box.md)**-egenskapen på denne kontrollen angitt til *sann*, slik at ingen mellomrom brukes, hvis det ikke oppstår feil. **[Height](controls/properties-size-location.md)** og **[Y](controls/properties-size-location.md)**-egenskapene for **[Redigeringsskjema](controls/control-form-detail.md)** kontrollen justeres også dynamisk for å ta hensyn til at denne kontrollen vokser når det oppstår en feil. Hvis du vil ha mer informasjon, kan du generere en app fra eksisterende data, og undersøke disse egenskapene. Tekstbokskontrollen for feil er svært kort når det er ikke har oppstått noen feil, og du må kanskje åpne **Avansert** visning (tilgjengelig på **Visning**-fanen) for å velge denne kontrollen.

![App fra redigeringsskjema for data med tekstkontroll for feil valgt](./media/working-with-forms/edit-assets-error1.png)

![App fra redigeringsskjema for data med skjemakontroll valgt](./media/working-with-forms/edit-assets-error2.png)

## <a name="refresh-data"></a>Å oppdatere data
Datakilden oppdateres hver gang brukeren åpner appen, men brukeren vil kanskje oppdatere postene i galleriet uten å lukke appen. Legg til en **Oppdater**-knapp, slik at brukeren kan velge den for å oppdatere dataene manuelt:

1. Legg til en **[Knapp](controls/control-button.md)**-kontroll på skjermen med **[Galleri](controls/control-gallery.md)**-kontrollen, og angi **[Tekst](controls/properties-core.md)**-egenskapen til å vise **Refresh**.

2. Angi **[OnSelect](controls/properties-core.md)**-egenskapen for denne kontrollen til denne formelen:<br> **Refresh( 'Ice Cream' )**

    ![Å oppdatere datakilden](./media/working-with-forms/browse-icecream-refresh.png)

## <a name="search-and-sort-the-gallery"></a>Å søke og sortere i galleriet
I appen som PowerApps har generert fra data, er det to kontroller øverst på Bla gjennom-skjermen som vi ikke har gått gjennom. Ved hjelp av disse kontrollene, kan brukeren søke etter én eller flere poster, sortere listen over poster i stigende eller synkende rekkefølge, eller begge deler.

![Å kontrollere for sortering og søk på skjermbildet for Bla gjennom](./media/working-with-forms/afd-browse-search-sort.png)

Når brukeren velger Sorter-knappen, reverseres sorteringsrekkefølgen i galleriet. En *kontekstvariabel* brukes til å spore retningen som galleriet er sortert i, hvis du vil opprette denne virkemåten. Når brukeren velger denne knappen, oppdateres variabelen, og retningen reverseres. **[OnSelect](controls/properties-core.md)**-egenskapen for sorter-knappen er angitt til denne formelen: **UpdateContext( {SortDescending1: !SortDescending1} )**

**[UpdateContext](functions/function-updatecontext.md)**-funksjonen oppretter kontekstvariabelen for **SortDescending1** hvis den ikke allerede finnes. Funksjonen vil lese verdien for variabelen og angi den til det logiske motsatte ved å bruke **!** operator. Hvis verdien er *sann*, blir den *usann*. Hvis verdien er *usann*, blir den *sann*.

Formelen for **[Items](controls/properties-core.md)**-egenskapen for **[Galleri](controls/control-gallery.md)**-kontrollen bruker denne kontekstvariabelen, sammen med teksten i **TextSearchBox1**-kontrollen:

    Gallery1.Items = Sort( If( IsBlank(TextSearchBox1.Text),
                               Assets,
                               Filter( Assets,
                                       TextSearchBox1.Text in Text(ApproverEmail) ) ),
                            ApproverEmail,
                            If(SortDescending1, Descending, Ascending) )

La oss gjøre det enklere å forstå:

* På utsiden har vi **[Sorterings](functions/function-sort.md)**-funksjonen, som tar tre argumenter: en tabell, et felt å sortere i og retningen du vil sortere i.  
  
  * Sorteringsretningen er hentet fra kontekstvariabelen som veksler når brukeren velger **ImageSortUpDown1**-kontrollen. Den *sanne*/*usanne* verdien blir oversatt til konstantene **Synkende** og **Stigende**.
  * Feltet som skal sorteres i, er fastsatt til **ApproverEmail**. Hvis du endrer feltene som vises i galleriet, må du endre dette argumentet også.
* På innsiden har vi **[Filter](functions/function-filter-lookup.md)**-funksjonen, som tar en tabell som et argument og et uttrykk som evalueres for hver post.
  
  * Tabellen er den rå **Aktiva**-datakilden, som er utgangspunkt før filtrering eller sortering.
  * Uttrykket søker etter en forekomst av strengen i **TextSearchBox1** i **ApproverEmail**-feltet.  Igjen, hvis du endrer feltene som vises i galleriet, må du også oppdatere dette argumentet.
  * Hvis **TextSearchBox1** er tom, brukeren ønsker å vise alle poster, og **[Filter](functions/function-filter-lookup.md)**-funksjonen blir forbigått.

Dette er bare ett eksempel. Du kan lage din egen formel for **[Items](controls/properties-core.md)**-egenskapen, avhengig av behovene til appen din, ved å skrive **[Filter](functions/function-filter-lookup.md)**, **[Sorter](functions/function-sort.md)** og andre funksjoner og operatorer sammen.    

## <a name="screen-design"></a>Skjermutforming
Vi har så langt ikke diskutert andre måter å fordele kontroller på tvers av skjermer på. Dette er fordi du har mange alternativer, og det beste valget avhenger av behovene til den bestemte appen.

Fordi eiendomstjenester på telefonskjermer er såpass begrenset, vil du trolig ønske å bla gjennom, vise, og redigere/opprette på forskjellige skjermer. I dette emnet åpner **[Navigate](functions/function-navigate.md)** og **[Back](functions/function-navigate.md)**-funksjonene hver skjerm.  

På et nettbrett kan du bla gjennom, vise og redigere/opprette på to, eller bare én skjerm. For sistnevnte vil verken **[Navigate](functions/function-navigate.md)** eller **[Back](functions/function-navigate.md)**-funksjonen være nødvendig.

Hvis brukeren arbeider på den samme skjermen, må du passe på at brukeren ikke kan endre valget i **[Galleriet](controls/control-gallery.md)** og risikere å miste endringer i **[Redigeringsskjema](controls/control-form-detail.md)**-kontrollen.  Hvis du vil forhindre at brukeren skal velge en annen post når du ikke har lagret endringer til en annen post ennå, kan du angi **[Deaktiver](controls/properties-core.md)**-egenskapen for galleriet til denne formelen:<br>
**EditForm.Unsaved**

