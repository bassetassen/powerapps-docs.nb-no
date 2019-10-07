---
title: 'Kolonnekontroll: referanse | Microsoft Docs'
description: Dette emnet inneholder informasjon om Kolonnekontroll i Microsoft PowerApps.
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/05/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bb98295a5ecac6bf12af965e4ae6c668b1900af5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71986834"
---
# <a name="column-control-in-powerapps"></a>Kolonnekontroll i PowerApps
Leverer skjermopplevelsen for et enkelt felt i en [**Datatabellkontroll**](control-data-table.md).

## <a name="description"></a>Beskrivelse
[**Datatabellkontrollen**](control-data-table.md) viser et datasett i et tabellformat, og hver kolonne i et tabellformatet representeres med en **Kolonnekontroll**. **Kolonnekontrollen** inneholder egenskaper som skaperen av appen kan bruke til å tilpasse kolonnens utseende og virkemåte.

## <a name="capabilities"></a>Funksjoner
### <a name="now-available"></a>Nå tilgjengelig
* Endre bredden på en **Kolonnekontroll**.
* Endre teksten på en **Kolonnekontroll**.
* Du navigerer ved å klikke eller trykke på verdien i en **Kolonnekontroll**.

### <a name="not-yet-available"></a>Ikke tilgjengelig
* Tilpass utseende til en **Kolonnekontroll**.

### <a name="known-issues"></a>Kjente problemer
* Egenskapen **Synlig** fungerer ikke ennå.

## <a name="properties"></a>Egenskaper
* **DisplayName** – teksten som vises i kolonnens topptekst.
  
  > [!NOTE]
  > Denne egenskapen vil snart bli endret til **HeaderText**.
  > 
  > 
* **IsHyperlink** – en verdi som angir om dataene i kolonnen bør understrekes for å angi at det er en hyperkobling.
* [**Bredde**](properties-size-location.md) – avstanden mellom **Kolonnekontrollens** venstre og høyre kant.

## <a name="examples"></a>Eksempler
### <a name="resize-a-column"></a>Endre størrelse på en kolonne
1. Opprett en tom app for nettbrett.
2. Klikk eller trykk på **Datatabell** på **Sett inn**-fanen, og deretter endrer du størrelsen i **Datatabell**-kontrollen slik at den dekker hele skjermen.
3. Klikk eller trykk på Pil ned til høyre for **Ingen datakilde er valgt** i den høyre ruten, og deretter klikker eller trykker du på **Legg til en datakilde**.
4. Klikk eller trykk på tilkoblingen for Common Data Service-databasen din i listen over tilkoblinger.
5. Klikk eller trykk på **Konto** i listen over enheter, og deretter klikker eller trykker du på **Koble til**.
   
    **Datatabellkontrollen** er initialisert og viser et sett med standardfelt.
6. Klikk eller trykk på kolonnen **Fullt navn**.
   
    ![Kolonnekontroll valgt](./media/control-column/pre-resize-column.png)
7. Dra i adorner på høyre side for å endre størrelsen på feltet.
   
    ![Størrelsen på Kolonnekontrollen er endret](./media/control-column/post-resize-column.png)


## <a name="accessibility-guidelines"></a>Retningslinjer for tilgjengelighet
### <a name="screen-reader-support"></a>Kundestøtte for skjermlesere
* **DisplayName** må være tilstede.
