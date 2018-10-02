---
title: Endre løsningsutgiverprefikset | MicrosoftDocs
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: ece684h8-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="change-the-solution-publisher-prefix"></a>Endre løsningsutgiverprefikset

Alle tilpassinger du gjør, er en del av en løsning. Hver løsning har en utgiver. Som standard vil løsningen du vil arbeide med i PowerApps, være **standardløsningen for Common Data Service** som er knyttet til **standardutgiveren for CDS**.

Standard tilpassingsprefiks tilordnes vilkårlig for denne utgiveren, det kan for eksempel være `cr8a3`. Dette betyr at navnet på alle nye metadataelementer som er opprettet for din organisasjon, får dette foran navnene som brukes til å unikt identifisere elementene. Hvis du oppretter en ny enhet med navnet **Dyr**, vil det unike navnet som brukes av CDS for Apps, være `cr8a3_animal`. Det samme gjelder for nye felt (attributter), relasjoner eller alternativsettalternativer.

Med mindre du vil distribuerer løsningen slik at den installeres sammen med metadataelementer som ble opprettet for en annen løsningsutgiver, er det virkelig ikke viktig hva tilpassingsprefikset er. Det er ikke synlig for de fleste brukere som bruker appene. Men det vises for utviklere og andre tekniske personer som utfører oppgaver som å bygge rapporter. Det gjør det enkelt å finne ut hvilken løsning som er lagt elementet.

Derfor liker mange personer å endre prefikset for løsningsutgiver slik at det gir mer mening, spesielt ved visning av metadataelementer som inkluderer de som er importert fra andre løsninger. 

> [!NOTE]
> Hvis du endrer prefikset for løsningsutgiver, bør du gjøre det før du oppretter nye metadataelementer. Du kan ikke endre navnet på metadataelementer.
> Når du endrer verdien for tilpassingsprefiks, må du passe på at du flytter til neste felt ved hjelp av tabulatortasten. **Prefiks for alternativverdi** vil automatisk generere et tall basert på tilpassingsprefikset. Dette nummeret brukes når du legger til alternativer i alternativsett og angir en indikator for hvilken løsning som ble brukt til å legge til alternativet. 

## <a name="change-the-solution-publisher-prefix-for-the-cds-default-publisher"></a>Slik endrer du løsningsutgiverprefikset for standardutgiveren for CDS  

 1. I PowerApps-portalen velger du **Modelldrevet** nederst til venstre.
 2. Klikk på **Avansert** i den venstre navigasjonen for å åpne **standardløsningen for Common Data Services**.
 3. I løsningsutforskeren velger du **Informasjon**-området i den venstre navigasjonen.
 4. Klikk på **Utgiver**-koblingen for å åpne **Standardutgiver for CDS**-skjemaet.
 5. Rediger **Prefiks**-feltverdien til tilpassingsprefikset du ønsker.
 6. Klikk **Lagre og lukk**.
  
## <a name="change-the-solution-publisher-prefix-for-any-publisher"></a>Endre løsningsutgiverprefikset for en utgiver

Personer som distribuerer løsningene, arbeider vanligvis i en løsning som de oppretter i stedet for **standardløsningen for Common Data Services**. Tilpassingsprefikset angis vanligvis når de oppretter løsningen. Du kan endre tilpassingsprefikset for en annen uadministrert løsning som du arbeider med, ved å følge disse trinnene: 

 1. I PowerApps-portalen velger du **Modelldrevet** nederst til venstre.
 2. Klikk på **Avansert** i den venstre navigasjonen for å åpne **standardløsningen for Common Data Services**.
 3. Rediger URL-adressen til siden for å fjerne alt etter `dynamics.com`, og last siden på nytt.
 4. Naviger til **Innstillinger** > **Tilpassing** > **Tilpassinger**. 
 5. Klikk på **Utgivere**. Nå kan du se en liste over utgivere som er tilgjengelige.
 6. Klikk på utgiveren som du vil redigere, for å åpne utgiverskjemaet.
 7. Rediger **Prefiks**-feltverdien til tilpassingsprefikset du ønsker.
 6. Klikk **Lagre og lukk**.
  
