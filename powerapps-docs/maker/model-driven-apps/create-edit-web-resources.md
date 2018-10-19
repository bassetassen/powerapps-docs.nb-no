---
title: Opprette eller redigere modelldrevne nettressurser for apper i PowerApps | MicrosoftDocs
description: Finn ut hvordan du oppretter eller redigerer en nettressurs
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: ef4ba8df-9ba9-4066-b40d-def9761c7de2
caps.latest.revision: 21
ms.author: matp
manager: kvivek
ms.openlocfilehash: 8d9414ba4c900f98ac26010e4e6d7240b336e2d7
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696062"
---
# <a name="create-or-edit-model-driven-app-web-resources-to-extend-an-app"></a>Opprette eller redigere modelldrevne nettressurser for apper for å utvide en app

Nettressurser brukes vanligvis av utviklere til å utvide en app som bruker filer som brukes i nettutvikling. Appbrukere må kanskje behandle nettressurser fra en utvikler eller designer.  

> [!TIP]
> Se [Utviklerdokumentasjon: nettressurser for Customer Engagement](/dynamics365/customer-engagement/developer/web-resources) for en dyptgående diskusjon av nettressurser.<br /> Se [Utviklerdokumentasjon: avhengigheter for nettressurser](/dynamics365/customer-engagement/developer/web-resources) for informasjon om avhengigheter for nettressurser lagt til i PowerApps.
   
<a name="BKMK_WhatAreWebResources"></a>

## <a name="what-are-web-resources"></a>Hva er nettressurser?  

Nettressurser er virtuelle filer som er lagret i systemet. Hver nettressurs har et unikt navn som kan brukes i en nettadresse for å hente filen. Tenk på dem på denne måten: Hvis du hadde tilgang til nettserveren som kjører nettappen, kunne du kopiert filer til nettsiden. Med de fleste onlinetjenester kan du ikke gjøre dette.  I stedet kan du bruke nettressurser til å laste opp filer til systemet, og deretter referere til dem ved navn som om du hadde kopierte dem til nettserveren.  
  
For eksempel, hvis du oppretter en HTML-side som en nettressurs med navnet «new_mynettResource.htm», kan du åpne siden i en nettleser ved hjelp av en slik nettadresse:  
 
`<base URL>/WebResources/new_myWebResource.htm   `
  
der *\<base URL>* er en del av nettadressen du bruker til å vise apper som slutter på `dynamics.com`. Fordi nettressursen er data i systemet, kan bare lisensierte brukere for organisasjonen din få tilgang til dem på denne måten. Nettressurser er vanligvis inkludert i skjemaer i stedet for at det refereres direkte til dem. De brukes oftest til å gi skjemaskript tilgang til JavaScript-biblioteker.  
    
Fordi nettressursen er data i systemet, og er bevisste på løsninger, kan du flytte dem til forskjellige organisasjoner ved å eksportere dem som en del av en løsning, og importerer løsningen til en annen organisasjon. Du må bruke løsningsutforsker for å arbeide med nettressurser.
  
## <a name="open-solution-explorer"></a>Åpne løsningutforsker

Tilpassingprefikset er en del av navnet på alle nettressurser du oppretter. Dette angis basert på løsningutgiveren for løsningen du arbeider i. Hvis tilpassingsprefikset er viktig, må du kontrollere at du jobber i en ikke-administrert løsning, der tilpassingsprefikset er det du vil ha for denne enheten. For mer informasjon, se: [Endre prefiks for løsningutgiver](../common-data-service/change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-web-resources"></a>Vis nettressurser

Når løsningsutforskeren er åpen, velger du **Nettressurser** under **Komponenter**.

![Vis nettressurser](media/view-web-resources-solution-explorer.png)

<a name="BKMK_CreateAndEditWebResources"></a>

## <a name="create-or-edit-web-resources"></a>Opprett eller rediger nettressurser  

Mens [nettressursvisningen](#view-web-resources) er åpen kan du velge **Ny** for å opprette en ny nettressurs eller dobbeltklikke på en eksisterende nettressurs for å redigere den.

![Nytt skjema for nettressurs](media/new-web-resource-form.png)

Fyll ut skjemaet for å opprette eller redigere nettressursen:
  
|Felt|Beskrivelse|  
|-----------|-----------------|  
|**Navn**|*Obligatorisk*. Dette er det unike navnet for denne nettressursen. Du kan ikke endre dette når du har lagret nettressursen.<br />&bull; Navnet kan bare inneholde bokstaver, tall, punktum og ikke-påfølgende skråstrek («/»).<br /> &bull; Tilpassingprefikset for løsningutgiveren vil legges til foran navnet på nettressursen.|  
|**Visningsnavn**|Navnet som vises hvis du viser en liste over ressurser på nettet.|  
|**Beskrivelse**|En beskrivelse av nettressursen.|  
|**Type**|*Obligatorisk*. Dette er nettressurstypen. Du kan ikke endre dette når du har lagret nettressursen.|  
|**Redigeringsprogram for tekst**|Når nettressurstypen representerer en type tekstfil, kan du trykke på denne knappen for å åpne en side hvor du kan redigere innholdet med redigeringsprogrammet for tekst.<br />Mer informasjon: [Bruk redigeringsprogrammet for tekst på riktig måte](#use-the-text-editor-appropriately)| 
|**Språk**|Gjør det mulig å velge språk. Dette alternativet koder bare posten som lagrer data for nettressursen. Dette endrer ikke virkemåten til nettressursen.|  
|**Last opp fil**|Velg **Bla gjennom...**- knappen for å velge en fil som skal lastes opp som en nettressurs.<br />&bull; Du kan laste opp en fil når du oppretter en ny nettressurs eller for å overskrive en eksisterende nettressurs.<br />&bull; Filtypen må samsvare med tillatte utvidelser.<br />&bull; Som standard er maksimumstørrelsen på filen som kan lastes opp som en nettressurs 5 MB. Denne verdien kan endres i Dynamics 365 Customer Engagement ved hjelp av **Systeminnstillinger** > **E-post**-fanen > innstillingen **Sett grensen for filstørrelser for vedlegg**. Mer informasjon: [Dialogboks for Systeminnstillinger – E-post-fanen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-email-tab) |  
|**Nettadresse**|Når du har lagret nettressursen, vises nettadressen til nettressursen her. Velg denne koblingen for å vise nettressursen i nettleseren.|  
  
Når du har lagt til endringene, velger du **Lagre** og deretter **Publiser**.  

> [!NOTE]
> Endringer i en nettressurs vil ikke være synlige i programmet før du publiserer den.
  
<a name="BKMK_UsingTextEditor"></a>
   
### <a name="use-the-text-editor-appropriately"></a>Bruk redigeringsprogrammet for tekst på riktig måte

Tekstredigeringsprogrammet som leveres i programmet for nettressurser, bør bare brukes for enkel redigeringer av tekstfiler. Du kan bruke den til å opprette og redigere HTML-nettressurser, men du bør bare redigere HTML-nettressurser som ble opprettet ved hjelp av redigeringsprogrammet for tekst. Tekstredigeringsprogrammet er utformet for svært enkelt HTML-innhold. 

> [!IMPORTANT]
> Hvis innholdet i en HTML-nettressurs ikke ble opprettet ved hjelp av redigeringsprogrammet for tekst, må du ikke bruke tekstredigeringsprogrammet til å redigere det.  
> Tekstredigeringsprogrammet bruker en kontroll som endrer HTML-kilden på en måte som gjør at den kan redigeres. Disse endringene kan føre til at siden fungerer annerledes i nettleseren og at mer avanserte kode slutter å fungere. Åpning av en HTML-nettressurs med redigeringsprogrammet for tekst og lagring uten å gjøre endringer kan ødelegge noen HTML-nettressurser.  Mer informasjon: [Utviklerdokumentasjon: Bruk redigeringsprogrammet for tekst for HTML-nettressurser](/dynamics365/customer-engagement/developer/webpage-html-web-resources#use-the-text-editor-for-html-web-resources)
  
Vi anbefaler at du bruker et eksternt redigeringsprogram for å redigere tekstfiler og lagrer dem lokalt før du laster dem opp med knappen **Last opp fil**. Slik beholder du en kopi av nettressursen hvis du må gå tilbake til en tidligere versjon. Du kan bruke et enkelt redigeringsprogram som Notisblokk, men det anbefales sterkt et tekstredigeringsprogram med mer avanserte funksjoner. [Visual Studio Community](https://www.visualstudio.com/vs/community/) og [Visual Studio Code](https://code.visualstudio.com/) er gratis og har kraftige funksjoner for redigering av tekstbaserte filer som brukes av nettressurser.  

<a name="BKMK_CreateAndEditFormWebResources"></a>
 
## <a name="create-and-edit-a-web-resource-on-a-form"></a>Opprett og rediger en nettressurs i et skjema

Du kan legge til eller redigere nettressurser i et skjema for å gjøre det mer tiltalende eller nyttig for brukere. 

> [!NOTE]
> Du kan ikke inkludere en nettressurs i en topptekst eller bunntekst i et skjema.  

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="navigate-to-a-form"></a>Gå til et skjema
Med løsningsutforskeren åpen utvider du **Enheter** under elger du **Komponenter**, og utvider enheten du vil arbeide med.

Velg **Skjemaer**, finn et skjema av typen Hoved i listen og dobbeltklikk eller trykk på oppføringen for å åpne og redigere skjemaet.

### <a name="add-or-edit-web-resource-in-a-form"></a>Legg til eller rediger en nettressurs i et skjema

Se [Nettressursegenskaper](web-resource-properties-legacy.md) for informasjon om egenskapene du kan angi for nettressurser i et skjema.

### <a name="preview"></a>Testversjon

Slik forhåndsviser du hvordan hovedskjemaet vises og hvordan hendelser vil fungere:
- Velg **Forhåndsvisning**, og deretter **Opprett skjema**, **Oppdater skjema** eller **Skrivebeskyttet skjema** på **Hjem**-fanen.
- Du lukker forhåndsvisningsskjemaet med **Lukk** på **Fil**-menyen.

### <a name="save"></a>Lagre

Når du er ferdig med å redigere skjemaet, velger du **Lagre og Lukk** på **Hjem**-fanen for å lukke skjemaet. 

### <a name="publish"></a>Publiser

Når tilpassingene er ferdige, publiserer du dem:
- Hvis du vil publiserer tilpassinger for bare komponenten du redigerer, merker du enheten du har arbeidet med i navigasjonsruten, og velger **Publiser**.
- Hvis du vil publisere tilpassinger for alle upubliserte komponenter på en gang, velger du **Enheter**, og deretter **Publiser alle tilpassinger**  på **Handling**-verktøylinjen i navigasjonsruten.
   
  
### <a name="see-also"></a>Se også  

[Egenskaper for nettressurs](web-resource-properties-legacy.md) <br /> 
[Opprett og utform skjemaer](create-design-forms.md) <br />
[Kom i gang med tilpassing](getting-started-customization.md) <br /> 
[Utviklerdokumentasjon: nettressurser for Customer Engagement](/dynamics365/customer-engagement/developer/web-resources)
