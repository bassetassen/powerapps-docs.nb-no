---
title: Å opprette en egendefinert enhet | Microsoft Docs
description: I denne hurtiginnføringen finner du ut mer om hvordan du oppretter en egendefinert enhet i PowerApps.
author: Mattp123
ms.service: powerapps
ms.component: cds
ms.topic: quickstart
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: 45a341d28b4138ce03ce50d7325f9daa0f159d1a
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/07/2018
ms.locfileid: "37897436"
---
# <a name="quickstart-create-a-custom-entity"></a>Hurtiginnføring i hvordan oppretter en egendefinert enhet
I PowerApps definerer en *enhet* informasjonen du ønsker å spore i form av poster, som typisk inneholder egenskaper som eksempelvis firmanavn, plasseringer, produkter, e-postadresser og telefonnumre. Deretter kan du se nærmere på dataene ved å utvikle en app som refererer til enheten. PowerApps tilbyr standard «bruksklare»-enheter for å dekke vanlige scenarioer i en organisasjon (for eksempel sporing av avtaler), men det kan være ganger da du trenger å opprette egendefinerte enheter for å lagre data som er spesifikke for din organisasjon.

I denne hurtigveiledningen finner du ut hvordan du oppretter en egendefinert enhet kalt Produktgjennomgang, som du kan bruke til å opprette en app som viser rangering og merknader for produkter som firmaet ditt selger.

## <a name="prerequisites"></a>Forutsetninger
Følgende elementer kreves for å følge denne hurtiginnføringen:
* En lisens for enten et PowerApps 2-abonnement eller et Microsoft Flow 2-abonnement. Du kan også registrere deg for en [gratis prøveversjon av PowerApps (abonnement 2)](https://web.powerapps.com/signup?redirect=marketing&email=).
* En sikkerhetsrolle som systemadminstrator eller systemtilpasser i Common Data Service for apper.

## <a name="sign-in-to-powerapps"></a>Å logge deg på PowerApps
Logg deg på PowerApps på [https://web.powerapps.com](https://web.powerapps.com).

## <a name="create-an-entity"></a>Å opprette en enhet
1. I navigasjonsruten klikker eller trykker du på **Data** for å utvide den, og deretter klikker eller trykker du på **Enheter**.

    ![Liste over enheter og tilknyttede detaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på **Ny enhet** i kommandolinjen.

    Før du oppretter en enhet, kan du sjekke ut [enhetsreferansen](../../developer/common-data-service/reference/about-entity-reference.md) for en beskrivelse av tilgjengelige standardenheter. Disse enhetene dekker vanlige scenarioer. Hvis én av disse enhetene oppfyller kravene dine som den er eller etter noen små endringer, kan du spare noe tid ved å starte med denne enheten. 

3. Skriv inn **Produktgjennomgang** i **Ny enhet**-ruten i **Visningsnavn**-boksen, og skriv deretter eventuelt inn en beskrivelse (beskrivelser er nyttige hvis andre personer skal bruke enheten). Andre felt i panelet er automatisk utfylt, som beskrevet nedenfor. Når du er ferdig, klikker du på **Neste**.

   * **Visningsnavn i flertall** – dette feltet er automatisk utfylt når du skriver inn et visningsnavn, men du kan endre det om nødvendig. Visningsnavn i flertall – dette brukes når du samhandler med denne enheten fra PowerApps eller Flow, og brukes som navnet på enheten i Common Data Service WebAPI.
   * **Navn** – dette feltet er også automatisk utfylt når du skriver inn et visningsnavn. Navnet inkluderer også et prefiks som ble konfigurert da miljøer ble opprettet. Dette brukes for å sikre at enhetene du oppretter kan eksporteres og importeres i andre miljøer, der andre enheter kan ha samme navn. Dette prefikset kan endres ved å oppdatere det i Publisher for standardløsningen i Common Data Service. Hvis du vil sørge for at eksisterende apper ikke ødelegges, kan du ikke endre navnet etter å ha lagret enheten.
     
     ![Ny enhet](./media/data-platform-cds-create-entity/newentitypanel.png "Nytt enhetspanel")

4. På detaljsiden for enheten klikker eller trykker du på **Primærnavn**-feltet for å åpne **Primærnavn**-ruten, og deretter erstatter du **Primærnavn** med **Produktgjennomgang** i **Visningsnavn**-boksen. Erstatt **PrimaryName** med **ProductReview** i **Navn**-boksen, og deretter klikker eller trykker du på **Ferdig**.
 
    Hver enhet inneholder som standard et Primært navn-felt som brukes av oppslagsfelt ved oppretting av relasjoner med andre enheter. Feltet skal som regel brukes for å lagre navnet eller den primære beskrivelsen av dataene som lagres i enheten. Navnet og visningsnavnet til Primært navn-feltet kan oppdateres før du lagrer enheten første gang.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/newentitydetails.png "Nye enhetsdetaljer")

5. Hvis du vil legge til et felt til enhet, gjør du følgende:
 
    a. I kommandolinjen klikker eller trykker du på **Legg til felt** for å åpne **Feltegenskaper**-panelet.

    b. Skriv inn **Gjennomgangsdato** i **Visningsnavn**-boksen.

    c. Velg **Bare dato** fra **Datatype**-rullegardinlisten.

    d. Merk av for **Obligatorisk**.
    
    e. Klikk eller trykk på **Ferdig**.
     
    Hvis du vil ha mer informasjon, kan du se[Å administrere felter i en enhet](data-platform-manage-fields.md).

    ![Nytt felt](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Nytt felt-panel")

6. Gjenta de forrige trinnene for å legge til tre felt til med følgende konfigurasjoner:
   * **Visningsnavn** = Produktvurdering; **Datatype** = Heltall; merk av for **Obligatorisk**
   * **Visningsnavn** = Navn på korrekturleser; **Datatype** = Tekst
   * **Visningsnavn** = Kommentar fra korrekturleser; **Datatype** = Tekst

     Når du er ferdig, skal du ha fem felt som er oppført på enhetens detaljside.

     ![Feltliste](./media/data-platform-cds-create-entity/addedfields.png "liste over felt")

     Vær oppmerksom på at alle enheter har skrivebeskyttede systemfelt. Systemfelt blir som standard ikke vist i listen over felt, selv om de finnes på enheten. Hvis du vil se alle feltene, kan du endre filteret på kommandolinjen fra **Standard** til **Alle**. Hvis du vil ha mer informasjon om metadataene som er knyttet til enheten, kan du se [Enhetsmetadata](../../developer/common-data-service/entity-metadata.md).

7. Klikk på **Lagre enhet** for å lagre enheten og gjøre den tilgjengelig for bruk i apper.

    Produktgjennomgangen skal vises i listen over enheter i databasen. Hvis du ikke ser den, kan du endre filteret i kommandolinjen fra **Standard** til **Egendefinert**.

    ![Filtrer](./media/data-platform-cds-create-entity/filter.png "Filtrer utvalg")

## <a name="next-steps"></a>Neste trinn
I denne hurtigveiledningen finner du ut hvordan du oppretter en egendefinert enhet kalt Produktgjennomgang, som du kan bruke til å opprette en app som viser rangering og merknader for hvert produkt som selges av et bestemt firma. Nå skal du få finne ut hvordan du kan definere relasjoner mellom enheter (i dette tilfellet mellom Produktenhet som er standard og den tilpassede enheten din Produktgjennomgang), slik at du kan knytte hvert produkt med gjennomganger og kommentarer de mottar.

> [!div class="nextstepaction"]
> [Å opprette en relasjon](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>Erklæring om personvern
Med den vanlige datamodellen i Microsoft PowerApps samler vi inn og lagrer egendefinerte enhets- og feltnavn i diagnostiseringssystemene. Vi bruker denne kunnskapen til å forbedre den vanlige datamodellen for kundene våre. Enhets- og feltnavnene som appoppretterne lager, hjelper oss med å forstå scenarioer som er typiske i Microsoft PowerApps-fellesskapet, og få rede på hull i tjenestens standarddekning for enheter, som eksempelvis skjemaer knyttet til organisasjoner. Dataene i databasetabeller som er knyttet til disse enhetene, blir ikke åpnet eller brukt av Microsoft eller replisert utenfor området hvor databasen er klargjort. Merk deg imidlertid at den egendefinerte enheten og feltnavnene kan repliseres på tvers av områder og blir slettet i henhold til retningslinjene våre for dataoppbevaring. Microsoft tar vare på personvernet ditt, som ytterligere beskrevet i [Klareringssenteret](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
