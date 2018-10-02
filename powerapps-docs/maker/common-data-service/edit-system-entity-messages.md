---
title: Redigere systemenhetsmeldinger med PowerApps | MicrosoftDocs
description: Finn ut hvordan du redigerer systemenhetsmeldinger
ms.custom: ''
ms.date: 05/15/2018
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
ms.assetid: 3ccbd8de-8d6f-4058-87f7-15463667cfc6
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="edit-system-entity-messages"></a>Redigere systemenhetsmeldinger

Standard visningsnavn for noen av systemenhetene brukes i tekst og feilmeldinger i brukergrensesnittet i Common Data Service for Apps. Hvis du endrer visningsnavnet, bør du også oppdatere eventuelle meldinger som bruker standard visningsnavn. Hvis du for eksempel endrer visningsnavnet fra *Konto* til *Firma*, kan du fremdeles se en feilmelding med det gamle navnet.  

Du kan ikke redigere systemmeldinger ved hjelp av PowerApps-portalen. Du må bruke løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Hvis du ser en **Meldinger**-node under enheten i løsningsutforskeren, kan du redigere bestemt tekst som inneholder referanser til det opprinnelig visningsnavnet for enheten. 

![Enhetsmeldinger](../model-driven-apps/media/entity-messages.png)

Det er enkelt å redigere denne teksten. Dobbeltklikk på meldingen for å se et skjema med tre felt:  
  
|Felt|Beskrivelse|  
|-----------|-----------------|  
|**Standard visningsstreng**|Viser den opprinnelige teksten.|  
|**Egendefinert visningsstreng**|Rediger denne teksten hvis du vil endre visningsstrengen.|  
|**Kommentar**|Valgfritt. Inkluder en kommentar om hva du har endret og hvorfor.|  
  
Noe av meldingsteksten kan ha plassholdere. Disse plassholderne er tall med hakeparenteser på hver side. Eksempel: `{0}`. Med disse plassholderne kan du sette inn tekst i meldingen. Hvis du redigerer meldinger, må du passe på at du beholder disse plassholderne. 

Velg ![Lagre](media/save-entity-icon-solution-explorer.png) for å ta i bruk endringene. Velg **Lagre og lukk** for å lukke skjemaet når du lagrer det.

> [!NOTE]
> Selv om brukergrensesnittet som brukes til redigering av systemenhetsmeldinger, inneholder mange referanser til enhetsnavn, er ikke alle inkludert. For en mer omfattende fremgangsmåte kan du se [Oppdatere oversettbar tekst på originalspråket](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language)

## <a name="programmatically-update-entity-display-strings"></a>Programmatisk oppdatering av visningsstrenger for enhet

For utviklere som ser etter en måte for å arbeide med disse i kode, lagres visningsstrenger i [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md)-enheten. 

Enheten `DisplayString` inneholder ikke standard visningsstrenger. De to attributtene for denne enheten som inneholder tekst, er [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) og [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString). Disse attributtverdiene er null som standard, med mindre visningsstrengen er tilpasset og publisert. Verdien `PublishedDisplayString` er skrivebeskyttet og viser den gjeldende publiserte `CustomDisplayString`.
 
## <a name="see-also"></a>Se også
[Redigere en enhet](edit-entities.md)<br />
[Oversette oversettbar tekst for modelldrevne apper](../model-driven-apps/translate-localizable-text.md)
