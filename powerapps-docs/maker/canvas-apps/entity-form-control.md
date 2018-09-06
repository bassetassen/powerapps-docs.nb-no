---
title: Bruke enhetsskjemakontrollen | Microsoft Docs
description: Opprett apper på en raskere måte ved å bruke enhetsskjemakontrollen til å legge til funksjonsrike skjemaer for Common Data Service-enheter.
author: aneesmsft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/11/2017
ms.author: aneesa
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ee8573cb9ae4df5ac42deefad4ac67aede3a3502
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836281"
---
# <a name="use-the-entity-form-control"></a>Bruke enhetsskjemakontrollen
Opprett apper på en raskere måte ved å bruke **enhetsskjemakontrollen** til å legge til funksjonsrike skjemaer for Common Data Service-enheter.

Hvis du vil ha en innføring i **enhetsskjemakontrollen**, kan du lese dette blogginnlegget: [Ny enhetsskjemakontroll (eksperimentell funksjon) for Common Data Service](https://powerapps.microsoft.com/blog/new-entity-form-control-experimental-feature-for-common-data-service/).

> [!IMPORTANT]
> Vær oppmerksom på at **enhetsskjemakontrollen** er en eksperimentell funksjon, som beskrevet i blogginnlegget, og unngå å bruke **enhetsskjemakontrollen** i produksjonsapper for øyeblikket.

## <a name="key-properties"></a>Nøkkelegenskaper
Dette er nøkkelegenskapene i en **enhetsskjemakontroll**.

**DataSource** – angir datakilden som inneholder postene du vil vise.   
> [!NOTE]
> For øyeblikket støttes bare enheter i Common Data Service som datakilder for **enhetsskjemakontrollen**.  

**Pattern** – angir stilen på skjemaet du vil vise i **enhetsskjemakontrollen**. Angi denne egenskapen ved hjelp av **FormPattern**-opplistingen.

* **FormPattern.List** – viser en tabelliste med poster.
* **FormPattern.CardList** – viser en kortliste med poster.
* **FormPattern.Details** – viser et skjema for å vise eller redigere detaljene for en enkelt post.
* **FormPattern.None** – ingen stil er angitt. Er som standard satt til **List** for nettbrettapper og **CardList** for mobilapper.

**Item** – angir posten i datakilden som **enhetsskjemakontrollen** viser. Denne egenskapen brukes bare når **Pattern** er satt til **FormPattern.Details**.

**Valgte** – henter posten som er valgt.  
Eksempel: Hvis **enhetsskjemakontrollen** viser en liste over poster for salgsordrer, gir **Valgt**-egenskapen deg posten som er valgt for øyeblikket. Du kan også åpne et felt i en post. (For eksempel kan du angi verdien for **Konto**-feltet i den valgte posten som **Selected.Account**.)

**SelectableFields** – angir hvilke felt som skal vises som koblinger. Angi verdien for denne egenskapen ved hjelp av denne syntaksen:  
**{Field1Name : true, Field2Name : true}**  
Eksempel: Hvis du vil at **SalesOrderId**- og **Konto**-feltet skal vises som koblinger i et skjema, angir du **SelectableFields**-egenskapen for dette skjemaet til denne verdien:  
**{SalesOrderId : true, Account : true}**

**SelectedField** – bestemmer hvilket felt som ble trykket eller klikket på. Dette gjelder bare for feltene som er angitt som **SelectableFields**.  
Eksempel: Hvis du angir **SelectableFields**-egenskapen som **{SalesOrderId : true, Account : true}**, og brukeren klikker eller trykker på **Konto**-feltet, settes **SelectedField.Account** til true.

**OnFieldSelect** – hvordan en app reagerer når brukeren klikker eller trykker på et felt. Dette gjelder bare for feltene som er angitt som **SelectableFields**.

**Modus** – angir modusen for skjemaet. Hvis du vil endre modus, kan du bruke **ViewForm**-, **EditForm**- eller **NewForm**-funksjonen. Disse funksjonene fungerer bare når **Mønster**-egenskapen er satt til **FormPattern.Details**. Angi verdien for **Mode**-egenskapen til en verdi av **FormMode**-opplistingen.

* **FormMode.View** – lar brukere vise, men ikke redigere eller legge til en post.
* **FormMode.Edit** – lar brukere redigere en post.
* **FormMode.Edit** – lar brukere legge til poster.

**OnSuccess** – hvordan en app reagerer når en dataoperasjon er vellykket.

**OnFailure** – hvordan en app reagerer når en dataoperasjon mislykkes.

**Unsaved** – bestemmer om en post som redigeres av en bruker har ulagrede endringer.

## <a name="related-functions"></a>Relaterte funksjoner
Du kan bruke disse delte funksjonene med enten **enhetsskjemakontrollen** eller [redigeringsskjemakontrollen](functions/function-form.md). Disse funksjonene fungerer bare med **enhetsskjemakontrollen** når **Pattern**-egenskapen er satt til **FormPattern.Details**.

**ViewForm** – angir **Mode**-egenskapen for en **enhetsskjemakontroll** til **FormMode.View**.

**EditForm** – angir **Mode**-egenskapen for en **enhetsskjemakontroll** til **FormMode.Edit**.

**NewForm** – angir **Mode**-egenskapen for en **enhetsskjemakontroll** til **FormMode.New**.

**SubmitForm** – lagrer endringer når en bruker redigerer en post i en **enhetsskjemakontroll**.

**ResetForm** – forkaster ulagrede endringer når en bruker redigerer en post i en **enhetsskjemakontroll**.

Nå som du har en oversikt over de forskjellige egenskapene og funksjonene, kan vi ta en titt på dem i praksis.

> [!NOTE]
> Hvis du ikke har tilgang til en Common Data Service-database, må du opprette en før du følger disse trinnene.

## <a name="display-a-list-of-records"></a>Vise en liste over poster
Disse fem prosedyrene gir deg et fullstendig eksempel på hvordan du bruker **enhetsskjemakontroller**. I denne prosedyren legger du til et skjema som viser en liste over salgsordre.  

1. Opprett en tom app for nettbrett.
   
    ![](media/entity-form-control/entityform-tutorial-01-01.png)
2. Gi den første skjermen navnet **SalesOrderListScreen**.
   
    ![](media/entity-form-control/entityform-tutorial-01-02.png)
3. På **Sett inn**-fanen klikker eller trykker du på **Skjemaer**, og klikker eller trykker deretter på **Enhetsskjema (eksperimentell)**.  
   
    En **enhetsskjemakontroll** legges til på skjermen.  
   
    ![](media/entity-form-control/entityform-tutorial-01-03.png)
4. Gi **enhetsskjemakontrollen** navnet **SalesOrderListForm**, og endre størrelsen, slik at den dekker hele skjermen.
5. Klikk eller trykk på databaseikonet ved siden av **Ingen datakilde er valgt** i den høyre ruten, og klikk eller trykk **Legg til en datakilde**.  
   
    ![](media/entity-form-control/entityform-tutorial-01-04.png)
6. Klikk eller trykk på tilkoblingen for databasen din i listen over tilkoblinger.  
   
    ![](media/entity-form-control/entityform-tutorial-01-05.png)
7. Klikk eller trykk på **Salgsordre** i listen over enheter, og klikk eller trykk deretter på **Koble til**.  
   
    En datakilde opprettes for **Salgsordre**-enheten, og **DataSource**-egenskapen til **SalesOrderListForm** er satt til den aktuelle datakilden.
   
    ![](media/entity-form-control/entityform-tutorial-01-06.png)  
   
    **Enhetsskjemakontrollen** viser en liste over salgsordre. Ved hjelp av **enhetsskjemakontrollen** får du raskt se et listeskjema uten å måtte bygge det manuelt.
   
    ![](media/entity-form-control/entityform-tutorial-01-07.png)  
   
    Du har ikke angitt **Pattern**-egenskapen for **enhetsskjemakontrollen**, så den bruker **Liste**-mønsteret som standard. I tillegg brukes **DefaultList**-feltgruppen i **Salgsordre**-enheten til å vise listeskjemaet. Skjemaet er dynamisk, og eventuelle endringer i feltgruppen gjenspeiles automatisk.


## <a name="display-the-details-of-a-record"></a>Vis detaljene for en post
La oss legge til en annen **enhetsskjemakontroll** for å vise detaljene for salgsordren som er valgt i listen du opprettet tidligere.  

1. Endre størrelsen på **SalesOrderListForm**, slik at den dekker halve skjermen, og legg til en ekstra **enhetsskjemakontroll** som dekker den andre halvdelen av skjermen.  
   <br>![](media/entity-form-control/entityform-tutorial-01-09.png)
2. Endre navnet på den andre **enhetsskjemakontrollen** til **SalesOrderDetailsForm** og koble den til **Salgsordre**-datakilden du opprettet tidligere.  
   <br>![](media/entity-form-control/entityform-tutorial-01-10.png)
3. Angi **Pattern**-egenskapen for **SalesOrderDetailsForm** til **FormPattern.Details**.  
   
    **SalesOrderDetailsForm** bruker **DefaultDetails**-feltgruppen i **Salgsordre**-enheten til å vise skjemaet. Som med **SalesOrderListForm** får du rask tilgang til postdetaljer uten å bygge et skjema manuelt.  
   
    ![](media/entity-form-control/entityform-tutorial-01-11.png)
4. Angi **Item**-egenskapen for **SalesOrderDetailsForm** som **SalesOrderListForm.Selected**.
   
    **SalesOrderDetailsForm** viser informasjon om posten som brukeren klikker eller trykker på, i **SalesOrderListForm**.
   
    ![](media/entity-form-control/entityform-tutorial-01-12.png)
5. Forhåndsvis appen ved å trykke på F5, og klikk eller trykk på en salgsordre i listen til venstre.  
   
    På høyre side vises detaljene for ordren du valgte.  
   
    ![](media/entity-form-control/entityform-tutorial-01-13.png)  

## <a name="configure-a-field-to-navigate-to-another-screen"></a>Konfigurere et felt for å navigere til en annen skjerm
Neste trinn er å legge til flere skjermer i appen vår og deretter konfigurere feltene i en **enhetsskjemakontroll** til å navigere til en annen skjerm i appen når brukeren klikker eller trykker på et felt.  

1. Legg til en skjerm i appen, og gi skjermen navnet **SalesOrderDetailsScreen**.
2. Klipp ut **SalesOrderDetailsForm**, lim det inn i **SalesOrderDetailsScreen**, og endre størrelsen på skjemaet, slik at det dekker mesteparten av skjermen, men det er nok plass til et ikon øverst.
3. Legg til et ikon for Tilbake-pilen øverst til venstre på **SalesOrderDetailsScreen**.
4. Angi **OnSelect**-egenskapen for ikonet for Tilbake-pilen til [**Tilbake**](functions/function-navigate.md)-funksjonen.  
   
    ![](media/entity-form-control/entityform-tutorial-01-14.png)
5. På **SalesOrderListScreen** endrer du størrelsen på **SalesOrderListForm** til å dekke hele skjermen.
6. Klikk eller trykk på **SalesOrderListForm** for å velge den.
7. I ruten til høyre, under **Felter**, angir du at **SalesOrderId** skal navigere til **SalesOrderDetailsScreen**.  
   
    ![](media/entity-form-control/entityform-tutorial-01-15.png)
   
    **Enhetsskjemakontrollen** viser verdiene i **SalesOrderId**-feltet (den første kolonnen i listen) som koblinger.
   
    ![](media/entity-form-control/entityform-tutorial-01-16.png)  
8. Forhåndsvis appen ved å trykke på F5, og klikk eller trykk på en kobling i listen over salgsordre.
   
    ![](media/entity-form-control/entityform-tutorial-01-17.png)  
   
    Den andre skjermen åpnes og viser detaljene for salgsordren du har angitt.
   
    ![](media/entity-form-control/entityform-tutorial-01-18.png)  
   
    Hvis du vil se detaljene for en annen salgsordre, klikker eller trykker du på Tilbake-pilen for å gå tilbake til listen og deretter klikker eller trykker du på koblingen til ordren du vil se detaljene for.

## <a name="navigate-with-a-context-variable"></a>Navigere med kontekstvariabel
**Item**-egenskapen for **SalesOrderDetailsForm** er satt til **SalesOrderListForm.Selected**, slik at **SalesOrderDetailsForm** viser detaljer for posten som brukeren velger i **SalesOrderListForm**. Du kan også få konteksten for den valgte posten ved å bruke **NavigationContext**-kontekstvariabelen, som opprettes automatisk når du bruker ruten for skjematilpassing til å konfigurere et felt til å navigere.  

1. Angi **Item**-egenskapen for **SalesOrderDetailsForm** som **NavigationContext**.
   
    ![](media/entity-form-control/entityform-tutorial-01-19.png)
2. Forhåndsvis appen ved å trykke på F5, og klikk eller trykk på en kobling i listen over salgsordre.
   
    Appen åpner **SalesOrderDetailsScreen** og viser detaljene for salgsordren du har angitt.

La oss se nærmere på hvordan ruten for skjematilpassing setter opp navigasjon og kontekst for oss.  

**SelectableFields**-egenskapen for **SalesOrderListForm** angir **SalesOrderId** som et felt som kan velges.

![](media/entity-form-control/entityform-tutorial-01-20.png)  

Dette ble konfigurert automatisk da vi brukte ruten for skjematilpassing til å angi at **SalesOrderId**-feltet navigerer til **SalesOrderDetailsScreen**. Verdiene i **SalesOrderId**-feltet vises derfor som koblinger.

Egenskapen **OnFieldSelect** for **SalesOrderListForm** er satt til en [**If**](functions/function-if.md)-funksjon, som bestemmer om brukeren klikker eller trykker på **Sales order ID**-feltet: **SalesOrderListForm.SelectedField.SalesOrderId = true**.  

Hvis funksjonen evalueres som sann, åpnes **SalesOrderDetailsScreen** med kontekstvariabelen med navnet **NavigationContext** som vi brukte tidligere.  

Dette ble også konfigurert automatisk da vi bruke ruten for skjematilpassing til å angi at **SalesOrderId**-feltet navigerer til **SalesOrderDetailsScreen**.  

Når brukeren klikker eller trykke på et felt for salgsordre-ID, blir [**If**](functions/function-if.md)-funksjonen vurdert som sann, og [**Navigate**](functions/function-navigate.md)-funksjonen kalles opp med den aktuelle konteksten, og detaljerskjermen åpnes.  

![](media/entity-form-control/entityform-tutorial-01-21.png)  

> [!NOTE]
> Når du bruker ruten for skjematilpassing, bestemmes **NavigationContext** automatisk på en intelligent måte. Når brukeren klikker eller trykker på **SalesOrderId**, blir **NavigationContext** satt til **SalesOrderListForm.Selected**, som vist i den tidligere formelen. Hvis vi hadde angitt **Account**-feltet for navigasjon i stedet, hadde **NavigationContext** vært satt til **SalesOrderListForm.Selected.Account**, slik at den korrekte konteksten ble brukt. For å bruke denne konteksten trenger du imidlertid en **enhetsskjemakontroll** som er koblet til **Account**-enheten i Common Data Service.

## <a name="edit-and-save-a-record"></a>Redigere og lagre en post
Til slutt skal vi forklare hvordan du kan redigere og lagre en post i en **enhetsskjemakontroll**.  

1. På **SalesOrderDetailsScreen** legger du til et redigeringsikon, og angir deretter **OnSelect**-egenskapen til denne formelen:  
   **EditForm(SalesOrderDetailsForm)**
   
    ![](media/entity-form-control/entityform-tutorial-01-22.png)
2. Legg til et merkeikon ved siden av redigeringsikonet, og angi deretter **OnSelect**-egenskapen til merkeikonet til denne formelen:  
   **SubmitForm(SalesOrderDetailsForm)**  
   
    ![](media/entity-form-control/entityform-tutorial-01-23.png)
3. Forhåndsvis appen ved å trykke på F5, klikk eller trykk på en **salgsordre-ID**-kobling for å se detaljene for en salgsordre. Deretter klikker du eller trykker du på redigeringsikonet.  
   
    **Modusen** for **enhetsskjemakontrollen** er satt til **FormMode.Edit**, slik at du kan redigere posten.
4. Oppdater **Ordrestatus** til **Faktura**.  
   
    ![](media/entity-form-control/entityform-tutorial-01-24.png)
5. Oppdater **Salgsperson** til **WRK014**.
   
    For å hjelpe deg med å velge **Salgsperson** viser **enhetsskjemakontrollen** automatisk et detaljert oppslag. For å generere og vise dette oppslaget bruker kontrollen **DefaultLookup**-feltgruppen i **Worker**-enheten i Common Data Service. **Worker**-enheten brukes fordi **Sales person**-feltet har typen **Worker**.
   
    ![](media/entity-form-control/entityform-tutorial-01-25.png)
6. Klikk eller trykk på merkeikonet for å lagre endringene.

Dette er siste trinn i forklaringen på hvordan du bruker **enhetsskjemakontrollen** i appene dine. Vi håper at denne artikkelen har gitt deg informasjonen du trenger for å komme i gang med **enhetsskjemakontroll**. Vi vil gjerne høre hva du synes om **enhetsskjemakontrollen** og tjenestene vi tilbyr for å la deg generere funksjonsrike skjemaer for appene dine på en rask måte.

