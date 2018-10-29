---
title: Bruk segmenterte løsninger og oppdateringer til å forenkle løsningsoppdateringer med PowerApps | MicrosoftDocs
description: Finn ut hvordan du bruker løsningssegmentering til å oppdatere løsningene dine
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 5c05f683-e1bd-4885-be23-b6973128773f
caps.latest.revision: 15
ms.author: matp
manager: kvivek
ms.openlocfilehash: 274e2914d65b6bcb644821c044adb3b0246a75fc
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693699"
---
# <a name="use-segmented-solutions-and-patches-to-export-selected-entity-assets"></a>Bruk segmenterte løsninger og oppdateringer til å eksportere utvalgte enhetsressurser

Bruk løsningssegmentering for å få en bedre kontroll over det du distribuerer i løsninger og løsningsoppdateringer. Med løsningssegmentering kan du eksportere løsninger med utvalgte enhetsressurser, som for eksempel enhetsfelt, skjemaer og visninger, i stedet for hele enheter med alle ressursene. Du kan bruke brukergrensesnittet for løsningen til å opprette de segmenterte løsningene og oppsdateringene, uten å skrive kode.  
  
 I tillegg til å få en bedre kontroll over innholdet i en løsning, vil du også være i stand til å kontrollere innholdet i en oppdatering. Du kan opprette en oppdatering for en overordnet løsning og eksportere den som en mindre oppdatering til den grunnleggende løsningen. Når du kloner en løsning, innlemmer systemet alle de relevante oppdateringene i den grunnleggende løsningen, og oppretter en ny versjon.  
  
 Når du arbeider med oppdateringer og klonede løsninger, må du være oppmerksom på følgende:  
  
-   En oppdatering representerer en trinnvis mindre oppdatering til den overordnede løsningen. En oppdatering kan legge til eller oppdatere komponenter og ressurser i den overordnede løsningen når den er installert på målsystemet, men den kan ikke slette eventuelle komponenter eller ressurser fra den overordnede løsningen.  
  
-   En oppdatering kan bare ha én overordnet løsning, men en overordnet løsning kan ha én eller flere oppdateringer.  
  
-   En oppdatering opprettes for uadministrerte løsninger. Du kan ikke opprette en oppdatering for en administrert løsning.  
  
-   Når du eksporterer en oppdatering til et målsystem, må du eksportere den som en administrert oppdatering. Bruk ikke uadministrerte oppdateringer i produksjonsmiljøer.  
  
-   Den overordnede løsningen må være tilstede i målsystemet for å installere en oppdatering.  
  
-   Du kan slette eller oppdatere en oppdatering.  
  
-   Hvis du sletter en overordnet løsning, slettes også alle underordnede oppdateringer. Systemet gir deg en advarsel om at du ikke kan angre slettingsoperasjonen. Slettingen utføres i én enkelt transaksjon. Hvis én av oppdateringene eller den overordnede løsningen ikke slettes, rulles hele transaksjonen tilbake.  
  
-   Etter at du har opprettet den første oppdateringen for en overordnet løsning, låses løsningen, og du kan ikke foreta noen endringer til denne løsningen eller eksportere den. Hvis du sletter alle de underordnede oppdateringene, låses imidlertid den overordnede løsningen opp.  
  
-   Når du kloner en grunnleggende løsning, innlemmes alle de underordnede oppdateringene i den grunnleggende løsningen, og den oppretter en ny versjon. Du kan legge til, redigere eller slette komponenter og ressurser i den klonede løsningen.  
  
-   En klonet løsning representerer en erstatning av den grunnleggende løsningen når den installeres på målsystemet som en administrert løsning. Du kan som regel bruke en klonet løsning for å sende en viktig oppdatering til den foregående løsningen.  
  
## <a name="understanding-version-numbers-for-cloned-solutions-and-patches"></a>Forstå versjonsnumre for klonede løsninger og oppdateringer  
 En løsningsversjon har følgende format: større.mindre.bygg.revisjon. En oppdatering må ha et høyere bygg- eller revisjonsnummer enn den overordnede løsningen. Den kan ikke ha høyere større eller mindre versjon. For en grunnleggende løsningsversjon 3.1.5.7 kan en oppdatering for eksempel være versjon 3.1.5.8 eller versjon 3.1.7.0, men ikke versjon 3.2.0.0. En klonet løsning må ha et versjonsnummer som er større enn eller lik versjonsnummeret til den grunnleggende løsningen. For en grunnleggende løsningsversjon 3.1.5.7 kan en klonet løsning for eksempel være versjon 3.2.0.0 eller versjon 3.1.5.7. Du kan bare angi de større og mindre versjonsverdiene for en klonet løsning i og bygg- eller revisjonsverdiene for en oppdatering, i brukergrensesnittet.  
  
## <a name="create-a-segmented-solution-with-the-entity-assets-you-want"></a>Opprett en segmentert løsning med ønsket enhetsressurs  
 Hvis du vil opprette en segmentert løsning, begynner du med en uadministrert løsning. Deretter legger du til de eksisterende ressursene. Du kan legge til flere systemenheter eller egendefinerte enheter, og du må velge ressursene du ønsker å inkludere i løsningen for hver enhet. Det veiviseraktige oppsettet veileder deg trinnvis gjennom prosessen med å legge til enhetsressurser.  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  Velg **Ny** og opprett en ny løsning. Skriv inn informasjon i de obligatoriske feltene. Velg **Lagre og lukk**.  
  
3.  Åpne løsningen du nettopp opprettet. Velg **Enhet** i rullegardinlisten **Legg til eksisterende**.  
  
4.  Velg én eller flere enheter du ønsker å legge til i tjenesten, i dialogboksen **Velg løsningskomponenter**. Velg **OK**.  
  
5.  Veiviseren åpnes. Følg veiviseren for å legge til ressurser for hver valgte enhet i løsningen.  
  
6.  Velg **Publiser** for at endringene skal tre i kraft.  
  
 De følgende illustrasjonene gir et eksempel på hvordan du oppretter en segmentert løsning ved å velge enhetsressurser fra `Account`-, `Case`- og `Contact`-enheter.  
  
 Begynn med å velge **Enhet**-komponenten.  
  
 ![Legg til eksisterende ressurser.](media/solution-segmentation-add-existing-resources-admin.png "Legg til eksisterende ressurser.")  
  
 Deretter velger du løsningskomponentene.  
  
 ![Velg løsningskomponenter.](media/solution-segmentation-select-components-admin.png "Velg løsningskomponenter.")  
  
 Følg veiviseren. I Trinn 1, i alfabetisk rekkefølge, velger du ressursene for den første enheten ( `Account`-enheten), som vist her.  
  
 ![Start veiviseren.](media/solution-segmentation-wizard-starts-admin.png "Start veiviseren.")  
  
 Åpne **Felter**-fanen og velg **Kontonummer**-feltet.  
  
 ![Velg kontoenhetsressursene.](media/solution-segmentation-select-account-assets-admin.png "Velg kontoenhetsressursene.")  
  
 I Trinn 2 legger du til alle ressursene for **Sakenheten**.  
  
 ![Velg Sakenhetsressursene.](media/solution-segmentation-select-case-assets-admin.png "Velg Sakenhetsressursene.")  
  
 I Trinn 3 legger du til **Jubileum**-feltet for **Kontaktenheten**.  
  
 ![Velg Kontaktenhetsressursene.](media/solution-segmentation-select-contact-assets-admin.png "Velg Kontaktenhetsressursene.")  
  
 Som et resultat av dette, inneholder løsningen tre enheter: `Account`, `Case` og `Contact`. Hver enhet inneholder bare ressursene som ble valgt.  
  
 ![Løsning med enheter.](media/solution-segmentation-solution-entities-admin.png "Løsning med enheter.")  
  
## <a name="create-a-solution-patch"></a>Opprett en løsningsoppdatering  
 En oppdatering inneholder endringer til den overordnede løsningen, som tillagte eller redigerte komponenter og ressurser. Du må ikke inkludere de komponentene til den overordnede løsningen med mindre du planlegger å redigere dem.  
  
 #### <a name="create-a-patch-for-an-unmanaged-solution"></a>Opprett en oppdatering for en uadministrert løsning  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  Velg en uadministrert løsning du ønsker å opprette en oppdatering for, i listen. Velg **Klon en oppdatering**. Dialogboksen som åpnes inneholder navnet på og oppdateringsversjonsnummeret til den grunnleggende løsningen. Velg **Lagre**.  
  
3.  Finn og åpne den nylig opprettede oppdateringen fra rutenettet. Følg veiviseren for å legge til ønskede komponenter og ressurser,i likhet med den grunnleggende løsningen.  
  
4.  Velg **Publiser** for at endringene skal tre i kraft.  
  
 De følgende illustrasjonene gir et eksempel på hvordan du oppretter en oppdatering for en eksisterende løsning. Begynn med å velge **Klon en oppdatering** (i den komprimerte visningen vises **Klon en oppdatering**-ikonet som to små firkanter, som vist nedenfor).  
  
 ![Klon en oppdatering-ikonet.](media/solution-segmentation-click-patch-icon-admin.png "Klon en oppdatering-ikonet.")  
  
 I dialogboksen **Klon en oppdatering** ser du at versjonsnummeret for oppdateringen er basert på versjonsnummeret til den overordnede løsningen, men byggnummeret økes med én. Hver etterfølgende oppdatering har et høyere bygg- eller revisjonsnummer enn den forrige oppdateringen.  
  
 ![Bruk dialogboksen Klon en oppdatering.](media/solution-segmentation-clone-patch-dialog-admin.png "Bruk dialogboksen Klon en oppdatering.")  
  
 Det følgende skjermbildet viser den grunnleggende løsningen **SegmentedSolutionExample**, versjon **1.0.1.0** og oppdateringen **SegmentedSolutionExample_Patch**, versjon **1.0.2.0**.  
  
 ![Et rutenett med løsninger og oppdateringer.](media/solution-segmentation-solution-patch-grid-admin.png "Et rutenett med løsninger og oppdateringer.")  
  
 I oppdateringen la vi til et ny egendefinert enhet med navn `Book`, og inkluderte alle ressursene til `Book`-enhetene i oppdateringen.  
  
 ![Legg til egendefinert enhet i oppdateringen.](media/solution-segmentation-add-book-patch-admin.png "Legg til egendefinert enhet i oppdateringen.")  
  
## <a name="clone-a-solution"></a>Klon en løsning  
 Når du kloner en uadministrert løsning, innlemmes alle de relaterte oppdateringene til denne løsningen i den nyopprettede versjonen av den opprinnelige løsningen.  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  Velg en uadministrert løsning du ønsker å klone, i listen. Velg **Klon løsning**. Dialogboksen som åpnes inneholder navnet på og det nye versjonsnummeret til den grunnleggende løsningen. Velg **Lagre**.  
  
3.  Velg **Publiser** for at endringene skal tre i kraft.  
  
 Hvis du fortsetter med dette eksemplet, ser du dialogboksen **Klon til løsning** viser det nye versjonsnummeret til løsningen.  
  
 ![Bruk dialogboksen Klon til løsning.](media/solution-segmentation-clone-solution-dialog-admin.png "Bruk dialogboksen Klon til løsning.")  
  
 Etter at kloningen er ferdig, inneholder den nye løsningsversjonen tre opprinnelige enheter (`Account`, `Case` og `Contact`), og den egendefinerte enheten med navn `Book` som ble lagt til i oppdateringen. Hver enhet inneholder bare ressursene som ble lagt til i eksemplet.  
  
 ![En klonet løsning med innlemmet oppdatering.](media/solution-segmentation-solution-rolled-up-patch-admin.png "En klonet løsning med innlemmet oppdatering.")  
  
## <a name="next-steps"></a>Neste trinn  
 [Løsningsoversikt](solutions-overview.md) [oppretter oppdateringer for å forenkle løsningsoppdateringer]

