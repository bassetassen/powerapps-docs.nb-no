---
ms.openlocfilehash: fa4a17c2a3131f49f8a702388bdb405661855c10
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/19/2019
ms.locfileid: "61550023"
---
Når du godtar vilkårene for hendelsesbehandling, er funksjonen for nettseminarintegrering aktivert. Funksjonen for nettseminarintegrering bruker en leverandør av nettseminar for å utføre en hendelse eller en økt som et nettseminar. Hvis du vil bruke en tjeneste fra en leverandør av nettseminaret, må du ha en konto hos leverandøren. Den eneste leverandøren som leverer en nettseminarløsning som er klar til bruk uten tilpasninger, er ON24. Når du bruker funksjonen for nettseminarintegrering, behandles og lagres data som er viktige for å levere og kjøre nettseminaret i [!INCLUDE[pn-azure-service-fabric](../includes/pn-azure-service-fabric.md)], og sendes deretter til ON24. Disse dataene inkluderer registreringsopplysninger for deltakere på nettseminaret, som for eksempel navn, e-postadresse og firmanavn. I tillegg sender ON24 måledata for nettseminaret, som for eksempel hvor lenge deltakerne så på nettseminaret, til [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] via [!INCLUDE[pn-azure-service-fabric](../includes/pn-azure-service-fabric.md)].

Du trenger ikke å aktivere funksjonen for nettseminar for å bruke resten av løsningen for hendelsesbehandling. En administrator kan deaktivere funksjonen for nettseminarintegrering ved å fjerne legitimasjonen i konfigurasjonen av nettseminaret.

Følgende [!INCLUDE[pn-windows-azure](../includes/pn-windows-azure.md)]-komponenter og -tjenester brukes av funksjonen for nettseminarintegrering:

- [!INCLUDE[pn_azure_key_vault](../includes/pn_azure_key_vault.md)] ([!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Hva er Azure Key Vault?](https://docs.microsoft.com/azure/key-vault/key-vault-whatis))
  - Gir krypteringsnøkkel for kryptering/dekryptering av kundenes kontolegitimasjonen for ON24
- [!INCLUDE[pn-azure-service-fabric](../includes/pn-azure-service-fabric.md)] ([!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Oversikt over Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview))
  - Behandler og sender registreringsdata og kontolegitimasjon for nettseminaret til ON24
  - Henter måledata for nettseminaret fra ON24 til [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] – lagrer kundens kontolegitimasjonen for ON24 (egendefinert kryptering)