---
title: Opprette eller redigere webressurser for modelldrevne apper i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter eller redigerer en webressurs.
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-web-resources-to-extend-an-app"></a>Opprette eller redigere webressurser for modelldrevne apper for å utvide en app

Webressurser brukes vanligvis av utviklere til å utvide applikasjonen ved hjelp av filer som brukes i webutvikling. Applikasjonsbrukere må kanskje håndtere webressurser som leveres av en utvikler eller designer.  

> [!TIP]
> For en inngående diskusjon om webressurser kan du se [Dokumentasjon for utviklere: Webressurser for Customer Engagement](/dynamics365/customer-engagement/developer/web-resources).<br /> Hvis du vil ha informasjon om avhengigheter for webressurs som ble lagt til i PowerApps, kan du se [Dokumentasjon for utviklere: Avhengigheter for webressurs](/dynamics365/customer-engagement/developer/web-resources).
   
<a name="BKMK_WhatAreWebResources"></a>

## <a name="what-are-web-resources"></a>Hva er webressurser?  

Webressurser er virtuelle filer som er lagret i systemet. Hver webressurs har et unikt navn som kan brukes i en URL-adresse for å hente filen. Tenk på dem på denne måten: Hvis du har tilgang til den faktiske webserveren som kjører applikasjonen, kan du kopiere filer til dette webområdet. Men med de fleste online tjenester kan du ikke gjøre dette.  I stedet kan du bruke webressurser for å laste opp filer til et system og deretter referere til dem ved navn som om du hadde kopiert dem som filer til webserveren.  
  
Hvis du for eksempel oppretter en HTML-side som en webressurs med navnet new_myWebResource.htm, kan du åpne denne siden i en webleser ved hjelp av en URL-adresse som dette:  
 
`<base URL>/WebResources/new_myWebResource.htm`
  
der *\<primær URL-adresse>* er en del av URL-adressen du bruker til å vise appene som slutter på `dynamics.com`. Ettersom webressursen er data i systemet kan bare lisensierte brukere i organisasjonen få tilgang til dem på denne måten. Vanligvis er webressurser inkludert i skjemaer i stedet for å være referert til direkte. Den vanligste bruken er å tilby JavaScript-biblioteker for skjemaskript.  
    
Siden webressurser er data i systemet og er løsningsavhengige kan du flytte dem til ulike organisasjoner ved å eksportere dem som en del av en løsning og importere løsningen i en annen organisasjon. Du må bruke løsningsutforskeren til å arbeide med webressurser.
  
## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på en webressurs du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne webressursen. Mer informasjon: [Endre løsningsutgiverprefikset](../common-data-service/change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-web-resources"></a>Vise webressurser

Med løsningsutforskeren åpen velger du **Webressurser** under **Komponenter**.

![Vise webressurser](media/view-web-resources-solution-explorer.png)

<a name="BKMK_CreateAndEditWebResources"></a>

## <a name="create-or-edit-web-resources"></a>Opprette eller redigere webressurser  

Når du [viser webressurser](#view-web-resources), velger du **Ny** for å opprette en ny webressurs eller dobbeltklikker en eksisterende webressurs for å redigere den.

![Skjema for ny webressurs](media/new-web-resource-form.png)

Fyll ut skjemaet for å opprette eller redigere webressursen:
  
|Felt|Beskrivelse|  
|-----------|-----------------|  
|**Navn**|*Required*. Dette er det unike navnet for denne webressursen. Du kan ikke endre dette når du lagrer webressursen.<br />&bull; Dette navnet kan bare inkludere bokstaver, tall, punktum og ikke-påfølgende skråstreker (/).<br /> &bull; Tilpassingsprefikset for løsningsutgiveren vil være foran navnet på webressursen.|  
|**Visningsnavn**|Navnet som vises hvis du viser en liste over webressurser.|  
|**Beskrivelse**|En beskrivelse av webressursen.|  
|**Type**|*Påkrevd*. Dette er typen webressurs. Du kan ikke endre dette når du lagrer webressursen.|  
|**Tekstredigering**|Når typen webressurs representerer en type tekstfil, velger du denne knappen for å åpne en side for å redigere innhold ved hjelp av tekstredigeringsprogrammet.<br />Mer informasjon: [Bruke tekstredigeringsprogrammet på riktig måte](#use-the-text-editor-appropriately)| 
|**Språk**|Gjør det mulig å velge et språk. Dette alternativet koder bare oppføringen som lagrer webressursdataene. Det endrer ikke virkemåten for webressursen.|  
|**Last opp fil**|Velg knappen **Bla gjennom...** for å velge en fil som du vil laste opp som en webressurs.<br />&bull; Du kan laste opp en fil når du oppretter en ny webressurs eller for å overskrive en eksisterende webressurs.<br />&bull; Filtypen for filen må samsvare med tillatte filtyper.<br />&bull;Som standard er maksimumsstørrelsen for filen som kan lastes opp som et webområde, 5 MB. Denne verdien kan endres i ved hjelp av innstillingen i Dynamics 365 Customer Engagement **Systeminnstillinger** > kategorien **E-post** > **Angi grense for filstørrelse på vedlegg**. Mer informasjon: [Dialogboksen Systeminnstillinger – kategorien E-post](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-email-tab) |  
|**URL-adresse**|Når du lagrer webressursen, vises URL-adressen til webressursen her. Velg denne koblingen for å vise webressursen i webleseren.|  
  
Når du har lagt til endringene, velger du **Lagre** og deretter **Publiser**.  

> [!NOTE]
> Endringer i en webressurs vil ikke være synlig i programmet før du publiserer den.
  
<a name="BKMK_UsingTextEditor"></a>
   
### <a name="use-the-text-editor-appropriately"></a>Bruke tekstredigeringsprogrammet på riktig måte

Tekstredigeringsprogrammet i programmet for webressurser bør bare brukes for enkel redigering av tekstfiler. Du kan bruke det til å opprette og redigere HTML-webressurser, men du bør bare redigere HTML-webressurser som er opprettet ved hjelp av tekstredigeringsprogrammet. Tekstredigeringsprogrammet er utformet for svært enkelt HTML-innhold. 

> [!IMPORTANT]
> Hvis innholdet i en HTML-webressursen ikke ble opprettet ved hjelp av tekstredigeringsprogrammet, skal du ikke bruke tekstredigeringsprogrammet til å redigere det.  
> Tekstredigeringsprogrammet bruker en kontroll som endrer HTML-kilden på en måte som gjør at den kan redigeres. Disse endringene kan gjøre at siden fungerer annerledes i nettleseren og føre til at mer avansert kode slutter å fungere. Hvis du åpner en HTML-webressurs med tekstredigeringsprogrammet og lagrer den uten å gjøre endringer, kan det føre til feil for noen HTML-webressurser.  Mer informasjon: [Dokumentasjon for utviklere: Bruke tekstredigeringsprogrammet for HTML-webressurser](/dynamics365/customer-engagement/developer/webpage-html-web-resources#use-the-text-editor-for-html-web-resources)
  
Vi anbefaler at du bruker et eksternt redigeringsprogram til å redigere tekstfiler og deretter lagrer dem lokalt før du laster dem opp med knappen **Last opp fil**. På denne måten kan du beholde en kopi av webressursen hvis du trenger å gå tilbake til en tidligere versjon. Du kan bruke et enkelt redigeringsprogram, for eksempel Notisblokk, men et tekstredigeringsprogram med mer avanserte funksjoner anbefales sterkt. [Visual Studio Community](https://www.visualstudio.com/vs/community/) og [Visual Studio Code](https://code.visualstudio.com/) er gratis og inneholder kraftige funksjoner for redigering av tekstbaserte filer som brukes av webressurser.  

<a name="BKMK_CreateAndEditFormWebResources"></a>
 
## <a name="create-and-edit-a-web-resource-on-a-form"></a>Opprette og redigere en webressurs i et skjema

Du kan legge til eller redigere webressurser i et skjema for å gjøre det mer tiltalende eller nyttig for brukere. 

> [!NOTE]
> Du kan ikke inkludere en webressurs i en topptekst eller bunntekst.  

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="navigate-to-a-form"></a>Navigere til et skjema
Når løsningsutforskeren er åpen, viser du **Enheter** under **Komponenter**, og viser deretter enheten du vil arbeide med.

Velg **Skjemaer**, finne et skjema av typen Hovedskjema i listen, og dobbeltklikk eller trykk deretter oppføringen for å åpne og redigere skjemaet.

### <a name="add-or-edit-web-resource-in-a-form"></a>Legge til eller redigere webressurs i et skjema

Se [Egenskaper for webressurser](web-resource-properties-legacy.md) hvis du vil ha informasjon om egenskapene du kan angi for webressurser i et skjema.

### <a name="preview"></a>Forhåndsvisning

Slik forhåndsviser du hovedskjemaet og prøver ut hvordan hendelser fungerer:
- Velg **Forhåndsvisning** i kategorien **Hjem**, og velg deretter **Opprett skjema**, **Oppdater skjema** eller **Skrivebeskyttet skjema**.
- Velg **Lukk** på **Fil**-menyen for å lukke Forhåndsvisning-skjemaet.

### <a name="save"></a>Lagre

Når du ferdig med å redigere skjemaet, går du til kategorien **Hjem** og velger eller trykker **Lagre og lukk** for å lukke skjemaet. 

### <a name="publish"></a>Publiser

Når du er ferdig med tilpassingene, publiserer du dem:
- Hvis du vil publisere tilpassinger for bare komponenten som du redigerer, kan du velge enheten du har arbeidet med, i navigasjonsruten, og deretter velge **Publiser**.
- Hvis du vil publisere tilpassinger for alle upubliserte komponenter samtidig, velger du **Enheter** i navigasjonsruten, og velger deretter **Publiser alle tilpassinger** på **handlingsverktøylinjen**.
   
  
### <a name="see-also"></a>Se også  

[Egenskaper for webressurs](web-resource-properties-legacy.md) <br /> 
[Opprette og utforme skjemaer](create-design-forms.md) <br />
[Forstå modelldrevede appkomponenter](model-driven-app-components.md) <br /> 
[Dokumentasjon for utviklere: Webressurser for Customer Engagement](/dynamics365/customer-engagement/developer/web-resources)
