---
title: Importer, oppdater og eksporter løsninger | MicrosoftDocs
description: Lær hvordan du importerer, oppdaterer og eksporterer en løsning
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
ms.assetid: 56363ea3-ea76-4311-9b7a-b71675e446fb
caps.latest.revision: 57
ms.author: matp
manager: kvivek
ms.openlocfilehash: 89907e80085fe2bfcf3c38972724a0f9b55836c7
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39691707"
---
# <a name="import-update-and-export-solutions"></a>Importer, oppdater og eksporter løsninger 

 Du kan importere løsninger manuelt ved hjelp av trinnene nedenfor. Bare import løsninger som du har fått fra en klarert kilde. Tilpassinger kan inneholde kode som kan sende data til eksterne kilder. Du kan importere standardløsningen til organisasjonen som du eksporterte den fra, men ikke til en annen organisasjon.  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.  
  
2.  Velg **Importer** i løsningsliste-menyen.  
  
3.  **Velg løsningspakke**-trinnet i dialogboksen**Importer løsning**. Bla gjennom til den komprimerte (ZIP- eller CAB)-filen som inneholder løsningen du vil importere. 
  
4.  Velg **Neste**.  
  
5.  Du kan vise informasjon om løsningen før du velger **Importer**.  
  
6.  Du må kanskje vente litt når løsningsimporten blir fullført. Hvis den er vellykket, kan du vise resultatene og velge **Lukk**.  
  
 Hvis du har importert eventuelle endringer som krever publisering, må du publisere tilpassinger før de blir tilgjengelige. 
  
 Hvis importen ikke er vellykket, ser du en rapport som viser eventuelle feil eller advarsler som ble fanget opp. Du kan velge **Last ned loggfil** til å fange opp detaljer om hva som forårsaket at importen er mislykket. Den vanligste årsaken til at en løsningsimport mislykkes, er at løsningen ikke inneholder noen av de nødvendige løsningskomponentene.  
  
 Når du laster ned loggfilen, finner du en XML-fil du kan åpne ved hjelp av Office Excel, og vise innholdet.  
  
> [!NOTE]
>  Du kan ikke redigere et aktivt rutingsregelsett. Hvis du importerer en løsning som inkluderer et aktivt rutingsregelsett til en organisasjon hvor regelen allerede finnes med samme ID, mislykkes løsningsimporten. Mer informasjon: [Opprett regler for å rute saker automatisk](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/create-rules-automatically-route-cases)  
  
<a name="BKMK_UpdateSolutions"></a>   

## <a name="update-solutions"></a>Oppdater løsninger  
 Det finnes tilfeller når du kanskje ønsker å installere en oppdatering til en eksisterende administrert løsning. Fremgangsmåten ligner på å installere en ny administrert løsning, bortsett fra at du får noen andre alternativer. Hvis du oppdaterer en løsning, som du har fått fra andre, får du veiledning fra løsningsutgiveren om hvilke alternativer du bør velge.  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  Velg **Importer** i løsningsliste-menyen.  
  
3.  **Velg løsningspakke**-trinnet i dialogboksen**Importer løsning**. Bla gjennom til den komprimerte (ZIP- eller CAB)-filen som inneholder løsningen du vil oppdatere.  
4.  Velg **Neste**.  
  
5.  Du kan vise informasjon om løsningen før du velger **Neste**. Denne siden viser en gul stolpe som sier **Denne løsningspakken inneholder en oppdatering for en løsning som allerede er installert**.  
  
6.  Du har følgende alternativer:  
  
    - **Behold tilpassinger (anbefales)**  
  
         Hvis du velger dette alternativet, vil du beholde eventuelle uadministrerte tilpassinger utført på komponenter, men det betyr også at noen av oppdateringene i denne løsningen ikke vil tre i kraft.  
  
    - **Overskriv tilpassinger**  
  
         Hvis du velger dette alternativet, blir eventuelle uadministrerte tilpassinger som tidligere ble utført på komponenter i denne løsningen overskrevet. Alle oppdateringer som er inkludert i denne løsningen vil tre i kraft.  
  
     Velg det riktige alternativet, og velg deretter **Neste**.  
  
7.  Du må kanskje vente litt når løsningsimporten blir fullført. Hvis den er vellykket, kan du vise resultatene og velge **Lukk**.  
  
 Hvis du har importert eventuelle endringer som krever publisering, må du publisere tilpassinger før de blir tilgjengelige. 
  
 Løsningsutgivere kan be deg om å eksportere eksisterende uforvaltede tilpassinger, oppdatere administrerte løsninger ved hjelp av alternativet for å overskrive tilpassinger, og deretter importere de uadministrerte tilpassingene på nytt. Dette sikrer at forventede endringer er i bruk, samtidig som du beholder tilpassingene.  
  
<a name="BKMK_ExportSolutions"></a>   

## <a name="export-solutions"></a>Eksporter løsninger  
 Vi anbefaler at du eksporterer de uadministrerte tilpassingene med jevne mellomrom, slik at du har en sikkerhetskopi i tilfelle noe skjer. Du kan ikke eksportere en administrerte løsninger.  
  
1. Gå til **[Innstillinger](../model-driven-apps/advanced-navigation.md#settings)** > **Løsninger**.   
  
2.  Velg løsningen du vil eksportere fra listen som du vil eksportere, og velg **Eksporter**.  
  
3.  I **Publiser tilpassinger**-trinnet får du en påminnelse om at bare publiserte tilpassinger eksporteres, og du vil ha muligheten til å **Publisere alle tilpassinger** før du velger **Neste**.  
  
4.  Hvis løsningen inneholder mangler noen nødvendige komponenter, ser du trinnet **Nødvendige komponenter mangler**. Du kan bare ignorere denne advarselen hvis du har tenkt til å importere dette som en uadministrert løsning tilbake til den opprinnelige organisasjonen. Ellers følger du instruksjonene i dialogboksen for å avbryte eksporten og legge til de nødvendige komponentene.  
  
5.  I trinnet **Eksporter systeminnstillinger (avansert)**, kan du velge enkelte systeminnstillinger som skal inkluderes i løsningen. Hvis løsningen er avhengig av noen av gruppene av systeminnstillinger, merker du dem, og velger **Neste**.  
  
     Se **Alternativer for løsningseksport** nedenfor for mer informasjon om innstillingene som vil bli inkludert i hvert alternativ.  
  
6.  I **Pakketype**-trinnet må du velge om du vil eksportere løsningen som en **Uadministrert** eller **Administrerte** løsning.  
  
7.  Neste trinn lar deg velge en målløsning for en bestemt Dynamics 365-versjon. Dette alternativet brukes vanligvis av ISV-er, som kanskje ønsker å eksportere en løsning som er kompatibel med en tidligere versjon. Med mindre du har tenkt til å importere denne løsningen til en organisasjon som ikke er oppgradert til samme versjon som organisasjonsversjonen du bruker, må du godta standard.   
  
8.  Velg **Eksporter** for å laste ned løsningsfilen.  
  
 Den nøyaktige virkemåten for å laste ned filer varierer mellom nettlesere.  

<a name="BKMK_SettingsOptionsOnSolutionExport"></a>  
 
## <a name="settings-options-for-solution-export"></a>Alternativer for innstillinger for løsningseksport  
 Den følgende tabellen viser de tilgjengelige alternativene når du eksporterer en løsning:  
  
|Gruppe|Innstilling|Beskrivelse|  
|-----------|-------------|-----------------|  
|Automatisk nummerering|Kampanjeprefiks|Prefiks som brukes for kampanjenummerering.|  
|Saksprefiks|Prefiks som brukes for alle tilfeller i hele appen.|  
|Kontraktsprefiks|Prefiks som brukes for alle kontrakter i hele appen.|  
|Fakturaprefiks|Prefiks som brukes for alle fakturaer i hele appen.|  
|Artikkelprefiks|Prefiks som brukes for alle artikler i appen.|  
|Ordreprefiks|Prefiks som brukes for alle ordrer i hele appen.|  
|Minimum strenglengde|Antall tegn som er lagt til faktura, tilbud og ordretall.|  
|Kalender|Kalendertype|Kalendertype for systemet. Angitt som Gregoriansk USA-kalender som standard|  
|Kode for datoformat|Informasjon om hvordan datoen vises i hele Dynamics 365.|  
|Datoskilletegn|Tegnet som brukes til å skille måneden, dagen og året i datoer i hele appen.|  
|Maksimal avtalevarighet|Maksimalt antall dager en avtale kan vare.|  
|Vis ukenummer|Informasjon som angir om du vil vise ukenummeret i kalendervisninger i hele appen.|  
|Kode for klokkeslettformat|Informasjon som angir hvordan tiden vises i hele appen.|  
|Kode for dagen som starter uken|Angitt første dag i uken i hele appen.|  
|Tilpassing|Er programmodusen aktivert|Angir om innlasting av appen i et nettleservindu som ikke har adresse, verktøy og menylinjer er aktivert.|  
|E-postsporing|Tillat sending av uløst e-postadresse|Angir om brukere har tillatelse til å sende e-post til uløste parter (parter må fortsatt ha en e-postadresse).|  
|Ignorer intern e-post|Angir om innkommende e-post som sendes av app-brukere eller køer, skal spores.|  
|Maks sporingsnummer|Maksimum sporingsnummer før resirkulering finner sted.|  
|Gjengi sikker ramme for e-post|Flagg for å gjengi brødteksten fra en e-post i nettskjemaet i en IFRAME med sikkerheten = «begrenset» attributtsett. Dette er ekstra sikkerhet, men kan føre til en forespørsel om legitimasjon.|  
|Sporingsprefiks|Loggliste for prefikser for sporingstoken.|  
|Grunnlag for sporingstoken|Grunntallet som brukes til å angi separate identifikatorer for sporingstoken for brukere som hører til forskjellige distribusjoner.|  
|Sifre i sporingstoken|Antall sifre som brukes til å representere en identifikator for sporing av token.|  
|Generelt|Blokker vedlegg|Forhindre opplasting eller nedlasting av visse vedleggstyper som anses som farlige.|  
|Kode for valutaformat|Informasjon om hvordan valutasymboler er plassert i hele appen.|  
|Valutasymbol|Valutasymbol|  
|Visning av fullstendig navnerekkefølge|Rekkefølgen som navn skal vises i for hele appen.|  
|Tilgjengelighet aktivert|Informasjon om IM-tilgjengelighet er aktivert.|  
|Negativt format|Informasjon som angir hvordan negative tall vises i hele appen.|  
|Tallformat|Angivelse av hvordan tall vises i hele appen.|  
|Priser med desimalpresisjon|Antall desimaler som kan brukes for priser.|  
|Del med forrige eier ved tilordning|Informasjon som angir om du vil dele med forrige eier ved tilordning.|  
|Markedsføring|Tillat automatisk oppretting av svar|Angir om oppretting av automatisk svar er tillatt|  
|Tillat automatisk oppheving av abonnement|Angir om automatisk oppheving av abonnement er tillatt.|  
|Tillat bekreftelse på automatisk oppheving av abonnement|Angir om bekreftelse av automatisk oppheving av abonnement e-post er tillatt å sende.|  
|Tillate kjøring av e-post for markedsføring|Angir om kjøring av markedsføring for e-postmeldinger er tillatt.|  
| Outlook-synkronisering|Tillat synkronisering av adressebok|Angir om adresseboksynkronisering i bakgrunnen i Microsoft Office Outlook er tillatt.|  
|Tillat frakoblet, planlagt synkronisering|Angir om frakoblet synkronisering i bakgrunnen i Outlook er tillatt.|  
|Tillat planlagt synkronisering|Angir om planlagte synkroniseringer til Outlook er tillatt.|  
|Hyppighet for sending av avspørring via e-post|Normal avspørringsfrekvens som brukes til å sende e-post i Outlook.|  
|Minste hyppighet for synkronisering av adresse|Normal avspørringsfrekvens som brukes for adresseboksynkronisering i Outlook.|  
|Minste hyppighet for frakoblet synkronisering|Normal avspørringsfrekvens som brukes for frakoblet synkronisering i bakgrunnen i Outlook.|  
|Minste hyppighet for synkronisering|Minste tillatte tid mellom planlagt [! INCLUDEOutlooksynchronizations.|  
|Maksimalt antall sykluser for automatisk merking|Maksimalt antall aggressive avspørringssykluser utført for automatisk merking for e-post når en ny e-post blir mottatt.|  
|Intervall for automatisk merking|Normal avspørringsfrekvens som brukes til å sende automatisk merking for e-post i Outlook.|  
|ISV-konfigurasjon|Konfigurasjonen for tjenestekalenderutseende|Du kan definere visuelle stiler for tjenestekalendere.

Mer informasjon: [Konfigurasjonen for tjenestekalenderutseende](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/service-calendar-appearance-configuration)|

  
## <a name="next-steps"></a>Neste trinn

[Distribuer løsninger og oppdateringer](use-segmented-solutions-patches-simplify-updates.md)