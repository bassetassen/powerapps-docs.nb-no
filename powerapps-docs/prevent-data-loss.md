---
title: Policyer for hindring av datatap (DLP) | Microsoft Docs
description: Innføring i policyer for hindring av datatap for Microsoft PowerApps.
services: ''
suite: powerapps
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/28/2016
ms.author: deonhe
ms.openlocfilehash: a9f6bf12672c425a30d05a8072aafd34945eb795
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/23/2018
ms.locfileid: "30986497"
---
# <a name="data-loss-prevention-dlp-policies"></a>Policyer for hindring av datatap

Organisasjonens data er kritiske for bedriftens suksess. Dataene skal være lett tilgjengelige ved beslutningstakinger, men de skal være beskyttet slik at de ikke er delt med målgrupper som ikke burde ha tilgang. Hvis du vil beskytte disse dataene, gir Microsoft PowerApps (PowerApps) deg muligheten til å opprette og fremtvinge policyer som angir hvilke forbrukertjenester/-koblinger spesifikke forretningsdata kan deles med. Disse policyene som angir hvordan data kan deles, er referert til som policyer for hindring av datatap (DLP).  

## <a name="why-create-a-dlp-policy"></a>Hvorfor opprette en DLP-policy?
Du oppretter en DLP-policy for å tydeliggjøre hvilke forbrukertjenester forretningsdata kan deles med. En organisasjon som bruker PowerApps ønsker for eksempel ikke at forretningsdataene deres som er lagret i SharePoint skal publiseres automatisk til Twitter-feeden. Dette kan du forhindre ved å opprette en DLP-policy som blokkerer SharePoint-data fra å brukes som kilden for tweets.

Fordelene med en DLP-policy:
* Sikrer at dataene administreres på en ensartet måte i hele organisasjonen  
* Forhindrer at viktige forretningsdata feilaktig publiseres til tjenester som sosiale medier.   

## <a name="managing-dlp-policies"></a>Å administrere DLP-policyer
### <a name="prerequisites"></a>Forutsetninger
Hvis du ønsker å opprette, redigere eller slette DLP-policyer, er følgende elementer obligatorisk:

* Enten miljøadministrator- eller leieradministratortillatelser. Du kan finne ut mer om tillatelser i [emnet om miljøer](environments-administration.md)

### <a name="create-a-dlp-policy"></a>Å opprette en DLP-policy
Hvis du ønsker å opprette en DLP-policy, må du ha tillatelse til minst ett miljø.  

Følg disse trinnene for å opprette en DLP-policy som forhindrer data som er lagret i SharePoint-databasene fra å publiseres på Twitter:  

1. Velg **Ny policy**-koblingen fra Datapolicyer-fanen:  
   ![Å logge seg på](./media/prevent-data-loss/create-policy-1.png)    
2. Skriv inn navnet for DLP-policyen som *Sikker datatilgang for Contoso* i etiketten **Navn på datapolicy** øverst på siden som åpnes:   
   ![Å logge seg på](./media/prevent-data-loss/create-policy-2.png)  
3. Velg [miljøet](environments-administration.md) på **Gjelder for**-fanen.  
   ![Å logge seg på](./media/prevent-data-loss/create-policy-3.png)  
4. Velg **Datagrupper**-fanen:  
   ![Å logge seg på](./media/prevent-data-loss/create-policy-4.png)  
5. Velg **+ Legg til**-koblingen fra **Bare forretningsdata**-gruppeboksen:    
   ![Å logge seg på](./media/prevent-data-loss/create-policy-5.png)  
6. Velg **SharePoint**- og **Salesforce**-tjenesten fra **Legg til tjenester**-siden:  
   ![Å logge seg på](./media/prevent-data-loss/create-policy-6.png)  
7. Velg **Legg til tjenester**-knappen for å legge til tjenestene du valgte i listen over tjenester som har tillatelse til å dele forretningsdata:    
   ![Å logge seg på](./media/prevent-data-loss/create-policy-7.png)  
8. Velg **Lagre policy**:  
   ![Å logge seg på](./media/prevent-data-loss/create-policy-8.png)  
9. Etter en liten stund vises den nye DLP-policyen i listen over policyer for hindring av datatap:  
   ![Logg på](./media/prevent-data-loss/create-policy-9.png)  
10. (**valgfritt**) Send en e-post eller annen kommunikasjon til teamet, og varsle dem om at en ny DLP-policy er tilgjengelig.

Gratulerer, du har nå opprettet en DLP-policy som lar appen dele data mellom SharePoint og Salesforce, og som blokkerer deling av data med andre tjenester.  

### <a name="find-a-dlp-policy"></a>Å finne en DLP-policy
#### <a name="admins"></a>Administratorer
Administratorer kan bruke søkefunksjonen fra administrasjonssenteret for å finne bestemte DLP-policyer.  

> [!NOTE]
> Administratorer skal publisere alle DLP-policyer slik at brukerne i organisasjonen er klar over policyene, før de oppretter PowerApps.

#### <a name="makers"></a>Skapere
Hvis du ikke har administratortillatelser, og ønsker å finne ut mer om DLP-policyer i organisasjonen, kontakter du administratoren din. Du får også mer informasjon fra [emnet om skapermiljøer](environments-overview.md)  

> [!NOTE]
> Bare administratorer kan redigere eller slette DLP-policyer.  

### <a name="edit-a-dlp-policy"></a>Å redigere en DLP-policy
1. Start administrasjonssenteret ved å gå til https://admin.powerapps.com.   
2. Velg **Datapolicyer**-koblingen på venstre side i administrasjonssenteret som åpnes.  
   ![Å logge seg på](./media/prevent-data-loss/2.png)  
3. Søk i listen etter eksisterende DLP-policyer og velg redigeringskoblingen ved siden av policyen du har tenkt å redigere:  
   ![Logg på](./media/prevent-data-loss/3.png)  
4. Foreta ønskede endringer. Du kan for eksempel endre miljøet eller tjenestene i datagrupper.  
5. Velg **Lagre policy** for å lagre endringene:  
   ![Å logge seg på](./media/prevent-data-loss/create-policy-8.png)  

Policyen er nå oppdatert. Du kan bekrefte at endringene har blitt utført ved å finne policyen i listen over policyer for hindring av datatap, og gå gjennom egenskapene.   

### <a name="delete-a-dlp-policy"></a>Å slette en DLP-policy
1. Start administrasjonssenteret ved å gå til https://admin.powerapps.com    
2. Velg **Datapolicyer**-koblingen på venstre side i administrasjonssenteret som åpnes.  
   ![Å logge seg på](./media/prevent-data-loss/2.png)  
3. Søk i listen etter eksisterende DLP-policyer og velg slettekoblingen ved siden av policyen du har tenkt å slette:  
   ![Logg på](./media/prevent-data-loss/3-delete.png)  
4. Bekreft at du virkelig ønsker å slette policyen ved å velge **Slett**-knappen:  
   ![Å logge seg på](./media/prevent-data-loss/4.png)  

Policyen er nå slettet. Du kan bekrefte at policyen ikke lenger er oppført i listen over policyer for hindring av datatap ved å velge **Data Policies**-koblingen til venstre, og gå gjennom listen over policyer.   

### <a name="dlp-policy-permissions"></a>Tillatelser for DLP-policy
Bare leieren og miljøadministratoren kan opprette og endre DLP-policyer. Du kan finne ut mer om tillatelser i [emnet om miljøer](environments-administration.md).  

## <a name="next-steps"></a>Neste trinn
* [Finn ut mer om miljøer](environments-administration.md)  
* [Finn ut mer om Microsoft PowerApps](getting-started.md)  
* [Finn ut mer om administrasjonssenteret](introduction-to-the-admin-center.md)  

