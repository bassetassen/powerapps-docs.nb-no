---
title: Opprette og redigere virtuelle enheter med Common Data Service | MicrosoftDocs
description: Finn ut hvordan du oppretter virtuelle enheter
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 44834893-0bf6-4a64-8f06-7583fe08330d
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-virtual-entities-that-contain-data-from-an-external-data-source"></a>Opprette og redigere virtuelle enheter som inneholder data fra en ekstern datakilde

En virtuell enhet er en egendefinert enhet i Common Data Service som har felt som inneholder data fra en ekstern datakilde. Virtuelle enheter vises i appen din for brukere som vanlige enhetsoppføringer, men de inneholder data som er hentet fra en ekstern database, for eksempel en Azure SQL-database. Oppføringer basert på virtuelle enheter, er tilgjengelige i alle klienter, inkludert tilpassede klienter som er utviklet med Common Data Service-webtjenestene.  
  
Før måtte du opprette en kobling for å flytte data eller utvikle en tilpasset plugin-modul på klient- eller serversiden for å integrere ulike datakilder. Med virtuelle enheter kan du imidlertid koble direkte til en ekstern datakilde ved kjøretid slik at bestemte data fra den eksterne datakilden er tilgjengelig i et miljø, uten behov for datareplikering.  

Virtuelle enheter består av tre hovedkomponenter, en *dataleverandør*, en *datakilde*oppføring og en *virtuell enhet*. Dataleverandøren består av plugin-moduler og en datakildeenhet. Datakilden er en enhetsoppføring i Common Data Service, som inkluderer metadata som representerer skjemaet for tilkoblingsparameterne. Hver virtuelle enhet refererer til en datakilde i enhetsdefinisjonen.  
  
Common Data Service inkluderer en OData-dataleverandør som du kan bruke til å koble til en OData v4-webtjeneste som har tilgang til de eksterne dataene. 
  
Utviklere kan også bygge sine egne dataleverandører. Dataleverandører er installert i et miljø som en løsning. Mer informasjon: [Dokumentasjon for utviklere: Komme i gang med virtuelle enheter](../../developer/common-data-service/virtual-entities/get-started-ve.md)
  
 ![Diagram for virtuell enhet](media/virtual-entity-diagram.png "Diagram for virtuell enhet")  
  
<a name="benefits"></a> 
  
## <a name="virtual-entity-benefits"></a>Fordeler med virtuelle enheter  
  
- Utviklere kan implementere plugin-moduler for å lese eksterne data ved hjelp av Common Data Service-webtjenestene og registreringsverktøyet for plugin-modulen.  
- Systemtilpassere bruker løsningsutforskeren i PowerApps til å konfigurere datakildeoppføringen og opprette virtuelle enheter som brukes til å få tilgang til eksterne data uten å skrive kode.  
- Sluttbrukere arbeider med oppføringene som er opprettet av den virtuelle enheten, for å vise data i felt, rutenett, søkeresultater og Fetch XML-baserte rapporter og instrumentbord.  
  
<a name="AddDataSource"></a> 
  
## <a name="add-a-data-source-to-use-for-virtual-entities"></a>Legge til en datakilde som skal brukes for virtuelle enheter 
 
 Utviklere oppretter en egendefinert plugin-modul som skal brukes som dataleverandør for en virtuell enhet.  Alternativt kan du bruke den medfølgende OData v4-dataleverandøren. Mer informasjon: [Konfigurasjon av, krav for og anbefalte fremgangsmåter for OData v4-dataleverandøren](virtual-entity-odata-provider-requirements.md)  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Administrasjon** > **Datakilder for virtuelle enheter**.  
1. Velg **Ny** på handlingsverktøylinjen.  
1. Velg fra følgende datakilder i dialogboksen **Velg dataleverandør**, og velg deretter **OK**.
 
    |Dataleverandør|Beskrivelse|
    |--|--|
    |*Egendefinert dataleverandør*|Hvis du har importert en plugin-modul for dataleverandør, vises dataleverandøren her. Mer informasjon: [Dokumentasjon for utviklere: Komme i gang med virtuelle enheter](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)|
    |**Dataleverandør for OData v4**|Common Data Service har en OData-dataleverandør som kan brukes med OData v4-webtjenester. Mer informasjon: [Konfigurasjon av, krav for og anbefalte fremgangsmåter for OData v4-dataleverandøren](virtual-entity-odata-provider-requirements.md)|

  
### <a name="add-a-secured-field-to-a-data-source"></a>Legge til et sikkert felt i en datakilde

Du kan opprette felt for en datakilde på samme måte som enhver annen enhet. Når det gjelder data som er krypterte eller sensitive, kan du aktivere attributtet Datakildehemmelighet for det egendefinerte feltet i datakilden. Du kan gjøre dette hvis du for eksempel vil sikre et felt som inneholder en databasetilkoblingsstreng. 

> [!NOTE]
> Attributtet Datakildehemmelighet er bare tilgjengelig med felt som legges til i et datakildeskjema.

> [!div class="mx-imgBorder"] 
> ![Attributtet Datakildehemmelighet](media/datasourcesecret.png)
  
<a name="createVirtualEntity"></a> 
  
## <a name="create-a-virtual-entity"></a>Opprette en virtuell enhet
  
Du oppretter en virtuell enhet på samme måte som enhver annen enhet i Common Data Service, med noen få ekstra attributter som beskrives her, i tillegg. Virtuelle enheter må opprettes ved hjelp av løsningsutforskeren.

> [!NOTE]
>  Selv om du kan opprette en virtuell enhet ved å velge **Ingen** som datakilde, må en virtuell enhet ha en datakilde for å kunne innhente data. Mer informasjon: [Legge til en datakilde som skal brukes for virtuelle enheter](#AddDataSource)

### <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på virtuelle enheter du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne virtuelle enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="create-a-virtual-entity"></a>Opprette en virtuell enhet
  
1. I løsningsutforsker oppretter du en ny enhet. Du gjør dette ved å velge **Enheter** i navigasjonsruten til venstre, og deretter velge **Ny**.  
2. I kategorien **Generelt** i **Enhetsdefinisjon**, velger du **Virtuell enhet**, og deretter velger du ønsket datakilde i rullegardinlisten **Datakilde**.  

    > [!div class="mx-imgBorder"] 
    > ![Alternativet for virtuell enhet i enhetsdefinisjon](media/virtual-entity-click-option.png)  
  
1. Fyll ut følgende obligatoriske felt i enhetsdefinisjonen.
  
    |Felt|Beskrivelse|
    |--|--|
    |**Eksternt navn**|Skriv inn navnet på tabellen i den eksterne datakilden som denne enheten er tilordnet til.|
    |**Navn på ekstern samling**|Skriv inn flertallsnavnet på tabellen i den eksterne datakilden som denne enheten er tilordnet til.|
      
    Her er et eksempel på en virtuell enhet kalt *Movie* som bruker en Azure Cosmos DB-dataleverandør for å få tilgang til dokumentfiler.  
      
    > [!div class="mx-imgBorder"] 
    > ![Virtuell enhet-definisjon som bruker Azure Cosmos DB-dataleverandør](media/virtual-entity-definition.PNG)  
      
    > [!IMPORTANT]
    > Flere alternativer, for eksempel Tilgangsteam, Køer og Hurtigoppretting, er ikke tilgjengelige med virtuelle enheter. Mer informasjon: [Vurderinger ved bruk av virtuelle enheter](#considerations)  
      
    Fullfør ytterligere obligatoriske og valgfrie egenskaper, for eksempel visningsnavn og flertallsnavn, etter behov. Hvis du vil ha mer informasjon om disse egenskapene, kan du se [Opprette og redigere enheter](create-edit-entities.md).  
  
1. Opprette og legge til ett eller flere felt for den virtuelle enheten. I tillegg til standard feltegenskaper som kreves for å opprette et egendefinert felt, er disse valgfrie egenskapene tilgjengelige for hvert egendefinerte felt du oppretter for en virtuell enhet.

    |Felt|Beskrivelse|
    |--|--|
    |**Eksternt navn**|Dette er vanligvis det unike navnet for å identifisere dataene du vil vise i feltet.|
    |**Navn på ekstern type**|Hvis felttypen du oppretter, er OptionSet: Denne egenskapen er tilordnet til det eksterne navnet på verdisettet i den eksterne tjenesten for alternativsettet.  Vanligvis kan dette være en opplisting eller navn på en strengverdiklasse. Navn på ekstern type kan brukes når et fullstendig kvalifisert navn er nødvendig.  For eksempel, som *Navn på type* med OData der parametere i en spørring trenger det fullstendig kvalifiserte navnet, som [*Navn på type*].[*Verdi*].|
    |**Ekstern verdi**|Hvis felttypen du oppretter, er OptionSet: Denne egenskapen er tilordnet til den tilsvarende verdien i den eksterne datakilden for alternativsettelementet.  Denne verdien brukes til å fastsette hvilket alternativsettelement som skal vises i appen.  |

    Fyll ut ytterligere egenskaper etter behov. Hvis du vil ha mer informasjon om disse egenskapene, kan du se [Opprette og redigere felt](create-edit-fields.md).  
  
1. Velg **Lagre og lukk** på egenskapssiden for **Felt**.  
1. Velg **Lagre** på verktøylinjen for løsningsutforsker.  
1. Velg **Publiser** på verktøylinjen for løsningsutforsker.  
1. Lukk løsningsutforsker.  

<a name="considerations"></a>
   
## <a name="considerations-when-you-use-virtual-entities"></a>Vurderinger ved bruk av virtuelle enheter  

Virtuelle enheter har følgende begrensninger.  
  
- Alle virtuelle enheter er skrivebeskyttet.  
- Eksisterende enheter kan ikke konverteres til virtuelle enheter.  
- Som standard inneholder virtuelle enheter bare et Navn- og ID-felt.  Ingen andre systemadministrerte felt, for eksempel Status eller Opprettet den / Endret den støttes.
- Virtuelle enheter støtter ikke egendefinerte felt med datatypen valuta, bilde eller kunde.
- Virtuelle enheter støtter ikke sporing av endringer.  
- Virtuelle enhetsfelt kan ikke brukes i felt for beregnet verdi eller beregnede felt.
- En virtuell enhet kan ikke være en aktivitetstype for enhet.  
- Mange funksjoner som påvirker enhetstabellrader kan ikke aktiveres med virtuelle enheter.  Eksempler er køer, kunnskapsstyring, serviceavtaler, duplikatregistrering, endringssporing, Mobile Offline-funksjonen, feltsikkerhet, Relevanssøk, portaler for Dynamics 365-webportalløsninger og N:N-relasjoner mellom virtuelle enheter.  
- Virtuelle enheter eies av organisasjonen og støtter ikke sikkerhetsbegrepene på radnivå i Common Data Service. Vi anbefaler at du bruker din egen sikkerhetsmodell for den eksterne datakilden.  
- Vi anbefaler at du merker av for én enkelt datakilde når du bruker virtuelle enheter i avansert søk. For eksempel oppretting av et avansert søk som til slutt oppretter en kobling mellom opprinnelige Common Data Service-data og eksterne data for den virtuelle enheten, støttes ikke.  
- Egenskaper for feltmetadata som valideres ved oppdatering, gjelder ikke for virtuell enheter. Et heltallsfelt for et felt for virtuell enhet kan for eksempel settes til å ha minimumsverdien null. Siden verdien kommer fra en ekstern datakilde, returnerer imidlertid en spørring verdier som er mindre enn null, når de hentes inn fra en virtuell enhet.  Egenskapen for minimumsverdi ikke er underforstått i spørringen.  Du må fortsatt filtrere verdiene slik at de er større enn 0, hvis det er det du vil.
- Virtuelle enheter støtter ikke endringssporing og kan ikke synkroniseres ved hjelp av en Common Data Service-funksjon, for eksempel dataeksporttjenesten.
  
### <a name="see-also"></a>Se også  

[Krav og anbefalte fremgangsmåter for OData v4-dataleverandøren](virtual-entity-odata-provider-requirements.md)</br> 
[Opprette og redigere enheter](create-edit-entities.md)</br>
[Opprette og rediger felt](create-edit-fields.md)
