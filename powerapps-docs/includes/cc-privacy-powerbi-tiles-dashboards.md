---
ms.openlocfilehash: 41ec7aed42a950e5adf0b87783fc568dbe9d02af
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61581197"
---
Når innebygging av Power BI-fliser og -instrumentbord er aktivert, og en bruker bygger inn en flis eller et instrumentbord fra Power BI, brukes vedkommendes [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]-godkjenningstoken for [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] til å godkjenne med Power BI-tjenesten med en spesifikk tillatelse. Dette gir en direkte, enkel påloggingsopplevelse for sluttbrukeren.  
  
 En administrator kan deaktivere innebygging av Power BI-fliser og -instrumentbord når som helst, ved å stoppe bruken av [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-godkjenningstokenet for godkjenning med Power BI-tjenesten. Eventuelle eksisterende fliser eller instrumentbord blir ikke lenger gjengitt for sluttbrukeren.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenten eller -tjenesten som brukes til innebygging av Power BI-fliser, beskrives i delen nedenfor.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
 Denne tjenesten leverer godkjenningenstokenet som utveksles med Power BI-tjenesten for API- og UI-godkjenning.