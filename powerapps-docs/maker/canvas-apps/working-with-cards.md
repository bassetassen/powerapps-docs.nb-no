---
title: Å forstå datakort i Microsoft Docs
description: Bruk skjemakort til å samle inn og vise informasjon fra en datakilde i PowerApps.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/26/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: db0e42a45af217e9e5703242c2a5a867a52b687b
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "63317832"
---
# <a name="understand-data-cards-in-powerapps"></a>Slik fungerer datakort i PowerApps

**[Kort](controls/control-card.md)**-kontrollene er byggesteinene i **[Redigeringsskjema](controls/control-form-detail.md)**- og **[Vis skjema](controls/control-form-detail.md)**-kontrollene i lerretsapper. Skjemaet representerer hele posten, og hvert kort representerer et enkelt felt for den aktuelle posten.

Du kan lettest samhandle med kort i ruten til høyre, når du har valgt en skjemakontroll i utformingsområdet. I denne ruten, kan du velge hvilke felt du vil vise, hvordan du viser hvert felt og i hvilken rekkefølge de skal vises. Dette eksemplet viser en kontroll for **Redigeringsskjema** i en app som er bygd fra en SharePoint-liste, kalt **Aktiva**.

![Første skjerm](./media/working-with-cards/first-screen.png)

For å komme i gang med kort kan du se [Legge til et skjema](add-form.md) og [Forstå dataskjemaer](working-with-forms.md). Resten av dette emnet inneholder mer detaljert informasjon om hvordan kort fungerer, og hvordan du kan tilpasse, eller til og med opprette dine egne kort.

## <a name="predefined-cards"></a>Forhåndsdefinerte kort

PowerApps tilbyr et forhåndsdefinert sett med kort for strenger, tall og andre datatyper. Du kan se variasjonene som er tilgjengelige, og endre kortet som brukes for et felt, i ruten til høyre:

![](./media/working-with-cards/selected-card.png)

Et kort med én enkelt linje med tekst er valgt i dette eksemplet, men nettadresse-teksten er lengre enn det som kan vises på en enkelt linje. La oss endre dette til et flerlinjet tekst-kort for å gi brukerne våre mer plass til å redigere:

![](./media/working-with-cards/multiline-edit.png)

Flere felt på denne datakilden blir ikke vist, men du kan vise eller skjule et felt ved å velge avmerkingsboksen. Dette eksemplet illustrerer hvordan du viser **SecurityCode**-feltet.

![](./media/working-with-cards/add-security-code.png)

## <a name="customize-a-card"></a>Å tilpasse et kort
Kort består av andre kontroller. I en **Redigeringsskjema**-kontroll skriver brukeren inn data i en standard **[Tekstinndata](controls/control-text-input.md)**-kontroll du legger til fra **Sett inn**-fanen.  

La oss gå gjennom et eksempel for hvordan du endrer utseendet på et kort ved å manipulere kontrollene i det.

1. La oss først gå tilbake til kortet vi nylig satte inn for **SecurityCode**-feltet. Velg dette kortet ved å klikke eller trykke på det én gang:
   
    ![](./media/working-with-cards/select-security-code.png)
2. Velg **[Tekstinndata](controls/control-text-input.md)**-kontrollen i kortet ved å klikke eller trykke på selve inndata-kontrollen.
   
    ![](./media/working-with-cards/select-text-input.png)
3. Flytt denne kontrollen i kortet ved å dra i valgboksen, og endre størrelsen på kontrollen ved å dra i håndtakene langs kanten av valgboksen:
   
    ![](./media/working-with-cards/customize-text-input.png)  

Du kan endre størrelse på, flytte og gjøre andre endringer for kontrollene i et kort, men du kan ikke slette det uten å låse det opp først.

## <a name="unlock-a-card"></a>Å låse opp et kort
I tillegg til å inneholde kontroller, er kortene kontroller i seg selv, som har egenskaper og formler, akkurat som en hvilken som helst annen kontroll. Når du velger å vise et felt i et skjema, vil den høyre ruten automatisk opprette kortet for deg, og generere de nødvendige formlene.  Vi kan se disse formlene i **Avansert**-fanen i den høyre ruten:

![](./media/working-with-cards/advanced-locked.png)

Vi ser umiddelbart en av de viktigste egenskapene for kortet: **[DataField](controls/control-card.md)**-egenskapen. Denne egenskapen indikerer hvilket felt i datakilden som brukeren ser og kan redigere i dette kortet.  

Banneret over **Avansert**-fanen indikerer at egenskapene for dette kortet er låst. Et låseikon vises også ved siden av **[DataField](controls/control-card.md)**-,  **[DisplayName](controls/control-card.md)**- og  **[Obligatorisk](controls/control-card.md)**-egenskaper. Den høyre ruten opprettet disse formlene, og låsen hindrer tilfeldige endringer i disse egenskapene.

![](./media/working-with-cards/lock-icons.png)

Klikk eller trykk på banneret øverst for å låse opp kortet, slik at du kan endre disse egenskapene:

![](./media/working-with-cards/unlocked-card.png)

La oss endre **[DisplayName](controls/control-card.md)** for å sette et mellomrom mellom **Aktiva** og **ID**. Ved å gjøre denne endringen, endrer vi det som ble generert for oss.  Dette kortet har en annen etikett i den høyre ruten:

![](./media/working-with-cards/change-display-name.png)

Vi har nå tatt kontroll over dette kortet og kan endre det ytterligere til å tilpasses vårt behov. Men vi har mistet muligheten til å endre kortet fra én representasjon til en annen (for eksempel fra én enkelt linje med tekst, til flerlinjet tekst), slik vi gjorde tidligere. Vi har transformert det forhåndsdefinerte kortet til et «egendefinert kort», som vi nå kontrollerer.  

> [!IMPORTANT]
> Du kan ikke låse et kort på nytt, hvis du låser det opp. Fjern kortet og sett det inn i den høyre ruten på nytt, for å returnere et kort til låst tilstand.

Du kan endre utseendet og virkemåten til et ulåst kort på en rekke måter, for eksempel ved å legge til og slette kontrollene i det. Du kan for eksempel legge til en stjerneform fra **Ikon**-menyen på **Sett inn**-fanen.

![](./media/working-with-cards/add-star.png)

Stjernen er nå en del av kortet og vil følge det, hvis du for eksempel omorganiserer kortene i skjemaet.

Som et annet eksempel kan du låse opp **ImageURL**-kortet, og deretter legge til en **Bilde**-kontroll til den fra **Sett inn**-fanen:

![](./media/working-with-cards/add-image.png)

Du kan angi **Bilde**-egenskapen på formellinjen for denne kontrollen til *TextBox*.**Tekst**, der *TextBox* er navnet på **Tekstinndata**-kontrollen som inneholder nettadressen:

> [!TIP]
> Trykk på ALT for å vise navnet på hver kontroll.

![](./media/working-with-cards/show-image.png)

Og nå kan vi se bildene og redigere nettadressene deres. Legg merke til at vi kunne ha brukt **Parent.Default** som **Bilde**-egenskapen, men den ville ikke ha blitt oppdatert hvis brukeren har endret nettadressen.

Vi kan gjøre samme på det andre skjermbildet i denne appen, der vi bruker en **Vis skjema**-kontroll til å vise detaljene for en post. I dette tilfellet vil vi kanskje skjule etiketten (Angi **Synlig**-egenskapen for etiketten, ikke på kortet, til **usann**), fordi brukeren ikke skal redigere nettadressen på denne skjermen:

![](./media/working-with-cards/show-image-display.png)

## <a name="interact-with-a-form"></a>Samhandling med et skjema
Når du låser opp et kort, kan du endre hvordan det samhandler med skjemaet som inneholder det.

Nedenfor finner du noen retningslinjer for hvordan kontroller bør fungere med kortene, og hvordan kortene bør fungere med skjemaet. Dette er bare retningslinjer. I likhet med en hvilken som helst kontroll i PowerApps, kan du opprette formler som refererer til en annen kontroll i PowerApps, og dette er ikke mindre sant for kort og kontroller i kort. Du kan være kreativ og opprette en app på mange måter.  

### <a name="datafield-property"></a>DataField-egenskapen
Den viktigste egenskapen på kortet er **[DataField](controls/control-card.md)**-egenskapen.  Denne egenskapen styrer validering, hvilket felt som er oppdatert og andre aspekter av kortet.

### <a name="information-flowing-in"></a>Informasjon som flyter inn
Som en beholder gjør skjemaet **ThisItem** tilgjengelig for alle kortene i det. Denne posten inneholder alle feltene for den gjeldende posten av interesse.  

**[standard](controls/properties-core.md)**-egenskapen for hvert kort bør settes til **ThisItem**.*FieldName*.  I noen tilfeller vil du kanskje transformere denne verdien på vei inn. Du ønsker kanskje å formatere en streng, eller oversette verdien fra ett språk til et annet.

Alle kontrollene i kortet skal referere til **Parent.Default** for å komme til verdien til feltet. Denne strategien gir et nivå for innkapsling for kortet, slik at kortets **[Standard](controls/properties-core.md)**-egenskap kan endres uten å endre de interne formlene for kortet.

**DefaultValue**- og **[Obligatorisk](controls/control-card.md)**-egenskapene blir som standard hentet fra datakildens metadata, basert på **[DataField](controls/control-card.md)**-egenskapen. Du kan overstyre disse formlene med din egen logikk ved å integrere datakildens metadata ved hjelp av **[DataSourceInfo](functions/function-datasourceinfo.md)**-funksjonen.

### <a name="information-flowing-out"></a>Informasjon som flyter ut
Etter at brukeren endrer en post ved hjelp av kontroller i kortene, lagrer **[SubmitForm](functions/function-form.md)**-funksjonen disse endringene til datakilden. Når denne funksjonen kjører, leser skjemakontrollen verdiene for hvert kort sin **[DataField](controls/control-card.md)**-egenskap for å vite hvilket felt som skal endres.  

Skjemakontrollen leser også verdien for hvert kort sin **[Oppdatering](controls/control-card.md)**-egenskap. Denne verdien vil bli lagret i datakilden for dette feltet. Dette er stedet der du kan bruke en annen transformasjon, kanskje for å reversere transformeringen som ble brukt i **[Standard](controls/properties-core.md)**-formelen for kortet.

**Gyldig**-egenskapen styres av metadata fra datakilden, basert på **[DataField](controls/control-card.md)**-egenskapen. Det er også basert på **[Obligatorisk](controls/control-card.md)**-egenskapen, og om **[Oppdatering](controls/control-card.md)**-egenskapen inneholder en verdi. Hvis verdien i **[Oppdatering](controls/control-card.md)**-egenskapen ikke er gyldig, angir **Feil**-egenskapen en brukervennlig feilmelding.

Hvis **[DataField](controls/control-card.md)**-egenskapen for et kort er *tom*, er kortet bare en beholder for kontroller. **Gyldig**- og  **[Oppdatering](controls/control-card.md)**-egenskapene til kortet vil ikke delta når skjemaet sendes.

## <a name="dissecting-an-example"></a>Eksaminering av et eksempel
La oss se på kontrollene som utgjør et grunnleggende dataregistreringskort. Avstanden mellom kontroller ble øket for å vise hver kontroll tydeligere:

![](./media/working-with-cards/dissect-card1.png)

Hold nede ALT for å vise navnene på kontrollene som utgjør dette kortet:

![](./media/working-with-cards/dissect-card2.png)

Fire kontroller gjør at dette kortet fungerer:

| navn | Type | Beskrivelse |
| --- | --- | --- |
| **TextRequiredStar** |**[Etikett](controls/control-text-box.md)**-kontrollen |Viser en stjerne, som ofte brukes i skjemaer for dataregistrering, for å indikere at et felt er nødvendig. |
| **TextFieldDisplayName** |**[Etikett](controls/control-text-box.md)**-kontrollen |Viser det brukervennlige navnet for dette feltet. Dette navnet kan være forskjellig fra det som er i datakildeskjemaet. |
| **InputText** |**Tekstinndata**-kontrollen |Viser startverdien for feltet og lar brukeren endrer denne verdien. |
| **TextErrorMessage** |**[Etikett](controls/control-text-box.md)**-kontrollen |Viser en brukervennlig feilmelding til brukeren, hvis det oppstår et problem med validering. Sikrer også at feltet har en verdi hvis det kreves en. |

Hvis du vil fylle ut disse kontrollene med data, kan egenskapene bli drevet av egenskapene til kortet, gjennom disse viktige formlene. Vær oppmerksom på at ingen av disse formlene refererer til et bestemt felt. All informasjon kommer i stedet fra kortet.

| Egenskapen for kontrollen | Formel | Beskrivelse |
| --- | --- | --- |
| **TextRequiredStar.Visible** |**Parent.Required** |Stjernen vises bare hvis feltet er nødvendig. Nødvendig er en formel som styres av deg eller metadataene, for datakilden. |
| **TextFieldDisplayName.Text** |**Parent.DisplayName** |Tekstboks-kontrollen viser det brukervennlige navnet som du eller datakildens metadata gir, og som er angitt i kortets **[DisplayName](controls/control-card.md)**-egenskap. |
| **InputText.Default** |**Parent.Default** |Tekstinndata-kontrollen viser først verdien i feltet fra datakilden, som ble angitt fra kortet sin standardverdi. |
| **TextErrorMessage.Text** |**Parent.Error** |**Feil**-egenskapen for kortet angir en aktuell feilmelding, hvis det oppstår et problem med validering. |

Hvis du vil hente informasjon fra disse kontrollene, og skyve den tilbake i datakilden, har vi følgende viktige formler:

| Kontrollnavn | Formel | Beskrivelse |
| --- | --- | --- |
| **DataCard.DataField** |**"ApproverEmail"** |Navnet på feltet som brukeren kan vise og redigere i dette kortet. |
| **DataCard.Update** |**InputText.Text** |Verdien til å validere og skyve tilbake datakilden når  **[SubmitForm](functions/function-form.md)** kjører. |

