Ved å aktivere [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]tillater du flyten av data fra [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] til visse [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-servicer for å utføre noen av markedsføringsprosessene. Disse servicene er samlet kalt "[!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer."

Hvis du vil gjennomføre kundereiser, må [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] sende definisjoner på kundereise, e-post, innsendingsskjema og markedsføringsside til disse [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicene, som kjører på [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]. Markedsføringssider blir videresendt til en kundes egen forekomst av portalfunksjoner for [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)].

Hvis du vil tilpasse sendte e-postmeldinger, må [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] aktivere dataflyt til og fra [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]. Se nedenfor hvis du vil ha mer informasjon om [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]-servicen. Dataflyt til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] inkluderer synkronisering av kontakter og forretningsforbindelser til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]. [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer bruker disse dataene til å tilpasse e-postinnholdet. Dataene som inkluderes, avhenger ene og alene av e-postdefinisjonen.

Hvis du vil omberegne poengsummodeller og markedsføringssegmenter for kundeemne, må [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] sende definisjoner på poengsummodeller for kundeemne og segmentdefinisjoner til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] og bruke profiler og samhandlinger i [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] i disse beregningene.

Hvis du vil ha innsikt i e-post- og Internett-samhandlinger som er lagret av [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer, må de innsamlede dataene flyte fra [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer til både [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] og [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)].

Hvis integrering av hendelsesbehandling for [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] i tillegg er aktivert, synkroniserer [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] hendelser til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (direkte via koblingen for [!INCLUDE[pn-crm-online-shortest](../includes/pn-crm-online-shortest.md)]) og hendelsesregistreringer og innsjekkinger (via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer som samhandlinger).

Dataflyt som omfatter [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)], er følgende:
- Enhetsdata fra [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)], ved hjelp av vanlig innkommende kobling for [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)], for å formidle innhold for tilpassing av e-post, poengsummodell for kundeemne og segmentering (hovedsakelig kontakter og forretningsforbindelser, og til slutt også kundeemner og hendelser)
- Enhetsdata fra [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] for å formidle identifikatorene for samhandlinger og innsikter (kundereise, markedsførings-e-poster, markedsføringssider)
- Kommunikasjon fra [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (e-postsporing, nettstedssporing, kundereisefremdrift)
- Samhandlinger fra [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (hendelsesregistreringer og innsjekkinger)
- [!INCLUDE[pn-insights](../includes/pn-insights.md)] (samhandlinger og KPI-er) fra [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] via [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-servicer til [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] (hovedsakelig kundereise e-postfremdrift og resultater i poengsummodell for kundeemne)
- [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]-apper (segmentering og kontrollprogrammer) fra [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] direkte til dedikerte elementer og grensesnittelementer i sandkassemodus i skjemaer for[!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]

### <a name="marketing-services"></a>Markedsføringstjenester

[!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] bruker disse [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tjenestene:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] DocumentDB
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Lagringsplass

> [!NOTE]
> Hvis du vil ha mer informasjon om flere [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-servicetilbud, kan du se [!INCLUDE[cc_privacy_note_azure_trust_center](../includes/cc_privacy_note_azure_trust_center.md)] (<https://azure.microsoft.com/support/trust-center/>).

### [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]

Ved hjelp av [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] aktiverer du overføring av kundedata til [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] for videre behandling. Din bruk av [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] for [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] krever overholdelse av spesifikke personvernlover. Still eventuelle spørsmål til de riktige representantene i organisasjonen.

For øyeblikket er [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] i offentlig forhåndsversjon og tilbyr ikke kundene samme nivå av personvern og sikkerhetsforpliktelser som [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]eller [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] Customer Engagement. [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] er opprinnelig basert på [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-servicer, og respektive samsvars- og sikkerhetsstandarder for hver aktuelle [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-service gjelder. Hvis du vil ha mer informasjon, kan du gå til [!INCLUDE[cc-microsoft](../includes/cc-microsoft.md)] Klareringssenter: [https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)

[!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] bruker disse [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tjenestene:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] HDInsight (Spark, Phoenix, HBase)
- [!INCLUDE[pn-ms-azure-sql-database](../includes/pn-ms-azure-sql-database.md)]
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Secret Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Event Hub
- [!INCLUDE[pn-azure-stream-analytics](../includes/pn-azure-stream-analytics.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Redis Cache
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Monitoring
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Metrics
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Websites
- [!INCLUDE[pn_azure_service_bus](../includes/pn_azure_service_bus.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Lagringsplass
