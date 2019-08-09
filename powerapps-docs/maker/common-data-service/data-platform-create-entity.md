---
title: Opprette en egendefinert enhet | Microsoft Docs
description: Lær hvordan du oppretter en egendefinert enhet i PowerApps.
author: Mattp123
ms.service: powerapps
ms.component: cds
ms.topic: quickstart
ms.date: 05/01/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-custom-entity"></a>Opprette en egendefinert enhet
I PowerApps definerer en *enhet* informasjon som du vil spore ved hjelp av oppføringer, som vanligvis inneholder egenskaper som firmanavn, sted, produkter, e-post og telefon. Du kan deretter vise disse dataene ved å utvikle en app som refererer til enheten. PowerApps tilbyr medfølgende standard enheter for å dekke vanlige scenarioer i en organisasjon (for eksempel spore avtaler), men det kan være tilfeller der du trenger å opprette egendefinerte enheter for å lagre data som er spesifikke for organisasjonen.

I dette emnet lærer du hvordan du oppretter en egendefinert enhet kalt Produktvurdering som du kan bruke til å opprette en app som viser vurderinger og kommentarer for produkter som selskapet selger.

## <a name="prerequisites"></a>Forhåndskrav
Hvis du vil følge denne prosedyren, må du ha enten en systemansvarlig- eller en systemtilpasser-sikkerhetsrolle i Common Data Service.

## <a name="sign-in-to-powerapps"></a>Logg på PowerApps
Logg på PowerApps på [https://web.powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-an-entity"></a>Opprett en enhet
1. I navigasjonsruten klikker eller trykker du på **Data** for å vise den, og klikker eller trykker deretter på **Enheter**.

    ![Liste over enheter og deres detaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. På kommandolinjen klikker eller trykker du på **Ny enhet**.

    Før du oppretter en enhet, kan du se [enhetsreferansen](../../developer/common-data-service/reference/about-entity-reference.md) for en beskrivelse av tilgjengelige standardenheter. Disse enhetene dekker vanlige scenarioer. Hvis en av disse enhetene oppfyller kravene som den er eller etter mindre endringer, kan du spare tid ved å begynne med denne enheten. 

3. Gjør følgende i panelet **Ny enhet**:

    a. I **Visningsnavn**-boksen skriver du inn **Produktvurdering**.

    Se at følgende bokser fylles ut etter hvert som du skriver inn et visningsnavn:

    * **Flertallsvisningsnavn** – denne boksen fylles ut automatisk når du angir et visningsnavn, men du kan endre det om nødvendig. Flertallsvisningsnavnet er navnet på enheten i Common Data Service-WebAPI-en og brukes ved samhandling med denne enheten fra PowerApps eller Flow.
    * **Navn** – denne boksen fylles også ut automatisk når du angir et visningsnavn. Prefikset ble opprettet da miljøet ble opprettet, og sikrer at enhetene du oppretter, kan eksporteres og importeres til andre miljøer uten å være i konflikt med andre enhetsnavn. Du kan endre dette prefikset ved å oppdatere prefikset i utgiveren for Common Data Service-standardløsningen. For å unngå å ødelegge eksisterende apper, kan du ikke endre navnet når du har lagret enheten.

       > [!NOTE]
       > For at enhetsnavnet skal fungere med [Dynamics 365 for Customer Service-innebygd kunnskapssøk](/dynamics365/customer-engagement/customer-service/set-up-knowledge-management-embedded-knowledge-search), kan ikke maksimal enhetsnavnlengde inkludert utgiverprefikset overskride 24 tegn.

    b. **I hovedfelt**-delen, i **visningsnavn**-boksen, erstatter du **Navn** med **Produktvurdering**. 

    Hver enhet inneholder som standard et **Hovedfelt** som brukes av oppslagsfelt ved oppretting av relasjoner med andre enheter. Hovedfeltet inneholder vanligvis navnet eller hovedbeskrivelsen av dataene som er lagret i enheten. Du kan oppdatere navnet og visningsnavnet for Hovedfeltet før du lagrer enheten første gang.

    Du bør også se at hovedfeltet har sin egen **navn**-boks, som fungerer på samme måte som enhetsnavnet som er beskrevet ovenfor. Hovedfeltnavnet fylles ut etter hvert som et visningsnavn registreres, bruker samme prefiks som entiteten, og kan ikke endres etter at enheten er opprettet.

    c. Åpne delen **Flere innstillinger** og utvid trekkspillmenyen **Beskrivelse**. Du kan angi en beskrivelse for enheten hvis du ønsker det (det kan være nyttig for andre som bruker denne enheten). 
    
    d. Klikk **Opprett** når du er ferdig.
     
    ![Ny enhet](./media/data-platform-cds-create-entity/newentitypanel.png "Nytt enhetspanel")

4. På siden enhetsdetaljer ser du at enheten nå blir klargjort i bakgrunnen. Når klargjøringen er fullført, blir enheten lagret og tilgjengelig for bruk i apper. Felt, relasjoner og nøkler kan legges til i enheten når som helst (selv når klargjøringen fremdeles pågår), men visninger, skjemaer, diagrammer, instrumentbord og forretningsregler kan bare legges til i enheten etter at klargjøringen er fullført.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/newentitydetails.png "Detaljer om ny enhet")

5. I kategorien **felt** ser du hvilket **hovedfelt** du har angitt i forrige trinn. Klikk eller trykk på **hovedfelt**-feltet for å åpne **hovedfeltet**, hvis du vil gjøre flere tilpasninger for feltet. Legg merke til at **Navn** ikke lenger kan endres, fordi enheten allerede er lagret.

5. Hvis du vil legge til et felt i enheten, kan du gjøre følgende:
 
    a. På kommandolinjen klikker eller trykker du på **Legg til felt** for å åpne **Feltegenskaper**-panelet.

    b. I **Visningsnavn**-feltet skriver du inn **Vurderingsdato**.

    c. I **Datatype**-rullegardinlisten velger du **Bare dato**.

    d. Klikk eller trykk på **Nødvendig**-avmerkingsboksen.
    
    e. Klikk eller trykk på **Ferdig**.
     
    Hvis du vil ha mer informasjon, kan du se [Administrere felt i en enhet](data-platform-manage-fields.md).

    > [!div class="mx-imgBorder"] 
    > ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Panelet for nytt felt")

6. Gjenta det forrige trinnet for å legge til tre felt til med følgende konfigurasjoner:
    * **Visningsnavn** = Produktvurdering, **Datatype** = Heltall, klikk eller trykk på **Nødvendig**-avmerkingsboksen
    * **Visningsnavn** = Kontrollørnavn, **Datatype** = Tekst
    * **Visningsnavn** = Kontrollørkommentar, **Datatype** = Tekst

    Når du er ferdig, skal du ha fem felt oppført på enhetsdetaljsiden.

    ![Feltliste](./media/data-platform-cds-create-entity/addedfields.png "Liste med felt")

    Vær oppmerksom på at alle enheter har skrivebeskyttede systemfelt. Som standard vises ikke systemfelt i listen over felt selv om de finnes i enheten. Hvis du vil vise alle felt, endrer du filteret på kommandolinjen fra **Standard** til **Alle**. Hvis du vil ha mer informasjon om metadataene knyttet til en enhet, kan du se [Metadata for enhet](../../developer/common-data-service/entity-metadata.md).

7. Klikk **lagre enhet** for å lagre de siste endringene i enheten.

    Produktvurdering-enheten skal vises i listen over enheter i databasen. Hvis den ikke vises, endrer du filteret på kommandolinjen fra **Standard** til **Egendefinert**.

    > [!div class="mx-imgBorder"] 
    > ![Filter](./media/data-platform-cds-create-entity/filter.png "Filtervalg")

## <a name="next-steps"></a>Neste trinn
I dette emnet lærte du hvordan du oppretter en egendefinert enhet kalt Produktvurdering som kan brukes til å opprette en app som viser vurderinger og kommentarer for hvert produkt som selges av et bestemt selskap. I neste trinn vil du lære hvordan du definerer relasjoner mellom enheter (i dette tilfellet mellom standard produktenhet og den egendefinerte Produktvurdering-enheten) slik at du kan knytte hvert produkt til vurderingene og kommentarene det får.

> [!div class="nextstepaction"]
> [Opprette en relasjon](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>Personvernerklæring
Med Common Data Model for Microsoft Microsoft PowerApps samler og lagrer Microsoft egendefinerte enhets- og feltnavn i diagnosesystemene våre. Vi bruker denne kunnskapen til å forbedre Common Data Model for kundene våre. Enhets- og feltnavnene som appoppretterne lager, hjelper oss å forstå scenarioer som er vanlige i Microsoft PowerApps-fellesskapet, og fastslår mangler i tjenestens standardenhetsdekning, for eksempel skjemaer som er relatert til organisasjoner. Dataene i databasetabellene som er knyttet til disse enhetene, brukes ikke eller er ikke tilgjengelige for Microsoft eller replikeres utenfor området der databasen klargjøres. Vær imidlertid oppmerksom på at de egendefinerte enhets- og feltnavnene kan replikeres på tvers av områder, og slettes i henhold til våre oppbevaringspolicyer for data. Microsoft går inn for å verne om dine personlige opplysninger som beskrevet ytterligere i vårt [Klareringssenter](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
