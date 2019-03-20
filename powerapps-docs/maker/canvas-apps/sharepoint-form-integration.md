---
title: Integrasjon av skjemaer i SharePoint | Microsoft Docs
description: Forstå hvordan tilpassede skjemaer fungerer med SharePoint
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/11/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 919efacd1a1dc5c931d71e07024aa7c8a30168bf
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799253"
---
# <a name="understand-sharepoint-forms-integration"></a>Forstå integrasjon for SharePoint-skjemaer
Du kan nå enkelt [tilpasse alle SharePoint-listeskjemaer](customize-list-form.md) i PowerApps. I denne artikkelen forklarer vi i detalj hvordan disse skjemaene fungerer, og hvordan du kan tilpasse dem enda mer.

Hvis du har tilpasset et skjema for en SharePoint-liste, har du sikkert lagt merke til at det standardgenererte skjemaet fungerer for alle operasjoner, som oppretting, visning eller redigering av elementer. Dette skjer ved hjelp av genererte formler og **SharePointIntegration**-kontrollen.

## <a name="understand-the-default-generated-form"></a>Forstå det standardgenererte skjemaet

Det standardgenererte skjemaet består av følgende kontroller med tilhørende standarder:

* **FormScreen1** – Dette er [skjermen](controls/control-screen.md) som inneholder skjemaet.

* **SharePointForm1** – Dette er [skjemaet](working-with-forms.md) som brukes til å opprette, vise eller redigere listeelementet.

    * **Datakilde** – listen som skjemaet er tilpasset for.

    * **Element** – det valgte elementet fra listen. For å gjøre det enkelt er dette satt som First() element i listen når du jobber i PowerApps Studio.

        **If(IsBlank(SharePointIntegration.Selected) || IsEmpty(SharePointIntegration.Selected),First('*YourListName*'),SharePointIntegration.Selected)**

    * **OnSuccess** – Når elementet er opprettet eller lagret, blir skjemaet nullstilt, og SharePoint skjuler skjemaet.

        **ResetForm(SharePointForm1); RequestHide()**

* **SharePointIntegration** – Kontrollen som kommuniserer brukerhandlinger mellom SharePoint og PowerApps.

    * **Datakilde** – Listen som skjemaet er tilpasset til.

        **'*YourListName*'**

    * **OnNew** – Setter **SharePointForm1** i ny modus.

        **NewForm(SharePointForm1)**

    * **OnView** – Setter **SharePointForm1** i visningsmodus.

        **ViewForm(SharePointForm1)**

    * **OnEdit** – Setter **SharePointForm1** i redigeringsmodus.

        **EditForm(SharePointForm1)**

    * **OnSave** – Sender endringene til **SharePointForm1**. Når skjemaet er sendt inn, blir **SharePointForm1.OnSuccess**-formelen utført.

        **SubmitForm(SharePointForm1)**

    * **OnCancel** – Tilbakestiller endringene til **SharePointForm1**. SharePoint skjuler alltid skjemaet når en bruker klikker eller trykker på **Avbryt** i SharePoint.

        **ResetForm(SharePointForm1)**

Disse standardene sikrer at skjemaet fungerer når det kjører i SharePoint. De endrer skjemamodusen i PowerApps når brukeren samhandler med det i SharePoint, og de sikrer at endringene blir sendt til SharePoint.

## <a name="understand-the-sharepointintegration-control"></a>Hvordan SharePointIntegration-kontrollen fungerer
**SharePointIntegration**-kontrollen kommuniserer brukerhandlinger mellom SharePoint og PowerApps.

![](./media/sharepoint-form-integration/sharepointintegration-object.png)

>[!NOTE]
>Egenskapene for kontrollen for **SharePointIntegration** er bare tilgjengelige når skjemaet kjører i SharePoint, men ikke når skjemaet tilpasses i PowerApps Studio. Disse egenskapene er kanskje ikke tilgjengelige i **OnStart** eller **OnVisible**. 

**SharePointIntegration**-kontrollen har følgende egenskaper:

**Selected** – Det valgte elementet fra SharePoint-listen.

**OnNew** – Hvordan en app responderer når en bruker klikker eller trykker på **Ny**-knappen eller åpner **Opprett element**-skjemaet i SharePoint.

**OnView** – Hvordan en app responderer når en bruker klikker eller trykker på et **element** eller åpner **Elementdetalj**-skjemaet i SharePoint.

**OnEdit** – Hvordan en app responderer når en bruker klikker eller trykker på **Rediger alt**-knappen eller åpner **Rediger element**-skjemaet i SharePoint.

**OnSave** – Hvordan en app responderer når en bruker klikker eller trykker på **Lagre**-knappen i SharePoint.

**OnCancel** – Hvordan en app responderer når en bruker klikker eller trykker på **Avbryt**-knappen i SharePoint.

**SelectedListItemID** – Element-ID for det valgte elementet i en SharePoint-liste.

**Datakilde** – Listen som inneholder oppføringen som skjemaet skal vise, redigere eller opprette. Vær oppmerksom på at hvis du endrer denne egenskapen, kan det være at **Valgt** og **SelectedItemID** slutter å virke.

## <a name="customize-the-default-form"></a>Tilpassing av standardskjemaet
Nå som du har en bedre forståelse av det standardgenererte skjemaet og **SharePointIntegration**-kontrollen, kan du endre formlene for å tilpasse skjemaene enda mer. Her er noe du må huske på når du tilpasser skjemaene:

* Du kan opprette adskilte tilpassede opplevelser for oppretting, visning og redigering av et element ved å sette formlene **OnNew**, **OnView** eller **OnEdit** av **SharePointIntegration**-kontrollen til å angi variabler eller gå til andre skjermer.

* Bruk **OnSave**-formelen for **SharePointIntegration**-kontrollen for å tilpasse hva som skal skje når en bruker klikker eller trykker på **Lagre** i SharePoint. Hvis du har flere skjemaer, må du passe på å bare sende endringene for det skjemaet som brukes i øyeblikket.

  > [!TIP]
  >    Angi forskjellige verdier for en variabel i formlene **OnNew**, **OnView** og **OnEdit**. Du kan bruke denne variabelen i **OnSave**-formelen for å finne ut hvilket skjema som brukes.

* Pass på å inkludere **RequestHide()** i **OnSuccess**-formelen i alle skjemaene dine. Hvis du glemmer dette, kan ikke SharePoint vite når skjemaet skal skjules.

* Du kan ikke kontrollere skjulingen av et skjema når en bruker klikker eller trykker på **Avbryt** i SharePoint, så sørg for at du tilbakestiller skjemaene dine i **OnCancel**-formelen i **SharePointIntegration**-kontrollen.

* Egenskapene for kontrollen for **SharePointIntegration** er kanskje ikke tilgjengelige i **OnStart** eller **OnVisible**, og disse hendelsene utføres bare én gang mens listen lastes inn. Du kan bruke formlene **OnNew**, **OnView** eller **OnEdit** for å kjøre Logic før skjemaet vises til brukeren hver gang. 
