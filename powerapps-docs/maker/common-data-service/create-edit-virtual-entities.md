---
title: Opprett og rediger virtuelle enheter med Common Data Service for Apps | MicrosoftDocs
description: Lær hvordan du oppretter virtuelle enheter
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
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
ms.openlocfilehash: 675c0ac5763698c82a7d13bfc75f8b7357d6cf0b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691056"
---
# <a name="create-and-edit-virtual-entities-that-contain-data-from-an-external-data-source"></a>Opprett og rediger virtuelle enheter som inneholder data fra en ekstern datakilde

En virtuell enhet er en egendefinert enhet i Common Data-Service for Apps, med felter som inneholder data fra en ekstern datakilde. Virtuelle enheter vises i appen for brukere som vanlige enhetsoppføringer, men inneholder data med kilde fra en ekstern database, for eksempel en Azure SQL Database. Poster basert på virtuelle enheter er tilgjengelige for alle klienter, inkludert egendefinerte klienter som er utviklet ved hjelp av CDS for Apps-nettjenester.  
  
For å integrere de uensartede datakildene måtte du tidligere opprette en kobling for å flytte data eller utvikle et egendefinert programtillegg, enten for klient eller server. Med virtuelle enheter kan du imidlertid koble til direkte med en ekstern datakilde ved kjøretid, slik at bestemte data fra den eksterne datakilden er tilgjengelig i et miljø, uten behov for datareplikering.  

Virtuelle enheter består av tre hovedkomponenter, en *dataleverandør*, en *datakildepost*, og en *virtuell enhet*. Dataleverandøren består av programtillegg og en datakilde for enhet. Datakilden er en enhetsoppføring i CDS for Apps, som inneholder metadata som representerer skjemaet for tilkoblingsparameterne. Hver virtuell enhet refererer til en datakilde i enhetsdefinisjonen.  
  
CDS for Apps inkluderer en OData-dataleverandør du kan bruke til å koble til en nettjeneste for OData v4 som har tilgang til de eksterne dataene. 
  
Utviklere kan også bygge egne dataleverandører. Dataleverandører installeres i et miljø som en løsning. Mer informasjon: [Utviklerdokumentasjon: Kom i gang med virtuelle enheter](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)
  
 ![Virtuelt enhetsdiagram](media/virtual-entity-diagram.png "Virtuelt enhetsdiagram")  
  
<a name="benefits"></a> 
  
## <a name="virtual-entity-benefits"></a>Virtuell enhetsfordel  
  
- Utviklere kan implementere programtillegg for å lese eksterne data ved hjelp av nettjenester for CDS for Apps, og registreringsverktøy for programtillegg.  
- Systemtilpassere bruker PowerApps-løsningsutforsker til å konfigurere datakildeposten, og opprette virtuelle enheter som brukes for å få tilgang til eksterne data uten å skrive kode.  
- Sluttbrukere arbeider med poster som er opprettet av den virtuell enheten for å vise dataene i felt, rutenett, søkeresultater, og Fetch XML-baserte rapporter og instrumentbord.  
  
<a name="AddDataSource"></a> 
  
## <a name="add-a-data-source-to-use-for-virtual-entities"></a>Legg til en datakilde som skal brukes for virtuelle enheter 
 
 Utviklere oppretter et egendefinert programtillegg, som skal brukes som dataleverandøren for en virtuell enhet. Du kan også bruke den oppgitte dataleverandøren for OData v4. Mer informasjon: [Konfigurasjon, krav og anbefalte fremgangsmåter for dataleverandøren for OData v4](virtual-entity-odata-provider-requirements.md)  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Administrasjon** > **Datakilder for virtuell enhet**.  
1. Velg **Ny** på handlingsverktøylinjen.  
1. Velg fra følgende datakilder i dialogboksen **Velg dataleverandør**, og velg deretter **OK**.
 
    |Dataleverandør|Beskrivelse|
    |--|--|
    |*Egendefinert dataleverandør*|Hvis du har importert et programtillegg for dataleverandøren, vises dataleverandøren her. Mer informasjon [Utviklerdokumentasjon: Kom i gang med virtuelle enheter](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)|
    |**Dataleverandør for OData v4**|CDS for Apps inkluderer en dataleverandør for OData som kan brukes med nettjenester for OData v4. Mer informasjon: [Konfigurasjon, krav og anbefalte fremgangsmåter for dataleverandøren for OData v4](virtual-entity-odata-provider-requirements.md)|

  
### <a name="add-a-secured-field-to-a-data-source"></a>Legg til et sikret felt i en datakilde

Du kan opprette felt for en datakilde på samme måte som for en annen enhet. For data som er kryptert eller sensitive, kan du aktivere attributtet Datakildehemmelighet for det egendefinerte feltet i datakilden. For eksempel for å sikre et felt som inneholder en tilkoblingsstreng for en database. 

> [!NOTE]
> Attributtet Datakildehemmelighet er bare tilgjengelig med felt som er lagt til et datakilde-skjema.

![Attributtet Datakildehemmelighet](media/datasourcesecret.png)
  
<a name="createVirtualEntity"></a> 
  
## <a name="create-a-virtual-entity"></a>Opprett en virtuell enhet
  
Du oppretter en virtuell enhet akkurat som andre enheter i CDS for Apps i tillegg til noen ekstra attributter som er beskrevet her. Virtuelle enheter må opprettes ved hjelp av løsningsutforsker.

> [!NOTE]
>  En virtuell enhet krever en datakilde for å hente data, selv om du kan opprette en virtuell enhet ved å velge **Ingen** som datakilde. Mer informasjon [Legg til en datakilde som skal brukes for virtuelle enheter](#AddDataSource)

### <a name="open-solution-explorer"></a>Åpne løsningutforsker

En del av navnet for alle enheter du oppretter, er tilpassingsprefikset. Dette angis basert på løsningutgiveren for løsningen du arbeider i. Hvis du er opptatt av tilpassingsprefikset, må du kontrollere at du jobber i en ikke-administrert løsning, der tilpassingsprefikset er det du vil ha for denne virtuelle enheten. Mer informasjon: [Endre prefiks for løsningutgiver](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="create-a-virtual-entity"></a>Opprett en virtuell enhet
  
1. Opprett en ny enhet i løsningsutforsker. Hvis du vil gjøre dette, kan du velge **Enheter** i venstre navigasjonsrute, og deretter velge **Ny**.  
2. Velg **virtuell enhet** på **Generelt**-fanen i **Enhetsdefinisjonen**, og velg deretter datakilden som du vil bruke i rullegardinlisten for **Datakilden**.  
  
    ![Virtuelt enhetsalternativ i enhetsdefinisjonen](media/virtual-entity-click-option.png)  
  
1. Fullfør følgende obligatoriske felt i enhetsdefinisjonen.
  
    |Felt|Beskrivelse|
    |--|--|
    |**Eksternt navn**|Angi navnet på tabellen i den eksterne datakilden som er tilordnet til enheten.|
    |**Navn på ekstern samling**|Angi flertallsnavnet for tabellen i den eksterne datakilden som er tilordnet til enheten.|
      
    Her er et eksempel på en virtuell enhet med navnet *Film* som bruker en dataleverandør for Azure Cosmos DB for å få tilgang til dokumentfiler.  
      
    ![Virtuell enhetsdefinisjon ved hjelp av dataleverandøren for Azure Cosmos DB](media/virtual-entity-definition.PNG)  
      
    > [!IMPORTANT]
    > Flere alternativer, for eksempel Tilgangsteam, Køer og Hurtigoppretting, er ikke tilgjengelige med virtuelle enheter. Mer informasjon [Hensyn når du bruker virtuelle enheter](#considerations)  
      
    Fullfør de nødvendige og valgfrie tilleggsegenskapene, for eksempel skjerm og flertallsnavn, etter behov. Hvis du vil ha mer informasjon om disse egenskapene, se [Opprett og rediger enheter](create-edit-entities.md).  
  
1. Opprett og legg til ett eller flere felt for den virtuelle enheten. Disse valgfrie egenskapene er tilgjengelige for hvert egendefinerte felt som du oppretter for en virtuell enhet i tillegg til de standard feltegenskapene, som kreves for å opprette et egendefinert felt.

    |Felt|Beskrivelse|
    |--|--|
    |**Eksternt navn**|Dette er vanligvis det unike navnet til å identifisere dataene du vil vise i feltet.|
    |**Eksternt typenavn**|Hvis felttypen du oppretter er OptionSet: Denne egenskapen er tilordnet til det eksterne navnet på settet med verdier i den eksterne tjenesten for alternativsettet.  Dette kan vanligvis være en opplisting eller navnet på en strengverdiklasse. Navnet på den eksterne typen kan brukes når et fullstendig kvalifisert navn kreves.  For eksempel som med *Typenavn* med OData der parameterne i en spørring må ha det fullstendig kvalifiserte navnet, slik som [*Typenavn*]. [ *Verdi*].|
    |**Ekstern verdi**|Hvis felttypen du oppretter er OptionSet: Denne egenskapen er tilordnet den tilsvarende verdien i den eksterne datakilden for alternativsett-elementet.  Denne angitte verdien brukes til å bestemme hvilket alternativsett-element som skal vises i appen.  |

    Fullfør tilleggsegenskapene etter behov. Hvis du vil ha mer informasjon om disse egenskapene, se [Opprett og rediger felt](create-edit-fields.md).  
  
1. Velg **Lagre og Lukk** på siden for **Felt**-egenskaper.  
1. Velg **Lagre** på verktøylinjen i løsningsutforskeren.  
1. Velg **Publiser** på verktøylinjen i løsningsutforskeren.  
1. Lukk løsningsutforsker.  

<a name="considerations"></a>
   
## <a name="considerations-when-you-use-virtual-entities"></a>Hensyn når du bruker virtuelle enheter  

Virtuelle enheter har disse begrensningene.  
  
- Alle virtuelle enheter er skrivebeskyttet.  
- Eksisterende enheter kan ikke konverteres til virtuelle enheter.  
- Virtuelle enheter inneholder bare et Navn og ID-felt som standard.  Ingen andre systemstyrte felt, for eksempel Status eller Opprettet/Endret, støttes.
- Virtuelle enheter støtter ikke egendefinerte felt med datatypene Valuta, Bilde eller Kunde.
- Virtuelle enheter støtter ikke revisjon.  
- Virtuelle enhetsfelt kan ikke brukes i opprulleringer eller beregnede felt.
- En virtuell enhet kan ikke være en aktivitetstype for enheten.  
- Mange funksjoner som påvirker tabellrader for enheter kan ikke aktiveres med virtuelle enheter.  Eksempler inkluderer køer, kunnskap administrering, serviceavtaler, duplikatregistrering, endringssporing, Mobile Offline-funksjonalitet, feltsikkerhet, relevansesøk, nettportal-løsninger for Dynamics 365 og mange-til-mange-relasjoner mellom virtuelle enheter.  
- Virtuelle enheter er organisasjonseide, og støtter ikke sikkerhetskonseptene på radnivå for Common Data Service for Apps. Vi anbefaler at du bruker din egen sikkerhetsmodell for den eksterne datakilden.  
- Vi anbefaler at du tar for deg en enkelt datakilde når du bruker virtuelle enheter i Avansert søk. For eksempel støttes ikke oppretting av et avansert søk som til slutt oppretter en sammenkobling mellom opprinnelige data for Common Data Service for Apps og de eksterne dataene for den virtuelle enheten.  
- Feltegenskaper for metadata som validerer ved oppdatering gjelder ikke for virtuelle enheter. Et heltallsfelt på et felt for en virtuell enhet kan for eksempel settes til en minimumsverdi på null. Men siden verdien kommer fra en ekstern datakilde, returnerer spørringen verdier som er mindre enn null når de hentes fra en virtuell enhet.  Egenskapen for minimumsverdien er ikke angitt i spørringen.  Du må fortsatt filtrere verdiene til å være større enn 0, hvis det er det som er ønskelig.
- Virtuelle enheter støtter ikke endringssporing, og kan ikke synkroniseres ved hjelp av en CDS for Apps-funksjon, som dataeksport-tjenesten.
  
### <a name="see-also"></a>Se også  

[Krav og anbefalte fremgangsmåter for dataleverandøren for OData v4](virtual-entity-odata-provider-requirements.md)</br> 
[Opprett og rediger enheter](create-edit-entities.md)</br>
[Opprette og redigere felter](create-edit-fields.md)
