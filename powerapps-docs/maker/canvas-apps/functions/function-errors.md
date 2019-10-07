---
title: Errors-funksjonen | Microsoft Docs
description: Referanseinformasjon, inkludert syntaks og eksempler for Errors-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/11/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 114474696f85980da315b6dd225250dc1b197805
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992782"
---
# <a name="errors-function-in-powerapps"></a>Errors-funksjonen i PowerApps
Gir feilinformasjon om tidligere endringer i en [datakilde](../working-with-data-sources.md).

## <a name="overview"></a>Oversikt
Feil kan skje når en [post](../working-with-tables.md#records) i en datakilde blir endret.  Det er mange mulige årsaker, inkludert nettverksbrudd, utilstrekkelige tillatelser og redigeringskonflikter.  

**[Patch](function-patch.md)** -funksjonen og andre datafunksjoner returnerer ikke feil direkte. I stedet returnerer de resultatet av operasjonen. Når en datafunksjon er utført, kan du bruke **Errors**-funksjonen til å hente detaljer om feil.  Du kan kontrollere om det finnes feil med **[IsEmpty]** -funksjonen i formelen **IsEmpty( Errors ( ... ) )** .

Du kan unngå feil før de skjer, ved hjelp av **[Validate](function-validate.md)** - og **[DataSourceInfo](function-datasourceinfo.md)** -funksjonene.  Du kan se [Slik arbeider du med datakilder](../working-with-data-sources.md) for flere forslag om hvordan du arbeider med og unngår feil.

## <a name="description"></a>Beskrivelse
**Errors**-funksjonen returnerer en [tabell](../working-with-tables.md) over feil, som inneholder følgende [kolonner](../working-with-tables.md#columns):

* **Post**.  Posten i datakilden som hadde feilen.  Denne kolonnen er *tom* hvis feilen oppstod under oppretting av en post.
* **Kolonne**.  Kolonnen som forårsaket feilen, hvis feilen kan tilskrives en enkelt kolonne. Hvis ikke vil denne være *tom*.
* **Melding**.  Beskrivelse av feilen.  Denne feilstrengen kan vises for sluttbrukeren.  Vær oppmerksom på at denne meldingen kan genereres av datakilden, at den kan være lang og inneholde rå kolonnenavn som kanskje ikke gir mening for brukeren.
* **Feil**.  En feilkode som kan brukes i formler for å bidra til å løse feilen:

| ErrorKind | Beskrivelse |
| --- | --- |
| ErrorKind.Conflict |En annen endring ble utført på samme post, noe som resulterte i en endringskonflikt.  Kjør **[Refresh](function-refresh.md)** -funksjonen for å laste inn posten på nytt, og prøv endringen på nytt. |
| ErrorKind.ConstraintViolation |En eller flere begrensninger ble brutt. |
| ErrorKind.CreatePermission |Det ble gjort et forsøk på å opprette en post, og den gjeldende brukeren har ikke tillatelse til å opprette poster. |
| ErrorKind.DeletePermission |Det ble gjort et forsøk på å slette en post, og den gjeldende brukeren har ikke tillatelse til å slette poster. |
| ErrorKind.EditPermission |Det ble gjort et forsøk på å redigere en post, og den gjeldende brukeren har ikke tillatelse til å redigere poster. |
| ErrorKind.GeneratedValue |Det ble gjort et forsøk på å endre en kolonne som datakilden genererer automatisk. |
| ErrorKind.MissingRequired |Verdien for en nødvendig kolonne mangler fra posten. |
| ErrorKind.None |Finner ingen feil. |
| ErrorKind.NotFound |Det ble gjort et forsøk på å redigere eller slette en post, men posten ble ikke funnet.  En annen bruker kan ha endret posten. |
| ErrorKind.ReadOnlyValue |Det ble gjort et forsøk på å endre en kolonne som er skrivebeskyttet. |
| ErrorKind.Sync |En feil ble rapportert av datakilden.  Kontroller meldingskolonnen for mer informasjon. |
| ErrorKind.Unknown |Det oppstod en feil, men av en ukjent type. |
| ErrorKind.Validation |Det ble oppdaget et generelt problem med validering, som ikke passet med en av de andre typene. |

Feil kan returneres for hele datakilden eller for en valgt rad, ved å gi *Post*-argumentet til funksjonen.  

**[Patch](function-patch.md)** , eller en annen datafunksjon, kan returnere en *tom* verdi, hvis for eksempel en post ikke kan opprettes. Du kan sende *tom* til **Errors**, og det vil returneres aktuell feilinformasjon i disse tilfellene.  Etterfølgende bruk av datafunksjoner på den samme datakilden, vil fjerne denne feilinformasjonen.

Tabellen som **Errors** returnerer, er [tom](function-isblank-isempty.md) hvis det ikke er noen feil, og den kan testes med **[IsEmpty](function-isblank-isempty.md)** -funksjonen.

## <a name="syntax"></a>Syntaks
**Errors**( *DataSource* [, *Record* ] )

* *DataSource* – nødvendig. Datakilden som du ønsker å returnere feil til.
* *Post* – valgfritt.  En bestemt post som du vil returnere feil til. Funksjonen returnerer feil for hele datakilden hvis du ikke angir dette argumentet.

## <a name="examples"></a>Eksempler
### <a name="step-by-step"></a>Trinn for trinn
I dette eksemplet skal vi arbeide med datakilden **IceCream**:

![](media/function-errors/icecream.png)

En bruker laster inn sjokolade-posten via appen til et skjema for dataregistrering og endrer verdien fpr **Antall** til 90.  Posten som skal arbeides med, er plassert i [kontekstvariabelen](../working-with-variables.md#use-a-context-variable) **EditRecord**:

* **UpdateContext ({RedigerPost: First (filter (IceCream, Flavor = "sjokolade")))**

**[Patch](function-patch.md)** -funksjonen blir brukt for å gjøre denne endringen i datakilden:

* **Patch( IceCream, EditRecord, Gallery.Updates )**

WHERE- **galleri. oppdateringer** evalueres til ** {kvantitet: 90} @no__t – 0, siden bare egenskapen **kvantitet** er endret.

Uheldigvis ble **Quantity** for Chocolate endret av noen andre til 80 like før **[Patch](function-patch.md)** -funksjonen ble startet.  PowerApps vil oppdage dette og ikke tillate at den motstridende endringen skal oppstå.  Du kan se etter denne situasjonen med formelen:

* **IsEmpty( Errors( IceCream, EditRecord ) )**

som returnerer **USANN**, fordi **Errors**-funksjonen returnerte følgende tabell:

| Post | Kolonne | Melding | Feil |
| --- | --- | --- | --- |
| Flavor «Sjokolade», antall: 100} |*tom* |«En annen bruker har endret posten som du prøver å endre. Last inn posten på nytt og prøv igjen.» |ErrorKind.Conflict |

Du kan plassere en etikett i skjemaet for å vise denne feilen til brukeren.

* Hvis du vil vise feilen, kan du angi etikettens **[Text](../controls/properties-core.md)** -egenskap til denne formelen:<br>
  **Label.Text = First(Errors( IceCream, EditRecord )).Message**

Du kan også legge til en **Last inn på nytt**-knapp på skjemaet, slik at brukeren effektivt kan løse konflikten.

* Hvis du vil vise knappen bare når en konflikt har oppstått, kan du angi knappens **[Visible](../controls/properties-core.md)** -egenskap til denne formelen:<br>
    **!IsEmpty( Lookup( Errors( IceCream, EditRecord ), Error = ErrorKind.Conflict ) )**
* For å gå tilbake til endringen der brukeren velger knappen, kan du angi **[OnSelect](../controls/properties-core.md)** -egenskapen til denne formelen:<br>
    **ReloadButton.OnSelect = Revert( IceCream, EditRecord )**

