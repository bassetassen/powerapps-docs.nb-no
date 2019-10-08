---
title: 'Datatabell-kontroll: referanse | Microsoft Docs'
description: Informasjon, inkludert egenskaper og eksempler, om Datatabell-kontrollen
author: jasongre
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/05/2017
ms.author: jasongre
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f29b3a782ce62c475c80804225787a0a42e85a2c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993621"
ms.PowerAppsDecimalTransform: true
---
# <a name="data-table-control-in-powerapps"></a>Datatabell-kontrollen i PowerApps
Viser et sett med data i et tabellformat.

## <a name="description"></a>Beskrivelse
**Datatabell**-kontrollen viser et datasett i et format som inkluderer kolonneoverskrifter for hvert felt som kontrollen viser. Du som oppretter appen, har full kontroll over hvilke felt som vises, og i hvilken rekkefølge. **Datatabell**-kontrollen vedlikeholder en **Valgt**-egenskap, på lik linje med **Galleri**-kontrollen, som peker til den valgte raden. Du kan derfor tilknytte **Datatabell**-kontrollen til andre kontroller.

## <a name="capabilities"></a>Funksjoner
PowerApps introduserte **Datatabell**-kontrollen 5. mai 2017. Denne delen inneholder informasjon om funksjoner som støttes og ikke støttes.

### <a name="now-available"></a>Nå tilgjengelig
* Data i **Datatabell**-kontrollen er skrivebeskyttet.
* En enkelt rad er alltid utvalgt i en **Datatabell**-kontroll.
* Tilknytt en **Datatabell**-kontroll til en tilkoblet eller lokal datakilde.
* Juster kolonnebredden med en **Datatabell**-kontroll mens du kjører appen, men endringene lagres ikke.
* Et sett med standardfelt vises i en **Datatabell**-kontroll når du tilknytter den til en tilkobling som har implementert denne funksjonen, som Common Data Service. Du kan deretter vise eller skjule disse feltene og andre etter behov.
* Tilpass kolonnebredde og overskriftstekst.
* Vis hyperkoblinger i en **Datatabell**-kontroll.
* Kopier og lim inn en **Datatabell**-kontroll.

### <a name="not-yet-available"></a>Ikke tilgjengelig
* Tilpass stilen til individuelle kolonner.
* Legg til en **Datatabell**-kontroll i en Skjema-kontroll.
* Endre høyden på alle radene.
* Vis bilder i en **Datatabell**-kontroll.
* Vis felter fra relaterte enheter.
* Bruk innebygget funksjonalitet til å filtrere og sortere data etter kolonneoverskrift.
* Legg til en **Datatabell**-kontroll i en **Galleri**-kontroll.
* Rediger data i **Datatabell**-kontrollen.
* Velg flere rader.

### <a name="known-issues"></a>Kjente problemer
* Det vises ingen data hvis du bruker **FirstN**-funksjonen i **Elementer**-egenskapen.

## <a name="key-properties"></a>Nøkkelegenskaper
* [**Elementer**](properties-core.md) – kilden til dataene som vises i **Datatabell**-kontrollen.
* **Valgt** – den valgte raden i **Datatabell**-kontrollen.

## <a name="other-properties"></a>Andre egenskaper
* [**BorderColor**](properties-color-border.md) – fargen på kantlinjen til **Datatabell**-kontrollen.
* [**BorderStyle**](properties-color-border.md) – stilen på kantlinjen til **Datatabell**-kontrollen. Alternativene er **Heltrukket**, **Stiplet**, **Prikket** og **Ingen**.
* [**BorderThickness**](properties-color-border.md) – tykkelsen til kantlinjen til **Datatabell**-kontrollen.
* [**Farge**](properties-color-border.md) – standard tekstfarge for alle dataradene.
* [**Fyll**](properties-color-border.md) – standard bakgrunnsfarge for alle dataradene.
* [**Skrift**](properties-text.md) – standard skrift for alle dataradene.
* [**FontWeight**](properties-text.md) – standard skrifttykkelse for alle dataradene.
* **HeadingColor** – tekstfargen for kolonneoverskriftene.
* **HeadingFill** – bakgrunnsfargen til kolonneoverskriftene.
* **HeadingFont** – skriften for kolonneoverskriftene.
* **HeadingFontWeight** – skrifttykkelsen for kolonneoverskriftene.
* **HeadingSize** – skriftstørrelsen for kolonneoverskriftene.
* [**Høyde**](properties-size-location.md) – Avstanden mellom **Datatabell**-kontrollens øvre og nedre kant.
* [**HoverColor**](properties-color-border.md) – tekstfargen for raden som pekeren beveger seg over.
* [**HoverFill**](properties-color-border.md) – bakgrunnsfargen for raden som pekeren beveger seg over.
* **NoDataText** – meldingen som brukeren mottar når det ikke er noen poster å vise i **Datatabell**-kontrollen.
* **SelectedColor** – fargen på teksten i den valgte raden.
* **SelectedFill** – bakgrunnsfargen for den valgte raden.
* [**Størrelse**](properties-text.md) – standard skriftstørrelse for alle dataradene.
* [**Synlig**](properties-core.md) – en verdi som bestemmer om **Datatabell**-kontrollen vises eller skjules.
* [**Bredde**](properties-size-location.md) – Avstanden mellom **Datatabell**-kontrollens venstre og høyre kant.
* [**X**](properties-size-location.md) – avstanden mellom **Datatabell**-kontrollens venstre kant og den venstre kanten til kontrollens overordnede beholder (eller den venstre kanten til skjermen, hvis det ikke finnes noen overordnet beholder).
* [**Y**](properties-size-location.md) – avstanden mellom **Datatabell**-kontrollens øvre kant og den øvre kanten til kontrollens overordnede beholder (eller den øvre kanten til skjermen, hvis det ikke finnes noen overordnet beholder).

## <a name="related-functions"></a>Relaterte funksjoner
* [**Filter(DataSource; Formula)** ](../functions/function-filter-lookup.md)(*DataSource*, *Formula*)
* [**Search(DataSource; SearchString; Column)** ](../functions/function-filter-lookup.md)(*DataSource*, *SearchString*, *Column*)

## <a name="examples"></a>Eksempler
### <a name="basic-usage"></a>Grunnleggende bruk
1. Opprett en tom app for nettbrett.
2. Klikk eller trykk på **Datatabell** på **Sett inn**-fanen.
   
    ![Slik legger du til en Datatabell-kontroll på skjermen](./media/control-data-table/insert-data-table.png)
   
    En **Datatabell**-kontroll legges til på skjermen.
3. Gi **Datatabell**-kontrollen det nye navnet **SalesOrderTable**, og endre størrelse slik at den dekker hele skjermen.
4. Klikk eller trykk på Pil ned til høyre for **Ingen datakilde er valgt** i den høyre ruten, og deretter klikker eller trykker du på **Legg til en datakilde**.
   
    ![Å legge til en datakilde](./media/control-data-table/add-data-to-data-table.png)
5. Klikk eller trykk på tilkoblingen for Common Data Service-databasen din i listen over tilkoblinger.
   
    ![Velg tilkoblingen for datakilden](./media/control-data-table/choose-cds-data-table.png)
6. Klikk eller trykk på **Salgsordre** i listen over enheter, og klikk eller trykk deretter på **Koble til**.
   
    ![Å velge salgsordreenheten](./media/control-data-table/choose-so-data-table.png)
   
    **Datatabell**-kontrollen er nå knyttet til **Salgsordre**-datakilden. Flere innledende felt vises i **Datatabell**-kontrollen, fordi vi bruker en tilkobling som støtter den funksjonen.
   
    ![Datatabell](./media/control-data-table/pre-order-data-table.png)
7. Velg én eller flere avmerkingsbokser for å vise eller skjule individuelle felter.
   
    Merk for eksempel av for **CustomerPurchaseOrderReference** for å skjule feltet.
8. Ordne rekkefølgen på feltene på nytt ved å dra dem opp og ned, fra ruten til høyre.
   
    ![Du kan ordne rekkefølgen på feltene ved behov](./media/control-data-table/field-re-order-data-table.png)
   
    **SalesOrderTable**-kontrollen viser feltene i rekkefølgen du angir.
   
    ![Oppdatert datatabell](./media/control-data-table/post-order-data-table.png)

### <a name="restyle-the-header-for-the-data-table-control"></a>Endring av stilen på overskriften for datatabellkontrollen
1. Mens **Datatabell**-kontrollen er valgt, klikker eller trykker du på **Advanced**-fanen, i ruten til høyre.
2. Klikk eller trykk på feltet for **HeadingFill**-egenskapen, og endre deretter verdien til **RGBA(62;96;170;1)** .
3. Klikk eller trykk på feltet for **HeadingColor**-egenskapen, og endre deretter verdien til **Hvit**.
4. Klikk eller trykk på feltet for **HeadingSize**-egenskapen, og endre deretter verdien til **14**.
   
    ![Datatabell](./media/control-data-table/restyled-data-table.png)

### <a name="connect-a-data-table-control-to-another-control"></a>Slik kobler du en Datatabell-kontroll til en annen kontroll
1. Legg til en **Redigeringsskjema**-kontroll på skjermen.
2. Endre størrelsen på **Datatabell**- og **Redigeringsskjema**-kontrollene slik at **Datatabell**-kontrollen vises til venstre på skjermen, og **Redigeringsskjema**-kontrollen vises til høyre på skjermen.
   
    ![Datatabell og Redigeringsskjema på samme skjerm](./media/control-data-table/data-table-empty-form.png)
3. Når **Form1** er valgt, endrer du antallet kolonner til **1** fra ruten til høyre.
4. Koble til **Form1** i **Salgsordre**-datakilden.
   
    Flere innledende felter vises i **Form1**.
   
    ![Form1 med innledende felter](./media/control-data-table/data-table-disconnected-form.png)
5. Klikk eller trykk på **Avansert**-fanen i ruten til høyre.
6. Angi **Item**-egenskapen for **Form1** til **SalesOrderTable.Selected**.
   
    **Form1** viser informasjon fra raden som er valgt i **Datatabell**-kontrollen.
   
    ![Redigering av skjema som er koblet til datatabellen](./media/control-data-table/connected-form-data-table.png)


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="color-contrast"></a>Fargekontrast
Det må være tilstrekkelig fargekontrast mellom:
* [**Farge**](properties-color-border.md) og [**Fyll**](properties-color-border.md)
* **HeadingColor** og **HeadingFill**
* **SelectedColor** og **SelectedFill**
* [**Pekefarge**](properties-color-border.md) og [**Pekefyll**](properties-color-border.md)

Dette er i tillegg til [kravene for standard fargekontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **NoDataText** må foreligge.
