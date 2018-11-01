---
title: Egenskaper for skjemaer i modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå egenskapene for hovedskjema
Keywords: Main form properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 4ed30bb7-dca1-4de8-80f3-842152ea921a
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="model-driven-app-form-properties"></a>Egenskaper for skjemaer i modelldrevne apper 

Du kan få tilgang til **Skjemaegenskaper** i løsningsutforskeren. Vis **Enheter** under **Komponenter**, utvid deretter ønsket enhet, og klikk deretter **Skjemaer**. I listen over skjemaer åpner du skjemaet av typen **Hoved**. I kategorien **Hjem** velger du **Skjemaegenskaper**.

![skjemaegenskaper](media/form-properties.png)

Tabellen nedenfor viser skjemaegenskapene:  
  
|Kategori|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Hendelser**|**Skjemabiblioteker**|Behandle hvilke JavaScript-webressurser som er tilgjengelige i skjemaet og rekkefølgen for innlasting.|  
||**Hendelsesbehandlinger**|Konfigurer hvilke JavaScript-funksjoner fra skjemabiblioteker som kjøres for skjemahendelsene `OnLoad` og `OnSave` og rekkefølgen for kjøring.|  
|**Vis**|**Skjemanavn**|Skriv inn et navn som gir mening for brukere. Dette navnet vises for brukere når de bruker skjemaet. Hvis de kan bruke flere skjemaer som er konfigurert for enheten, bruker de dette navnet til å skille mellom tilgjengelige skjemaer.|  
||**Beskrivelse**|Skriv inn en beskrivelse som forklarer hvordan dette skjemaet er forskjellig fra andre hovedskjemaer. Denne beskrivelsen vises bare i listen over skjemaer for en enhet i løsningsutforskeren.|  
||**Skjemahjelper**|I avmerkingsboksen velger du om du vil aktivere skjemahjelperen eller vise et utvidet skjema som standard.|
||**Sidenavigasjon**|Du kan velge ikke å vise navigasjonselementer.<br /><br /> I skjemaer for oppdaterte enheter betyr dette at hovednavnverdien for oppføringen som vises, ikke vil vises i navigasjonsfeltet for å tillate navigasjon til tilknyttede visninger.<br /><br /> Når du bruker den klassiske presentasjonen i skjemaer, vises ikke navigasjonsalternativene for å velge tilknyttede visninger på venstre side av skjemaet.|  
||**Bilde**|Når en enhet har et bildefelt og alternativet **Hovedbilde** for enheten er angitt, vil denne innstillingen aktivere visning av bildefeltet i toppteksten i skjemaet.<br /><br /> Se [Aktivere eller deaktivere enhetsalternativer](../common-data-service/edit-entities.md#enable-or-disable-entity-options) hvis du vil ha mer informasjon om alternativene for enheten.|  ||**Vis**|**Angi en maks. bredde (i piksler)** for å begrense bredden på skjemaet. Standardverdien er 1 900.|  
||**Vis**|Her kan du angi ønsket maksimal bredde for skjemaet i piksler.|
|**Parametere**|**Parametere**|Hvert skjema kan åpnes med kode ved hjelp av en URL-adresse. URL-adressen kan også inneholde data som kan sendes til skjemaet ved å bruke en spørrestreng som legges til URL-adressen. Spørrestrenger ser ut som i dette eksemplet:<br />`?p_firstName=Jim&p_lastName=Daly`<br /><br /> Som et sikkerhetstiltak godtar ikke skjemaer ukjente spørringsstrengparametere. Bruk denne parameterlisten til å angi parametere som dette skjemaet skal godta for å støtte kode som vil sende data til skjemaene ved hjelp av en spørrestreng.<br /><br /> Navnet og datatypen vil bli kontrollert, og skjemaet åpnes ikke hvis ugyldige parametere for spørrestrenger sendes til det.<br /><br />**Merk:** Navnet kan ikke starte med understrek (_) eller crm\_. Det må starte med alfanumeriske tegn som etterfølges av en understrek (\_). For eksempel parameter_1 eller 1_parameter. Navnet kan ikke inneholde bindestreker (-), kolon (:), semikolon (;), komma (,) eller punktum (.). <br /><br />|  
|**Avhengigheter som ikke er knyttet til hendelser**|**Avhengige felt**|Hver hendelsesbehandling har en **Avhengige felt**-egenskap, slik at alle felt som er nødvendige i skriptet kan registreres. Det er ikke mulig å fjerne de avhengige feltene.<br /><br /> Enkelte skript behandler skjemaet, men er ikke konfigurert i en hendelsesbehandling. Skript som startes fra kommandolinjen har ingen plassering for registrering av avhengige felt. Denne skjemaegenskapen er et sted for avhengige felt der disse skriptene kan registreres.|  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
