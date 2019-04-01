---
title: Importer data i modelldrevne apper | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
- D365CE
ms.openlocfilehash: 37e9602d48bbfbb802afefa0f6d47fad241dc6f5
ms.sourcegitcommit: 212d397284c431f5989dc7b39549e2fc170d447e
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/27/2019
ms.locfileid: "58491531"
---
# <a name="import-data"></a>Importer data

Enten du har lagret dataene i et regneark, på telefonen, eller i et e-postprogram, ser du her hvordan du importerer dataene til appen din. Du kan for eksempel importere kontaktlisten for kunder fra et Excel-regneark og inn i appen, slik at du kan holde oversikt over all kundeinformasjon på ett sted.
  
## <a name="step-1-get-your-import-file-ready"></a>Trinn 1: Klargjør importfilen  
Eksporter først dataene til en Excel-fil. Disse filformatene støttes:
 - Excel-arbeidsbok (.xlsx)
 - Kommadelte verdier (.csv)
  
Den maksimale filstørrelsen som er tillatt for ZIP-filer, er 32 MB. For andre filformater er den maksimale tillatte filstørrelsen 8 MB.  
  
### <a name="export-data-from-an-email-program"></a>Eksporter data fra et e-postprogram  
  
1.  Eksporter dataene til en fil med kommadelte verdier (.csv).  
  
     Hvis du vil finne en bestemt fremgangsmåte for å eksportere kontakter fra e-postprogrammet, åpner du programmets Hjelp-del, og søker etter «eksport». Se etter emner som inneholder «eksportere kontakter», «eksportere adresseboken» eller «eksportveiviser» i tittelen.  
  
2.  Lagre filen på en plassering der du enkelt kan finne den senere.  
  
### <a name="export-data-from-a-spreadsheet"></a>Eksporter data fra et regneark  
  
1.  Åpne regnearket.  
  
2.  Rediger eventuelle kolonnenavn i regnearket slik at de stemmer overens med navnene her, ved behov.  
  
    > [!WARNING]
    > Hvis regnearket ikke inneholder alle kolonnenavnene som er oppført, så er det greit. Hvis et kolonnenavn imidlertid finnes, må det stemme overens med tilsvarende navn i liste. Ellers kommer ikke importen til å fungere. Mellomrom er nødvendig. Vær oppmerksom på at ordet «Epost» ikke inneholder et bindestrek.  

    |**Kolonnenavn i regneark (må skrives på nøyaktig samme måte)**|
    |---------|
    |Fornavn|  
    |Mellomnavn|  
    |Etternavn|  
    |Telefon, arbeid|  
    |Mobiltelefon|  
    |Stilling|  
    |Gateadresse, arbeid|  
    |Poststed, arbeid|  
    |Region, arbeid|  
    |Postnummer, arbeid|  
    |Land/område, arbeid|  
    |E-postadresse|  
  
3.  Lagre filen.  
  
### <a name="export-data-from-your-phone"></a>Eksporter data fra telefonen  

Bruk en USB-kabel eller app til å eksportere dataene, slik som kontakter fra telefonen til datamaskinen.
  
Hvis du vil finne en bestemt fremgangsmåte for å eksportere kontakter for ditt telefonmerke, søker du etter «eksporter kontakter fra telefonen min» i din foretrukne søkemotor (som Bing).  
  
Hvis du vil finne en app, søker du i telefonens nettbutikk.  
  
## <a name="step-2-import-the-file"></a>Trinn 2: Å importere filen 
  
1. Velg **Importer fra Excel** eller **Importer fra CSV** på kommandolinjen.

   > [!div class="mx-imgBorder"]
   > ![Hovedmeny i PowerApps](media/import.png "Hovedmeny i PowerApps")
  
2. Bla gjennom til mappen der du lagret filen som inneholder eksporten av kontaktene. Merk filen, velg **Åpne**, og velg deretter **Neste**.  
  
   > [!TIP]
   > Du kan importere bare én fil om gangen. Hvis du ønsker å importere flere filer, kjører du veiviseren på nytt senere.
   
3. Se gjennom filnavnet og bekreft at feltet og dataskilletegnene er riktig ved bruk av alternativet **Se gjennom tilordning**. Hvis alt ser bra ut, velger du **Avslutt import**.  
 
## <a name="step-3-check-that-the-import-is-successful"></a>Trinn 3: Kontroller at importen er vellykket

Når veiviseren er fullført, kan du kontrollere dataene dine (for eksempel, kontaktlisten) for å sikre at de ble skikkelig importert.  
  
1. Gå til **Kontakter** fra hovedmenyen.
  
2. Ble gjennom kontaktlisten. Kontroller at alle personene er oppført, og bekreft at innholdet i feltene er nøyaktig.

## <a name="import-double-byte-characters"></a>Importer dobbeltbyte-tegn 

Hvis du importerer data som inkluderer dobbelbyte-tegn for østasiatiske språk, kontrollerer du at filen er kodet som UTF-8 Stykkliste. Vanlig UTF-8 er kanskje ikke nok.

1. Åpne CSV-filen ved bruk av Visual Studio Code.
2. Klikk på etiketten **UTF-8** (popup-vindu åpnes) på den nederste linjen. 
3. Velg **Lagre med koding**. 

Du kan nå velge UTF-8 Stykkliste for den filen.

