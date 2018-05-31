---
title: Vanlige problemer og løsninger for PowerApps | Microsoft Docs
description: Les om problemer og løsninger for PowerApps
services: ''
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/05/2018
ms.author: sharik
ms.openlocfilehash: 6df3a0d92f8dd8352f93bdb377ac9c4b446e1e99
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30996332"
---
# <a name="common-issues-and-resolutions-for-powerapps"></a>Vanlige problemer og løsninger for PowerApps
## <a name="recently-addedchanged"></a>Nylig lagt til eller endret
1. **Endring av oppsettet til SharePoint-skjemaer**

    Når du prøver å endre oppsettet fra stående (standard) til liggende mens du tilpasser et SharePoint-listeskjema på bestemte språk, kan det hende appen viser flere feil (gule trekanter i kontroller). Du løser disse feilene og beholder liggende retning ved å klikke på **Angre**.

1. **Appen fungerer ikke**

    Hvis appen du har opprettet plutselig slutter å fungere, kan det hende du ikke har oppdatert eller publisert den på nytt de siste seks månedene. Du løser dette problemet ved å oppdatere eller publisere appen på nytt, slik at den synkroniseres med den nyeste versjonen av PowerApps. Deretter sørger du for å fortsette å oppdatere eller publisere appen på nytt innen seks måneder etter siste publisering.

1. **Datatabellkontroll**

    Hvis du kopierer og limer inn en **Datatabell**-kontroll der **Elementer**-egenskapen er angitt til en formel som inneholder en **Filter**-funksjon, ender formelen for **Elementer**-egenskapen på den nye **Datatabell**-kontrollen opp med feltnavn som inneholder et **_1**-suffiks. Dette gjør feltnavnene ugyldige og resulterer i at ingen data vises i datatabellen. Du kan omgå dette problemet før du kopierer kontrollen, ved å bekrefte at **Filter**-funksjonen ikke refererer til et felt i datakilden, som har samme navn som en kolonne i **Datatabell**-kontrollen. Hvis den har det, gir du et nytt navn til kolonnen i **Datatabell**-kontrollen. Du kan også fjerne **_1**-suffikset fra de ugyldige feltnavnene, slik at de samsvarer med navnene i enheten.

1. **Kamerakontroller i PowerApps Studio for Windows**

    PowerApps Studio for Windows kan krasje hvis du legger til en kamerakontroll eller åpner en app som bruker en kamerakontroll. Du unngår dette problemet ved å bruke [PowerApps Studio for nett](create-app-browser.md) når du legger til eller bruker en kamerakontroll.

2. **Versjon 2.0.700 på Android-enheter**

    Hvis du installerer versjon 2.0.700 på en Android-enhet, og deretter ikke kan åpne apper (eller en app slutter å svare), kan du avinstallere PowerApps, starte enheten på nytt og deretter installere PowerApps på nytt.

3. **«Tomt» galleri når du åpner en app**

    Hvis du genererer en app automatisk fra data, lagrer du appen og åpner den deretter på nytt. Bla gjennom-galleriet viser kanskje ikke data umiddelbart. Du løser dette problemet ved å skrive inn minst ett tegn i søkeboksen og deretter slette teksten du har skrevet inn. Galleriet viser deretter data som forventet.

4. **Oppgradering av PowerApps på Windows 8.1**

    Hvis du installerer PowerApps på en datamaskin som kjører Windows 8 eller Windows 8.1, holder du Windows Store-appen åpen og aktiv, bruker Innstillinger-symbolet for å se etter oppdateringer, og deretter installerer du dem.

5. **Egendefinerte koblinger og Common Data Service**

   Hvis en app som er opprettet ved hjelp av PowerApps bygg 2.0.540 eller tidligere, er avhengig av en database i Common Data Service og minst én egendefinert kobling i et annet miljø, må du distribuere koblingen i det samme miljøet som databasen og oppdatere appen for å bruke den nye koblingen. Hvis ikke, vil en dialogboks varsle brukerne om at API-en ikke ble funnet. Hvis du vil ha mer informasjon, kan du se [Oversikt over miljøer](../../administrator/environments-overview.md).

6. **Kjøring av en app på Windows 8.1**

    Hvis du installerer [denne oppdateringen for Windows 8.1](https://technet.microsoft.com/library/security/ms16-118), kan du ikke kjøre apper du åpner i PowerApps Studio i dette operativsystemet. Du kan imidlertid fremdeles kjøre apper du åpner i [powerapps.com](https://web.powerapps.com), eller ved bruk av PowerApps Mobile.

7. **Kolonnenavn med mellomrom**

    Hvis du bruker en SharePoint-liste eller en Excel-tabell der et kolonnenavn inneholder et mellomrom, erstattes dette med **\_x0020\_** i PowerApps. **Kolonnenavn** i SharePoint eller Excel vil for eksempel vises som **Column_x0020_Name** i PowerApps når de vises i dataoppsettet eller brukes i en formel.

## <a name="older"></a>Eldre
1. **Endring av en flyt i en delt app**

    Hvis du legger til en flyt i en app, deler den og deretter legger til en tjeneste eller endrer en kobling i flyten, må du fjerne flyten fra den delte appen, legge til flyten på nytt og dele appen på nytt. Hvis ikke, får brukere som utløser flyten en godkjenningsfeil.

2. **Bruk av en lokalisert versjon**.

    Hvis du kjører versjon 2.0.531 på Windows 8.1, kan du ikke skrive inn en kontroll for **Tekstinndata** hvis enheten er stilt inn på et språk som krever et IME-vindu.

3. **Kamerakontroll på en Windows Phone**

    En app som inneholder en kamerakontroll kan komme til å krasje hvis du åpner appen på en Windows Phone som kjører bygg 10.0.10586.107. Du unngår dette problemet ved å oppgradere til den nyeste versjonen (for eksempel ved å kjøre [Upgrade Advisor](https://www.microsoft.com/store/p/upgrade-advisor/9nblggh0f5g4)).

4. **Åpne en app fra en mal**.

    Hvis du kjører versjon 2.0.500 eller eldre, vises en feilmelding når du prøver å opprette en app fra en mal. Du må oppgradere for å kunne bruke denne funksjonen.

    Hvis du kjører versjon 2.0.510 eller senere, vises kanskje en advarsel når du prøver å opprette en app fra en mal. Du kan imidlertid lukke meldingen og opprette appen.

5. **Skanning av en strekkode**

    Hvis du vil ha informasjon om begrensninger og anbefalte fremgangsmåter når du bruker en **Strekkode**-kontroll, kan du se [Skanne en strekkode](scan-barcode.md).

6. **Oppretting og endring av apper i en nettleser**

    Du kan gjøre mange, men ikke alle, av de samme tingene i PowerApps Studio for nett, som du kan i PowerApps Studio for Windows. Hvis du vil ha mer informasjon, kan du se [Oppretting av en app i en nettleser](create-app-browser.md).

7. **Endring av et tittelfelt i en enhet**

    Hvis du endrer tittelfeltet for en enhet som andre enheter refererer til gjennom ett eller flere oppslag, oppstår en feilmelding når du prøver å lagre endringen. Du kan omgå dette problemet ved å fjerne oppslag for enheten du vil endre tittelfelt for, gjøre endringen og deretter opprette oppslagene på nytt. Hvis du vil ha mer informasjon om oppslag, kan du se [Oppretting av relasjoner mellom enheter](../common-data-service/data-platform-entity-lookup.md).

8. **Apper som kan kobles til lokal SharePoint**

    Hvis du deler en app som er avhengig av tilkoblinger som ikke deles automatisk (for eksempel et lokalt SharePoint-område), vil brukere som åpner appen i en nettleser se en dialogboks uten tekst når de klikker eller trykker på **Logg på**. Du lukker dialogboksen ved å klikke eller trykke på lukk (X)-ikonet i øvre høyre hjørne. Dialogboksen vises ikke hvis du åpner appen i PowerApps Studio eller PowerApps Mobile. Hvis du vil ha mer informasjon om delte tilkoblinger, kan du se [Dele appressurser](share-app-resources.md).

9. **Når PowerApps genererer en app fra data, konfigureres ikke feltet som brukes til sortering og søk automatisk**.

   Du konfigurerer dette feltet ved å redigere **[Elementer](controls/properties-core.md)**-formelen for galleriet, slik delene for filtrering og sortering i [Legg til et galleri](add-gallery.md) beskriver.

10. **Bare de 500 første postene i en datakilde kan åpnes i apper som er opprettet fra data**.

     PowerApps fungerer vanligvis med en datakilde på hvilken som helst størrelse, ved at operasjoner delegeres til datakilden. Operasjoner som ikke kan delegeres, får en advarsel fra PowerApps i redigeringsmodus og opererer bare på de 500 første postene i datakilden.  Hvis du vil ha mer informasjon om delegering, kan du se [Filterfunksjon](functions/function-filter-lookup.md)-artikkelen.

11. **Excel-data må være formatert som en tabell**.

     Hvis du vil ha informasjon om begrensninger når du bruker Excel som datakilde, kan du se [Skylagringstilkoblinger](connections/cloud-storage-blob-connections.md#known-limitations).

12. **Egendefinerte SharePoint-lister støttes, men biblioteker, noen typer listekolonner eller kolonner som støtter flere verdier eller valg, støttes ikke**.

     Hvis du vil ha mer informasjon, kan du se [SharePoint Online](connections/connection-sharepoint-online.md#known-issues).

13. **Samtidig redigering støttes ikke. Én forfatter av gangen**.

     Du kan ødelegge en app eller overskrive andres endringer hvis mer enn én person endrer samme app samtidig. Lukk appen før noen andre redigerer den.

14. **Noen ganger kan det ta litt tid før en nylig delt app kan tas i bruk**.

     I enkelte tilfeller vil ikke en nylig delt app være tilgjengelig umiddelbart. Vent litt, så blir den tilgjengelig.

15. Du kan ikke endre data  **i [Skjemakontrollen](controls/control-form-detail.md) ved å bruke et egendefinert kort**.

     Det egendefinerte kortet for lager mangler **[Oppdatering](controls/control-card.md)**-egenskapen, noe som kreves for å skrive tilbake endringer. Du kan omgå dette slik:

    * Velg skjemakontrollen, og sett inn et kort ved å bruke den høyre ruten som er basert på feltet du vil at kortet skal vise.  
    * Lås opp kortet, som beskrevet i [Forstå datakort](working-with-cards.md#unlock-a-card).
    * Fjern eller organiser kontrollene på nytt i kortet slik det passer, på samme måte som med det egendefinerte kortet.

16. **En app som kjører på Android 5.0, Nexus 6 med Webview-versjonene v48 eller v49 kan komme til å krasje**.

     Brukere kan løse dette problemet ved å oppdatere til en tidligere versjon av Webview (3x) eller oppdatere til Android 6.0.

17. **Kamerabruk kan være midlertidig deaktivert hvis det er lite minne**.

     Hvis mobilenheten har lite minne, deaktiveres kameraet midlertidig for å unngå at enheten krasjer.

18. **Office 365 Video-koblingen støttes ikke**.

19. **Kortgalleriet er avskrevet**.

     Eksisterende apper som bruker denne funksjonen, vil for øyeblikket fortsette å kjøre, men du kan ikke legge til et kortgalleri. Erstatt kortgallerier med de nye kontrollene **[Redigeringsskjema](controls/control-form-detail.md)** og **[Visningsskjema](controls/control-form-detail.md)**.
