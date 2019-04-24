---
title: Opprette en komponent for lerretsapper | Microsoft Docs
description: Innføring i gjenbrukbare komponenter for lerretsapper
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 12/12/2018
ms.author: yifwang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 369304ded3fdc9fcd69459da9875e6080d5d860c
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61562242"
---
# <a name="create-a-component-for-canvas-apps"></a>Opprette en komponent for lerretsapper

> [!IMPORTANT]
> Denne funksjonen er fremdeles eksperimentell og deaktivert som standard. Hvis du vil ha mer informasjon, se [Experimental og forhåndsvisning av funksjoner](working-with-experimental.md).

Komponenter er gjenbrukbare byggesteinene for lerret-apper slik at apputviklere kan opprette egendefinerte kontroller for å bruke i en app eller på tvers av apper. Avanserte funksjoner, for eksempel egendefinerte egenskaper, muliggjør komplekse egenskaper i komponenter. Denne artikkelen introduserer komponenten konsepter og noen eksempler.

Komponentene er nyttig å bygge større apper som har lignende mønstre for kontrollen. Hvis du oppdaterer en definisjon for komponenten, er endringene for alle forekomster i appen. Du kan også forbedre ytelsen ved hjelp av én eller flere komponenter fordi du ikke Kopier og Lim inn kontroller, som dupliserer faste kostnader. Komponenter også tilrettelegger for samarbeid om utvikling og standardiserer utseende og funksjonalitet for i en organisasjon.

## <a name="prerequisite"></a>Forutsetning

Åpne den **Appinnstillinger** Velg **avanserte innstillinger**, og aktivere funksjonen, samt å sikre at **forbedret appgjengivelse** også er aktivert.

## <a name="component-canvas"></a>Komponenten lerret

Du kan opprette en komponent fra den **komponenter** -menyen på den **Sett inn** fanen eller, som vist i neste grafisk, i navigasjonsfeltet til venstre. Denne listen viser komponentene som er definert i appen, sortert etter opprettingstidspunkt.

![Komponenten listevisning](./media/create-component/list-view.png)

Uavhengig av hvilken fremgangsmåte du tar, vises et tomt lerret, der du kan legge til kontroller som en del av komponenten definisjonen. Hvis du redigerer en komponent i lerretet, vil du oppdatere forekomster av samme komponent i andre app-skjermer og andre apper.

Hvis du velger en skjerm, kan du velge en komponent fra listen over eksisterende komponenter i navigasjonsfeltet til venstre eller **komponenter** -menyen på den **Sett inn** fanen. Når du velger en komponent, du sette inn en forekomst av denne komponenten på skjermen, på samme måte som du setter inn en kontroll.

## <a name="scope"></a>Omfang

Tenk på en komponent som en encapsulated svart boks med egenskaper som grensesnitt. Du får ikke tilgang til kontroller i komponenten fra utenfor komponenten, og du kan ikke referere til noe utenfor komponenten fra inne i komponenten. Hvis du prøver, vises en feilmelding. Omfanget begrensninger Behold datakontrakt for en komponent enkel og enhetlig, og den hjelper med å aktivere sømløs komponent-definisjonsoppdateringer, spesielt på tvers av apper. Du kan oppdatere datakontrakt av komponenten ved å opprette én eller flere egendefinerte egenskaper.

## <a name="variables"></a>Variabler

Komponentene støtter ikke den **UpdateContext** -funksjonen, men du kan opprette og oppdatere variabler i en komponent ved hjelp av den **angi** funksjonen. Omfanget av disse variablene er begrenset til komponenten, men du kan få tilgang til dem fra utenfor komponenten ved å benytte egendefinerte utdataegenskaper.

## <a name="import-and-export"></a>Importer og Eksporter

Hvis du eksporterer en komponent, kan du opprette en lokal fil som du kan importere til en annen app. Hvis appen inneholder en endret versjon av samme komponent, blir du bedt om å bestemme om du vil erstatte den endrede versjonen eller avbryte importen. Du kan ikke lagre komponenter i skyen eller dele dem i et miljø i skrivende stund.

![Importer og Eksporter](./media/create-component/import.png)

## <a name="custom-properties"></a>Egendefinerte egenskaper

En komponent kan motta inndataverdier og Eksporter data hvis du oppretter én eller flere egendefinerte egenskaper. Disse scenariene er avanserte og krever at du forstå formler og binde kontrakter.

En inndata-egenskapen er hvordan en komponent mottar data som skal brukes i komponenten. Inndataegenskaper vises i den **Egenskaper** fanen i ruten til høyre hvis en forekomst av komponenten er valgt. Du kan konfigurere egenskaper for inndata for med uttrykk og formler, akkurat som du konfigurerer standard egenskaper i andre kontroller. Andre kontroller har inndata egenskaper, slik som den **standard** -egenskapen for en **tekstinndata** kontroll.

Utdataegenskaper kan sende data eller komponent tilstand. For eksempel den **valgt** egenskapen på en **galleriet** kontrollen er en output-egenskapen. Når du oppretter en output-egenskapen, kan du bestemme hva andre kontroller kan referere til en komponent-tilstand.

Denne gjennomgangen ytterligere forklarer disse konseptene.

## <a name="create-an-example-component"></a>Opprette en eksempel-komponent

I dette eksemplet skal du opprette en meny-komponent som ligner på denne grafikken, og der du kan endre teksten og bruke i flere skjermer, apper eller begge:

![Det endelige galleriet](./media/create-component/menu-instance.png)

1. I PowerApps Studio, kan du opprette en tom app.

1. Åpne listen over komponenter i navigasjonsfeltet til venstre, og velg deretter **ny komponent**.

    ![Listen over komponenter](./media/create-component/component-list.png)

1. Når pekeren holdes over den nye komponenten, velger du ellipsen (...), velger **gi nytt navn til**, og Skriv eller lim deretter **MenuComponent**.

1. I den høyre ruten, kan du angi komponentens bredden til **150** og høyden til **250**, og velg deretter **ny egendefinert egenskap**.

    ![Ny egenskap](./media/create-component/new-property.png)

1. I den **visningsnavn**, **egenskapsnavn**, og **beskrivelse** alternativene, Skriv eller Lim inn **elementer**.

    ![Visningsnavn, egenskapsnavn, beskrivelse boksene](./media/create-component/property-names.png)

    Når du angir et egenskapsnavn, ikke ta med mellomrom fordi du vil referere til en komponent med dette navnet når du skriver en formel (for eksempel **ComponentName.PropertyName**).

    Visningsnavnet vises på den **Egenskaper** fanen i ruten til høyre hvis du velger komponenten. Et beskrivende visningsnavn hjelper deg med å og andre som lager forstå hensikten med denne egenskapen. Den **beskrivelse** vises i et verktøytips Hvis du holder pekeren over visningsnavnet for denne egenskapen i den **Egenskaper** fanen.

1. I den **datatypen** listen, velg **tabellen**, og velg deretter **Opprett**.

    ![Datatypen for egenskapen](./media/create-component/property-data-type.png)

    Den **elementer** egenskapen er satt til en standardverdi som er basert på datatypen som du har angitt, men du kan angi en verdi som passer dine behov. Hvis du har angitt en datatype på **tabellen** eller **post**, kan du endre verdien for den **elementer** til å samsvare med det XML-skjemaet som du vil skrive inn til komponenten. I dette tilfellet skal du endre det til en liste over strenger.

    Du kan angi verdien for egenskapen i formellinjen Hvis du velger navnet på egenskapen på den **Egenskaper** fanen i ruten til høyre.

    ![Egendefinert inndata-egenskapen på Egenskaper-fanen](./media/create-component/properties-tab.png)

    Som vist i neste grafisk, kan du også redigere verdien for egenskapen på den **avansert** fanen i ruten til høyre.

1. Angi komponentens **elementer** egenskapen til denne formelen:

    ```powerapps-dot
    Table({Item:"SampleText"})
    ```

    ![Formel](./media/create-component/set-component-items.png)

1. Sett inn en tom loddrett i komponenten, **galleriet** kontroll.

1. Kontroller at egenskapslisten viser den **elementer** egenskapen (slik den gjør det som standard), og angi deretter verdien for egenskapen til dette uttrykket:

    ```powerapps-dot
    MenuComponent.Items
    ```

    På denne måten den **elementer** -egenskapen for den **galleriet** kontrollen leser og avhenger av den **elementer** inndata-egenskapen for komponenten.

1. Angi den **galleriet** kontrollens **BorderThickness** egenskapen til **1** og **TemplateSize** egenskapen til **50**.

1. I malen for den **galleriet** kontrollen, legger til en **etikett** kontroll.

    ![Legg til etikett og angi kantlinjen på galleriet](./media/create-component/add-label.png)

Deretter kan du legge til komponenten til en skjerm og angi en tabell med strenger å vise-komponenten.

1. Velg listen over skjermer i navigasjonsfeltet til venstre, og velg deretter standardskjermen.

    ![Standard-skjermen](./media/create-component/default-screen.png)

1. På den **Sett inn** åpne den **komponenter** -menyen, og velg deretter **MenuComponent**.

    ![Sett inn](./media/create-component/insert.png)

    Den nye komponenten heter **MenuComponent_1** som standard.

1. Angi den **elementer** -egenskapen for **MenuComponent_1** til denne formelen:

    ```powerapps-dot
    Table({Item:"Home"}, {Item:"Admin"}, {Item:"About"}, {Item:"Help"})
    ```

    Denne forekomsten ligner denne grafikken, men du kan tilpasse teksten og andre egenskaper for hver forekomst.

    ![Det endelige galleriet](./media/create-component/menu-instance.png)

Du har så langt har opprettet en komponent og lagt det til en app. Deretter oppretter du en output-egenskapen som gjenspeiler elementet som brukeren velger i menyen.

1. Åpne listen over komponenter, og velg deretter **MenuComponent**.

1. I den høyre ruten, velger du den **Egenskaper** fanen, og velg deretter **ny egendefinert egenskap**.

1. I den **visningsnavn**, **egenskapsnavn**, og **beskrivelse** alternativene, Skriv eller Lim inn **valgt**.

1. Under **egenskapstype**, og velg **utdata**, og velg deretter **Opprett**.

1. På den **avansert** fanen, angi verdien for den **valgt** egenskapen til dette uttrykket, justere tallet i gallerinavnet om nødvendig:

    ```powerapps-dot
    Gallery1.Selected.Item
    ```

    ![Avansert-ruten](./media/create-component/advance.png)

1. På det standardskjermbildet i appen, legge til en etikett, og angi dens **tekst** egenskapen til dette uttrykket, justere tallet i komponentnavnet på den om nødvendig:

    ```powerapps-dot
    MenuComponent_1.Selected
    ```

    Legg merke til at **MenuComponent_1** er standardnavn for en forekomst, ikke navnet på komponenten definisjonen. Du kan gi nytt navn til en forekomst.

1. Mens du holder nede Alt-tasten, velger du hvert element i menyen.

    Den **etikett** kontrollen gjenspeiler menyelementet som du valgte sist.

## <a name="known-limitations"></a>Kjente begrensninger

- I skrivende stund lagres datakilder ikke med komponenter, slik at skjemaer og datatabeller er deaktivert. 
- Hvis du oppretter en variabel i en komponent, vil denne variabelen er tilknyttet bare i denne komponenten og vises ikke med app-variabler.
- PowerApps støtter ikke samlinger i komponenter.
- Du kan ikke sette inn en komponent i et galleri, et skjema eller et datakort.
- En overordnede forekomst av en komponent er en lokal hoved- og omfang til appen. Hvis du endrer en overordnede forekomst, kan bare kopier av komponenten i appen, gjenspeiler endringen. Kopier i andre apper forblir den samme med mindre du importerer komponentbiblioteket på nytt. Alle master forekomster i disse appene vil automatisk oppdaget og oppdatert.
- Du kan ikke pakke mediefiler når du importerer en komponent.
