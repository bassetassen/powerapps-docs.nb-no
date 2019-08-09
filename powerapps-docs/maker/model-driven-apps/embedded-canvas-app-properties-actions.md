---
title: Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll | MicrosoftDocs
ms.custom: ''
ms.date: 06/25/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 00e62904-2ce9-4730-a113-02b1fedbf22e
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="modeldrivenformintegration-control-properties-and-actions"></a>Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll
Lerretapper som er innebygd i modelldrevne skjemaer, inneholder en spesiell kontroll kalt **ModelDrivenFormIntegration**. Denne kontrollen er ansvarlig for å hente kontekstavhengige data fra det vertsmodelldrevne skjemaet til den innebygde lerretappen.  

Dette emnet forklarer egenskapene og handlingene som er tilgjengelige på ModelDrivenFormIntegration-kontrollen.

| Egenskap eller handling | Beskrivelse |
|:--------------|:-------------------------|
|**DataSource** | Bør settes til datakilden som er koblet til den overordnede enheten i det vertsmodelldrevne skjemaet. <br />Angis automatisk ved [innebygging av en ny lerretapp](embedded-canvas-app-add-classic-designer.md). |
|**Item** | Skrivebeskyttet egenskap som gir den innebygde lerretappen tilgang til å hente informasjon fra det vertsmodelldrevne skjemaet. <br />Hvis du for eksempel vil hente verdien for et felt med navnet accountnumber og visningsnavn nummer for forretningsforbindelse, kan du bruke ModelDrivenFormIntegration.Item.accountnumber eller ModelDrivenFormIntegration.Item.'nummer'. |
|**OnDataRefresh** | Formelen i denne egenskapen evalueres når det vertsmodelldrevne skjemaet lagrer data. <br />Bruk den til å oppdatere datakilden som er koblet til den overordnede enheten i det vertsmodelldrevne skjemaet, og til å utføre andre handlinger, for eksempel å angi eller oppdatere variabler. <br /> Hvis du for eksempel setter den til formelen nedenfor, oppdateres forretningsforbindelsesdatakilden, og en variabel med navnet CurrentAccountNumber er satt til verdien i Nummer for forretningsforbindelse-feltet for den gjeldende oppføringen. <br /> Refresh(Accounts); Set(CurrentAccountNumber, ModelDrivenFormIntegration.Item.'Account Number') |
|**RefreshForm** | Oppdaterer dataene i det vertsmodelldrevne skjemaet. <br />Se [Utføre forhåndsdefinerte handlinger i vertsskjemaet](embedded-canvas-app-actions.md#refreshformshowprompt) hvis du vil ha mer informasjon. |
|**SaveForm** | Lagrer dataene i det vertsmodelldrevne skjemaet. <br />Se [Utføre forhåndsdefinerte handlinger i vertsskjemaet](embedded-canvas-app-actions.md#saveform) hvis du vil ha mer informasjon.  |
|**NavigateToMainForm** | Tar det vertsmodelldrevne skjemaet til et hovedskjema og viser den angitte oppføringen. <br />Se [Utføre forhåndsdefinerte handlinger i vertsskjemaet](embedded-canvas-app-actions.md#navigatetomainformentityname-mainformname-recordid) hvis du vil ha mer informasjon. |
|**NavigateToView** | Tar det vertsmodelldrevne skjemaet til en visning. <br />Se [Utføre forhåndsdefinerte handlinger i vertsskjemaet](embedded-canvas-app-actions.md#navigatetoviewentityname-viewname) hvis du vil ha mer informasjon.  |
|**OpenQuickCreateForm** | Åpner standard hurtigopprettingsskjema for en enhet.  <br />Se [Utføre forhåndsdefinerte handlinger i vertsskjemaet](embedded-canvas-app-actions.md#openquickcreateformentityname) hvis du vil ha mer informasjon.  |
|**Data** | Skrivebeskyttet egenskap som brukes av rammeverket til å sende enkelte nøkkeldata fra det vertsmodelldrevne skjemaet til den innebygde lerretappen.  <br /> Ikke bruk denne egenskapen. Bruk Item for å få tilgang til oppføringen fra det vertsmodelldrevne skjemaet.  |

## <a name="see-also"></a>Se også
[Bygge inn en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Legge til en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-add-classic-designer.md) <br />
[Redigere en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-edit-classic-designer.md) <br />
[Tilpasse skjermstørrelsen og -retningen for en lerretapp som er innebygd i et modelldrevet skjema](embedded-canvas-app-customize-screen.md) <br />
[Utføre forhåndsdefinerte handlinger på vertsskjemaet fra en innebygd lerretapp](embedded-canvas-app-actions.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md) <br />
[Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon av nyeste](embedded-canvas-app-migrate-from-preview.md) <br />
