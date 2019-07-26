---
ms.openlocfilehash: f331670a2fd6b051c91a7fe2bfa607c54c9ab41a
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/18/2019
ms.locfileid: "67225238"
---
Ved å aktivere [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)], godtar du tillatelse for flyt av dataene fra [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] til enkelte [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tjenester for å kunne utføre noen av markedsføringsprosessene. Disse tjenestene er samlet kalt «[!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenester.»

Gjøremål for kundereiser, [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]-behov for å sende kundereise, e-post, sendeskjema og sidedefinisjoner for markedsførings til disse [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenestene, som kjører på [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]. Markedsføringssider sendes videre til en kundes egne forekomst for portalefunksjoner for [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)].

[!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] må aktivere dataflyt til og fra [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] for å tilpasse sendte e-postmeldinger. Se nedenfor hvis du vil ha mer informasjon om [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]-tjenesten. Dataflyt til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] inkluderer synkronisering av kontakter og -kontoer til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]. [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenester bruker disse dataene til å tilpasse e-postinnhold. Dataene som er inkludert avhenger utelukkende av e-postdefinisjonen.

[!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] må sende definisjoner for resultatmodellen for kundeemne og segmentdefinisjonene til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] for å beregne resultatmodellen for kundeemne og markedsføringssegmenter på nytt, og for å dra nytte av profiler og samhandlinger i [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] i disse beregningene.

De innsamlede dataene flyter fra [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenester, til både [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] og [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)], for gi innsikt i e-post og Internett-samhandlinger fanget opp av [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenester.

Hvis [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]-integrasjon for hendelsesadministrering også er aktivert, synkroniserer [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] hendelser til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (direkte via koblingen for [!INCLUDE[pn-crm-online-shortest](../includes/pn-crm-online-shortest.md)]), og hendelsesregistreringer og innsjekkinger (via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenestene, som samhandlinger).

Dataflyt som involverer [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)], er følgende:
- Enhetsdata fra [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)], ved hjelp av den vanlige innkommende koblingen for [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] for å kunne levere innhold for e-posttilpassing, resultater for kundeemner og segmentering (hovedsakelig kontakter og kontoer, og til slutt også kundeemner og hendelser)
- Enhetsdata fra [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenestene til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] for å gi identifikatorer for samhandlinger og innsikter (kundereise, e-poster for markedsføring, markedsføringssider)
- Samhandlinger fra [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenester til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (e-postsporing, sporing av nettsted, fremdrift for kundereise)
- Samhandlinger fra [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenester til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (hendelsesregistreringer og innsjekkinger)
- [!INCLUDE[pn-insights](../includes/pn-insights.md)] (samhandlinger og KPI-er) fra [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-tjenestene til [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] (hovedsakelig kundereise og fremdrift for sending av e-post og resultater for kundeemne)
- [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] apper (Segmentering og kontrollprogrammer) fra [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] direkte til dedikerte grensesnittelementer i sandkassemodus i skjemaer for [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]

### <a name="marketing-services"></a>Markedsføringstjenester

[!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] bruker disse [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tjenestene:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] DocumentDB
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Storage

> [!NOTE]
> Hvis du vil mer informasjon om flere [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tjenestetilbud, kan du se [!INCLUDE[cc_privacy_note_azure_trust_center](../includes/cc_privacy_note_azure_trust_center.md)] (<https://azure.microsoft.com/support/trust-center/>).

### [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]

Ved hjelp av [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)], aktiverer du overføring av kundedata til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] for ytterligere behandling. Din bruk av [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] for [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] kan kanskje kreve samsvar med bestemte personvernlover. Henvend deg med eventuelle spørsmål til den riktige representanten i organisasjonen.

[!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] er for øyeblikket i offentlig testversjon, og tilbyr ikke det samme nivået av personvern og sikkerhetsforpliktelser som [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] eller [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] Customer Engagement. [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] er opprinnelig bygd på [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tjenester, og respektive standarder for samsvar og sikkerhet for hver aktuelle [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] for tjenestebruk. Hvis du vil ha mer informasjon, kan du gå til [!INCLUDE[cc-microsoft](../includes/cc-microsoft.md)] Klareringssenteret: [https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)

[!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] bruker disse [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tjenestene:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] HDInsight (Spark, Phoenix, HBase)
- [!INCLUDE[pn-ms-azure-sql-database](../includes/pn-ms-azure-sql-database.md)]
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Hemmelig lager
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Hendelseshub
- [!INCLUDE[pn-azure-stream-analytics](../includes/pn-azure-stream-analytics.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Redis Cache
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Overvåking
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Måledata
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Nettsteder
- [!INCLUDE[pn_azure_service_bus](../includes/pn_azure_service_bus.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Storage
