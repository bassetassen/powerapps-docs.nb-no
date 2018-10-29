---
title: Bruk nettressurser | Microsoft Docs
description: Lær hvordan utviklere bruker nettressurser i modelldrevne apper.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 88e51e4547732bed2d3e7ef3290bc8d933afded3
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849915"
---
# <a name="use-web-resources"></a>Bruke ressurser på nettet

Det finnes en virtuell mappe som heter `webresources` i hver forekomst av Common Data Service for apper, der du kan sende en forespørsel om HTML, JS, CSS, bilde og andre filer ved navn, og få tilgang til dem i nettleseren. Du kan laste opp disse filene ved bruk av programmet eller legge dem til som [WebResource Entity](../common-data-service/reference/entities/webresource.md)-poster programmatisk. [XrmToolBox WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/) er et fellesskapsverktøy som gjør det mulig å arbeide med disse postene.

Disse postene kan henvise til hver andre ved bruk av relative banenavn i innholdet. Denne muligheten til å laste opp filer og forespørre dem ved navn, gir deg alle byggesteinene du trenger for å opprette nettprogrammer ved bruk av filer som behandles i den godkjente økten i nettleseren. Ved bruk av kode bare på klientsiden med AJAX-teknikker, kan du opprette rike programmer som kan kjøres i et nettleservindu, eller i en iFrame i et skjema eller instrumentbord. 

Som regel bruker du JavaScript-nettressurser til å legge til funksjoner for hendelsesbehandling i skjemaer og kommandoer.

Mer informasjon:
- [Klientskripting med modelldrevne apper](client-scripting.md)
- [Dynamics 365 Customer Engagement – Veileding for utviklere: Nettressurser](/dynamics365/customer-engagement/developer/web-resources)
