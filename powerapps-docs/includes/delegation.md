---
ms.openlocfilehash: 7b0f9ce710887c870d22a6362f9cd28245d72519
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "62091280"
---
## <a name="delegation"></a>Delegering
Når det er mulig, vil PowerApps delegere filtrerings- og sorteringsoperasjoner til datakilden og bla gjennom resultatene ved behov. Når du eksempelvis starter et program som viser en **[galleri](../maker/canvas-apps/controls/control-gallery.md)** -kontroll som er fylt med data, er det bare det første settet med poster som i utgangspunktet overføres til enheten. Når brukeren ruller, lastes det inn tilleggsdata fra datakilden. Resultatet er en raskere oppstart for appen samt tilgang til svært store datasett.

Delegering er imidlertid kanskje ikke alltid mulig. Datakilder varierer med tanke på hvilke funksjoner og operatorer de støtter med delegering. Hvis komplett delegering av en formel ikke er mulig, vil redigeringsmiljøet flagge den delen som ikke kan delegeres med en advarsel. Når det er mulig, kan du vurdere å endre formelen for å unngå funksjoner og operatorer som ikke kan delegeres.  [Delegeringslisten](../maker/canvas-apps/delegation-list.md) opplyser om hvilke datakilder og operasjoner som kan delegeres.

Hvis delegering ikke er mulig, vil PowerApps hente bare et lite sett med poster å arbeide med globalt. Funksjoner for filtrering og sortering vil operere på et begrenset sett med poster. Det som er tilgjengelig i **[galleriet](../maker/canvas-apps/controls/control-gallery.md)**, illustrerer kanskje ikke helheten, noe som kan forvirre brukerne. 

Se [Oversikten over delegering](../maker/canvas-apps/delegation-overview.md) for mer informasjon.

