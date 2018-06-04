---
title: Forstå integrasjon av skjemaer i SharePoint | Microsoft Docs
description: Forstå hvordan tilpassede skjemaer fungerer med SharePoint
services: ''
suite: powerapps
documentationcenter: na
author: sarafankit
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/11/2017
ms.author: ankitsar
ms.openlocfilehash: 75d8f98644d45fb713c0bc7df46439351577a6a2
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997412"
---
# <a name="understand-sharepoint-forms-integration"></a>Forstå integrasjon for SharePoint-skjemaer
Du kan nå enkelt [tilpasse alle SharePoint-listeskjemaer](customize-list-form.md) i PowerApps. I denne artikkelen forklarer vi i detalj hvordan disse skjemaene fungerer og hvordan du kan tilpasse dem ytterligere.

Hvis du har tilpasset et skjema for en SharePoint-liste, har du sikkert lagt merke til at det standardgenererte skjemaet fungerer for alle operasjoner, som å opprette, vise eller redigere et element. Dette blir utført ved hjelp av genererte formler og **SharePointIntegration**-kontrollen.

## <a name="understand-the-default-generated-form"></a>Forstå det standardgenererte skjemaet

Det standardgenererte skjemaet består av følgende kontroller med tilhørende standarder:

* **FormScreen1** – Dette er [skjermen](controls/control-screen.md) som inneholder skjemaet.

* **SharePointForm1** – Dette er [skjemaet](working-with-forms.md) som brukes til å opprette, vise eller redigere listeelementet.

    * **Datakilde** – listen som skjemaet er tilpasset for.

    * **Element** – det valgte elementet fra listen. For å gjøre det lettere for deg er dette satt som Første() element i listen når du jobber i PowerApps Studio.

        **If(IsBlank(SharePointIntegration.Selected) || IsEmpty(SharePointIntegration.Selected),First('*YourListName*'),SharePointIntegration.Selected)**

    * **OnSuccess** – når elementet er opprettet eller lagret, blir skjemaet nullstilt, og SharePoint skjuler det.

        **ResetForm(SharePointForm1); RequestHide()**

* **SharePointIntegration** – kontrollen som kommuniserer brukerhandlinger mellom SharePoint og PowerApps.

    * **Datakilde** – listen som skjemaet er tilpasset for.

        **'*YourListName*'**

    * **OnNew** - Sets **SharePointForm1** i ny modus.

        **NewForm(SharePointForm1)**

    * **OnView** – angir **SharePointForm1** i visningsmodus.

        **ViewForm(SharePointForm1)**

    * **OnEdit** – angir **SharePointForm1** i redigeringsmodus.

        **EditForm(SharePointForm1)**

    * **OnSave** – sender endringene til **SharePointForm1**. Når skjemaet er sendt inn, blir **SharePointForm1.OnSuccess**-formelen utført.

        **SubmitForm(SharePointForm1)**

    * **OnCancel** – tilbakestiller endringene til **SharePointForm1**. SharePoint skjuler alltid skjemaet når en bruker klikker eller trykker på **Avbryt** i SharePoint.

        **SubmitForm(SharePointForm1)**

Disse standardene sikrer at skjemaet fungerer når det kjører i SharePoint. De endrer skjemamodusen i PowerApps når brukeren samhandler med det i SharePoint, og de sikrer at endringene blir sendt til SharePoint.

## <a name="understand-the-sharepointintegration-control"></a>Hvordan SharePointIntegration-kontrollen fungerer
**SharePointIntegration**-kontrollen kommuniserer brukerhandlinger mellom SharePoint og PowerApps.

![](./media/sharepoint-form-integration/sharepointintegration-object.png)

>[!NOTE]
>Egenskapene for **SharePointIntegration**-kontrollen er bare tilgjengelige når skjemaet kjører i SharePoint, og de er utilgjengelige når skjemaet tilpasses i PowerApps Studio.

**SharePointIntegration**-kontrollen har følgende egenskaper:

**Selected** – Det valgte elementet fra SharePoint-listen.

**OnNew** – hvordan en app responderer når en bruker klikker eller trykker på **Ny**-knappen eller åpner **Opprett element**-skjemaet i SharePoint.

**OnView** – hvordan en app responderer når en bruker klikker eller trykker på et **element**, eller åpner **Elementdetalj**-skjemaet i SharePoint.

**OnEdit** – hvordan en app responderer når en bruker klikker eller trykker på **Rediger alt**-knappen eller åpner **Rediger element**-skjemaet i SharePoint.

**OnSave** – hvordan en app responderer når en bruker klikker eller trykker på **Lagre**-knappen i SharePoint.

**OnCancel** – hvordan en app responderer når en bruker klikker eller trykker på **Avbryt**-knappen i SharePoint.

**SelectedListItemID** – element-ID for det valgte elementet i en SharePoint-liste.

**Datakilde** – listen som inneholder oppføringen som skjemaet vil vise, redigere eller opprette. Vær oppmerksom på at hvis du endrer denne egenskapen, kan det være at **Valgt** og **SelectedItemID** slutter å virke.

## <a name="customize-the-default-form"></a>Tilpassing av standardskjemaet
Nå som du har en bedre forståelse av det standardgenererte skjemaet og **SharePointIntegration**-kontrollen, kan du endre formlene for å tilpasse skjemaene enda mer. Her er noe du må huske på når du tilpasser skjemaene:

* Du kan opprette separate tilpassede opplevelser for oppretting, visning og redigering av et element ved å angi **OnNew**-, **OnView**- eller **OnEdit**-formlene av **SharePointIntegration**-kontrollen til å angi variabler eller navigere til andre skjermer.

* Bruk **OnSave**-formelen for **SharePointIntegration**-kontrollen for å tilpasse hva som skal skje når en bruker klikker eller trykker på **Lagre** i SharePoint. Hvis du har flere skjemaer, må du passe på å bare sende endringene for det skjemaet som brukes i øyeblikket.

    >[!TIP]
     Angi forskjellige verdier for en variabel i **OnNew**-, **OnView**- og **OnEdit**-formlene. Du kan bruke denne variabelen i **OnSave**-formelen for å bestemme hvilket skjema som er i bruk.

* Pass på å inkludere **RequestHide()** i **OnSuccess**-formlene i alle skjemaene dine. Hvis du glemmer dette, kan ikke SharePoint vite når skjemaet skal skjules.

* Du kan ikke kontrollere skjulingen av et skjema når en bruker klikker eller trykker på **Avbryt** i SharePoint, så sørg for at du tilbakestiller skjemaene dine i **OnCancel**-formelen i **SharePointIntegration**-kontrollen.
