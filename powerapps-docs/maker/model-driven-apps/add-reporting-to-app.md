---
title: Legge til rapportering i en modelldrevet app
ms.custom: ''
ms.date: 06/24/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: b4098c96-bce1-4f57-804f-8694e6254e81
caps.latest.revision: 15
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-reporting-to-your-model-driven-app"></a>Legge til rapportering i en modelldrevet app

PowerApps-apper kan inkludere rapporter som gir nyttig forretningsinformasjon til brukeren. Disse rapportene er basert på SQL Server Reporting Services og gir samme sett med funksjoner som er tilgjengelige for vanlige SQL Server Reporting Services-rapporter.

> [!div class="mx-imgBorder"] 
> ![](media/progress-against-goals-report.png "Standardrapport om fremdrift mot mål")

Systemrapporter er tilgjengelige for alle brukere. Enkeltpersoner som oppretter eller på annen måte eier rapporter, kan dele dem med bestemte kolleger eller team. De kan også gjøre rapportene tilgjengelige for organisasjonen, slik at alle brukerne kan kjøre dem. Disse rapportene bruker FetchXML-spørringer som er proprietære til Common Data Service og Dynamics 365 for Customer Engagement-apper, og henter data for å bygge rapporten. Rapporter som du oppretter i en PowerApps-app, er Fetch-baserte rapporter.

> [!NOTE]
> Rapportfunksjoner fungerer ikke med lerretsapper eller modelldrevne apper som kjører på mobile enheter, for eksempel nettbrett og mobiltelefoner. 

Rapporter kan bygges på en av følgende måter.

- Fra en modelldrevet app ved hjelp av rapportveiviseren. Mer informasjon: [Opprette eller redigere en rapport ved hjelp av rapportveiviseren](/dynamics365/customer-engagement/basics/create-edit-copy-report-wizard) 
<!-- From a model-driven app using an advanced find query. To do this, you build an advanced find query and then select **Download as FetchXML**. Next, from the reports area select **New**, for **Report Type** select **Existing File**, select **Choose File** open the xml file, fill in the required fields, and save the report. More information: [Add a report](/dynamics365/customer-engagement/basics/add-existing-report) -->
- Opprette egendefinert rapport med SQL Server Data Tools og rapportredigeringsutvidelser. Mer informasjon: [Veiledning for rapportering og analyse](/dynamics365/customer-engagement/analytics/reporting-analytics-with-dynamics-365)


## <a name="add-reporting-to-a-unified-interface-app"></a>Legge til rapportering til en app med enhetlig grensesnitt
Du kan legge til Fetch-basert rapportfunksjonalitet i appen, slik at brukere kan kjøre, dele, opprette og redigere rapporter. Hvis du vil gjøre dette, legger du til rapport-enheten i områdekartet for appen. 

1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) og åpne en eksisterende app for redigering. 
2. Velg ![blyantikon for redigering av områdekart](media/ccf-pencil-icon.png) ved siden av **områdekart** i App Designer. 
3. I Sitemap Designer velger du **Legg til**, og deretter **Område**. 
4. Skriv inn navn på områdetittelen i **Tittel-boksen**, for eksempel *Rapporter*. 
5. Velg området du har gitt navnet i det forrige trinnet, velg **Legg til**, velg **Gruppe** og i gruppens **Tittel** angir du navn på gruppetittelen, for eksempel *Rapporter*. 
6. Velg gruppen du har angitt i forrige trinn, velg **Legg til**, velg **Underområde** og inkluder deretter følgende egenskaper: 

   - **Type**. Velg **Enhet**.
   - **Enhet**. Velg **rapport**-enheten fra listen over enheter.  
   - **Tittel**. Angi en beskrivende tittel, for eksempel *rapporter*.

      ![Legg til rapportenhet i områdekartet](media/report-entity-sitemap.png)

7. Velg **Lagre og lukk** for å gå tilbake til appdesigneren. 


8. I appdesigneren velger du **Lagre** og deretter **Publiser**.


Nå viser appen et **rapporter**-område der brukere kan vise, kjøre, tilordne, dele og redigere rapportene de har tillatelse til, samt opprette nye rapporter ved hjelp av rapportveiviseren. 

> [!div class="mx-imgBorder"] 
> ![](media/report-feature-in-app.png "Rapportvisning")

### <a name="see-also"></a>Se også
[Kjøre en rapport](/dynamics365/customer-engagement/basics/run-report)
