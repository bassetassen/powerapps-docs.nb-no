---
title: Administrere egendefinerte felt i en enhet | Microsoft Docs
description: 'Gjennomgang av hvordan du oppretter, leser, oppdaterer og sletter egendefinerte felt i en enhet i Common Data Service.'
author: lancedMicrosoft
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="manage-custom-fields-in-an-entity"></a>Administrere egendefinerte felt i en enhet
Du kan opprette og oppdatere ett eller flere egendefinerte felt i en enhet. Når du oppretter et egendefinert felt, kan du angi en rekke egenskaper, for eksempel feltnavnet, visningsnavnet og datatypen som det skal inneholde. Hvis du vil ha mer informasjon, kan du se [Attributtmetadata for enhet](../../developer/common-data-service/entity-attribute-metadata.md).

> [!NOTE]
> Hver enhet har systemfelt, for eksempel felt som angir når en oppføring sist ble oppdatert, og hvem som oppdaterte den. I tillegg har standardenheter standardfelt. Du kan ikke endre eller slette systemfelt eller standardfelt. Hvis du oppretter et egendefinert felt, må det inneholde funksjonalitet utover disse innebygde feltene.

## <a name="create-a-field"></a>Opprette et felt
1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Legg til et nytt felt i enheten ved å klikke på **Legg til felt**.

4. I Nytt felt-panelet angir du **Visningsnavn** for feltet. **Navn** fylles ut automatisk og brukes som det unike navnet på feltet. **Visningsnavn** brukes når du presenterer dette feltet til brukerne. **Navn** brukes når du bygger appen, i uttrykk og formler.

    > [!NOTE]
    > **Visningsnavn**-felt kan bli oppdatert når som helst for å vises annerledes i apper. **Navn**-feltet kan ikke endres etter at enheten er lagret, siden dette kan føre til brudd i en eksisterende app.

    > [!div class="mx-imgBorder"] 
    > ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel.png "Panelet for nytt felt")

5. Velg **Datatype** for feltet. Dette kontrollerer hvordan informasjonen lagres og hvordan den vises i apper. For eksempel lagres tekst forskjellig for et desimaltall eller en URL-adresse. For mer informasjon om datatypene som er tilgjengelig, kan du se [Attributtmetadata for enhet](../../developer/common-data-service/entity-attribute-metadata.md).

    Hvis du blir bedt om det, kan du angi ytterligere informasjon om datatypen du har angitt. Avhengig av datatype vises det andre felt. Hvis du oppretter et felt av typen Alternativsett eller Alternativsett med flere valg, kan du velge **Nytt alternativsett** og opprette et nytt alternativsett når du oppretter feltet. Hvis du vil ha mer informasjon, kan du se [Opprette alternativsett](custom-picklists.md).

    > [!div class="mx-imgBorder"] 
    > ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Panelet for nytt felt")


7. Under **Obligatorisk** merker du av hvis du vil anbefale dette feltet som obligatorisk i apper. Dette sørger ikke for hard håndhevelse gjennom alle tilkoblinger til Common Data Service. Hvis du vil sikre at feltet fylles ut, oppretter du en [forretningsregel](data-platform-create-business-rule.md)

8. Under **Søkbar** merker du av hvis du har behov for at dette feltet skal være tilgjengelig i visninger, diagrammer, instrumentbord og avansert søk. I de fleste tilfeller må dette være merket av for.

9. Klikk eller trykk **Fullført** for å lukke feltpanelet og gå tilbake til enheten. Du kan gjenta trinn 3 til 9 for hvert ekstra felt.
   
    > [!IMPORTANT]
    > Feltet blir ikke endelig opprettet før du lagrer endringene i enheten.

10. Klikk eller trykk **Lagre enhet** for å fullføre endringene og lagre dem i Common Data Service.

    Du blir varslet når handlingen er fullført. Hvis den mislykkes, angir en feilmelding problemene som oppstod, og hvordan du kan rette dem.

## <a name="create-a-calculated-or-roll-up-field"></a>Opprette et beregnet felt eller et felt for beregnet verdi
Med beregnede felt kan du automatisere manuelle beregninger som brukes i forretningsprosessene. En selger vil for eksempel vite hva vektet omsetning er for en salgsmulighet, som er basert på den beregnede omsetningen fra en salgsmulighet multiplisert med sannsynligheten. Eller de vil legge på en rabatt automatisk hvis en ordre er større enn 500 kroner. Et beregnet felt kan inneholde verdier fra vanlige matematiske eller betingede operasjoner, for eksempel større enn og hvis-ellers. Beregnede felt kan opprettes ved hjelp av følgende datatyper:

* En enkelt linje med tekst
* Alternativsett
* To alternativer
* Heltall
* Desimaltall
* Valuta
* Dato og klokkeslett

Hvis du vil ha mer informasjon om hvilke uttrykk som støttes, og eksempler, se [Definere beregnede felt](/dynamics365/customer-engagement/customize/define-calculated-fields)

## <a name="update-or-delete-a-field"></a>Oppdatere eller slette et felt
1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten, og deretter klikker du eller trykker på en enhet.
2. I listen over felt for enheten du valgte, klikk eller trykk et felt, og gjør deretter ett av følgende:
   
   * Endre én eller flere egenskaper for det valgte feltet.
   * Slett feltet ved å klikke eller trykke ellipsen (…) nær høyre kant av feltet og deretter klikke eller trykke **Slett**.

3. Klikk eller trykk **Lagre enhet** for å sende inn endringene.
   
    > [!IMPORTANT]
    > Endringene vil gå tapt hvis du ikke lagrer dem før du åpner en annen side i nettleseren eller avslutter nettleseren.

    Du blir varslet når handlingen er fullført. Hvis den mislykkes, angir en feilmelding problemene som oppstod, og hvordan du kan rette dem.

## <a name="best-practices-and-restrictions"></a>Gode fremgangsmåter og begrensninger
Husk følgende når du oppretter og endrer felt:

* Du kan ikke endre eller slette systemfelt eller verdiene i dem.
* I en standardenhet kan du ikke endre eller slette et standardfelt, legge til et felt som krever data, eller gjøre andre endringer som kan bryte en app som avhenger av denne enheten.
* I en egendefinert enhet må du kontrollere at endringene du gjør, ikke vil bryte en app som avhenger av denne enheten.
* Du må gi hvert egendefinert felt et navn som er unikt i enheten, og du kan ikke endre navnet på et felt etter at du har opprettet det.

## <a name="next-steps"></a>Neste trinn
* [Definere relasjoner mellom enheter](data-platform-entity-lookup.md)
* [Opprette en forretningsregel](data-platform-create-business-rule.md)
* [Opprette en app ved hjelp av enheter](../canvas-apps/data-platform-create-app.md)
* [Opprette en app fra bunnen ved å bruke en Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Personvernerklæring
Med Common Data Model for Microsoft PowerApps samler vi inn og lagrer egendefinerte enhets- og feltnavn i diagnosesystemene våre.  Vi bruker denne kunnskapen til å forbedre Common Data Model for kundene våre. Enhets- og feltnavnene som oppretterne lager, hjelper oss å forstå scenarioer som er vanlige i Microsoft PowerApps-fellesskapet, og fastslår mangler i tjenestens standardenhetsdekning, for eksempel skjemaer som er relatert til organisasjoner. Dataene i databasetabellene som er knyttet til disse enhetene, brukes ikke eller er ikke tilgjengelige for Microsoft eller replikeres utenfor området der databasen klargjøres. Vær imidlertid oppmerksom på at de egendefinerte enhets- og feltnavnene kan replikeres på tvers av områder, og slettes i henhold til våre oppbevaringspolicyer for data. Microsoft går inn for å verne om dine personlige opplysninger som beskrevet ytterligere i vårt [Klareringssenter](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

