---
title: Funksjonene EditForm, NewForm, SubmitForm, ResetForm og ViewForm | Microsoft Docs
description: Referanseinformasjon om funksjonene EditForm, NewForm, SubmitForm, ResetForm og ViewForm i PowerApps, i tillegg til syntaks og eksempler
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/06/2017
ms.author: gregli
ms.openlocfilehash: 7e64426cfee2b72cd8fda51b889b99b285147fcc
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996402"
---
# <a name="editform-newform-submitform-resetform-and-viewform-functions-in-powerapps"></a>Funksjonene EditForm, NewForm, SubmitForm, ResetForm og ViewForm i PowerApps
Vis, rediger eller opprett et element, lagre innholdet og tilbakestill kontrollene i en **[Redigeringskjema](../controls/control-form-detail.md)**-kontroll.

## <a name="overview"></a>Oversikt
Disse funksjonene endrer tilstanden til **Redigeringsskjema**-kontrollen.  Skjema-kontrollen kan være i én av disse modusene:

| Modus | Beskrivelse |
| --- | --- |
| **FormMode.Edit** |Skjemaet fylles ut med en eksisterende post, og brukeren kan endre verdiene til feltene.  Når dette er fullført, kan brukeren lagre endringene i posten. |
| **FormMode.New** |Skjemaet fylles ut med standardverdier, og brukeren kan endre verdiene til feltene.  Når dette er fullført, kan brukeren legge til posten i datakilden. |
| **FormMode.View** |Skjemaet fylles ut med en eksisterende post, men brukeren kan ikke endre verdiene til feltene. |

## <a name="description"></a>Beskrivelse
Disse funksjonene startes ofte fra **[OnSelect](../controls/properties-core.md)**-formelen til en **[Knapp](../controls/control-button.md)**- eller **[Bilde](../controls/control-image.md)**-kontroll, slik at brukeren kan lagre redigeringer, forkaste endringer eller opprette en post. Du kan [bruke kontrollene og disse funksjonene sammen](../working-with-forms.md) for å opprette en komplett løsning.

Disse funksjonene returnerer ingen verdier.

### <a name="submitform"></a>SubmitForm
Bruk **SubmitForm**-funksjonen i **[OnSelect](../controls/properties-core.md)**-egenskapen i en Knapp-kontroll for å lagre endringer til en Skjema-kontroll i datakilden.

Før du sender inn eventuelle endringer, kontrollerer denne funksjonen om det finnes noen valideringsproblemer i felter som er merket som obligatorisk, eller som har én eller flere begrensninger på verdien. Denne virkemåten samsvarer med virkemåten til **[Validate](function-validate.md)**-funksjonen.

**SubmitForm** kontrollerer også **[Valid](../controls/control-form-detail.md)**-egenskapen til skjemaet, som er en samling av alle **[Valid](../controls/control-card.md)**-egenskapene til **[Kort](../controls/control-card.md)**-kontrollene som Skjema-kontrollen inneholder. Hvis det oppstår et problem, sendes ikke dataene, og **[Feil](../controls/control-form-detail.md)**- og **[ErrorKind](../controls/control-form-detail.md)**-egenskapene til Skjema-kontrollen angis i henhold til dette.

Hvis valideringen blir godkjent, sender **SubmitForm** endringen til datakilden.

* Hvis valideringen er vellykket, kjører skjemaets **[OnSuccess](../controls/control-form-detail.md)**-virkemåte, og **[Feil](../controls/control-form-detail.md)**- og **[ErrorKind](../controls/control-form-detail.md)**-egenskapene fjernes.  Hvis skjemaet var i **FormMode.New**-modus, returneres det til **FormMode.Edit**-modusen.
* Hvis valideringen mislyktes, kjører skjemaets **[OnFailure](../controls/control-form-detail.md)**-virkemåte, og **[Feil](../controls/control-form-detail.md)**- og **[ErrorKind](../controls/control-form-detail.md)**-egenskapene angis i henhold til dette.  Modusen til skjemaet forblir uendret.  

### <a name="editform"></a>EditForm
**EditForm**-funksjonen endres Skjema-kontrollens modus til **FormMode.Edit**. I denne modusen brukes innholdet til Skjema-kontrollens **[Element](../controls/control-form-detail.md)**-egenskap til å fylle ut skjemaet.  Hvis **SubmitForm**-funksjonen kjøres når skjemaet befinner seg i denne modusen, blir en post endret, ikke opprettet.  **FormMode.Edit** er standard for Skjema-kontrollen.

### <a name="newform"></a>NewForm
**NewForm**-funksjonen endres Skjema-kontrollens modus til **FormMode.New**. I denne modusen ignoreres Skjema-kontrollens **[Element](../controls/control-form-detail.md)**-egenskap, og standardverdiene til skjemaets **[DataSource](../controls/control-form-detail.md)**-egenskap fyller ut skjemaet. Hvis **SubmitForm**-funksjonen kjøres når skjemaet befinner seg i denne modusen, blir en post opprettet, ikke endret.

### <a name="resetform"></a>ResetForm
**ResetForm**-funksjonen tilbakestiller innholdet i et skjema til sine opprinnelige verdier, slik de var før brukeren foretok endringer. Hvis skjemaet er i **FormMode.New**-modus, tilbakestilles det til **FormMode.Edit**-modusen. **[OnReset](../controls/control-form-detail.md)**-virkemåten til Skjema-kontrollen kjøres også.  Du kan også tilbakestille individuelle kontroller med **[Reset](function-reset.md)**-funksjonen, men bare fra selve skjemaet.

### <a name="viewform"></a>ViewForm
**ViewForm**-funksjonen endrer Skjema-kontrollens modus til **FormMode.View**. I denne modusen brukes innholdet til Skjema-kontrollens **[Element](../controls/control-form-detail.md)**-egenskap til å fylle ut skjemaet.  **SubmitForm**- og **RestForm**-funksjonene har ingen effekt i denne modusen.

### <a name="displaymode-poperty"></a>DisplayMode-egenskap
Den gjeldende modusen kan leses gjennom **Modus**-egenskapen.  Modusen bestemmer også verdien til **DisplayMode**-egenskapen, som kan brukes av datakortene og kontrollene i Skjema-kontrollen.  **DisplayMode**-egenskapen til datakortet angis ofte til **Parent.DisplayMode** (med henvisning til skjemaet), og det samme skjer med **DisplayMode**-egenskapen til kontrollen (med henvisning til datakortet): 

| Modus | DisplayMode | Beskrivelse |
| --- | --- | --- |
| **FormMode.Edit** |**DisplayMode.Edit** |Datakort og kontroller er redigerbare og klare for å godta endringer i en post. |
| **FormMode.New** |**DisplayMode.Edit** |Datakort og kontroller er redigerbare og klare for å godta en ny post. |
| **FormMode.View** |**DisplayMode.View** |Datakort og kontroller er ikke redigerbare eller optimalisert for visning. |

## <a name="syntax"></a>Syntaks
**SubmitForm**( *FormName* )

* *FormName* – Obligatorisk. Form-kontroll som skal sendes til datakilden.

**EditForm**( *FormName* )

* *FormName* – Obligatorisk.  Form-kontroll som skal byttes til **FormMode.Edit**-modus.

**NewForm**( *FormName* )

* *FormName* – Obligatorisk. Form-kontroll som skal byttes til **FormMode.New**-modus.

**ResetForm**( *FormName* )

* *FormName* – Obligatorisk. Form-kontroll som skal tilbakestilles til opprinnelige verdier. Bytter også skjemaet fra **FormMode.New**-modus til **FormMode.Edit**-modus.

**ViewForm**( *FormName* )

* *FormName* – Obligatorisk.  Form-kontroll som skal byttes til **FormMode.View**-modus.

## <a name="examples"></a>Eksempler
Se [Forstå dataskjemaer](../working-with-forms.md) utfyllende eksempler.

1. Legg til en Knapp-kontroll, angi kontrollens **[Text](../controls/properties-core.md)**-egenskap til **Save**, og sett kontrollens **[OnSelect](../controls/properties-core.md)**-egenskap til denne formelen:
   
    **SubmitForm( EditForm )**
2. Angi **[OnFailure](../controls/control-form-detail.md)**-egenskapen for en Skjema-kontroll til tom og**[OnSuccess](../controls/control-form-detail.md)**-egenskapen til denne formelen:
   
    **Back()**
3. Gi en **[Etikett](../controls/control-text-box.md)**-kontroll navnet **ErrorText**, og angi kontrollens **[Tekst](../controls/properties-core.md)**-egenskapen til denne formelen:
   
    **EditForm.Error**
   
    Når brukeren velger **Lagre**-knappen, sendes eventuelle endringer i Skjema-kontrollen til den underliggende datakilden.
   
   * Hvis innsendingen blir vellykket, lagres eventuelle endringer. Hvis skjemaet er i **Ny**-modusen, opprettes det en post. **ErrorText** er *tom*, og det forrige skjermbildet vises på nytt.
   * Hvis innsendingen mislyktes, viser**ErrorText** en brukervennlig feilmelding, og det gjeldende skjermbildet forblir synlig slik at brukeren kan rette opp problemet og prøve på nytt.
4. Legg til en Knapp-kontroll, angi kontrollens **[Text](../controls/properties-core.md)**-egenskap til å vise **Avbryt**, og angi kontrollens **[OnSelect](../controls/properties-core.md)**-egenskap til denne formelen:
   
    **ResetForm( EditForm ); Back()**
   
    Når en bruker velger **Avbryt**-knappen, tilbakestilles verdiene i Skjema-kontrollen til de opprinnelige verdiene, slik de var før brukeren begynte å redigere. Det forrige skjermbildet vises på nytt, og Skjema-kontrollen returneres til **Rediger**-modus hvis den var i **Ny**-modus.
5. Legg til en Knapp-kontroll, angi kontrollens **[Tekst](../controls/properties-core.md)**-egenskap til å vise **Ny**, og angi kontrollens **[OnSelect](../controls/properties-core.md)**-egenskap til denne formelen:
   
    **NewForm( EditForm ); Navigate( EditScreen, None )**
   
    Når brukeren velger **Ny**-knappen, veksler Skjema-kontrollen til **Ny**-modusen, standardverdiene for Skjema-kontrollens datakilde fyller ut kontrollen, og skjermbildet som inneholder Skjema-kontrollen vises på nytt. Når **SubmitForm**-funksjonen kjører, opprettes en post i stedet for å oppdateres.

