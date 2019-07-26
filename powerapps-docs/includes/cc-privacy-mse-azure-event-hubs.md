---
ms.openlocfilehash: 29226cfe8ab5c0ad01b785cfdaeec2e12a230dd7
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67225336"
---
Ved å aktivere Social Engagement for å koble til [Azure Event Hubs](https://azure.microsoft.com/documentation/articles/event-hubs-overview/), tillater du at sosiale data strømmes til Event Hubs ved hjelp av automatiseringsregler. Azure Event Hubs lagrer den sosiale dataen som strømmes fra Social Engagement for en [forhåndskonfigurert tidsperiode](https://azure.microsoft.com/documentation/articles/event-hubs-availability-and-support-faq/), og alle programmer som kan lytte til hendelseshuben kan få tilgang til, lagre eller behandle disse dataene.  
  
 Vær oppmerksom på at den sosiale dataen som sendes fra Social Engagement inkluderer informasjon om sosiale innlegg (forfatteren og tekst), i tillegg til mer detaljert informasjon som språk, plassering, stemning, merker, osv. For fullstendig informasjon om innholdet i et sosialt innlegg som er sendt til hendelseshuber, kan du se [JSON-skjemadefinisjon](http://go.microsoft.com/fwlink/p/?LinkId=786643).