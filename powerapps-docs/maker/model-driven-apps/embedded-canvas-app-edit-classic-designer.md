---
title: Redigere en innebygd lerretapp i et modelldrevet skjema | MicrosoftDocs
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

# <a name="edit-a-canvas-app-embedded-on-a-model-driven-form"></a>Redigere en innebygd lerretapp i et modelldrevet skjema
Dette emnet forklarer hvordan du redigerer en lerretapp innebygd i et modelldrevet skjema.

## <a name="edit-the-canvas-app-directly"></a>Redigere lerretappen direkte
Du kan redigere en lerretapp som er innebygd i et modelldrevet skjema på samme måte som andre lerretapper. Hvis du vil ha fremgangsmåte for redigering av en lerret-app, se [Redigere en lerretapp](../canvas-apps/edit-app.md)

## <a name="edit-the-canvas-app-via-the-host-model-driven-form"></a>Redigere lerretappen via det vertsmodelldrevne skjemaet
Et annet alternativ er å redigere den innebygde lerretappen via det vertsmodelldrevne skjemaet.

Forestill deg at du vil redigere en lerretapp innebygd i et skjema kalt Hovedskjema for forretningsforbindelser for forretningsforbindelserenheten. Slik gjør du det: 

1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2.  [Rediger skjemaet](create-and-edit-forms.md) kalt Hovedskjema for forretningsforbindelser for forretningsforbindelsesenheten. 
3.  Velg **Bytt til klassisk** på kommandolinjen for å åpne skjemaet i den klassiske skjemautformingen.
4.  I den klassiske skjemautformingen velger du feltet som er tilpasset for å vise den innebygde lerretappen.
5.  I kategorien **Hjem** i **Rediger**-gruppen velger du **Endre egenskaper** med feltet valgt.
6.  I **Feltegenskaper**-dialogboksen velger du **Kontroller**-kategorien.
7.  I **Feltegenskaper**-dialogboksen i listen over kontroller velger du **Lerretapp**.
8.  I delen under Kontroller-listen velger du **Tilpass** for å redigere lerretappen. Da åpnes lerretappen for redigering i PowerApps Studio, i en ny kategori.
       > [!NOTE]
       > Hvis åpning av PowerApps Studio blokkeres på grunn av popup-blokkering i nettleseren, må du må aktivere webområdet web.powerapps.com eller midlertidig deaktivere popup-blokkeringen og deretter velge **Tilpass** på nytt.
9. Når du er ferdig med å gjøre endringer, velger du kategorien **Fil**, og deretter **Lagre**.
10. For å tilby endringene til sluttbrukerne velger du **Publiser** og deretter **Publiser denne versjonen**.

## <a name="see-also"></a>Se også
[Bygge inn en lerretapp i et modelldrevet skjema](embed-canvas-app-in-form.md) <br />
[Legge til en innebygd lerretapp i et modelldrevet skjema](embedded-canvas-app-add-classic-designer.md) <br />
[Tilpasse skjermstørrelsen og -retningen for en lerretapp som er innebygd i et modelldrevet skjema](embedded-canvas-app-customize-screen.md) <br />
[Utføre forhåndsdefinerte handlinger på vertsskjemaet fra en innebygd lerretapp](embedded-canvas-app-actions.md) <br />
[Egenskaper og handlinger for ModelDrivenFormIntegration-kontroll](embedded-canvas-app-properties-actions.md) <br />
[Dele en innebygd lerretapp](share-embedded-canvas-app.md) <br />
[Retningslinjer for arbeid med innebygde lerretapper](embedded-canvas-app-guidelines.md) <br />
[Overføre innebygde lerretapper på modelldrevne skjemaer opprettet ved hjelp av offentlig forhåndsversjon av nyeste](embedded-canvas-app-migrate-from-preview.md) <br />
