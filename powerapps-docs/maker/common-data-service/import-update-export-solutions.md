---
title: 'Importere, oppdatere og eksportere løsninger | MicrosoftDocs'
description: 'Finn ut hvordan du importerer, oppdaterer og eksporterer en løsning i PowerApps'
ms.custom: ''
ms.date: 11/06/2018
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-update-and-export-solutions"></a>Importer, oppdater og eksporter løsninger 

 Du kan importere løsninger manuelt ved hjelp av fremgangsmåten nedenfor. Importer bare løsninger som kommer fra en klarert kilde. Tilpassinger kan omfatte kode som kan sende data til eksterne kilder. Du kan importere løsningen som kalles **Standardløsning** bare til miljøet som du eksporterte den fra, men ikke til et annet miljø.  
  
1.  Velg **Løsninger** fra navigasjonsruten til venstre.  
  
2.  Velg **Importer** på løsningslistemenyen.  

    > [!div class="mx-imgBorder"]  
    > ![Importer løsning](media/solution-import.png "Importer løsning") 
  
3.  I dialogboksen **Importer løsning** i trinnet **Velg løsningspakke** velger du **Velg fil** og blar frem til den komprimerte filen (ZIP eller CAB) som inneholder løsningen du vil importere. 
  
4.  Velg **Neste**.  
  
5.  Vis informasjon om løsningen. Velg **Importer**.  
  
6. Du må kanskje vente litt mens importen fullføres. Vis resultatene, og velg deretter **Lukk**.  
  
 Hvis du har importert eventuelle endringer som krever publisering, må du publisere tilpasninger før de er tilgjengelige. 
  
 Hvis importen ikke er vellykket, vil du se en rapport som viser eventuelle feil eller advarsler som ble registrert. Velg **Last ned loggfil** for å registrere detaljer om hva som forårsaket at importen mislyktes. Den vanligste årsaken til en import mislykkes er at løsningen ikke inneholder enkelte nødvendige komponenter.  
  
 Når du laster ned loggfilen, finner du en XML-fil som du kan åpne ved hjelp av Office Excel, for å vise innholdet.  
  
> [!NOTE]
>  Du kan ikke redigere et aktivt rutingsregelsett. Hvis du importerer en løsning som inneholder en aktiv rutingsregel satt inn i et miljø der regelen allerede finnes med samme ID, vil derfor importen mislykkes. Mer informasjon: [Opprett regler for å rute saker automatisk](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/create-rules-automatically-route-cases)  
  
<a name="BKMK_UpdateSolutions"></a>   

## <a name="update-solutions"></a>Oppdatere løsninger  
 Det finnes tre situasjoner hvor du kanskje ønsker å installere en oppdatering for en eksisterende administrert løsning. Fremgangsmåten ligner på installering av en ny administrert løsning, bortsett fra at du vil få noen andre alternativer. Hvis du oppdaterer en løsning som du har fått fra noen andre, bør du få veiledning fra løsningsutgiveren om hvilke alternativer du bør velge.  
  
1.  Velg **Løsninger** fra navigasjonsruten til venstre.
  
2.  Velg **Importer** på løsningslistemenyen.  
  
3.  I dialogboksen **Importer løsning** i trinnet **Velg løsningspakke** velger du **Velg fil** og blar frem til den komprimerte filen (ZIP eller CAB) som inneholder løsningen du vil oppdatere.

4.  Velg **Neste**.  
  
5.  Vis informasjon om løsningen, og velg deretter **Neste**. Denne siden viser en gul linje som med teksten **Denne løsningspakken inneholder en oppdatering for en løsning som allerede er installert**.  
  
6.  Du har følgende alternativer:  
  
    - **Behold tilpassinger (anbefales)**  
  
         Hvis du velger dette alternativet, beholdes eventuelle ubehandlede tilpassinger som er utført på komponenter. Det vil imidlertid også medføre at noen av oppdateringene som er inkludert i denne løsningen, ikke vil tre i kraft.  
  
    - **Overskrive tilpassinger**  
  
         Hvis du velger dette alternativet, overskrives eventuelle ubehandlede tilpassinger tidligere utført på komponenter som er inkludert i denne løsningen. Alle oppdateringene som er inkludert i løsningen, trer i kraft.  
  
     Velg det aktuelle alternativet, og velg deretter **Neste**.  
  
7.  Du må kanskje vente litt mens importen fullføres. Vis resultatene, og velg deretter **Lukk**.  
  
 Hvis du har importert eventuelle endringer som krever publisering, må du publisere tilpasninger før de er tilgjengelige. 
  
 Det kan hende at løsningsutgivere ber deg om å eksportere eksisterende ubehandlede tilpasninger, oppdatere deres administrerte løsning ved hjelp av alternativet til å overskrive tilpasninger og deretter importere de ubehandlede tilpasningene på nytt. Dette sikrer at endringene som de forventer, tas i bruk samtidig som tilpasningene dine beholdes.  
  
<a name="BKMK_ExportSolutions"></a>   

## <a name="export-solutions"></a>Eksportere løsninger  
 Vi anbefaler at du jevnlig eksporterer dine ubehandlede tilpasninger slik at du har en sikkerhetskopi i tilfelle noe skjer. Du kan ikke eksportere administrerte løsninger. Du kan eksportere løsninger fra PowerApps, eller du kan eksportere med den klassiske opplevelsen. 
 
### <a name="export-from-powerapps"></a>Eksportere fra PowerApps
  
1.  Velg **Løsninger** fra navigasjonsruten til venstre.   
  
2.  Velg løsningen du vil eksportere, i listen, og velg deretter **Eksporter**. 

3.  Velg pakketypen **Som uadministrert** eller **Som administrert**. Dette starter eksporten, som kan ta flere minutter å fullføre. Når du er ferdig, finnes ZIP-eksportfilen i nedlastingsmappen angitt i webleseren.

    > [!div class="mx-imgBorder"]  
    > ![Eksporter løsning](media/solution-export.png "Eksporter løsning") 

### <a name="export-from-the-classic-experience"></a>Eksportere fra den klassiske opplevelsen

1.  Velg **Løsninger** fra venstre navigasjonsrute, og velg deretter **Bytt til klassisk**. 
  
2.  Velg løsningen du vil eksportere, i listen, og velg deretter **Eksporter**. 
  
3.  I trinnet **Publiser tilpassinger** vil du bli minnet om at bare publiserte tilpasninger eksporteres, og du får alternativet **Publiser alle tilpassinger** før du velger **Neste**.  
  
4.  Hvis løsningen inneholder manglende obligatoriske komponenter, vises trinnet **Mangler obligatoriske komponenter**. Du kan se bort fra advarselen bare hvis du skal importere den som en uadministrert løsning tilbake til det opprinnelige miljøet. Hvis ikke følger du instruksjonene i dialogboksen for å avbryte eksporten og legge til de nødvendige komponentene.  
  
5.  I trinnet **Eksporter systeminnstillinger (avansert)** kan du velge bestemte systeminnstillinger som skal tas med i løsningen. Hvis løsningen er avhengig av gruppene av systeminnstillingene, merker du dem og velger **Neste**.  
  
     Se **Angi alternativer for løsningseksport** nedenfor hvis du vil ha informasjon om innstillingene som blir inkludert i hvert alternativ.  
  
6.  I trinnet **Pakketype** må du velge om du vil eksportere løsningen som en **uadministrert** eller **administrert** løsning.  
  
7.  Det neste trinnet gir deg muligheten til å velge en målløsning for en bestemt Dynamics 365 for Customer Engagement-versjon. Dette alternativet brukes vanligvis av uavhengige programvareleverandører som kanskje ønsker å eksportere en løsning som er kompatibel med en tidligere versjon. Med mindre du har tenkt å importere denne løsningen i et miljø som ikke er oppgradert til samme versjon som miljøversjonen du bruker, kan du godta standardvalget.   
  
8.  Velg **Eksporter** for å laste ned løsningsfilen.  
  
 Den eksakte virkemåten for å laste ned filer varierer mellom weblesere.  

<a name="BKMK_SettingsOptionsOnSolutionExport"></a>  
 
## <a name="settings-options-for-solution-export"></a>Angi alternativer for løsningseksport  
 Hvis du eksporterer løsningen fra PowerApps, kan du ignorere denne delen. Tabellen nedenfor viser alternativene som er tilgjengelige, når du eksporterer en løsning fra den klassiske opplevelsen.  
  
|Group|Innstilling|Beskrivelse|  
|-----------|-------------|-----------------|  
|Automatisk nummerering|Kampanjeprefiks|Prefiks som brukes ved nummerering av kampanjer.|  
|Saksprefiks|Prefiks som brukes for alle saker i appen.|  
|Kontraktsprefiks|Prefiks som brukes for alle kontrakter i appen.|  
|Fakturaprefiks|Prefiks som brukes for alle fakturanumre i appen.|  
|Artikkelprefiks|Prefiks som brukes for alle artikler i appen.|  
|Ordreprefiks|Prefiks som brukes for alle ordrer i appen.|  
|Unik strenglengde|Antall tegn som er tilføyd i fakturaen, tilbudet og ordrenumrene.|  
|Kalender|Kalendertype|Kalendertypen for systemet. Angitt som gregoriansk USA-kalender som standard|  
|Kode for datoformat|Informasjon om hvordan datoen vises i Dynamics 365 for Customer Engagement|  
|Datoskilletegn|Tegn som brukes til å skille måneden, dagen og året i datoer i appen.|  
|Maksimal avtalevarighet|Maksimalt antall dager en avtale kan vare.|  
|Vis ukenummer|Informasjon som angir om ukenummer i kalender skal vises i appen.|  
|Kode for klokkeslettformat|Informasjon som angir hvordan klokkeslett skal vises i appen.|  
|Kode for dagen som starter uken|Angitt første ukedag i appen.|  
|Tilpassing|Er programmodusen aktivert|Angir om appen skal lastes i et webleservindu som ikke har adresse-, verktøy- og menyfelt aktivert.|  
|E-postsporing|Tillat sending av uløst e-postadresse|Angir om brukere kan sende e-post til uløste parter (parter må fortsatt ha en e-postadresse).|  
|Ignorer intern e-post|Angir om innkommende e-post som er sendt av appbrukere eller køer, skal spores.|  
|Maksimalt antall sporingsnumre|Maksimalt antall sporingsnumre før resirkulering trer i kraft.|  
|Gjengi sikker ramme for e-post|Flagg til å gjengi innholdet i e-post i webskjemaet i en IFRAME med attributtet security='restricted' angitt. Dette gir tilleggssikkerhet, men kan føre til at bes om legitimasjon.|  
|Sporingsprefiks|Historikkliste for prefikser for sporing av tokener.|  
|Grunnleggende sporingstoken|Basistall som brukes til å formidle egne identifikatorer for sporing av token til brukere som hører til ulike distribusjoner.|  
|Antall sifre i sporingstoken|Antall sifre som brukes til å representere en identifikator for sporing av token.|  
|Generelt|Blokker vedlegg|Forhindre opplasting eller nedlasting av bestemte vedleggstyper som vurderes som farlige.|  
|Kode for valutaformat|Informasjon om hvordan valutasymboler er plassert i appen.|  
|Valutasymbol|Valutasymbol|  
|Visning av fullstendig navn i ordre|Rekkefølgen som navn skal vises i, i appen.|  
|Tilgjengelighet aktivert|Informasjon om IM-tilgjengelighet er aktivert.|  
|Negativt format|Informasjon som angir hvordan negative valutatall vises i appen.|  
|Tallformat|Angir hvordan tall vises i appen.|  
|Priser med desimalpresisjon|Antall desimaler som kan brukes for priser.|  
|Del med tidligere eier ved tilordning|Informasjon som angir om det skal deles med tidligere eier ved tilordning.|  
|Markedsføring|Tillat automatisk oppretting av svar|Angir om automatisk oppretting av svar er tillatt|  
|Tillat automatisk oppheving av abonnement|Angir om automatisk oppheving av abonnement er tillatt.|  
|Tillat automatisk oppheving av godkjenningsabonnement|Angir om det er tillatt å sende godkjennings-e-post for automatisk oppheving av abonnement.|  
|Tillat kjøring av markedsførings-e-post|Angir om det er tillatt å kjøre markedsførings-e-poster.|  
| Outlook-synkronisering|Tillat synkronisering av adressebok|Angir om det er tillatt med synkronisering av adressebok i bakgrunnen i Microsoft Office Outlook.|  
|Tillat frakoblet, planlagt synkronisering|Angir om det er tillatt med frakoblet synkronisering i bakgrunnen i Outlook.|  
|Tillat planlagt synkronisering|Angir om det er tillatt med planlagte synkroniseringer til Outlook.|  
|Hyppighet for sending av avspørring via e-post|Normal avspørringsfrekvens brukt ved sending av e-post i Outlook.|  
|Minste hyppighet for synkronisering av adresse|Normal avspørringsfrekvens som brukes til adresseboksynkronisering i Outlook.|  
|Minste hyppighet for frakoblet synkronisering|Normal avspørringsfrekvens som brukes ved frakoblet synkronisering bakgrunnen i Outlook.|  
|Minste synkroniseringshyppighet|Minste tillatte tid mellom planlagte synkroniseringer i Outlook.|  
|Maksimalt antall sykluser for automatisk merking|Maksimalt antall aggressive avspørringssykluser som kjøres for automatisk merking av e-post når en ny e-post mottas.|  
|Intervall for automatisk merking|Normal avspørringshyppighet som brukes for automatisk merking av e-post i Outlook.|  
|ISV-konfigurasjon|Konfigurasjon av utseende for servicekalender|Du kan definere visuelle stiler for servicekalendere.

Mer informasjon: [Konfigurasjon av utseende for servicekalender](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/service-calendar-appearance-configuration)|

  
## <a name="next-steps"></a>Neste trinn

[Distribuere løsninger og oppdateringer](use-segmented-solutions-patches-simplify-updates.md)
