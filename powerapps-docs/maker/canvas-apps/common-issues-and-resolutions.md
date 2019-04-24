---
title: Vanlige problemer og løsninger for PowerApps | Microsoft Docs
description: En liste over vanlige problemer og løsninger i PowerApps.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 11/09/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3c3b559be5f27c6ead9a4ea2f02027637c8aea8e
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551633"
---
# <a name="common-issues-and-resolutions-for-powerapps"></a>Vanlige problemer og løsninger for PowerApps

Denne artikkelen viser noen vanlige problemer som kan oppstå når du bruker PowerApps. Der det er aktuelt, er løsninger tilgjengelig.

## <a name="added-after-february-2018"></a>Lagt til etter februar 2018

1. **Kamera problemet på Android-mobilenheter** (1. januar 2019)

    Hvis kameraet kontrollen slutter å fungere på en Android-enhet, publisere appen på nytt, og åpne den på nytt på enheten. Kamera-kontrollen ble oppdatert som svar på en endring i Android-operativsystemet, og appen vil dra nytte av oppdateringen når du publiserer på nytt.

1. **Rulling i fleksibel høyde gallerier** (27. november 2018)

    Hvis du støter på en begrensning når du ruller med fingeren, løft den, og begynn å rulle på nytt.

1. **Tegning med musen eller inndata via berøring er ikke jevn i PowerApps for Windows** (tekstfiler 24, 2018)

    Pennekontrollen har bare delvis støtte for tegning ved hjelp av musen eller touch inndata i Windows-app. Streker kan være midlertidig. For jevn tegning, kan du bruke en penn eller kjøre appen i en nettleser.

1. **Flere mediekontroller i PowerApps Mobile** (2. august 2018)

    PowerApps Mobile kjører på forskjellige typer enheter, og noen av dem har begrensninger som er spesifikke for plattformen:

    - Du kan spille av videoer i flere **Video**-kontroller samtidig på alle plattformer, bortsett fra iPhone-enheter.
    - Du kan spille inn lydklipp med flere **Mikrofon**-kontroller samtidig på alle plattformer, bortsett fra nettspilleren.

1. **Ny publisering av apper** (2. august 2018)

    Hvis du ikke har oppdatert appen på flere måneder, må du publisere den på nytt for å synkronisere den med den nyeste versjonen av PowerApps, som inkluderer ytelsesforbedringer og andre løsninger.

1. <a name="out-of-memory"></a>**Leseren går tom for minne** (23. juli 2018)

    Hvis du kjører ikke nok minne når du bruker PowerApps, kan du vurdere å laste ned en 64-biters versjon av Chrome, Microsoft Edge eller Internet Explorer.

1. **Start et nettsted fra en innebygd app** (10. mai 2018)

    Internet Explorer og Microsoft Edge kan blokkere åpningen av en nettadresse eller et nettsted som er i beskyttet modus, eller har en lavere sikkerhetssone enn webområdet hvor appen er lastet inn. Du løser dette problemet ved å [endre innstillingene for sikkerhet og personvern](https://support.microsoft.com/en-us/help/17479/windows-internet-explorer-11-change-security-privacy-settings) for nettleseren.

1. **Kombinasjonsbokskontroller i gallerier** (3. mai 2018)

    Når du bruker en **kombinasjonsboks**-kontroll i et galleri, beholdes ikke valgene for den når brukeren ruller i galleriet. Dette er ikke et problem hvis du bruker en **kombinasjonsboks**-kontroll i et galleri som ikke ruller. En midlertidig løsning er ikke tilgjengelig.

1. **Bruk et egendefinert bilde som et appikon** (11. april 2018)

    Du kan ikke laste opp et egendefinert bilde som skal brukes som et ikon for appen i PowerApps Studio for Windows (versjon 3.18043). Hvis du vil omgå dette problemet, kan du bruke [PowerApps Studio for nett](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) for å laste opp et egendefinert bilde. Du kan eventuelt bruke ett av ikonene som er inkludert i PowerApps Studio for Windows og tilpasse bakgrunnsfargen.

1. **Kopier og lim inn skjermer på tvers av apper** (4. april 2018)

    Kopiering og innliming av skjermer på tvers av apper støttes ikke. Hvis du vil omgå dette, kan du legge til en ny skjerm i mål-appen, kopiere kontrollene fra skjermen i kilde-appen og deretter lime dem inn på skjermen for mål-appen.

1. **Endre oppsettet til SharePoint-skjemaer** (7. mars 2018)

    Når du prøver å endre oppsettet fra stående (standard) til liggende mens du tilpasser et SharePoint-listeskjema på bestemte språk, kan det hende appen viser flere feil (gule trekanter i kontroller). Du løser disse feilene og beholder liggende retning ved å klikke på **Angre**.

## <a name="added-in-or-before-february-2018"></a>Lagt til i eller før februar 2018

1. **Datatabell-kontroll**

    Hvis du kopierer og limer inn en **Datatabell**-kontroll der **Elementer**-egenskapen er angitt til en formel som inneholder en **Filter**-funksjon, ender formelen for **Elementer**-egenskapen på den nye **Datatabell**-kontrollen opp med feltnavn som inneholder et **_1**-suffiks. Dette gjør feltnavnene ugyldige og resulterer i at ingen data vises i datatabellen. Du kan omgå dette problemet før du kopierer kontrollen, ved å bekrefte at **Filter**-funksjonen ikke refererer til et felt i datakilden, som har samme navn som en kolonne i **Datatabell**-kontrollen. Hvis den har det, gir du et nytt navn til kolonnen i **Datatabell**-kontrollen. Du kan også fjerne **_1**-suffikset fra de ugyldige feltnavnene, slik at de samsvarer med navnene i enheten.

1. **Kamerakontroller i PowerApps Studio for Windows**

    PowerApps Studio for Windows kan krasje hvis du legger til en kamerakontroll eller åpner en app som bruker en kamerakontroll. Du unngår dette problemet ved å bruke [PowerApps Studio for nett](create-app-browser.md) når du legger til eller bruker en kamerakontroll.

1. **Versjon 2.0.700 på Android-enheter**

    Hvis du installerer versjon 2.0.700 på en Android-enhet, og deretter ikke kan åpne apper (eller en app slutter å svare), kan du avinstallere PowerApps, starte enheten på nytt og deretter installere PowerApps på nytt.

1. **«Tomt» galleri når du åpner en app**

    Hvis du genererer en app automatisk fra data, lagrer du appen og åpner den deretter på nytt. Bla gjennom-galleriet viser kanskje ikke data umiddelbart. Du løser dette problemet ved å skrive inn minst ett tegn i søkeboksen og deretter slette teksten du har skrevet inn. Galleriet viser deretter data som forventet.

1. **Oppgradering av PowerApps på Windows 8.1**

    Hvis du installerer PowerApps på en datamaskin som kjører Windows 8 eller Windows 8.1, holder du Windows Store-appen åpen og aktiv, bruker Innstillinger-symbolet for å se etter oppdateringer, og deretter installerer du dem.

1. **Egendefinerte koblinger og Common Data Service**

    Hvis en app som er opprettet ved hjelp av PowerApps bygg 2.0.540 eller tidligere, er avhengig av en database i Common Data Service og minst én egendefinert kobling i et annet miljø, må du distribuere koblingen i det samme miljøet som databasen og oppdatere appen for å bruke den nye koblingen. Hvis ikke, vil en dialogboks varsle brukerne om at API-en ikke ble funnet. Hvis du vil ha mer informasjon, kan du se [Oversikt over miljøer](../../administrator/environments-overview.md).

1. **Kjøring av en app på Windows 8.1**

    Hvis du installerer [denne oppdateringen for Windows 8.1](https://technet.microsoft.com/library/security/ms16-118), kan du ikke kjøre apper du åpner i PowerApps Studio i dette operativsystemet. Du kan imidlertid fremdeles kjøre apper du åpner på [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) eller ved hjelp av PowerApps Mobile.

1. **Kolonnenavn med mellomrom**

    Hvis du bruker en SharePoint-liste eller en Excel-tabell der et kolonnenavn inneholder et mellomrom, erstattes dette med **\_x0020\_** i PowerApps. **Kolonnenavn** i SharePoint eller Excel, vil for eksempel vises som **Column_x0020_Name** i PowerApps når det vises i dataoppsettet, eller brukes i en formel.

1. **Å endre en flyt i en delt app**

    Hvis du legger til en flyt i en app, deler den og deretter legger til en tjeneste eller endrer en kobling i flyten, må du fjerne flyten fra den delte appen, legge til flyten på nytt og dele appen på nytt. Hvis ikke, får brukere som utløser flyten en godkjenningsfeil.

1. **Å bruke en lokalisert versjon**.

    Hvis du kjører versjon 2.0.531 på Windows 8.1, kan du ikke skrive inn en kontroll for **Tekstinndata** hvis enheten er stilt inn på et språk som krever et IME-vindu.

1. **Kamerakontroll på en Windows Phone**

    En app som inneholder en kamerakontroll kan komme til å krasje hvis du åpner appen på en Windows Phone som kjører bygg 10.0.10586.107. Du unngår dette problemet ved å oppgradere til den nyeste versjonen (for eksempel ved å kjøre [Upgrade Advisor](https://www.microsoft.com/store/p/upgrade-advisor/9nblggh0f5g4)).

1. **Å åpn en app fra en mal**.

    Hvis du kjører versjon 2.0.500 eller eldre, vises en feilmelding når du prøver å opprette en app fra en mal. Du må oppgradere for å kunne bruke denne funksjonen.

    Hvis du kjører versjon 2.0.510 eller senere, vises kanskje en advarsel når du prøver å opprette en app fra en mal. Du kan imidlertid lukke meldingen og opprette appen.

1. **Å skanne en strekkode**

    Hvis du vil ha informasjon om begrensninger og anbefalte fremgangsmåter når du bruker en **Strekkode**-kontroll, kan du se [Å skanne en strekkode](scan-barcode.md).

1. **Å opprette og endre apper i en nettleser**

    Du kan gjøre mange, men ikke alle, av de samme tingene i PowerApps Studio for nett, som du kan i PowerApps Studio for Windows. Hvis du vil ha mer informasjon, kan du se [Å opprette en app i en nettleser](create-app-browser.md).

1. **Å endre et tittelfelt i en enhet**

    Hvis du endrer tittelfeltet for en enhet som andre enheter refererer til gjennom ett eller flere oppslag, oppstår en feilmelding når du prøver å lagre endringen. Du kan omgå dette problemet ved å fjerne oppslag for enheten du vil endre tittelfelt for, gjøre endringen og deretter opprette oppslagene på nytt. Hvis du vil ha mer informasjon om oppslag, kan du se [Å opprette relasjoner mellom enheter](../common-data-service/data-platform-entity-lookup.md).

1. **Apper som kan kobles til lokal SharePoint**

    Hvis du deler en app som er avhengig av tilkoblinger som ikke deles automatisk (for eksempel et lokalt SharePoint-område), vil brukere som åpner appen i en nettleser se en dialogboks uten tekst når de klikker eller trykker på **Logg på**. Du lukker dialogboksen ved å klikke eller trykke på lukk (X)-ikonet i øvre høyre hjørne. Dialogboksen vises ikke hvis du åpner appen i PowerApps Studio eller PowerApps Mobile. Hvis du vil ha mer informasjon om delte tilkoblinger, kan du se [Dele appressurser](share-app-resources.md).

1. **Når PowerApps genererer en app fra data, konfigureres ikke feltet som brukes til sortering og søk automatisk**.

   Du konfigurerer dette feltet ved å redigere **[Elementer](controls/properties-core.md)**-formelen for galleriet, slik delene for filtrering og sortering i [Legg til et galleri](add-gallery.md) beskriver.

1. **Bare de 500 første postene i en datakilde kan åpnes i apper som er opprettet fra data**.

     PowerApps fungerer vanligvis med en datakilde på hvilken som helst størrelse, ved at operasjoner delegeres til datakilden. Operasjoner som ikke kan delegeres, får en advarsel fra PowerApps i redigeringsmodus og opererer bare på de 500 første postene i datakilden.  Hvis du vil ha mer informasjon om delegering, kan du se [Filterfunksjon](functions/function-filter-lookup.md)-artikkelen.

1. **Excel-data må være formatert som en tabell**.

     Hvis du vil ha informasjon om begrensninger når du bruker Excel som datakilde, kan du se [Skylagringstilkoblinger](connections/cloud-storage-blob-connections.md#known-limitations).

1. **Egendefinerte SharePoint-lister støttes, men biblioteker, noen typer listekolonner eller kolonner som støtter flere verdier eller valg, støttes ikke**.

     Hvis du vil ha mer informasjon, kan du se [SharePoint Online](connections/connection-sharepoint-online.md#known-issues).

1. **Samtidig redigering støttes ikke. Én forfatter om gangen**.

     Du kan ødelegge en app eller overskrive andres endringer hvis mer enn én person endrer samme app samtidig. Lukk appen før noen andre redigerer den.

1. **Noen ganger kan det ta litt tid før en nylig delt app kan tas i bruk**.

     I enkelte tilfeller vil ikke en nylig delt app være tilgjengelig umiddelbart. Vent litt, så blir den tilgjengelig.

1. Du kan ikke endre data  **i [Skjema-kontrollen](controls/control-form-detail.md) ved å bruke et egendefinert kort**.

     Det egendefinerte kortet for lager mangler **[Oppdatering](controls/control-card.md)**-egenskapen, noe som kreves for å skrive tilbake endringer. Du kan omgå dette slik:

    * Velg skjema-kontrollen, og sett inn et kort ved å bruke den høyre ruten som er basert på feltet du vil at kortet skal vise.  
    * Lås opp kortet, som beskrevet i [Forstå datakort](working-with-cards.md#unlock-a-card).
    * Fjern eller organiser kontrollene på nytt i kortet slik det passer, på samme måte som med det egendefinerte kortet.

1. **En app som kjører på Android 5.0, Nexus 6 med Webview-versjonene v48 eller v49 kan komme til å krasje**.

     Brukere kan løse dette problemet ved å oppdatere til en tidligere versjon av Webview (3x) eller oppdatere til Android 6.0.

1. **Kamerabruk kan være midlertidig deaktivert hvis det er lite minne**.

     Hvis mobilenheten har lite minne, deaktiveres kameraet midlertidig for å unngå at enheten krasjer.

1. **Office 365 Video-koblingen støttes ikke**.

1. **Kortgalleriet er avskrevet**.

     Eksisterende apper som bruker denne funksjonen, vil for øyeblikket fortsette å kjøre, men du kan ikke legge til et kortgalleri. Erstatt kortgallerier med de nye kontrollene **[Redigeringsskjema](controls/control-form-detail.md)** og **[Visningsskjema](controls/control-form-detail.md)**.
