---
title: Vis, rediger eller legg til en post fra en tabell i en lerretsapp | Microsoft Docs
description: Bruk et lerretsappskjema til å vise, redigere eller legge til en post fra en tabell i datakilden.
author: karthik-1
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/06/2017
ms.author: sharik
ms.openlocfilehash: a8c786e499bdc1e4dacc0adbf2bee489d56229ce
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/02/2018
ms.locfileid: "39469975"
---
# <a name="show-edit-or-add-a-record-from-a-table-in-powerapps"></a>Å vise, redigere eller legge til en post fra en tabell i PowerApps

Hvis du vil vise alle feltene i en post, kan du legge til og konfigurere en **[Visningsskjema](controls/control-form-detail.md)**-kontroll i en lerretsapp. Hvis du vil redigere noen av feltene i en post (eller legge til en post) og lagre endringene i en datakilde igjen, kan du legge til og konfigurere en **[Redigeringsskjema](controls/control-form-detail.md)**-kontroll i en lerretsapp.

## <a name="prerequisites"></a>Forutsetninger

* Finn ut hvordan du [legger til og konfigurerer en kontroll](add-configure-controls.md) i PowerApps.
* Last ned [denne Excel-filen](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), som inneholder eksempeldata for denne opplæringen.
* Last opp Excel-filen til en [skylagringstjeneste](connections/cloud-storage-blob-connections.md), for eksempel OneDrive for Business.
* [Legg til en tilkobling](add-data-connection.md) i en ny eller eksisterende app til **FlooringEstimates**-tabellen i Excel-filen.
* Hvis du bruker en eksisterende app, [legger du til en skjerm](add-screen-context-variables.md) i den.

## <a name="add-a-form-and-show-data"></a>Å legge til et skjema og vise data
1. Legg til en **[Rullegardin](controls/control-drop-down.md)**-kontroll, gi den navnet **ChooseProduct**, og angi **[Elementer](controls/properties-core.md)**-egenskapen som denne verdien:

    **FlooringEstimates.Name**

    > [!NOTE]
   > Hvis du ikke er sikker på hvordan du legger til en kontroll, gir nytt navn til den eller angir en egenskap, kan du se [Å legge til og konfigurere kontroller](add-configure-controls.md).

    Listen viser navnene på gulvprodukter fra datakilden.

2. Legg til en **Redigeringsskjema**-kontroll, flytt den under **ChooseProduct**, og endre deretter størrelsen på skjemaet, slik at det dekker mesteparten av skjermen.

    ![Å legge til et skjema](./media/add-form/add-a-form.png)

    > [!NOTE]
   > Dette emnet beskriver **Redigeringsskjema**-kontrollen, men lignende prinsipper gjelder for **Visningsskjema**-kontrollen.

3. Angi skjemaets **[DataSource](controls/control-form-detail.md)**-egenskap som **FlooringEstimates** og **[Elementer](controls/control-form-detail.md)**-egenskapen som denne formelen:

   **First(Filter(FlooringEstimates, Name=ChooseProduct.Selected.Value))**

   Denne formelen angir at posten brukeren velger i **ChooseProduct**, skal vises når du har konfigurert skjemaet ferdig.

4. Klikk eller trykk på avmerkingsboksen i **Data**-ruten for hvert felt for å vise det.

    > [!NOTE]
   > Hvis **Data**-ruten er lukket, åpner du den ved å velge skjemaet i ruten til venstre og deretter klikke eller trykke på **Data** i ruten til høyre.

    ![Å vise felt i skjema](./media/add-form/checkbox.png)

5. Dra **Navn**-oppføringen til toppen av listen i **Data**-ruten.

    ![Å flytte et kort](./media/add-form/drag-field.png)

    **Redigeringsskjema**-kontrollen gjenspeiler endringen.

    ![Navnet øverst](./media/add-form/move-card-form.png)

## <a name="set-the-card-type-for-a-field"></a>Å angi korttypen for et felt
1. Når du har valgt skjemaet, klikker eller trykker du på kortvelgeren for **Pris** i **Data**-ruten.

    ![Å velge kortvelgeren](./media/add-form/price-card2.png)

2. Rull nedover, og klikk eller trykk på alternativet **Vis tekst** for å gjøre feltet skrivebeskyttet.

    ![Å vise tekst](./media/add-form/view-text.png)

    Skjemaet gjenspeiler endringen din.

    ![Skrivebeskyttet tall](./media/add-form/read-only.png)  

## <a name="edit-form-only-save-changes"></a>(Bare for redigeringsskjema) Lagre endringer
1. Velg skjemaet i ruten til venstre, og klikk eller trykk på ellipsen (...).

   ![Å velge skjemaet](./media/add-form/select-form.png)

2. Klikk eller trykk på **Gi nytt navn**, og gi skjemaet navnet **EditForm**.

3. Legg til en **[Knapp](controls/control-button.md)**, og angi knappens **[Tekst](controls/properties-core.md)**-egenskap som **Lagre**.

    ![Å legge til en lagringsknapp](./media/add-form/save-button.png)  

4. Angi **[OnSelect](controls/properties-core.md)**-egenskapen til **Lagre**-knappen som denne formelen:

   **SubmitForm(EditForm)**

5. Åpne forhåndsvisningsmodus ved å velge avspillingsknappen nær hjørnet øverst til høyre (eller ved å trykke på F5).

    ![Åpne forhåndsvisningsmodus](./media/add-form/open-preview.png)

6. Endre navnet på et produkt, og klikk eller trykk deretter på **Lagre**-knappen som du opprettet.

    **[SubmitForm](functions/function-form.md)**-funksjonen lagrer endringene i datakilden som du har konfigurert skjemaet med.

7. (valgfritt) Velg lukkeikonet for å lukke forhåndsvisningen (eller trykk på ESC).

    ![Lukk forhåndsvisningen](./media/add-form/close-preview.png)

## <a name="next-steps"></a>Neste trinn
Finn ut mer om hvordan du arbeider med [skjemaer](working-with-forms.md) og [formler](working-with-formulas.md).
