---
title: Bruke segmenterte løsninger og oppdateringer for å forenkle løsningsoppdateringer med PowerApps | MicrosoftDocs
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-segmented-solutions-and-patches-to-export-selected-entity-assets"></a>Bruke segmenterte løsninger og oppdateringer til å eksportere valgte enhetsressurser

Du kan oppnå bedre kontroll over hva du distribuerer i løsninger og løsningsoppdateringer, ved å bruke løsningssegmentering. Med løsningssegmentering kan du eksportere løsninger med utvalgte enhetsaktiva, for eksempel enhetsfelt, skjemaer og visninger, i stedet for hele enheter med alle aktivaene. Hvis du vil opprette segmenterte løsninger og oppdateringer, kan du bruke brukergrensesnittet for løsninger, uten å skrive kode.  
  
 I tillegg til å ha mer kontroll over hva som finnes i en løsning, vil du kunne kontrollere hva som skjer i en oppdatering. Du kan opprette en oppdatering for en overordnet løsning og eksportere den som en mindre oppdatering til den grunnleggende løsningen. Når du kloner en løsning, beregner systemet verdien av alle relaterte oppdateringene i den grunnleggende løsningen og oppretter en ny versjon.  
  
 Når du arbeider med oppdateringer og klonede løsninger, må du huske på følgende:  
  
-   En oppdatering representerer en trinnvis mindre oppdatering for den overordnede løsningen. En oppdatering kan legge til eller oppdatere komponenter og aktiva i den overordnede løsningen når den er installert på målsystemet, men den kan ikke slette alle komponenter eller aktiva fra den overordnede løsningen.  
  
-   En oppdatering kan bare ha én overordnet løsning, men en overordnet løsning kan ha én eller flere oppdateringer.  
  
-   En oppdatering opprettes for uadministrert løsning. Du kan ikke opprette en oppdatering for en administrert løsning.  
  
-   Når du eksporterer en oppdatering til et målsystem, bør du eksportere den som en administrert oppdatering. Ikke bruk uadministrerte oppdateringer i produksjonsmiljøer.  
  
-   Den overordnede løsningen må finnes i målsystemet for å installere en oppdatering.  
  
-   Du kan slette eller oppdatere en oppdatering.  
  
-   Hvis du sletter en overordnet løsning, slettes også alle underordnede oppdateringer. Systemet gir deg en advarsel om at du ikke kan angre sletteoperasjonen. Slettingen utføres i én enkelt transaksjon. Hvis en av oppdateringene eller den overordnede løsningen ikke kan slettes, tilbakestilles hele transaksjonen.  
  
-   Når du har opprettet den første oppdateringen for en overordnet løsning, blir løsningen låst, og du kan ikke gjøre endringer i denne løsningen eller eksportere den. Hvis du sletter alle de underordnede oppdateringene, blir imidlertid den overordnede løsningen låst opp.  
  
-   Når du kloner en grunnleggende løsning, beregner systemet verdien av alle underordnede oppdateringer i den grunnleggende løsningen, som blir en ny versjon. Du kan legge til, redigere eller slette komponenter og gjenstander i den klonede løsningen.  
  
-   En klonet løsning representerer en erstatning for den grunnleggende løsningen når den er installert på systemet som en uadministrert løsning. Du bruker vanligvis en klonet løsning for å levere en større oppdatering til den forrige løsningen.  
  
## <a name="understanding-version-numbers-for-cloned-solutions-and-patches"></a>Forstå versjonsnumre for klonede løsninger og oppdateringer  
 En løsnings versjon har følgende format: overordnet.underordnet.build.revisjon. En oppdatering må ha et høyere build- eller revisjonsnummer enn den overordnede løsningen. Den kan ikke ha en høyere overordnet eller underordnet versjon. For en grunnleggende løsning versjon 3.1.5.7 kan for eksempel en oppdatering være versjon 3.1.5.8 eller 3.1.7.0, men ikke versjon 3.2.0.0. En klonet løsning må ha et versjonsnummer som er større enn eller lik versjonsnummeret for den grunnleggende løsningen. For en grunnleggende løsning versjon 3.1.5.7 kan for eksempel en klonet løsning være versjon 3.2.0.0 eller versjon 3.1.5.7.. I brukergrensesnittet kan du bare angi verdier for overordnet og underordnet versjon for en klonet løsning, og verdiene for build eller revisjon for en oppdatering.  
  
## <a name="create-a-segmented-solution-with-the-entity-assets-you-want"></a>Opprette en segmentert løsning med ønskede enhetsaktiva  
 Hvis du vil opprette en segmentert løsning, kan du starte med å opprette en uadministrert løsning og legge til de eksisterende ressursene. Du kan legge til flere systemenheter eller egendefinerte entiteter, og for hver enhet kan du velge hvilke aktiva du vil ta med i løsningen. Det veiviserlignende oppsettet fører deg gjennom prosessen med å legge til enhetsaktiva trinn for trinn.  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  Velg **Ny**, og opprett en løsning. Skriv inn informasjon i de obligatoriske feltene. Velg **Lagre og lukk**.  
  
3.  Åpne løsningen du nettopp opprettet. Fra rullegardinlistsen **Legg til eksisterende** velger du **Enhet**.  
  
4.  I dialogboksen **Velg løsningskomponenter** velger du én eller flere enheter du vil legge til løsningen. Velg **OK**.  
  
5.  Veiviseren åpnes. Følg veiviseren for å legge til ressurser for hver valgte enhet i løsningen.  
  
6.  Velg **Publiser** for at endringene skal tre i kraft.  
  
 Illustrasjonene nedenfor gir et eksempel på hvordan du oppretter en segmentert løsning ved å velge enhetsaktiva fra enhetene `Account`, `Case` og `Contact`.  
  
 Start ved å velge **Enhet**-komponenten.  

 > [!div class="mx-imgBorder"] 
 > ![Legge til eksisterende ressurser.](media/solution-segmentation-add-existing-resources-admin.png "Legge til eksisterende ressurser.")  
  
 Velg deretter løsningskomponentene.  
  
 ![Velg løsningens komponenter.](media/solution-segmentation-select-components-admin.png "Velg løsningens komponenter.")  
  
 Følg veiviseren. I trinn 1, med start i alfabetisk rekkefølge, velger du aktivaene for den første enheten, `Account`-enheten, som vist her.  
  
 ![Start veiviseren.](media/solution-segmentation-wizard-starts-admin.png "Start veiviseren.")  
  
 Åpne kategorien **Felt**, og velg **Kontonummer**-feltet.  
  
 ![Velg aktiva i Forretningsforbindelse-enheten.](media/solution-segmentation-select-account-assets-admin.png "Velg aktiva i Forretningsforbindelse-enheten.")  
  
 I trinn 2, for **Sak**-enheten, legger du til alle aktiva.  
  
 ![Velg aktiva i Sak-enheten.](media/solution-segmentation-select-case-assets-admin.png "Velg aktiva i Sak-enheten.")  
  
 I trinn 3 kan du legge til **Jubileum**-felt for **Kontakt**-enheten.  
  
 ![Velg aktiva i Kontakt-enheten.](media/solution-segmentation-select-contact-assets-admin.png "Velg aktiva i Kontakt-enheten.")  
  
 Som et resultat inneholder den segmenterte løsningen som er opprettet, tre enheter, `Account`, `Case` og `Contact`. Hver enhet inneholder bare aktivaene som er valgt.  
  
 > [!div class="mx-imgBorder"] 
 > ![Løsning med enheter.](media/solution-segmentation-solution-entities-admin.png "Løsning med enheter.")  
  
## <a name="create-a-solution-patch"></a>Opprett løsningsoppdatering  
 En oppdatering inneholder endringer i den overordnede løsningen, for eksempel ved at komponenter og aktiva legges til eller redigeres. Du trenger ikke å ta med de overordnede komponentene med mindre du har tenkt å redigere dem.  
  
 #### <a name="create-a-patch-for-an-unmanaged-solution"></a>Opprette en oppdatering for en uadministrert løsning  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  I listen velger du en uadministret løsning du vil opprette en oppdatering for. Velg **Klon en oppdatering**. Dialogboksen som åpnes, inneholder den grunnleggende løsningen navn og versjonsnummeret for oppdateringen. Velg **Lagre**.  
  
3.  I rutenettet kan du finne og åpne den nylig opprettede oppdateringen. Akkurat som med den grunnleggende løsningen, følg veiviseren for å legge til komponenter og aktiva du vil bruke.  
  
4.  Velg **Publiser** for at endringene skal tre i kraft.  
  
 Illustrasjonene nedenfor gir et eksempel på hvordan du oppretter en oppdatering for en eksisterende løsning. Start ved å velge **Klon en oppdatering** (i komprimert visning avbildes ikonet **Klon en oppdatering** som to små firkanter, som vist nedenfor).  
  
 > [!div class="mx-imgBorder"] 
 > ![Klon et oppdateringsikon.](media/solution-segmentation-click-patch-icon-admin.png "Klon et oppdateringsikon.")  
  
 I dialogboksen **Klon til oppdatering** ser du at versjonsnummeret for oppdateringen er basert på det overordnede versjonsnummeret for løsningen, men build-nummeret økes med én. Hver etterfølgende oppdatering har et høyere build- eller revisjonsnummer enn den forrige oppdateringen.  
  
 ![Bruk dialogboksen Klon til oppdatering.](media/solution-segmentation-clone-patch-dialog-admin.png "Bruk dialogboksen Klon til oppdatering.")  
  
 Følgende skjermbilde viser den grunnleggende løsningen **SegmentedSolutionExample**, versjon **1.0.1.0** og oppdateringen **SegmentedSolutionExample_Patch**, versjon **1.0.2.0**.  
  
 > [!div class="mx-imgBorder"] 
 > ![Et rutenett med løsninger og oppdateringer.](media/solution-segmentation-solution-patch-grid-admin.png "Et rutenett med løsninger og oppdateringer.")  
  
 I oppdateringen har vi lagt til en ny egendefinert enhet kalt `Book`, og inkludert alle aktiva i `Book`-enheten i oppdateringen.  
  
 ![Legg til egendefinert enhet i oppdateringen.](media/solution-segmentation-add-book-patch-admin.png "Legg til egendefinert enhet i oppdateringen.")  
  
## <a name="clone-a-solution"></a>Klon en løsning  
 Når du kloner en uadministrert løsning, er alle oppdateringer som er relatert til denne løsningen, fremhevet til den nylig opprettede versjonen av den opprinnelige løsningen.  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  Velg en uadministrert løsning du ønsker å klone, fra listen. Velg **Klon løsning**. Dialogboksen som åpnes, inneholder den grunnleggende løsningens navn og det nye versjonsnummeret. Velg **Lagre**.  
  
3.  Velg **Publiser** for at endringene skal tre i kraft.  
  
 Videre i eksemplet ser du dialogboksen **Klon til løsning**, som viser det nye versjonsnummeret for løsningen.  
  
 ![Bruk dialogboksen Klon til løsning.](media/solution-segmentation-clone-solution-dialog-admin.png "Bruk dialogboksen Klon til løsning.")  
  
 Etter kloningen inneholder den nye løsningsversjonen tre opprinnelige enheter (`Account`, `Case` og `Contact`) og den egendefinerte enheten som kalles `Book`, som ble lagt til i oppdateringen. Hver enhet inneholder bare aktivaene som ble lagt til i eksemplet.  
  
 > [!div class="mx-imgBorder"] 
 > ![En klonet løsning med samleoppdatering.](media/solution-segmentation-solution-rolled-up-patch-admin.png "En klonet løsning med samleoppdatering.")  
  
## <a name="next-steps"></a>Neste trinn  
 [Oversikt over løsninger](solutions-overview.md) [Opprett oppdateringer for å forenkle løsningsoppdateringer]

