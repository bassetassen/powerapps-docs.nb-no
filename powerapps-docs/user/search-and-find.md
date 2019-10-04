---
title: Alternativer for Seach og søk i Common Data Service | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/02/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c7192b98d3f97a4aba57f58c52b02245cb71b155
ms.sourcegitcommit: 7c46e7ce889e2f1c5352ed2e705b0bb8968f2a89
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/04/2019
ms.locfileid: "71950891"
---
# <a name="compare-search-and-find-options-in-common-data-service"></a>Sammenlign alternativer for søk og søk i Common Data Service

Det finnes fire måter å finne data på i Common Data Service:

-   Relevanssøk  
  
-   Full tekst hurtig søk (enkelt enhet eller flere enheter)  
  
-   Hurtig søk (enkelt enhet eller flere enheter)  

-   Avansert søk

> [!NOTE]
> Hurtig Søk etter flere enheter kalles også kategorisert søk. 
  
Tabellen nedenfor gir en kort sammenligning av de fire tilgjengelige alternativene.

|Fungere|[Relevanss søk](search-records.md#relevance-search)|[Full tekst hurtig søk](search-records.md#start-a-search)|[Hurtig søk](search-records.md#start-a-search)|[Avansert søk](create-edit-or-save-advanced-find-search.md)|  
|-------------------|----------------------|---------------------------|----------------|-------------------|  
|Aktivert som standard?|nei. En administrator må aktivere den manuelt.|nei. En administrator må aktivere den manuelt.|ja|ja|  
|Søke omfang med én enhet|Ikke tilgjengelig i enhets rute nett. Du kan filtrere søke resultatene etter en enhet på resultats IDen.|Tilgjengelig i enhets rute nett.|Tilgjengelig i enhets rute nett.|Tilgjengelig i enhets rute nett.|  
|Søke omfang med flere enheter|Det finnes ingen maksimums grense for antallet enheter du kan søke i. **Merk:**  Selv om det ikke er noen maksimums grense for antallet enheter du kan søke i, viser oppførings type filteret data for bare 10 enheter.|Søker opptil 10 enheter, gruppert etter en enhet.|Søker opptil 10 enheter, gruppert etter en enhet.|Søk med flere enheter er ikke tilgjengelig.|  
|Søke virke måte|Finner treff for alle ord i søke ordet i hvilket som helst felt i enheten.|Finner treff for alle ord i søke ordet i ett felt i en enhet. ordene kan imidlertid samsvare i hvilken som helst rekkefølge i feltet.|Finner treff som i en SQL-spørring med like-setningsdeler. Du må bruke Joker tegn i søke ordet til å søke i en streng. Alle treff må være et nøyaktig treff for søke ordet.|Spørrings verktøy der du kan definere søke vilkår for den valgte oppførings typen. Kan også brukes til å klargjøre data for eksport til Office Excel, slik at du analyserer, oppsummerer eller samler inn data eller oppretter pivottabeller for å vise dataene fra forskjellige perspektiver.|  
|Søkbare felt|Tekst felt som enkelt linje med tekst, flere linjer med tekst, oppslag og alternativ sett. Støtter ikke søk i felt med numerisk datatype eller dato data typen.|Alle søkbare felt.|Alle søkbare felt.|Alle søkbare felt.|  
|Søke resultater|Returnerer søke resultatene etter relevansen, i én liste.|For én enhet returneres søke resultatene i et enhets rute nett. For flere enheter returnerer søke resultatene gruppert etter kategorier, for eksempel kontoer, kontakter eller kundeemner.|For én enhet returneres søke resultatene i et enhets rute nett. For flere enheter returnerer søke resultatene gruppert etter kategorier, for eksempel kontoer, kontakter eller kundeemner.|Returnerer søke resultater for den valgte oppførings typen med Kol onnene du har angitt, i sorterings rekkefølgen du har konfigurert.|
|Joker tegn (*)|Etterfølgende Joker tegn støttes for fullføring av ord.|Støtte for innledende Joker tegn. Etterfølgende Joker tegn lagt til som standard.|Støtte for innledende Joker tegn. Etterfølgende Joker tegn lagt til som standard.|Støttes ikke.|  
