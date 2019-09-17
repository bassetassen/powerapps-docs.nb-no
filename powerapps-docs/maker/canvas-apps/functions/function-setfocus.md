---
title: SetFocus-funksjonen | Microsoft Docs
description: Referanse informasjon, inkludert syntaks, for SetFocus-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: cdf34c3c4909697b70a105e5145620ab5bd31ea9
ms.sourcegitcommit: 5899d37e38ed7111d5a9d9f3561449782702a5e9
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 09/17/2019
ms.locfileid: "71038143"
ms.PowerAppsDecimalTransform: true
---
# <a name="setfocus-function-in-powerapps"></a>SetFocus-funksjonen i PowerApps
Flytter inn data fokus til en bestemt kontroll. 

## <a name="description"></a>Beskrivelse
**SetFocus** -funksjonen gir en kontroll til inn data fokuset.  Brukerens taste trykk mottas deretter av denne kontrollen, slik at de kan skrive inn i en tekst inn data-kontroll eller bruke *Enter* -tasten til å velge en knapp.  Brukeren kan også bruke *tabulatortasten* , berøring, mus eller andre bevegelser til å flytte inn data fokus. Virke måten til *tab* -nøkkelen styres av [egenskapen **TabIndex** ](../controls/properties-accessibility.md).

Bruk **SetFocus** -funksjonen til å angi fokus når (hver med et eksempel nedenfor):
- en nylig eksponert eller aktivert inn data kontroll, for å veilede brukeren i det som kommer så videre og for raskere data registrering.
- et skjema Valide res for å fokusere og vise den avvikende inn data kontrollen for rask løsing.
- Det vises en skjerm for å fokusere på den første inn data kontrollen med **OnVisible** -egenskapen til [**skjermen**](../controls/control-screen.md).

Kontrollen med fokus kan være visuelt forskjellig basert på [**FocusedBorderColor**](../controls/properties-color-border.md) -og [**FocusedBorderThickness**](../controls/properties-color-border.md) -egenskapene.

## <a name="limitations"></a>Begrensninger

**SetFocus** kan bare brukes med:
- [**Knapp**](../controls/control-button.md) -kontroll
- [**Ikon**](../controls/control-shapes-icons.md) -kontroll
- [**Bilde**](../controls/control-image.md) -kontroll
- [**Etikett**](../controls/control-text-box.md)-kontrollen
- [**Allowimenetworkaccess**](../controls/control-text-input.md) -kontroll

Du kan ikke angi fokus til kontroller som er i en [**Galleri**](../controls/control-gallery.md) -kontroll, [**redigerings skjema**](../controls/control-form-detail.md) -kontroll eller- [komponent](../create-component.md).  **SetFocus** kan brukes med en kontroll på en scrollbale-skjerm.

Du kan bare angi fokus til kontroller på samme skjerm som formelen som inneholder **SetFocus** -kallet.

Forsøk på å angi fokus til en kontroll som har egenskapen [**Display Mode**](../controls/properties-core.md) satt til **deaktivert** , har ingen virkning.  Fokuset vil være der det var tidligere.

På Apple iOS vises bare Soft keyboard automatisk hvis **SetFocus** ble startet av en direkte bruker handling.  Hvis du for eksempel aktiverer fra **OnSelect** -egenskapen for en knapp, vises det myke tastaturet mens du aktiverer fra et skjerm bilde **OnVisible** . 

Du kan bare bruke **SetFocus** i [formler for virke måte](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaks
**SetFocus** ( *Kontroll* )

* *Control* – obligatorisk.  Kontrollen som skal gi inn data fokuset.

## <a name="examples"></a>Eksempler

### <a name="focus-on-a-newly-exposed-or-enabled-input-control"></a>Fokuser på en nylig eksponert eller aktivert inn data kontroll

Mange handle kurver gir kunden mulighet til å bruke leverings adressen som fakturerings adresse, og du trenger å skrive inn samme informasjon to ganger.  Hvis en annen fakturerings adresse er ønsket, er tekst inn data boksene for fakturerings adresse aktivert, og det er nyttig å veilede kunden til disse nylig aktiverte kontrollene for raskere data registrering.  

![Animasjon av å velge å bruke en egen definert fakturerings adresse, med fokus flyttet til inn data kontrollen for fakturerings navn som et resultat, ved å deaktivere automatisk synkronisering med leverings adresser](media/function-setfocus/shipping-billing.gif)

Det finnes mange formler i spill av her, men den som flytter fokus, er på **OnUncheck** -egenskapen for **avmerkings boks** -kontrollen:

```powerappa-dot
SetFocus( BillingName ) 
```

Du kan også bruke *tabulatortasten* til å flytte fokus raskt fra ett felt til et annet.  *Tabulatortasten* ble ikke brukt i animasjonen for å illustrere bedre.

Slik oppretter du dette eksemplet:
1. Opprett en ny app.
1. Legg til [ **etikett** kontroller](../controls/control-text-box.md) med teksten «leverings adresse», «navn:», «adresse:», «fakturerings adresse», «navn:» og «adresse:», og plasser dem som vist i animasjonen.
1. Legg til en [ **tekst inn data** -kontroll](../controls/control-text-input.md) , og gi den det nye navnet **ShippingName**.
1. Legg til en [ **tekst inn data** -kontroll](../controls/control-text-input.md) , og gi den det nye navnet **ShippingAddress**.
1. Legg til en [ **avmerkings boks** -kontroll](../controls/control-check-box.md) , og gi den **SyncAddresses**.
1. Angi **tekst** -egenskapen for denne kontrollen til formelen `"Use Shipping address as Billing address"`.
1. Legg til en [ **tekst inn data** -kontroll](../controls/control-text-input.md) , og gi den det nye navnet **BillingName**.
1. Angi **Default** -egenskapen for denne kontrollen til formelen `ShippingName`.
1. Angi **Display Mode** -egenskapen for denne kontrollen til formelen `If( SyncAddresses.Value; DisplayMode.View; DisplayMode.Edit )`.  Dette vil automatisk aktivere eller deaktivere denne kontrollen basert på tilstanden til avmerkings boks kontrollen.
1. Legg til en [ **tekst inn data** -kontroll](../controls/control-text-input.md) , og gi den det nye navnet **BillingAddress**.
1. Angi **Default** -egenskapen for denne kontrollen til formelen `ShippingAddress`.
1. Angi **Display Mode** -egenskapen for denne kontrollen til formelen `If( SyncAddresses.Value; DisplayMode.View; DisplayMode.Edit )`.  Dette vil automatisk aktivere eller deaktivere denne kontrollen basert på tilstanden til avmerkings boks kontrollen.
1. Angi **standard** -egenskapen for avmerkings boksen til formelen `true`.  Dette er standard fakturerings adressen som bruker samme verdi som leverings adressen.
1. Angi **OnCheck** -egenskapen for avmerkings boksen til formelen `Reset( BillingName );; Reset( BillingAddress )`.  Hvis brukeren velger å synkronisere leverings-og fakturerings adresser, fjerner dette bruker inn data i fakturerings adresse feltene som tillater **standard** egenskapene i hver av dem for å hente verdiene fra de tilsvarende leverings adresse feltene.
1. Angi **OnUncheck** -egenskapen for avmerkings boksen til formelen `SetFocus( BillingName )`.  Hvis brukeren velger å ha en annen fakturerings adresse, flytter dette fokuset til den første kontrollen i fakturerings adressen.  Kontrollene er allerede aktivert på grunn av **Display Mode** -egenskapene.

### <a name="focus-on-validation-issues"></a>Fokuser på Valide Rings problemer

> [!NOTE]
> Selv om dette eksemplet ser ut til å være en **redigerings skjema** -kontroll, **støttes dessverre ikke** denne kontrollen ennå.  I stedet bruker dette eksemplet en skjerm som kan rulles til å være vert for inn data kontrollene.

Når du validerer et skjema, kan det være nyttig å ikke bare vise en melding hvis det er et problem, men også bruke feltet som avviker.  Det kan være spesielt nyttig hvis det aktuelle feltet rulles ut på skjermen og ikke vises.

![En animasjon av Valide ring av et data registrerings skjema og som ikke bare har en melding som vises, men som også angir inn data fokuset til den avvikende inn data kontrollen, selv om den er rullet ut av skjermen.](media/function-setfocus/scrollable-screen.gif)

I denne animasjonen trykkes Valide Rings knappen gjentatte ganger til alle feltene er fylt ut på riktig måte.  Vær oppmerksom på at muse pekeren ikke flyttes ned øverst på skjermen.   I stedet har **SetFocus** -funksjonen flyttet inn data fokuset til kontrollen som krever oppmerksomhet, med denne formelen:

```powerapps-comma
If( IsBlank( Name ); 
        Notify( "Name requires a value"; Error );; SetFocus( Name );
    IsBlank( Street1 ); 
        Notify( "Street Address 1 requires a value"; Error );; SetFocus( Street1 );
    IsBlank( Street2 ); 
        Notify( "Street Address 2 requires a value"; Error );; SetFocus( Street2 );
    IsBlank( City ); 
        Notify( "City requires a value"; Error );; SetFocus( City );
    IsBlank( County ); 
        Notify( "County requires a value"; Error );; SetFocus( County );
    IsBlank( StateProvince ); 
        Notify( "State or Province requires a value"; Error );; SetFocus( StateProvince );
    IsBlank( PostalCode ); 
        Notify( "Postal Code requires a value"; Error );; SetFocus( PostalCode );
    IsBlank( Phone ); 
        Notify( "Contact Phone requires a value"; Error );; SetFocus( Phone );
    Notify( "Form is Complete"; Success )
)
```

Slik oppretter du dette eksemplet:
1. Opprett en ny, tom telefon app.
1. Velg **ny skjerm**på **Sett inn** -menyen, og velg deretter **Rullbar**.
1. I den midterste delen av skjermen kan du legge til **tekst inn data** -kontroller og gi navn til **navn**, **Street1**, **Street2**, **by**, **fylke**, **del stat område**, **post nummer**og **telefon**. Legg til **etikett** -kontrollene over hver av dem for å identifisere feltene.  Du må kanskje endre størrelsen på inndelingen hvis den ikke er lang nok til å få plass til alle kontrollene.
1. Legg til en merke [ **ikon** kontroll](../controls/control-shapes-icons.md) øverst på skjermen, over den rullbare inndelingen.  
1. Angi **OnSelect** -egenskapen for ikon-kontrollen til formelen `If( IsBlank( ...` som er angitt ovenfor.

### <a name="focus-when-displaying-a-screen"></a>Fokuser når du viser en skjerm

> [!NOTE]
> Selv om dette eksemplet ser ut til å være en **redigerings skjema** -kontroll, støttes ikke Unforutnatley- **SetFocus** ennå av denne kontrollen.  I stedet bruker dette eksemplet en skjerm som kan rulles til å være vert for inn data kontrollene.

På samme måte som når du viser en inn data-kontroll, kan du fokusere på den første inn data-kontrollen for raskere data registrering ved visning av en data registrerings skjerm.

![En animasjon som viser en side-ved-side-sammenligning av bruk av SetFocus, kontra ikke å bruke den når du viser en data registrerings skjerm](media/function-setfocus/visible-setfocus.gif)

I denne animasjonen bruker ikke data registrerings skjermen til venstre til å bruke **SetFocus**.  Når det ikke vises en inn data kontroll, har du fokus, som krever at brukeren velger tab, berører, musen eller bruker en annen metode for å fokusere på **navne** feltet før en verdi kan skrives inn i det.

Til høyre har vi nøyaktig samme app med **OnVisible** -egenskapen for data registrerings skjermen angitt som denne formelen:

```powerapps-comma
SetFocus( Name )
```

Dette angir fokuset til **navn** -feltet automatisk.  Brukeren kan begynne å skrive inn og tab mellom felt umiddelbart uten å måtte gjøre noe tidligere.

Slik oppretter du dette eksemplet:
1. Opprett appen "fokus på Valide Rings problemer" ovenfor.
1. Angi **OnVisible** -egenskapen til formelen `SetFocus( Name )`på dette skjerm bildet.
1. Legg til en ekstra skjerm.
1. Legg til en [ **knapp** -kontroll](../controls/control-button.md).
1. Angi **OnSelect** -egenskapen for denne kontrollen til formelen `Navigate( Screen1 )`.
1. Forhånds Vis appen fra denne skjermen.  Trykk på knappen.  **OnVisible** -formelen evalueres, og **navn** -feltet vil automatisk være i fokus.
