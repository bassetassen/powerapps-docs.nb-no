---
title: Å skanne en strekkode | Microsoft Docs
description: Å skanne en rekke strekkodetyper, for eksempel UPC og Codabar
services: ''
suite: powerapps
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/23/2016
ms.author: anneta
ms.openlocfilehash: 078c53300c4e1489d179f9c91818a8e23616f3ae
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997582"
---
# <a name="scan-a-barcode-in-microsoft-powerapps"></a>Å skanne en strekkode i Microsoft PowerApps
Skann flere typer strekkoder ved å opprette en app, og kjøre den på en enhet, for eksempel en telefon som har et kamera. Den numeriske tilsvarende strekkoden vises i en **Etikett**kontroll, og du kan laste opp denne dataen til en rekke [datakilder](connections-list.md).

Hvis du ikke er kjent med PowerApps, kan du se [Komme i gang](getting-started.md).

## <a name="known-limitations"></a>Kjente begrensninger
* Strekkoder må være minst 1 tomme (2,5 cm) høy og 1,5 tommer (4 cm) bred.
* Hvis du vil skanne strekkoder ved hjelp av en telefon, må du holde den i stående retning, og flytte den sakte fra 7 tommer (18 cm) til 10 tommer (25 cm) bort fra strekkoden.
* Lang strekkodetyper (for eksempel I2of5, som kan ha 15 eller flere tegn) kan gi avkuttet eller ellers feil resultater, spesielt hvis strekkoden ikke er tydelig skrevet ut.
* For iPhone og Android-enheter kan du angi **Høyde**-egenskapen for **Strekkode**-kontrollen, men et fast størrelsesforhold bestemmer bredden.
* Du må kanskje angi **Skannefrekvens**-egenskapen for **Strekkode**-kontrollen til **35** eller mindre.
* Hvis du vil forsinke det å gå tom for minne på enheter som kjører iOS, kan du angi **Høyde**-egenskapen for **Strekkode**-kontrollen til **700** (eller lavere) og **Skannefrekvens**-egenskapen til **30**.
* Hvis enheten går tom for minne og appen fryser, kan du starte appen på nytt.

## <a name="create-a-blank-app"></a>Å opprette en tom app
1. [Registrer deg for PowerApps](../signup-for-powerapps.md), og gjør deretter *en* av følgende:

   * [Åpne PowerApps](https://create.powerapps.com/api/start) i en nettleser på en enhet som har et kamera.
   * [Installere PowerApps](http://aka.ms/powerappsinstall) fra Windows Store på en enhet som har et kamera. Åpne PowerApps, logg på, og klikk eller trykk på **Ny** på **Fil**-menyen (langs venstre kant).

2. Klikk eller trykk på **Telefonoppsett** på **Tom app**-flisen, under **Begynn med et tomt lerret eller en mal**.

    ![Å opprette en app fra grunnen av](./media/scan-barcode/create-from-blank.png)

3. Bli kjent med nøkkelområder i appen ved å ta Introduksjonsinnføringen (eller klikke eller trykke på **Hopp over**), hvis du ikke har brukt PowerApps før.

    ![Å åpne skjermbildet for hurtiginnføringen](./media/scan-barcode/quick-tour.png)

    > [!NOTE]
> Hvis du ønsker å se innføringen senere, kan du det ved å klikke eller trykke på spørsmålstegn-ikonet nær hjørnet øverst til høyre, og deretter klikke eller trykke på **Ta Introduksjonsinnføringen**.

## <a name="add-a-barcode-control"></a>Å legge til en strekkodekontroll
1. Klikk eller trykk på **Media** på **Sett inn**-fanen, og klikk eller trykk deretter på **Strekkode**.

    ![Å legge til strekkodeleser](./media/scan-barcode/add-scanner.png)

2. Forsikre deg om at **Strekkode**-kontroll er valgt ved å bekrefte at en valgboks (med håndtak for å endre størrelsen på kontrollen) omslutter den.

    ![Valgboks](./media/scan-barcode/selection-box.png)

3. Klikk eller trykk på **Barcode1** på **Hjem**-fanen, og skriv eller lim deretter inn **MyScanner** under **Gi nytt navn**.

    > [!TIP]
> Den første **Strekkode**-kontrollen du legger til, heter, som standard **Barcode1**. Hvis du sletter denne kontrollen og legger til en annen **Strekkode**-kontroll, får den, som standard navnet **Barcode2**. Ved å manuelt gi nytt navn til en kontroll, sikrer du at formler refererer til kontrollen med riktig navn.

    ![Å gi nytt navn til strekkodekontrollen](./media/scan-barcode/rename-barcode.png)

## <a name="add-a-text-input-control"></a>Å legge til en tekstinndatakontroll
1. Klikk eller trykk på **Tekst** på **Sett inn**-fanen, og klikk eller trykk deretter på **Tekstinndata**.

    Maksimer PowerApps-vinduet hvis **Sett inn**-fanen ikke vises.

    ![Å legge til en tekstinndatakontroll](./media/scan-barcode/add-text-input.png)

2. Dra valgboksen (ikke skaleringshåndtakene) rundt **Tekstinndata**-kontrollen ned til den vises under **MyScanner**.

    ![Etikett med valgboks](./media/scan-barcode/move-input-text.png)

3. Sørg for at **Standard** vises i egenskaper-listen mens **Tekstinndata**-kontrollen fortsatt er valgt, og skriv eller lim deretter inn **MyScanner.Text** på formellinjen.

    ![Tekstegenskapen for etikettkontrollen](./media/scan-barcode/default-text.png)

## <a name="change-the-barcode-type"></a>Å endre strekkodetypen
1. Klikk eller trykk på **Tekst** på **Sett inn**-fanen, og klikk eller trykk deretter på **Rullegardin**.

    ![Å legge til en rullegardinliste](./media/scan-barcode/insert-dropdown.png)

2. Flytt **Rullegardin**-kontrollen slik at den vises nedenfor de andre kontrollene på skjermen.

    ![Å flytte rullegardinlisten](./media/scan-barcode/move-dropdown.png)

3. Sørg for at egenskaper-listen viser **Elementer** mens **Rullegardin**-kontrollen fortsatt er valgt, og skriv eller lim deretter inn denne strengen med tekst på formellinjen:<br>
    **[Codabar, Code128, Code39, Ean, I2of5, Upc]**

    ![Å angi elementegenskaper for rullegardinlisten](./media/scan-barcode/items-property.png)

4. Gi nytt navn til **Rullegardin**-kontrollen som **ChooseType** på **Hjem**-fanen.

    ![Å gi nytt navn til rullegardinlisten](./media/scan-barcode/rename-dropdown.png)

5. Klikk eller trykk på **MyScanner** for å velge den, sørg for at egenskaper-listen viser **BarcodeType**, og skriv eller lim deretter inn denne strengen med tekst på formellinjen:<br>
    **ChooseType.Selected.Value**

## <a name="test-the-app"></a>Testing av appen
1. Åpne forhåndsvisningsmodus ved å trykke på F5 (eller ved å klikke på avspillingsknappen nær hjørnet øverst til høyre).

    ![Å åpne forhåndsvisningsmodus](./media/scan-barcode/open-preview.png)

2. Hold en strekkode opp til kameraet på enheten frem til den numeriske komponenten for strekkoden vises i **Etikett**-kontrollen.

    Hvis den numeriske komponenten ikke vises, kan du prøve et annet alternativ under **BarcodeType**-listen. Hvis de riktige dataene fremdeles ikke vises, skriver du inn det riktige nummeret i **Inndatatekst**-kontrollen.

## <a name="next-steps"></a>Neste trinn
* [Koble appen til en datakilde](add-data-connection.md) og konfigurer  **[Korrigering](functions/function-patch.md)**-funksjonen, slik at brukere kan lagre resultatene.
* Legg til en **[Rullegardin](controls/control-drop-down.md)**-kontroll og konfigurer den, slik at brukere kan velge hvilken type strekkode de ønsker å skanne.
* Legg til en **[Glidebryter](controls/control-slider.md)**-kontroll og konfigurer den, slik at brukere kan justere skannefrekvensen eller høyden på **Strekkode**-kontrollen.
