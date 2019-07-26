---
ms.openlocfilehash: 252f09737dbf55309a64ef5d02d479fde0e61c0e
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67224854"
---
Når du aktiverer e-postengasjement, en innebygd intelligens funksjon, og du sender en e-post med**Follow**-innstillingen fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], blir informasjon om samhandlinger med e-postmeldingen av mottakerne samlet inn og lagret i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Formålet med dette er å beregne mottakernes aktivitets-KPI-er og samhandlinger på «fulgte» e-poster.  
  
 En systemansvarlig aktiverer e-postengasjement ved å klargjøre funksjonen fra **E-postengasjement**-fanen i innebygd intelligens. Administratorer kan deaktivere e-postengasjement i organisasjonen fra **Konfigurasjon av intelligens**-noden, under **Innstillinger**.  
  
 Når funksjonen har blitt deaktivert, kan man ikke følge e-post som sendes fra [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], enten fra brukergrensesnittet eller programmatisk. Samhandlingsdata fra mottakerne blir ikke lenger samlet inn fra sendte e-postmeldinger som ble merket med **Følg**-innstillingen. Eventuell data som ble samlet inn tidligere, forblir i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Den blir tilgjengelig igjen hvis funksjonen aktiveres på nytt i organisasjonen. Data beholdes i 90 dager etter at kundene avslutter abonnementet fra Microsoft. [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-brukere kan også deaktivere funksjonen Innebygd intelligens – E-postengasjement per kontakt eller kundeemne ved å endre **Følg e-post**-innstillingen under **Kontaktinnstillinger**.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert med E-postengasjement-funksjonen, beskrives nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 **[!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)]**  
  
 E-postengasjement-funksjonen bruker [!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)] til å midlertidig lagre BLOB-er for e-postsamhandling.