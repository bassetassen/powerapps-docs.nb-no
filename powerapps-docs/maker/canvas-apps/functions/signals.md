---
title: Signaler fra Acceleration, App, Compass, Connection og Location | Microsoft Docs
description: Referanseinformasjon for sensorer for Acceleration, App, Compass, Connection og Location i PowerApps, inkludert syntaks og eksempler
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 18bd89549aa330b5da333dccfd723887db38a36e
ms.sourcegitcommit: 39c9b4cbc26617e302d46085d81c6d397e01fbf7
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/17/2019
ms.locfileid: "59671565"
---
# <a name="acceleration-app-compass-connection-and-location-signals-in-powerapps"></a>Signaler fra Acceleration, App, Compass, Connection og Location i PowerApps
Returnerer informasjon om appmiljøet, som hvor brukeren befinner seg i verden og hvilken skjerm som vises.  

## <a name="description-and-syntax"></a>Beskrivelse og syntaks
Alle signaler returnerer en [post](../working-with-tables.md#records) av informasjon. Du kan bruke og lagre denne informasjonen som en post, eller du kan trekke ut enkelte egenskaper ved bruk av **.** [operatoren](operators.md).

> [!NOTE]
> Den **akselerasjon** og **kompass** funksjoner returnerer nøyaktige verdier i en innebygd spiller som på iOS eller Android, men disse funksjonene returnerer nullverdier når du oppretter eller endrer en app i nettleseren.

### <a name="acceleration"></a>Acceleration
**Acceleration**-signalet returnerer enhetens akselerasjon i tre dimensjoner, relativ til enhetsskjermen. Akselerasjon måles i *g* enheter på 9,81 m/sekund<sup>2</sup> eller 32,2 ft/sekund<sup>2</sup> (akselerasjonen som jorden overfører til objekter på overflaten på grunn av tyngdekraft).

| Egenskap | Beskrivelse |
| --- | --- |
| **Acceleration.X** |Høyre og venstre.  Høyre er et positivt tall. |
| **Acceleration.Y** |Fremover og bakover.  Fremover er et positivt tall. |
| **Acceleration.Z** |Opp og ned.  Opp er et positivt tall. |

### <a name="app"></a>App
**App**-signalet returnerer informasjon om den kjørende appen.

| Egenskap | Beskrivelse |
| --- | --- |
| **App.ActiveScreen** | Skjermen som vises. Returnerer et skjermobjekt som du kan bruke til å henvise til egenskaper til skjermen, eller sammenligne med en annen skjerm for å bestemme hvilken skjerm som vises. Hvis du vil endre skjermen som vises, kan du bruke den **[tilbake](function-navigate.md)** eller **[Navigate](function-navigate.md)** funksjonen. |
| **App.Width** | Returnerer bredden på vinduet som appen kjører. Du kan bruke denne egenskapen i en formel når du angir den **bredde** -egenskapen for skjermen for å utvikle en responsive app.  |
| **App.Height** | Returnerer høyden på vinduet som appen kjører. Du kan bruke denne egenskapen i en formel når du angir den **høyde** -egenskapen for skjermen for å utvikle en responsive app. |
| **App.DesignWidth** | Returnerer bredden på appen i PowerApps Studio. Du kan bruke denne egenskapen i en formel når du angir den **bredde** -egenskapen for skjermen for å sikre en minimumsbredde i en responsive app.  |
| **App.DesignHeight** | Returnerer høyden på appen i PowerApps Studio. Du kan bruke denne egenskapen i en formel når du angir den **høyde** -egenskapen for skjermen for å sikre en minimumshøyden i en responsive app.  |
| **App.SizeBreakpoints** | En tabell med én kolonne med tall som avgrenser skjermstørrelse områder som den [ **Screen.Size** ](../controls/control-screen.md) egenskapen returnerer. Verdiene i denne tabellen kan endres for å tilpasse stoppunkt at alle appens skjermer bruk.

Den **App** objekt har også en [formel for virkemåte](../working-with-formulas-in-depth.md) som du kan angi.

| Egenskap  | Beskrivelse |
| --- | --- |
| **App.OnStart** | Virkemåten til appen når brukeren starter den. Produsentene ofte bruker denne egenskapen til å hente og hurtigbufring av data til samlinger med den **[samle inn](function-clear-collect-clearcollect.md)** funksjon, definere variabler med det **[angi](function-set.md)**, og navigere til en innledende skjermen med den **[Navigate](function-navigate.md)** funksjonen. Denne formelen evalueres før den første skjermen vises. Ingen skjermen er lastet inn, slik at du ikke kan angi kontekstvariabler med den **[UpdateContext](function-updatecontext.md)** funksjonen. Du kan imidlertid overføre kontekstvariablene med den **Navigate** funksjonen. |

Den **App** objektet vises øverst i den hierarkiske listen over kontroller i den venstre navigasjonsruten, og du kan velge dette objektet som en kontroll i en skjerm. Når du merker du objektet, kan du vise og redigere en av egenskapene for Hvis du velger denne egenskapen i rullegardinlisten til venstre for formellinjen.  

Når du har endret den **OnStart** -egenskapen, kan du teste den ved å hvile over den **App** objektet i den venstre navigasjonsruten, å velge ellipsen (...) som vises, og deretter velge **kjøre OnStart**. I motsetning til når appen er lastet for første gang, angis eksisterende samlinger og variabler allerede. Bruk den **[ClearCollect](function-clear-collect-clearcollect.md)** funksjonen i stedet for den **samle inn** funksjonen til å begynne med tom samlinger.

 ![Hurtigmenyen for App-element med kjøre OnStart](media/appobject-runonstart.png)

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

Når plasseringen endrer seg, vil tjenestene som er avhengig av plasseringen kontinuerlig beregnes på nytt. Dette forbruker enhetsbatteriet. Hvis du ønsker å spare batteriet, kan du bruke **[Enable](function-enable-disable.md)**- og **[Disable](function-enable-disable.md)**-funksjonene for å slå plasseringsoppdateringer på og av. Plasseringen slås automatisk av hvis skjermen som vises ikke er avhengig av plasseringsinformasjon.

| Egenskap | Beskrivelse |
| --- | --- |
| **Location.Altitude** |Returnerer et tall som angir høyden, målt i fot, over havet. |
| **Location.Latitude** |Returnerer et tall, fra -90 til 90, som angir breddegraden, som målt i grader fra ekvator. Et positivt tall angir en plassering som er nord for ekvator. |
| **Location.Longitude** |Returnerer et tall, fra 0 to 180, som angir lengdegraden, som målt i grader vest for Greenwich i England. |

## <a name="examples"></a>Eksempler
I et fotball-felt, en pitcheren kaster en telefon fra pitcherens mound til en mottaker på home-platen. Telefonen ligger flat mot bakken, toppen av skjermen peker mot mottakeren, og pitcheren legger ikke inn noen rotasjoner. På denne plasseringen har telefonen nettverkstjeneste som er forbruksmålt, men ingen trådløs Internett. **PlayBall**-skjermen vises.   

| Formel | Beskrivelse | Resultat |
| --- | --- | --- |
| **Location.Latitude** |Returnerer breddegraden til gjeldende plassering. Feltet er plassert på kartkoordinater 47,591 N, 122,333 W. |47,591<br><br>Breddegraden endres automatisk mens ballen beveger seg mellom pitcheren og mottakeren. |
| **Location.Longitude** |Returnerer lengdegraden til gjeldende plassering. |122,333<br><br>Lengdegraden endres automatisk mens ballen beveger seg mellom pitcheren og mottakeren. |
| **Plassering** |Returnerer breddegraden og lengdegraden til den gjeldende plasseringen, som en post. |{&nbsp;breddegrad:&nbsp;47,591, lengdegrad:&nbsp;122,333&nbsp;} |
| **Compass.Heading** |Returnerer kompassretningen øverst på skjermen. I dette feltet er home-platen omtrent Sørvest fra pitcherens mound. |230,25 |
| **Acceleration.X** |Returnerer akselerasjonen til enheten side til side. Pitcheren kaster telefonen rett frem med tanke på den øverste skjermkanten, slik at enheten ikke akselererer side til side. |0 |
| **Acceleration.Y** |Returnerer akselerasjonen fra enheten foran og bakover. Pitcheren gir innledningsvis enheten en stor akselerasjon når han kastet enheten, fra 0-145 kilometer i timen (40 meter per sekund) i et halvt sekund. Etter at enheten er i luften og ignorerer friksjonen, akselererer ikke enheten ytterligere. Enheten akselererer når mottakeren tar tak i den, og får den til å stoppe. |8,2, mens pitcheren kaster enheten.<br><br>0, mens enheten er i luften.<br><br>-8.2, idet mottakeren får tak i enheten. |
| **Acceleration.Z** |Returnerer akselerasjonen til enheten fra øverst til nederst. Mens enheten er i luften, opplever den effekten av tyngdekraften. |0, mens pitcheren kaster enheten.<br><br>1, mens enheten er i luften.<br><br>0, idet mottakeren får tak i enheten. |
| **Akselerasjon** |Returnerer akselerasjonen som en post. |{ X: 0, Y: 264, Z: 0} som pitcheren kaster enheten. |
| **Connection.Connected** |Returnerer en boolsk verdi som indikerer om enheten er tilkoblet nettverket |**sann** |
| **Connection.Metered** |Returnerer en boolsk verdi som indikerer om tilkoblingen er forbruksmålt |**sann** |
| **App.ActiveScreen = PlayBall** |Returnerer en boolsk verdi som indikerer om **PlayBall** vises. |**sann** |
| **App.ActiveScreen.Fill** |Returnerer bakgrunnsfargen for skjermbildet som vises. |**Color.Green** |

