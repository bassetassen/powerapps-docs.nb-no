---
title: Bruke den virtuelle enheten OData v4-dataleverandøren med Common Data Service for Apps | MicrosoftDocs
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
ms.assetid: null
caps.latest.revision: null
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="odata-v4-data-provider-configuration-requirements-and-best-practices"></a>Konfigurasjon av, krav for og anbefalte fremgangsmåter for OData v4-dataleverandøren

Dette emnet beskriver hvordan du konfigurerer OData v4-dataleverandøren samt kravene og de anbefalte fremgangsmåtene for bruk av OData v4-dataleverandøren til å koble til en OData v4-webtjeneste. 

## <a name="odata-v4-data-provider-best-practices"></a>Anbefalte fremgangsmåter for OData v4-dataleverandøren

- Common Data Service for Apps krever at alle enheter har et ID-attributt, og denne ID-en kalles en unik identifikator, og verdien må være en guid.  Du kan bare tilordne ID-felt til eksterne felt med datatypen `Edm.Guid`.  Du kan ikke tilordne en `Edm.Int32`-datatype til et felt med datatypen unik ID i CDS for Apps.
-  OData-enheter med egenskaper som kan nullstilles, må angis slik at de samsvarer med det tilordnede feltet i den virtuelle enheten. En egenskap for OData-enhet med Nullable=False må ha det tilordnede feltet i **Feltkrav**-attributtet i CDS for Apps satt til **Nødvendig for selskapet**. 
- Når du henter flere spørringer, for eksempel når du laster inn data i et rutenett, styrer du størrelsen på datasettet som returneres fra den eksterne datakilden ved å bruke spørringsparameterne for valg og filtrering.
- Systemansvarlige bør aktivere sporing av plugin-modul, hvis de ikke allerede har gjort det. Når den er aktivert, blir alle feil fra OData-endepunktet registrert i sporingsloggen for plugin-modul. Mer informasjon: [Administratorhåndbok: Dialogboksen Systeminnstillinger – kategorien Tilpassing](/dynamics365/customer-engagement/admin/system-settings-dialog-box-customization-tab) 

## <a name="data-type-mapping"></a>Tilordning av datatype

Tabellen nedenfor viser tilordningene av datatyper for OData Entity Data Model (EDM) med CDS for Apps-datatyper. 

|OData-datatype|CDS for Apps-datatypen  |
|---------|---------|
|`Edm.Boolean`|To alternativer|
|`Edm.DateTime`|Dato og klokkeslett|
|`Edm.DateTimeOffset`|Dato og klokkeslett|
|`Edm.Decimal`|Desimaltall eller valuta|
|`Edm.Double`|Flyttall|
|`Edm.Guid`|Unik identifikator|
|`Edm.Int32`|Heltall|
|`Edm.Int64`|Heltall|
|`Edm.String`|En enkelt linje med tekst eller flere linjer med tekst|


### <a name="odata-edm-data-types-that-are-not-supported-for-mapping-with-virtual-entities"></a>OData EDM-datatyper som ikke støttes for tilordning med virtuelle enheter 

- `Edm.Binary `
- `Edm.Time` 
- `Edm.Float `
- `Edm.Single` 
- `Edm.Int16` 
- `Edm.Byte` 
- `Edm.SByte`

 
## <a name="add-a-data-source-using-the-odata-v4-data-provider"></a>Legge til en datakilde som bruker OData v4-dataleverandøren

Denne fremgangsmåten viser hvordan du bruker den medfølgende OData-dataleverandøren som datakilden for virtuell enhet.   
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Administrasjon** > **Datakilder for virtuelle enheter**.  
1. Klikk **Ny** på handlingsverktøylinjen.  
1. Velg fra følgende datakilder i dialogboksen **Velg dataleverandør**, og klikk deretter **OK**.  
  
    - **Dataleverandør for OData v4**. CDS for Apps inneholder en Odata v4-dataleverandør som kan brukes for å koble til datakilder som støtter den åpne standarden for OData v4.  
    - *Egendefinert dataleverandør*. Hvis du har importert en plugin-modul for dataleverandør, vises dataleverandøren her. Mer informasjon: [Dokumentasjon for utviklere: Komme i gang med virtuelle enheter](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)  
    
1. Fyll ut følgende felt på egenskapssiden **Ny datakilde**, og lagre deretter oppføringen.  
  
    - **Name**. Skriv inn et navn som beskriver datakilden.  
    - **URI**. Hvis du bruker OData-dataleverandøren, skriver du inn URI-en for OData-webtjenesten. Hvis du for eksempel bruker OData-leverandøren for å koble til en webtjeneste driftet i Azure, kan URI-en ligne på *`http://contosodataservice.azurewebsites.net/odata/`*.  
    - **Tidsavbrudd i sekunder**. Skriv inn ventetiden for et svar fra webtjenesten før dataforespørselen blir tidsavbrutt, i antall sekunder. Du kan for eksempel angi 30 hvis du vil vente maksimalt 30 sekunder før et tidsavbrudd oppstår.  
    - **Pagineringsmodus**. Velg om du vil bruke sideveksling på klientsiden eller serversiden til å styre hvordan spørringsresultater sideveksles. Standardverdien er sideveksling på klientsiden. Med sideveksling på serversiden styrer serveren hvordan resultater sideveksles ved hjelp av parameteren $skiptoken, som legges til i spørringsstrengen. Mer informasjon: [Systemspørringsalternativ for overhoppingstoken ($skiptoken)](https://msdn.microsoft.com/library/dd942121.aspx)  
        -  **Returner innebygd antall**. Returnerer totalt antall oppføringer i resultatsettet. Denne innstillingen brukes til å aktivere neste side-funksjonalitet når du returnerer data til et rutenett. Du kan bruke verdien false hvis OData-endepunktet ikke støtter OData-parameteren $inclinecount. Standardverdien er false.
    - **Forespørselsparametere**. Du kan eventuelt legge til egendefinerte topptekst- eller spørringsstrengparametere som brukes for å koble til OData-webtjenesten, for eksempel godkjenningsparametere for den eksterne tjenesten. Klikk **Spørringsstreng** for å veksle mellom topptekst- og spørringsstrengparameter og verdi. Opptil ti topptekst- eller spørringsstrenger kan legges til. 
        > [!div class="mx-imgBorder"] 
        > ![Oppføring av datakilde for virtuelle enheter](media/virtual-entity-data-source.png) 


## <a name="see-also"></a>Se også  

[Opprette og redigere virtuelle enheter som inneholder data fra en ekstern datakilde](create-edit-virtual-entities.md) <br/>
[TechNet-bloggen: Samhandle med data fra eksterne systemer ved hjelp av de nye virtuelle enhetene](https://blogs.technet.microsoft.com/lystavlen/2017/09/08/virtual-entities/)
