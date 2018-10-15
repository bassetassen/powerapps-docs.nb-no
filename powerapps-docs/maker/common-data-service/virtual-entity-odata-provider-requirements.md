---
title: Bruk OData v4-dataleverandør for virtuell enhet med Common Data Service for apper | MicrosoftDocs
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: ''
caps.latest.revision: ''
author: Mattp123
ms.author: matp
manager: brycho
ms.openlocfilehash: 0bd2aed852b5d7eb9b354f30978725b1386a89aa
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39695395"
---
# <a name="odata-v4-data-provider-configuration-requirements-and-best-practices"></a>Konfigurasjon, krav og anbefalte fremgangsmåter for OData v4-dataleverandøren

Dette emnet beskriver hvordan du konfigurerer OData v4-dataleverandøren, samt krav og anbefalte fremgangsmåter for å bruke OData v4-dataleverandøren til å koble til en OData v4-nettjeneste. 

## <a name="odata-v4-data-provider-best-practices"></a>Anbefalte fremgangsmåter for OData v4-dataleverandøren

- Common Data Service for apper krever at alle enheter har et ID-attributt. Denne ID-en kalles også en unik identifikator, og verdien må være en guid.  Du kan bare tilordne ID-felt til eksterne felt med `Edm.Guid`-datatypen.  Du kan ikke tilordne en `Edm.Int32`-datatype til et datatypefelt for en unik identifikator i CDS for apper.
-  OData-enheter med egenskaper som kan nullstilles, må angis slik at de samsvarer med det tilordnede feltet på den virtuelle enheten. En OData-enhetsegenskap som kan nullstilles (er usann), må for eksempel ha det tilordnede feltet **Feltkrav** i CDS for apper, angitt som **Nødvendig for selskapet**. 
- Hvis du skal hente flere spørringer, for eksempel når du laster inn data i et rutenett, må du kontrollere størrelsen på datasettet som returneres fra den eksterne datakilden, ved å bruke parameterne utvalgs- og filterspørring.
- Hvis det ikke allerede er aktivert, bør systemansvarlige aktivere sporing av tillegg. Når dette er aktivert, samles alle feil fra OData-endepunktet i loggen for sporing av tillegg. Mer informasjon:  [Veiledning for administrator: dialogboks for systeminnstillinger – tilpassingsfane](/dynamics365/customer-engagement/admin/system-settings-dialog-box-customization-tab) 

## <a name="data-type-mapping"></a>Tilordning av datatype

Tabellen nedenfor viser datatypetilordninger for OData Entity Data Model (EDM) med CDS for apper-datatyper. 

|OData-datatype|CDS for apper-datatype  |
|---------|---------|
|`Edm.Boolean`|To alternativer|
|`Edm.DateTime`|Dato og klokkeslett|
|`Edm.DateTimeOffset`|Dato og klokkeslett|
|`Edm.Decimal`|Desimaltall eller valuta|
|`Edm.Double`|Flyttall|
|`Edm.Guid`|Unik identifikator|
|`Edm.Int32`|Heltall|
|`Edm.Int64`|Heltall|
|`Edm.String`|Enkeltlinje med tekst eller flere linjer med tekst|


### <a name="odata-edm-data-types-that-are-not-supported-for-mapping-with-virtual-entities"></a>OData-EDM-datatyper som ikke støttes for tilordning med virtuelle enheter 

- `Edm.Binary `
- `Edm.Time` 
- `Edm.Float `
- `Edm.Single` 
- `Edm.Int16` 
- `Edm.Byte` 
- `Edm.SByte`

 
## <a name="add-a-data-source-using-the-odata-v4-data-provider"></a>Legg til en datakilde som bruker OData v4-dataleverandøren

Denne prosedyren viser hvordan du bruker den ferdiglagede dataleverandøren for OData som datakilde for den virtuelle enheten.   
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Administrasjon** > **Datakilder for virtuell enhet**.  
1. Klikk på **Ny** på handlingsverktøylinjen.  
1. Velg fra følgende datakilder, i dialogboksen **Velg dataleverandør**, og klikk deretter på **OK**.  
  
    - **OData v4-dataleverandør**. CDS for apper omfatter en Odata v4-dataleverandør som kan brukes til å koble til datakilder som støtter den åpne standarden for OData v4.  
    - *Egendefinert dataleverandør*. Hvis du har importert et tillegg for dataleverandøren, vises dataleverandøren her. Mer informasjon:  [Utviklerdokumentasjon: Kom i gang med virtuelle enheter](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)  
    
1. Fyll ut følgende felt på egenskaper-siden **Ny datakilde**, og lagre deretter posten.  
  
    - **Navn**. Skriv inn et navn som beskriver datakilden.  
    - **Uri**. Hvis du bruker OData-dataleverandøren, skriver du inn uri-en for OData-nettjenesten. Hvis du for eksempel bruker OData-leverandøren til å koble til en nettjeneste som driftes i Azure, ser URI-en omtrent slik ut *`http://contosodataservice.azurewebsites.net/odata/`*.  
    - **Tidsavbrudd i sekunder**. Skriv inn antall sekunder du skal vente på svar fra nettjenesten før dataforespørselen får tidsavbrudd. Du kan for eksempel skrive inn 30 for å vente maksimum 30 sekunder før det skjer et tidsavbrudd.  
    - **Pagineringsmodus**. Velg om du vil bruke sideveksling på klientsiden eller serversiden for å kontrollere sideveksling av spørringsresultater. Standardverdien er sideveksling på klientsiden. Med sideveksling på serversiden, styrer serveren hvordan resultater sideveksles ved hjelp av parameteren $skiptoken, som legges til i spørringsstrengen. Mer informasjon:  [Hopp over alternativet tokensystemspørring ($skiptoken)](https://msdn.microsoft.com/library/dd942121.aspx)  
        -  **Returner innebygd antall**. Returnerer totalt antall poster i resultatsettet. Denne innstillingen brukes til å aktivere Neste side-funksjonen når du returnerer data til et rutenett. Bruk verdien usann hvis OData-endepunktet ikke støtter OData-$inlinecount-parameteren. Standardverdien er usann.
    - **Forespørselsparametere**. Hvis du vil, kan du legge til egendefinerte topptekst- eller spørringsstrengparametere som brukes til å koble til OData-nettjenesten, for eksempel godkjenningsparametere, til den eksterne tjenesten. Klikk på **Spørringsstreng** for å veksle mellom topptekst- og spørringsstrengparameter og -verdi. Du kan legge til opptil 10 hode- eller spørringsstrenger. 
        ![Datakildepost for virtuell enhet](media/virtual-entity-data-source.png) 


## <a name="see-also"></a>Se også  

[Opprett og rediger virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md) <br/>
[TechNet-bloggen: Samhandle med data fra eksterne systemer ved hjelp av de nye virtuelle enhetene](https://blogs.technet.microsoft.com/lystavlen/2017/09/08/virtual-entities/)
