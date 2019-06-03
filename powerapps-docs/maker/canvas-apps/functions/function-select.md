---
title: Select-funksjon | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks, for Select-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/11/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 74584e5855c6c72c619b4baefc2652f9ccc68997
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61520691"
---
# <a name="select-function-in-powerapps"></a>Select-funksjonen i PowerApps
Simulerer en valgt handling på en kontroll som fører til at **OnSelect**-formelen evalueres.

## <a name="description"></a>Beskrivelse
**Select**-funksjonen simulerer en valgt handling på en kontroll som om brukeren skulle ha klikket eller trykket på denne kontrollen. Som et resultat av dette evalueres **OnSelect**-formelen i målkontrollen.

Bruk **Select** til å overføre en valgt handling til en overordnet kontroll. Denne typen overføring er standard virkemåte i, for eksempel gallerier. Som standard er **OnSelect**-egenskapen for en kontroll i et **[Galleri](../controls/control-gallery.md)** satt til **Velg( overordnet )** . På den måten kan du angi verdien for **OnSelect**-egenskapen for selve gallerikontrollen, og denne formelen evalueres uavhengig av hvor i galleriet brukeren klikker eller trykker.

Hvis du vil at en eller flere kontroller i galleriet skal utføre andre handlinger enn de vanlige handlingene i galleriet, kan du angi **OnSelect**-egenskapen for disse kontrollene til noe annet enn standardverdien. Du kan la standardverdiene for **OnSelect**-egenskapene for de fleste kontrollene i galleriet stå uendret hvis du vil at de skal utføre den samme handlingen som selve galleriet.

**Velg** stiller **OnSelect** for målet i kø for senere behandling, som kan skje når gjeldende formel har blitt ferdig evaluert. **Velg** fører ikke til at **OnSelect** for målet evalueres umiddelbart. **Velg** venter heller ikke på at **OnSelect** skal bli ferdig evaluert.

**Velg** kan ikke krysse grensene for beholderkontroller, for eksempel et galleri eller et skjema. Kontroller i en beholderkontroll kan bare være emne for en **Select**-funksjon i formler som er i samme beholderkontrollen. Du kan ikke bruke **Select** på tvers av skjermer.

Du kan bruke **Select** bare med kontroller som har en **OnSelect**-egenskap.

Du kan bare bruke **Select** i [formler for virkemåte](../working-with-formulas-in-depth.md).

En kontroll kan ikke **Select** seg selv direkte eller indirekte gjennom andre kontroller.

## <a name="syntax"></a>Syntaks
**Select**( *Control* )

* *Control* – obligatorisk.  Kontrollen for å velge på vegne av brukeren.

## <a name="examples"></a>Eksempler

#### <a name="basic-usage"></a>Grunnleggende bruk

1. Legg til en **[Knapp](../controls/control-button.md)** , og gi den det nye navnet **Knapp1** hvis den har et annet navn.

1. Angi **OnSelect**-egenskapen for **Knapp1** i denne formelen:

    **Varsle( «Hello World» )**

1. Legg til en annen **Knapp** på samme skjerm, og angi **OnSelect**-egenskapen for den i denne formelen:

    **Velg ( Knapp1 )**

1. Velg den andre knappen mens du holder nede ALT-tasten.

    Det vises et varsel øverst i appen. **OnSelect**-egenskapen for **Knapp1** genererte dette varselet.

    ![En animasjon som viser innstillingene for OnSelect-egenskapen for de to knappene og varselet når det klikkes på den andre knappen](media/function-select/basic-select.gif)

#### <a name="gallery-control"></a>Gallerikontroll

1. Legg til en loddrett **[Galleri](../controls/control-gallery.md)** -kontroll som inneholder andre kontroller.

    ![Velg et loddrett galleri som inneholder kontroller](media/function-select/select-gallery.png)

2. Angi **OnSelect**-egenskapen for galleriet i denne formelen:
 
    **Varsle ( «Galleriet er valgt» )**

3. Klikk eller trykk på bakgrunnen eller en kontroll i galleriet mens du holder nede ALT-tasten.

    Alle handlinger viser varselet **Galleriet er valgt** øverst i appen.

    Bruk **OnSelect**-egenskapen til å angi standardhandlingen som skal utføres når brukeren klikker eller trykker på et element i galleriet.

5. Angi **OnSelect**-egenskapen for bildekontrollen i denne formelen:

    **Varsle( «Bildet er valgt», vellykket )**

6. Klikk eller trykk på de ulike elementene i galleriet mens du holder nede ALT-tasten.

    Når du klikker eller trykker på en kontroll i galleriet med unntak av bildet, vises **Galleriet er valgt** som før. Når du klikker eller trykker på bildet, vises **Bildet er valgt**.
 
    Bruk individuelle kontroller i galleriet for å utføre handlinger som er forskjellige fra standardhandlingen i galleriet.

    ![En animasjon som viser standardverdien for OnSelect-egenskapen for en gallerikontroll, i tillegg til en kontroll som tar en annen handling](media/function-select/gallery-select.gif)
