---
ms.openlocfilehash: ac90bfc27e03047cf422c44c83f550608d67b57e
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67212844"
---
Ved å aktivere portalegenskaper for [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], kan [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-data, for eksempel kundenavn, produktnavn, saksnummer eller egendefinerte enhetsdata, vises gjennom en utadrettet [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-portal. Alle data som vises via portalen, lagres i minnet i Microsoft [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Web Apps for bufring, og som filer på den lokale harddisken for å aktivere portalsøkefunksjonen.

En leieradministrator aktiverer [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-portaler ved å konfigurere dem gjennom [!INCLUDE[pn_dyn_365_admin_center](../includes/pn-dyn-365-admin-center.md)], som også installerer en pakke (med løsninger og data) i den valgte[!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-forekomsten. En leieradministrator eller en [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]-bruker som er konfigurert som en portaladministrator, kan deretter angi dataene som vises gjennom portalen. Hvis du vil deaktivere portalegenskapene senere, kan en leieradministrator avbryte abonnementet for portaltillegget med [!INCLUDE[pn_Office_365](pn-office-365.md)].

Viktige [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenter og -tjenester som er involvert med portalegenskapene, er:
- [Azure Web Apps](https://azure.microsoft.com/services/app-service/web/): [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]Web Apps brukes til å drifte portalen i [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)].
- [Azure Traffic Manager](https://azure.microsoft.com/services/traffic-manager/): [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]Traffic Manager brukes til å sikre høy tilgjengelighet av tjenesten ved å distribuere brukeren til Web Apps som er oppe og går. 
- [Azure service Bus](https://azure.microsoft.com/services/service-bus/): [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)](Emner/abonnementer) brukes til å dele opp hurtig bufferen for portalene. [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)] lagrer meldinger midlertidig, noe som utløses når en portalrelatert post endres i [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] og sendes videre til Web Apps for å bufre ugyldigjøringen. 
- [Azure Key Vault](https://azure.microsoft.com/services/key-vault/): Alle tjenester lagrer konfigurasjonsdata i [!INCLUDE[pn_azure_key_vault](pn_azure_key_vault.md)].
- [Azure Storage](https://azure.microsoft.com/services/storage/): Data relatert til organisasjonen, leier og Portal lagres på [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] lagrings plass.
- [Azure Active Directory](https://azure.microsoft.com/services/active-directory/): Alle net tjenester bruker [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] til å godkjennes.
