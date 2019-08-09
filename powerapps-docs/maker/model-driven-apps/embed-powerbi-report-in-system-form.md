---
title: Bygge inn en Power BI-rapport i et modelldrevet systemskjema | MicrosoftDocs
ms.custom: ''
ms.date: 03/05/2019
ms.reviewer: matp
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 99c795e0-9165-4112-85b1-6b5e1a4aa5ec
caps.latest.revision: 1
author: prsi-msft
ms.author: prsi
manager: kvivek
tags:
  - Links to topic not migrated
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="embed-a-power-bi-report-in-a-model-driven-system-form"></a>Bygge inn en Power BI-rapport i et modelldrevet systemskjema
Du kan bruke Power BI-rapporter i PowerApps-modelldrevne apper for å tilføre omfattende rapportering og analyse til systemskjemaene og gi brukerne muligheten til å oppnå mer. Dette gir deg mulighet til å samle inn data på tvers av systemer og skreddersy ned til konteksten for en enkelt oppføring.
 
## <a name="prerequisites"></a>Forhåndskrav
Innebygging av Power BI-innhold er en valgfri funksjon og deaktiveres i alle miljøer som standard. Du må aktivere den før du kan bygge inn Power BI-innhold. Hvis du vil ha mer informasjon: [Aktivere Power BI-visualiseringer i organisasjonen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/use-power-bi?#enable--visualizations-in-the-organization).

Denne funksjonen krever eksport av en løsning, endring av den for å legge til en XML-snutt og deretter importering tilbake til miljøet. Sørg for å importere endringene i målmiljøet bare via en administrert løsning. Se [Importer, oppdater og eksporter løsninger](https://docs.microsoft.com/powerapps/maker/common-data-service/import-update-export-solutions) for retningslinjer for hvordan du installerer en oppdatering til en eksisterende administrert løsning.

## <a name="embed-without-contextual-filtering"></a>Bygge inn uten kontekstavhengig filtrering
Du kan bruke Power BI-rapporter og -fliser ved å bare innebygge dem, og få nøyaktig samme rapport. Dette innebærer ikke å konteksttilpasse dem til det gjeldende modelldrevne skjemaet, og derfor får du samme rapport eller flis på alle oppføringer i enheten. For eksempel viser følgende rapport den geografiske plasseringen av alle forretningsforbindelser samtidig, og er nyttig for å vise sammendragsinformasjon.

> [!div class="mx-imgBorder"] 
> ![](media/embed-powerbi/embed-powerbi-report-in-system-form-unfiltered.png "Embed-powerbi-report-in-system-form-unfiltered")

Du kan bygge inn en del som er vert for Power BI-rapporter og -fliser i systemskjemaene ved å legge til følgende kodesnutt i `<sections>`-blokken i skjema-XML-en. Deretter kan du importere løsningen i målmiljøet. 

```xml
<section id="{d411658c-7450-e1e3-bc80-07021a04bcc2}" locklevel="0" showlabel="true" IsUserDefined="0" name="tab_4_section_1" labelwidth="115" columns="1" layout="varwidth" showbar="false">
    <labels>
        <label languagecode="1033" description="Unfiltered Power BI embedding demo"/>
    </labels>
    <rows>
        <row>
            <cell id="{7d18b61c-c588-136c-aee7-03e5e74a09a1}" showlabel="true" rowspan="20" colspan="1" auto="false">
                <labels>
                    <label languagecode="1033" description="Accounts (Parent Account)"/>
                </labels>
                <control id="unfilteredreport" classid="{8C54228C-1B25-4909-A12A-F2B968BB0D62}">
                    <parameters>
                        <PowerBIGroupId>00000000-0000-0000-0000-000000000000</PowerBIGroupId>
                        <PowerBIReportId>544c4162-6773-4944-900c-abfd075f6081</PowerBIReportId>
                        <TileUrl>https://xyz.powerbi.com/reportEmbed?reportId=544c4162-6773-4944-900c-abfd075f6081</TileUrl>
                    </parameters>
                </control>
            </cell>
        </row>
        <row/>
    </rows>
</section>
```
> [!IMPORTANT]
> Kontroller at du bruker kontrollen `classid="{8C54228C-1B25-4909-A12A-F2B968BB0D62}"` som angitt i XML-eksemplet.

 Denne tabellen beskriver egenskapene i det foregående eksemplet.

|                                                 Egenskap                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Beskrivelse                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         **PowerBIGroupId**                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Power BI-arbeidsområde-ID-en. Brukerens standardarbeidsområde er alltid 00000000-0000-0000-0000-000000000000. Du kan kontrollere ID-en for et arbeidsområde ved å se på URL-adressen. Eksempel: https://xyz.powerbi.com/groups/0ddbe381-256d-44bc-93de-34e47f3d9ab4/.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                               **PowerBIReportId**                                |                             Power BI-rapport-ID-en. Erstatt denne med rapporten du vil innebygge. Du kan kontrollere ID-en for en rapport ved å se på URL-adressen. Eksempel: https://xyz.powerbi.com/groups/me/reports/544c4162-6773-4944-900c-abfd075f6081.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|                                       **TileUrl**                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        URL-en for Power BI-rapporten eller -flisen som du vil innebygge. Bruk riktig Power BI-forekomstnavn (erstatt msit.powerbi.com med ditt eget) og rapport-ID (erstatt reportId=544c4162-6773-4944-900c-abfd075f6081 med din egen). Eksempel: https://xyz.powerbi.com/reportEmbed?reportId=544c4162-6773-4944-900c-abfd075f6081.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

## <a name="embed-with-contextual-filtering"></a>Bygge inn med kontekstavhengig filtrering
Du kan gjøre Power BI-rapporter og -fliser mer meningsfylte ved å bruke kontekstavhengige filtre i det gjeldende modelldrevne skjemaet, slik at rapporten eller flisen filtreres basert på attributter for den gjeldende oppføringen. Eksempelvis viser rapporten nedenfor den geografiske plasseringen for en forretningsforbindelse ved filtrering av Power BI-rapporten ved hjelp av navnet på forretningsforbindelsen. Dette gjør det mulig for en enkeltrapport å vise kontekstavhengig informasjon for alle oppføringer for enheten.

> [!div class="mx-imgBorder"] 
> ![](media/embed-powerbi/embed-powerbi-report-in-system-form-filtered.png "Embed-powerbi-report-in-system-form-filtered")

Filtreringen gjøres ved å legge til et `<PowerBIFilter>`-element i `<parameter>`-blokken, som vist her. Hvilket som helst attributt i enhetens skjema kan brukes til å konstruere filteruttrykk. Hvis du vil ha mer informasjon: [Lage filtre](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Filters#contructingfilters) for å forstå hvordan du oppretter dine egne filtre.
    
```xml
<control id="filteredreport" classid="{8C54228C-1B25-4909-A12A-F2B968BB0D62}">
    <parameters>
        <PowerBIGroupId>00000000-0000-0000-0000-000000000000</PowerBIGroupId>
        <PowerBIReportId>544c4162-6773-4944-900c-abfd075f6081</PowerBIReportId>
        <TileUrl>https://xyz.powerbi.com/reportEmbed?reportId=544c4162-6773-4944-900c-abfd075f6081</TileUrl>
        <PowerBIFilter>{"Filter": "[{\"$schema\":\"basic\",\"target\":{\"table\":\"My Active Accounts\",\"column\":\"Account Name\"},\"operator\":\"In\",\"values\":[$a],\"filterType\":1}]", "Alias": {"$a": "name"}}</PowerBIFilter>
    </parameters>
</control>
```

Vær oppmerksom på at dette bruker den samme kontrollen som den ufiltrerte rapporten, og derfor blir kontrollklasse-IDen uendret. 

Denne tabellen beskriver eventuelle tilleggsegenskaper som brukes i det foregående eksemplet.

|                                                 Egenskap                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Beskrivelse                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         **PowerBIFilter**                          |        Filteruttrykket som konteksttilpasser Power BI-rapporten ved å sende til skjemaattributter som parametere. Hvis du vil gjøre det enklere å lese, lages filteret som vist her.    |

    {
            "Filter": "[{
                    \"$schema\":\"basic\",
                    \"target\":{
                            \"table\":\"My Active Accounts\",
                            \"column\":\"Account Name\"
                    },
                    \"operator\":\"In\",
                    \"values\":[$a, $b],
                    \"filterType\":1
            }]",
            "Alias": {
                    "$a": "firstname",
                    "$b":"lastname"
            }
    }

Måldelen av det forrige uttrykket identifiserer tabellen og kolonnen som filtrene skal brukes på. Operatoren identifiserer logikken, og verdier identifisere dataene som sendes fra den PowerApps-modelldrevne appen. For å lage parametere på en generell måte lages verdiene ved hjelp av alias. I det forrige uttrykket sendes verdien av en forretningsforbindelses **fornavn** og **etternavn**, og et av dem søkes det etter i **Navn på forretningsforbindelse**-kolonnen i Power BI-rapporten. Vær oppmerksom på at **fornavn** og **etternavn** er unike navn for attributtene til forretningsforbindelsesenheten, og den tilhørende verdien sendes hit. 

Du kan opprette mer komplekse filteruttrykk ved å se på eksempler fra [Lage filtre](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Filters#contructingfilters) og angi de riktige verdiene for $schema og filterType. Husk å velge escape for hver litteral i filterdelen ved å bruke *\"*, slik at JSON genereres på riktig måte.

## <a name="known-issues-and-limitations"></a>Kjente problemer og begrensninger
1. Denne integreringen er bare tilgjengelig i klienten Enhetlig grensesnitt, på nettlesere og mobile enheter som støttes.
2. Åpning av dette skjemaet i PowerApps-skjemautforming vil ikke vise kontrollen på en meningsfull måte. Dette er fordi kontrollen tilpasses utenfor skjemautformingen.
3. Brukere godkjennes til Power BI automatisk med PowerApps-brukernavn og -passord. Hvis en Power BI-forretningsforbindelse med samsvarende legitimasjon ikke finnes, vises det en påloggingsledetekst som illustrert her. 

   > [!div class="mx-imgBorder"] 
   > ![](media/embed-powerbi/embed-powerbi-report-in-system-form-auth-1.png "Embed-powerbi-report-in-system-form-auth-1")

4. Ingen data vises hvis feil forretningsforbindelse brukes til å logge på Power BI. Hvis du vil logge på med riktig legitimasjon, logger du av og deretter på igjen.

   > [!div class="mx-imgBorder"] 
   > ![](media/embed-powerbi/embed-powerbi-report-in-system-form-auth-2.png "Embed-powerbi-report-in-system-form-auth-2")

   > [!div class="mx-imgBorder"] 
   > ![](media/embed-powerbi/embed-powerbi-report-in-system-form-auth-3.png "Embed-powerbi-report-in-system-form-auth-3")

5. Visningen av rapportdataene som vises i PowerApps, er de samme som i Power BI, og PowerApps-sikkerhetsroller og -rettigheter har ingen innvirkning på dataene som vises. Derfor er dataene stort sett de samme som de oppretteren av Power BI-datasettet ser. Hvis du vil bruke datatilgangsbegrensninger lignende PowerApps-sikkerhetsroller og -team, bruker du [Radnivåsikkerhet (RLS) med Power BI](https://docs.microsoft.com/power-bi/service-admin-rls).
6. Hvis skjemaet ikke viser Power BI-rapporten når du har importert løsningen og publisert tilpasninger, åpne den i det modelldrevne skjemaredigeringsprogrammet og lagre den, slik at skjema-JSON genereres.


### <a name="see-also"></a>Se også

[Bygge et Power BI-instrumentbord på et PowerApps-modelldrevet personlig instrumentbord](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard)

[Bruke Power BI med Dynamics 365 for Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/admin/use-power-bi)

[Importer, oppdater og eksporter løsninger](../common-data-service/import-update-export-solutions.md)
