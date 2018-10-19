---
title: Rediger systemenhetsmeldinger med PowerApps | MicrosoftDocs
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
ms.openlocfilehash: 797d6855bea421abd90752dd9ae0ad73a9d92f38
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39694795"
---
# <a name="edit-system-entity-messages"></a>Rediger systemenhetsmeldinger

Standard visningsnavn for enkelte systemenheter brukes i brukergrensesnittekst og feilmeldinger i Common Data Service for apper. Hvis du endrer visningsnavnet, bør du også oppdatere alle meldinger som bruker standard visningsnavn. Hvis du for eksempel endrer visningsnavnet fra *Konto* til *Firma*, ser du fremdeles en feilmelding med det gamle navnet.  

Du kan ikke endre systemmeldinger ved hjelp av PowerApps-portalen. Du må bruke Løsningsutforsker.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Hvis du ser en **Meldinger**-node i Løsningsutforsker, under enheten, kan du redigere bestemt tekst som inneholder referanser til det opprinnelige visningsnavnet for enheten. 

![Enhetsmeldinger](../model-driven-apps/media/entity-messages.png)

Det er enkelt å redigere denne teksten. Dobbeltklikk på meldingen for å se et skjema med tre felt:  
  
|Felt|Beskrivelse|  
|-----------|-----------------|  
|**Standard visningsstreng**|Viser den opprinnelige teksten.|  
|**Egendefinert visningsstreng**|Rediger denne teksten for å endre visningsstrengen.|  
|**Kommentar**|Valgfritt. Inkluder en kommentar om hva du har endret og hvorfor.|  
  
Noe av meldingsteksten kan inneholde plassholdere. Disse plassholderne er tall med hakeparenteser på hver side. Eksempel: `{0}`. Disse plassholderne tillater at tekst settes inn i meldingen. Hvis du redigerer meldinger, må du sørge for å beholde disse plassholderne. 

Velg ![Lagre](media/save-entity-icon-solution-explorer.png) for å lagre endringene. Velg **Lagre og lukk** for å lukke skjemaet når du lagrer.

> [!NOTE]
> Selv om brukergrensesnittet som vises for å redigere systemenhetsmeldinger, inneholder mange referanser til enhetsnavn, inneholder det ikke alle. For en mer omfattende tilnærming, kan du se [Oppdater lokaliserbar tekst på originalspråket](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language)

## <a name="programmatically-update-entity-display-strings"></a>Oppdater visningsstrenger for enheten programmatisk

For utviklere som ser etter en måte de kan arbeide med disse i kode på, lagres visningsstrengene i [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md)-enheten. 

`DisplayString`-enheten inneholder ikke standard visningsstrenger. De to attributtene for denne enheten, som inneholder tekst, er [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) og [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString). Disse attributtverdiene er null som standard, med mindre visningsstrengen er tilpasset og publisert. `PublishedDisplayString`-verdien er skrivebeskyttet og viser `CustomDisplayString`, som for øyeblikket er publisert.
 
## <a name="see-also"></a>Se også
[Rediger en enhet](edit-entities.md)<br />
[Oversett lokaliserbar tekst for modelldrevne apper](../model-driven-apps/translate-localizable-text.md)
