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
Denne prosedyren krever følgende elementer:
* Enten en PowerApps Plan 2- eller Microsoft Flow Plan 2-lisens. Eventuelt kan du registrere deg for en [gratis PowerApps Plan 2-prøveversjon](https://web.powerapps.com/signup?redirect=marketing&email=).
* Enten sikkerhetsrollen Systemadministrator eller Systemtilpasser i Common Data Service for Apps.

## <a name="sign-in-to-powerapps"></a>Logg på PowerApps
Logg på PowerApps på [https://web.powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-an-entity"></a>Opprette en enhet
1. I navigasjonsruten klikker eller trykker du på **Data** for å vise den, og klikker eller trykker deretter på **Enheter**.

    ![Liste over enheter og deres detaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. På kommandolinjen klikker eller trykker du på **Ny enhet**.

    Før du oppretter en enhet, kan du se [enhetsreferansen](../../developer/common-data-service/reference/about-entity-reference.md) for en beskrivelse av tilgjengelige standardenheter. Disse enhetene dekker vanlige scenarioer. Hvis en av disse enhetene oppfyller kravene som den er eller etter mindre endringer, kan du spare tid ved å begynne med denne enheten. 

3. I **Ny enhet**-panelet i **Visningsnavn**-feltet skriver du inn **Produktvurdering**, og angir deretter eventuelt en beskrivelse (beskrivelser er nyttige hvis andre bruker enheten). Andre felt i panelet fylles ut automatisk, som beskrevet nedenfor. Klikk på **Neste** når du er ferdig.

    * **Flertallsvisningsnavn** – Dette feltet fylles ut automatisk når du angir et visningsnavn, men du kan endre det om nødvendig. Flertallsvisningsnavnet er navnet på enheten i Common Data Service WebAPI og brukes ved samhandling med denne enheten fra PowerApps eller Flow.
    * **Navn** – Dette feltet fylles også ut automatisk når du angir et visningsnavn. Prefikset ble opprettet da miljøet ble opprettet, og sikrer at enhetene du oppretter, kan eksporteres og importeres til andre miljøer uten å være i konflikt med andre enhetsnavn. Du kan endre dette prefikset ved å oppdatere prefikset i utgiveren for Common Data Service-standardløsningen. For å unngå å ødelegge eksisterende apper, kan du ikke endre navnet når du har lagret enheten.

       > [!NOTE]
       > For at enhetsnavnet skal fungere med [innebygd kunnskapssøk i Dynamics 365 for Customer Service](/dynamics365/customer-engagement/customer-service/set-up-knowledge-management-embedded-knowledge-search), kan ikke maksimal enhetsnavnlengde inkludert utgiverprefikset overskride 24 tegn.
     
    ![Ny enhet](./media/data-platform-cds-create-entity/newentitypanel.png "Ny enhet-panelet")

4. På Enhetsdetaljer-siden kan du klikke eller trykke på **Hovednavn**-feltet for å åpne **Hovednavn**-panelet, og i **Visningsnavn**-feltet erstatter du **Hovednavn** med **Produktvurdering**. I **Navn**-feltet erstatter du **Hovednavn** med **Produktvurdering**, og klikker eller trykker deretter på **Ferdig**.
 
    Hver enhet inneholder som standard et Hovednavn-felt som brukes av oppslagsfelt ved oppretting av relasjoner med andre enheter. Hovednavn-feltet inneholder vanligvis navnet eller hovedbeskrivelsen av dataene som er lagret i enheten. Du kan oppdatere navnet og visningsnavnet for Hovednavn-feltet før du lagrer enheten første gang.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/newentitydetails.png "Detaljer om ny enhet")

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

7. Klikk på **Lagre enhet** for å lagre enheten og gjøre den tilgjengelig for bruk i apper.

    Produktvurdering-enheten skal vises i listen over enheter i databasen. Hvis den ikke vises, endrer du filteret på kommandolinjen fra **Standard** til **Egendefinert**.

    > [!div class="mx-imgBorder"] 
    > ![Filter](./media/data-platform-cds-create-entity/filter.png "Filtervalg")

## <a name="next-steps"></a>Neste trinn
I dette emnet lærte du hvordan du oppretter en egendefinert enhet kalt Produktvurdering som kan brukes til å opprette en app som viser vurderinger og kommentarer for hvert produkt som selges av et bestemt selskap. I neste trinn vil du lære hvordan du definerer relasjoner mellom enheter (i dette tilfellet mellom standard produktenhet og den egendefinerte Produktvurdering-enheten) slik at du kan knytte hvert produkt til vurderingene og kommentarene det får.

> [!div class="nextstepaction"]
> [Opprette en relasjon](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>Personvernerklæring
Med Common Data Model for Microsoft PowerApps samler og lagrer Microsoft egendefinert enhets- og feltnavn i diagnosesystemene våre. Vi bruker denne kunnskapen til å forbedre Common Data Model for kundene våre. Enhets- og feltnavnene som appoppretterne lager, hjelper oss å forstå scenarioer som er vanlige i Microsoft PowerApps-fellesskapet, og fastslår mangler i tjenestens standardenhetsdekning, for eksempel skjemaer som er relatert til organisasjoner. Dataene i databasetabellene som er knyttet til disse enhetene, brukes ikke eller er ikke tilgjengelige for Microsoft eller replikeres utenfor området der databasen klargjøres. Vær imidlertid oppmerksom på at de egendefinerte enhets- og feltnavnene kan replikeres på tvers av områder, og slettes i henhold til våre oppbevaringspolicyer for data. Microsoft går inn for å verne om dine personlige opplysninger som beskrevet ytterligere i vårt [Klareringssenter](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
