---
title: Med funksjonen | Microsoft Docs
description: Referanse informasjon, inkludert syntaks, for with-funksjonen i PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/15/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c8d793fcfd2992a781f92d529002e22a34a9df5a
ms.sourcegitcommit: 742a5a21e73a811e9cea353d8275f09c22366afc
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/29/2019
ms.locfileid: "70130333"
---
# <a name="with-function-in-powerapps"></a>Med-funksjonen i PowerApps
Beregner verdier og utfører handlinger for en enkelt [post](../working-with-tables.md#records), inkludert innebygde poster med navngitte verdier.

## <a name="description"></a>Beskrivelse

**With** -funksjonen evaluerer en formel for én enkelt post.  Formelen kan beregne en verdi og/eller utføre handlinger, for eksempel endring av data eller arbeide med en tilkobling.  Bruk [ **ForAll** -funksjonen](function-forall.md) til å evaluere en formel for alle postene i en tabell med poster.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Bruk **med** for å forbedre lesbarheten til kompliserte formler ved å dele den opp i mindre navngitte del formler.  Disse navngitte verdiene fungerer som enkle lokale variabler som er begrenset til området for **med**.  Den samme syn tak sen for innebygd post som brukes med [ **UpdateContext** -funksjonen](function-updatecontext.md) , kan brukes med **with**.  Bruk **med** er foretrukket over kontekst eller globale variabler, ettersom den er selv inkludert, enkel å forstå og kan brukes i enhver deklarativ formel kontekst.  

Bruk **med** for å få tilgang til feltene i posten som returneres av funksjoner, for eksempel [**oppdatering**](function-patch.md) eller [**treff**](function-ismatch.md).  **Med** inneholder verdien fra disse funksjonene lenge nok til å brukes i videre beregninger eller handlinger.  

Hvis *post* -argumentet til **with** er en feil, returneres denne feilen av funksjonen, og *formelen* evalueres ikke.

## <a name="syntax"></a>Syntaks
**Med** ( *Post*, *formel* )

* *Post* – obligatorisk. Oppføringen som skal utføres på.  Bruk den innebygde syn tak sen for navne verdier`{ name1: value1, name2: value2, ... }`
* *Formel* – obligatorisk.  Formelen som skal evalueres for *post*.  Formelen kan referere til noen av feltene i *posten* direkte som et post område.

## <a name="examples"></a>Eksempler

### <a name="simple-named-values"></a>Enkle navngitte verdier

```powerapps-dot
With( { radius: 10, 
        height: 15 },
    Pi() * (radius*radius) * height
)
// Result: 4712.38898038 (as shown in a label control)
```

Dette eksemplet bruker en post med navngitte verdier til å beregne volumet i en sylinder.  **Med** brukes til å hente alle inn data verdiene sammen, noe som gjør det enkelt å skille dem fra selve beregningen.  

### <a name="nested-with"></a>Nestet med

![Rente kalkulator med funksjon](media/function-with/interest-calculator.gif)

```powerapps-dot
With( { AnnualRate: RateSlider/8/100,        // slider moves in 1/8th increments and convert to decimal
        Amount: AmountSlider*10000,          // slider moves by 10,000 increment
        Years: YearsSlider,                  // slider moves in single year increments, no adjustment required
        AnnualPayments: 12 },                // number of payments per year
      With( { r: AnnualRate/AnnualPayments,  // interest rate
              P: Amount,                     // loan amount
              n: Years*AnnualPayments },     // number of payments
            r*P / (1 - (1+r)^-n)             // standard interest calculation
      )
)  
```

Dette eksemplet nester **med** funksjoner for å opprette en beregning på to nivåer for [månedlige](https://en.wikipedia.org/wiki/Mortgage_calculator#Monthly_payment_formula)utbetalinger.  Så lenge det ikke er noen konflikt, er alle ytter verdiene **med** navngitte verdier tilgjengelige i innersen **med**.

Siden Glide bryte ren bare kan flytte i trinn på 1, blir glidebryterne fordelt eller multiplisert for å opprette en egen definert økning.  Når det gjelder rente satsen, har **RateSliders** **maksimum** -egenskapen satt til **48**, delt på 8 for et 1/8 prosent punkt økning og delt på 100 for å konvertere fra en prosent til en desimal, som dekker områdets 0,125% til 6%.  Når det gjelder låne beløpet, har **AmountSlider** som er satt til **60** og multiplisert med 10 000, som dekker området 10 000 til 600 000.

**Med** blir automatisk beregnet på nytt etter hvert som glidebryterne flyttes, og den nye låne betalingen vises.  Ingen variabler brukes, og det er ikke nødvendig å bruke egenskapen **OnChange** for glidebryterne.

Her er de detaljerte instruksjonene for oppretting av denne appen:
1. Opprett en ny app.
2. Legg til en [ **Glidebryter** ](../controls/control-slider.md) , og gi den navnet **RateSlider**.  Angi **Maks** -egenskapen til 48.
3. Legg til en [ **etikett** -kontroll](../controls/control-text-box.md) til venstre for Glide kontrollen.  Angi **tekst** -egenskapen til **rente sats:** .
3. Legg til en **etikett** -kontroll til høyre for Glide kontrollen.  Angi **tekst** -egenskapen til formelen **RateSlider/&nbsp;8 &%** .
3. Legg til en ny **Glidebryter** -kontroll, og gi den navnet **AmountSlider**.  Angi **Maks** -egenskapen til 60.
3. Legg til en **etikett** -kontroll til venstre for denne Glide kontrollen.  Angi **tekst** -egenskapen til **låne beløp:** . 
3. Legg til en **etikett** -kontroll til høyre for denne Glide kontrollen.  Angi **tekst** -egenskapen til formelen **AmountSlider/8 * 10000**.
4. Legg til en ny **Glidebryter** -kontroll, og gi den navnet **YearsSlider**.  Angi **Maks** -egenskapen til 40.
3. Legg til en **etikett** -kontroll til venstre for denne Glide kontrollen.  Angi **tekst** -egenskapen til **«antall år:»** . 
3. Legg til en **etikett** -kontroll til høyre for denne Glide kontrollen.  Angi **tekst** -egenskapen til formelen **YearsSlider**.
5. Legg til en **etikett** -kontroll, og angi **tekst** -egenskapen til formelen som vises ovenfor.
3. Legg til en **etikett** -kontroll til venstre for den siste etikett-kontrollen.  Angi **tekst** -egenskapen til **«regelmessig månedlig betaling:»** .  

### <a name="primary-key-returned-from-patch"></a>Primær nøkkel returnert fra oppdatering

```powerapps-dot
With( Patch( Orders, Defaults( Orders ), { OrderStatus: "New" } ),
      ForAll( NewOrderDetails, 
              Patch( OrderDetails, Defaults( OrderDetails ), 
                     { Order: OrderID,          // from With's first argument, primary key of Patch result
                       Quantity: Quantity,      // from ForAll's NewOrderDetails table
                       ProductID: ProductID }   // from ForAll's NewOrderDetails table
              )
      )
)
```

Dette eksemplet legger til en post i **Order** -tabellen i SQL Server.  Deretter brukes den returnerte primær nøkkelen for ordren, som returneres av **patch** -funksjonen i **OrdreID** -feltet, til å opprette relaterte poster i **Ordredetaljer** -tabellen.  

### <a name="extracted-values-with-a-regular-expression"></a>Uttrukne verdier med et regulært uttrykk

```powerapps-dot
With( 
    Match( "PT2H1M39S", "PT(?:<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" ),
    Time( Value( hours ), Value( minutes ), Value( seconds ) )
)
// Result: 2:01 AM (as shown in a label control, use the Text function to see the seconds)
```

Dette eksemplet trekker ut timer, minutter og sekunder fra en ISO 8601 Duration-verdi, og bruker deretter disse del treffene til å opprette en dato/klokkeslett-verdi. 

Vær oppmerksom på at selv om del treff inneholder tall, er de fremdeles i en tekst streng.  Bruk [**Value**](function-value.md) -funksjonen til å konvertere til et tall før du utfører matematiske operasjoner.  

