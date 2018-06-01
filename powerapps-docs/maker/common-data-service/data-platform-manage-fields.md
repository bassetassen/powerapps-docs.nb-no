---
title: Behandling av egendefinerte felt i en hurtiginnføring i enheter | Microsoft Docs
description: Hurtiginnføring for opprette, lese, oppdatere og slette egendefinerte felt i en enhet.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 2175b684d88d1823fd2672f672e776ca1e26f164
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997427"
---
# <a name="quickstart-manage-custom-fields"></a>Hurtiginnføring i å behandle egendefinerte felt
Du kan opprette og oppdatere ett eller flere egendefinerte felt i en enhet. Når du oppretter et egendefinert felt, kan du angi et sett med egenskaper som feltnavn, visningsnavn, og typen data det skal inneholde. Hvis du vil ha mer informasjon, kan du se [Attributtmetadata for enhet](../../developer/common-data-service/entity-attribute-metadata.md).

> [!NOTE]
> Hver enhet har systemfelt, felt som angir når en post sist ble oppdatert, og hvem som oppdaterte det. [Standardenheter](data-platform-intro.md#system-fields) har i tillegg standardfelt. Du kan ikke endre eller slette systemfelt eller standardfelt. Hvis du oppretter et egendefinert felt, får du funksjonalitet i tillegg til disse innebygde feltene.

## <a name="create-a-field"></a>Å opprett et felt

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Legg til et nytt felt i enheten ved å klikke på **Legg til felt**.

4. I Nytt felt-panelet angir du **visningsnavn** for feltet. **Navn**-feltet blir automatisk utfylt og brukes som det unike navnet for feltet. **Visningsnavnet** brukes ofte når du presenterer dette feltet for brukerne dine, og **Navn**-feltet brukes når du bygger en app, i uttrykk og formler.

    > [!NOTE]
    > **Visningsnavn**-feltet kan oppdateres når som helst til en annen visning i appene dine, men **Navn**-feltet kan ikke endres etter at enheten er lagret. Dette kan resultere i at en eksisterende app ødelegges.

    ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel.png "Nytt felt-panel")

5. Velg **datatypen** til feltet. Dette kontrollerer måten informasjonen lagres så vel som hvordan den presenteres i appene. Tekst lagres for eksempel annerledes enn et desimaltall eller en nettadresse. Hvis du vil ha mer detaljert informasjon om tilgjengelige datatyper, kan du se [Attributtmetadata for enhet](../../developer/common-data-service/entity-attribute-metadata.md).

    Hvis du blir bedt om det, angir du ytterligere informasjon for datatypen som angav. Forskjellige felt presenteres avhengig av datatypen. Hvis du oppretter et felt av typen Alternativsett eller Flervalg av alternativsett, kan du velge **Nytt alternativsett** og opprette et nytt alternativsett når du oppretter feltet. Hvis du vil ha mer informasjon, kan du se [Oppretting av et alternativsett](custom-picklists.md)

    ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Nytt felt-panel")


7. Merk av for om du vil anbefale dette feltet som obligatorisk i appene dine, under **Obligatorisk**. Dette fører ikke til streng håndhevelse gjennom alle tilkoblingene til Common Data Service. Hvis du må sikre at feltet fylles ut, oppretter du en [forretningsregel](data-platform-create-business-rule.md)

8. Merk av for om du trenger at dette feltet er tilgjengelig i Visninger, Diagrammer, Instrumentbord og Avansert søk, under **Søkbar**. I de fleste tilfellene bør du merke av for dette.

9. Klikk eller trykk på **Ferdig** for å lukke feltpanelet og gå tilbake til enheten. Du kan gjenta trinnene 3–9 for hvert tilleggsfelt.
   
    > [!IMPORTANT]
    > Feltet er ikke lagret og opprettet før du lagrer endringene i enheten.

10. Klikk eller trykk på **Lagre enhet** for å fullføre endringene, og lagre dem til Common Data Service.

    Du blir varslet når operasjonen er fullført. Hvis operasjonen mislykkes, viser en feilmelding problemene som oppstod og hvordan du kan rette dem opp.

## <a name="create-a-calculated-or-roll-up-field"></a>Oppretting av et beregnet eller opprullingsfelt

Med beregnede felt kan du automatisere manuelle beregninger som brukes i forretningsprosesser. En selger ønsker for eksempel å vite vektet omsetning for en mulighet som er basert på anslått omsetning fra en mulighet, multiplisert med sannsynligheten. Eller selgeren ønsker kanskje å ta i bruk en rabatt automatisk, hvis en bestilling er større enn USD 500. Et beregnet felt kan inneholde verdier fra enkle matematiske operasjoner, eller betingede operasjoner, som for eksempel større enn/eller/hvis/annet, og mange andre. Du kan opprette beregnede felt ved bruk av følgende datatyper:

* Enkeltlinje med tekst
* Alternativsett
* To alternativer
* Heltall
* Desimaltall
* Valuta
* Dato og klokkeslett

Hvis du vil ha mer informasjon om uttrykkstypene som støttes og eksempler, kan du se [Definering av beregnede felt](/dynamics365/customer-engagement/customize/define-calculated-fields)


## <a name="update-or-delete-a-field"></a>Oppdater eller slett et felt
1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute. Deretter klikker eller trykker du på en enhet.
2. I feltlisten for enheten du valgte kan du klikke eller trykke på et felt, og deretter følge ett av disse trinnene:
   
   * Du kan endre én eller flere egenskaper for feltet.
   * Du kan slette feltet ved å klikke eller trykke på ellipsen (...) i nærheten av høyre kant av feltet, og deretter klikke eller trykke på **Slett**.

3. Klikk eller trykk på **Lagre enhet** for å sende inn endringene.
   
    > [!IMPORTANT]
    > Endringene går tapt hvis du ikke lagrer dem før du åpner en ny side i nettleseren, eller avslutter nettleseren.

    Du blir varslet når operasjonen er fullført. Hvis operasjonen mislykkes, viser en feilmelding problemene som oppstod og hvordan du kan rette dem opp.

## <a name="best-practices-and-restrictions"></a>Anbefalte fremgangsmåter og begrensninger
Når du oppretter og endrer felt, må du huske på følgende:

* Du kan ikke endre eller slette systemfelt eller verdiene deres.
* Du kan ikke endre eller slette et standardfelt, legge til et felt som krever data, eller foreta noen annen handling som kan ødelegge appen som baserer seg på enheten, i en standardenhet.
* I en egendefinert enhet må du sørge for at endringene du foretar deg, ikke ødelegger en app som baserer seg på den enheten.
* Du må gi hvert egendefinert felt et navn som er unikt i enheten, og du kan ikke gi feltet et nytt navn etter at du har opprettet det.

## <a name="next-steps"></a>Neste trinn
* [Definering av relasjoner mellom enheter](data-platform-entity-lookup.md)
* [Definering av en forretningsregel](data-platform-create-business-rule.md)
* [Oppretting av en app ved bruk av enheter](../canvas-apps/data-platform-create-app.md)
* [Slik oppretter du en app fra grunnen av ved hjelp av en Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Erklæring om personvern
Med den vanlige datamodellen i Microsoft PowerApps samler vi inn og lagrer egendefinerte enhets- og feltnavn i diagnostiseringssystemene.  Vi bruker denne kunnskapen til å forbedre den vanlige datamodellen for kundene våre. Enhets- og feltnavnene som skapere oppretter, hjelper oss med å forstå scenarioene som er typiske i Microsoft PowerApps-fellesskapet og få rede på hull i tjenestens standarddekning for enheter, som eksempelvis skjema knyttet til organisasjoner. Dataene i databasetabeller som er knyttet til disse enhetene, blir ikke åpnet eller brukt av Microsoft eller replisert utenfor området hvor databasen er klargjort. Merk deg imidlertid at den egendefinerte enheten og feltnavnene kan repliseres på tvers av områder og blir slettet i henhold til retningslinjene våre for dataoppbevaring. Microsoft tar vare på personvernet ditt, som beskrevet i [Klareringssenteret](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

