---
title: Utføre handlinger på det vertsmodelldrevne skjemaet fra en innebygd lerretapp | MicrosoftDocs
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
# <a name="perform-predefined-actions-on-the-host-model-driven-form-from-within-an-embedded-canvas-app"></a>Utføre forhåndsdefinerte handlinger på det vertsmodelldrevne skjemaet fra en innebygd lerretapp
Innebygde lerretapper gjør det mulig å utføre forhåndsdefinerte handlinger på det vertsmodelldrevne skjemaet. Med disse handlingene kan utviklere navigere, oppdatere og lagre det vertsmodelldrevne skjemaet. Ved hjelp av handlingene kan en innebygd lerretapp fungere som en mer integrert del av det vertsmodelldrevne skjemaet og den modelldrevne appen.  

Objektet **ModelDrivenFormIntegration** inkluderer nå følgende nye metoder for å gjøre det mulig for utviklere å utføre handlinger på det vertsmodelldrevne skjemaet.  
  
### <a name="navigatetomainformentityname-mainformname-recordid"></a>NavigateToMainForm(entityName, mainFormName, recordId)
Tar det vertsmodelldrevne skjemaet til et hovedskjema og viser den angitte oppføringen.  
* **entityName** – en nødvendig strengparameter som angir den overordnede enheten i hovedskjemaet.  
* **formName** – en nødvendig strengparameter som angir navnet på hovedskjemaet det skal navigeres til.  
* **recordId** – en nødvendig strengparameter som angir IDen for oppføringen som skal vises i hovedskjemaet.  
 
Kall av NavigateToMainForm-metoden kan vise følgende feilmeldinger.
  
| Feilmelding | Veiledning til feilsøking |
|:--------------|:-------------------------|
|**Fant ikke enhet: *[EntityName]*** | Kontroller verdien for *entityName*-parameteren, og kontrollerer at det er et gyldig enhetsnavn og at brukeren har tilgang til den. |
|**Fant ikke skjema: *[FormName]*** | Kontroller verdien for *mainFormName*-parameteren, og kontrollerer at det er et gyldig hovedskjemanavn og at brukeren har tilgang til den. |
|**Det oppstod et problem under innlasting av oppføringen.** | Kontroller verdien for *recordId*-parameteren, og kontrollerer at det er en gyldig oppførings-ID og at brukeren har tilgang til den. |
  
  
### <a name="navigatetoviewentityname-viewname"></a>NavigateToView(entityName, viewName)
Tar det vertsmodelldrevne skjemaet til en visning.  
* **entityName** – en nødvendig strengparameter som angir den overordnede enheten for visningen.  
* **viewName** – en nødvendig strengparameter som angir navnet på hovedskjemaet det skal navigeres til.  
 
Kall av NavigateToView-metoden kan vise følgende feilmeldinger.
  
| Feilmelding | Veiledning til feilsøking |
|:--------------|:-------------------------|
|**Fant ikke enhet: *[EntityName]*** | Kontroller verdien for *entityName*-parameteren, og kontrollerer at det er et gyldig enhetsnavn og at brukeren har tilgang til den. |
|**Fant ikke visning: *[ViewName]*** | Kontroller verdien for *viewName*-parameteren, og kontrollerer at det er et gyldig visningsnavn og at brukeren har tilgang til den. |
  
  
### <a name="openquickcreateformentityname"></a>OpenQuickCreateForm(entityName)  
Åpner standard hurtigopprettingsskjema for en enhet.  
* **entityName** – en nødvendig strengparameter som angir den overordnede enheten for hurtigopprettingsskjemaet.  
 
Kall av OpenQuickCreateForm-metoden kan vise følgende feilmeldinger.
  
| Feilmelding | Veiledning til feilsøking |
|:--------------|:-------------------------|
|**Fant ikke enhet: *[EntityName]*** | Kontroller verdien for *entityName*-parameteren, og kontrollerer at det er et gyldig enhetsnavn og at brukeren har tilgang til den. |
  
  
### <a name="refreshformshowprompt"></a>RefreshForm(showPrompt)  
Oppdaterer dataene i det vertsmodelldrevne skjemaet.  
* **showPrompt** – en nødvendig boolsk parameter som angir om det skal vises en bekreftelsesmelding for brukeren før lagring av ulagrede data i det vertsmodelldrevne skjemaet. Verdiene skal være "sann" eller "usann".
 
Kall av RefreshForm-metoden kan vise følgende feilmeldinger.
  
| Feilmelding | Veiledning til feilsøking |
|:--------------|:-------------------------|
|**Bruk "sann" eller "usann" som parameterverdien.** | Kontroller verdien for *showPrompt*-parameteren, og kontroller at den er "sann" eller "usann". |
  
  
### <a name="saveform"></a>SaveForm()  
Lagrer dataene i det vertsmodelldrevne skjemaet.  


> [!NOTE]
> Hvis du ikke ser IntelliSense for metodene for å utføre forhåndsdefinerte handlinger i innebygde lerretapper som er opprettet før funksjonaliteten gjøres tilgjengelig, kan du lagre, lukke og åpne appen på nytt. 

## <a name="see-also"></a>Se også
[Bygge inn en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Legge til en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-add-classic-designer.md) <br />
[Redigere en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-edit-classic-designer.md) <br />
[Tilpasse skjermstørrelsen og -retningen for en lerretapp som er innebygd i et modelldrevet skjema](embedded-canvas-app-customize-screen.md) <br />
[Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll](embedded-canvas-app-properties-actions.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md) <br />
[Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon av nyeste](embedded-canvas-app-migrate-from-preview.md) <br />
