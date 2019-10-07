---
title: Signaler fra Acceleration, App, Compass, Connection og Location | Microsoft Docs
description: Referanseinformasjon for sensorer for Acceleration, App, Compass, Connection og Location i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/29/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a06217470482eccdf368279eaabcd297bbf73ce5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983351"
---
# <a name="acceleration-app-compass-connection-and-location-signals-in-powerapps"></a>Signaler fra Acceleration, App, Compass, Connection og Location i PowerApps

Returnerer informasjon om appmiljøet, som hvor brukeren befinner seg i verden og hvilken skjerm som vises.

## <a name="description-and-syntax"></a>Beskrivelse og syntaks

Signaler er verdier som kan endres når som helst, uavhengig av hvordan brukeren kan samhandle med appen. Formler som er basert på signaler, beregnes automatisk på nytt når disse verdiene endres.

Signaler returnerer vanligvis en [post](../working-with-tables.md#records) med informasjon. Du kan bruke og lagre denne informasjonen som en post, eller du kan trekke ut enkelte egenskaper ved bruk av **.** [operatoren](operators.md).

> [!NOTE]
> Funksjonene **AKS ele rasjon** og **kompass** returnerer nøyaktige verdier i en opprinnelig spiller, som for eksempel på IOS eller Android, men disse funksjonene returnerer null verdier når du oppretter eller endrer en app i nett leseren.

### <a name="acceleration"></a>Acceleration

**Acceleration**-signalet returnerer enhetens akselerasjon i tre dimensjoner, relativ til enhetsskjermen. Akselerasjon måles i *g* enheter på 9,81 m/sekund<sup>2</sup> eller 32,2 ft/sekund<sup>2</sup> (akselerasjonen som jorden overfører til objekter på overflaten på grunn av tyngdekraft).

| Egenskap | Beskrivelse |
| --- | --- |
| **Acceleration.X** |Høyre og venstre.  Høyre er et positivt tall. |
| **Acceleration.Y** |Fremover og bakover.  Fremover er et positivt tall. |
| **Acceleration.Z** |Opp og ned.  Opp er et positivt tall. |

### <a name="app"></a>App

**App** -objektet inneholder et signal som angir hvilken skjerm som vises.

| Egenskap | Beskrivelse |
| --- | --- |
| **App.ActiveScreen** |Skjerm som vises. Returnerer et skjerm objekt, som du kan bruke til å referere til egenskaper på skjermen eller sammenligne med en annen skjerm for å bestemme hvilken skjerm som vises. Du kan bruke **[tilbake](function-navigate.md)** -eller **[Naviger](function-navigate.md)** -funksjonen til å endre skjermen som vises. |

Mer informasjon: Dokumentasjon for [ **app** -objekt](object-app.md) .

### <a name="compass"></a>Compass
**Kompass**-signalet returnerer kompassretningen øverst på skjermen. Overskriften er basert på magnetisk nord.

| Egenskap | Beskrivelse |
| --- | --- |
| **Compass.Heading** |Retning i grader.  Returnerer et tall mellom 0 og 360, og 0 er nord. |

### <a name="connection"></a>Tilkobling
**Tilkobling**-signalet returnerer informasjonen om nettverkstilkoblingen. Hvis du befinner deg på en forbruksmålt linje, kan du begrense hvor mye data du sender eller mottar over nettverket.

| Egenskap | Beskrivelse |
| --- | --- |
| **Connection.Connected** |Returnerer en boolsk **sann**- eller **usann**-verdi som indikerer om enheten er tilkoblet nettverket. |
| **Connection.Metered** |Returnerer en boolsk **sann**- eller **usann**-verdi som indikerer om tilkoblingen er forbruksmålt. |

### <a name="location"></a>Plassering
**Plassering**-signalet returnerer plasseringen til enheten basert på GPS (Global Positioning System) og annen enhetsinformasjon, som mobiltelefonkommunikasjon og IP-adresse.

Når en bruker får tilgang til plasseringsinformasjonen for første gang, kan det hende at enheten ber brukeren om å få lov til å bruke denne informasjonen.

Når plasseringen endrer seg, vil tjenestene som er avhengig av plasseringen kontinuerlig beregnes på nytt. Dette forbruker enhetsbatteriet. Hvis du ønsker å spare batteriet, kan du bruke **[Enable](function-enable-disable.md)** - og **[Disable](function-enable-disable.md)** -funksjonene for å slå plasseringsoppdateringer på og av. Plasseringen slås automatisk av hvis skjermen som vises ikke er avhengig av plasseringsinformasjon.

| Egenskap | Beskrivelse |
| --- | --- |
| **Location.Altitude** |Returnerer et tall som angir høyden, målt i fot, over havet. |
| **Location.Latitude** |Returnerer et tall, fra -90 til 90, som angir breddegraden, som målt i grader fra ekvator. Et positivt tall angir en plassering som er nord for ekvator. |
| **Location.Longitude** |Returnerer et tall, fra 0 to 180, som angir lengdegraden, som målt i grader vest for Greenwich i England. |

## <a name="examples"></a>Eksempler
I et felt i fotball kan en mugg inneholde en telefon fra Mound til en Catcher på hjemme platen. Telefonen ligger flat mot bakken, toppen av skjermen peker mot mottakeren, og pitcheren legger ikke inn noen rotasjoner. På denne plasseringen har telefonen nettverkstjeneste som er forbruksmålt, men ingen trådløs Internett. **PlayBall**-skjermen vises.   

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Location.Latitude** |Returnerer breddegraden til gjeldende plassering. Feltet befinner seg på kart koordinater 47,591 N, 122,333 W. |47,591<br><br>Breddegraden endres automatisk mens ballen beveger seg mellom pitcheren og mottakeren. |
| **Location.Longitude** |Returnerer lengdegraden til gjeldende plassering. |122,333<br><br>Lengdegraden endres automatisk mens ballen beveger seg mellom pitcheren og mottakeren. |
| **Plassering** |Returnerer breddegraden og lengdegraden til den gjeldende plasseringen, som en post. |{&nbsp;breddegrad:&nbsp;47,591, lengdegrad:&nbsp;122,333&nbsp;} |
| **Compass.Heading** |Returnerer kompassretningen øverst på skjermen. I dette feltet er Home-platen omtrent hoved kontor fra muggens Mound. |230,25 |
| **Acceleration.X** |Returnerer akselerasjonen til enheten side til side. Pitcheren kaster telefonen rett frem med tanke på den øverste skjermkanten, slik at enheten ikke akselererer side til side. |0 |
| **Acceleration.Y** |Returnerer akselerasjonen fra enheten foran og bakover. Pitcheren gir innledningsvis enheten en stor akselerasjon når han kastet enheten, fra 0-145 kilometer i timen (40 meter per sekund) i et halvt sekund. Etter at enheten er i luften og ignorerer friksjonen, akselererer ikke enheten ytterligere. Enheten akselererer når mottakeren tar tak i den, og får den til å stoppe. |8,2, mens pitcheren kaster enheten.<br><br>0, mens enheten er i luften.<br><br>-8.2, idet mottakeren får tak i enheten. |
| **Acceleration.Z** |Returnerer akselerasjonen til enheten fra øverst til nederst. Mens enheten er i luften, opplever den effekten av tyngdekraften. |0, mens pitcheren kaster enheten.<br><br>1, mens enheten er i luften.<br><br>0, idet mottakeren får tak i enheten. |
| **Akselerasjon** |Returnerer akselerasjonen som en post. |KRYSSET 0, Y: 264, Z: 0} når muggen genererer enheten. |
| **Connection.Connected** |Returnerer en boolsk verdi som indikerer om enheten er tilkoblet nettverket |**sann** |
| **Connection.Metered** |Returnerer en boolsk verdi som indikerer om tilkoblingen er forbruksmålt |**sann** |
| **App.ActiveScreen = PlayBall** |Returnerer en boolsk verdi som indikerer om **PlayBall** vises. |**sann** |
| **App.ActiveScreen.Fill** |Returnerer bakgrunnsfargen for skjermbildet som vises. |**Color.Green** |

