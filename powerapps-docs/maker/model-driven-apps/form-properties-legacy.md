---
title: Skjemaegenskaper for modelldrevne apper i PowerApps | MicrosoftDocs
description: Forstå de viktigste skjemaegenskapene
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
ms.openlocfilehash: 4aec7fd8a117257d4f21ac2f692643785fd21791
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39693288"
---
# <a name="model-driven-app-form-properties"></a>Skjemaegenskaper for modelldrevne apper 

Du har tilgang til **Skjemaegenskaper** i løsningsutforskeren. Utvid enheten du vil ha under **Komponenter**, utvid **Enheter**, velg enheten du vil ha, og velg deretter **Skjemaer.** Åpne skjemaet av typen **Hoved** i listen over skjemaer. Velg deretter **Skjemaegenskaper** på **Hjem**-fanen.

![skjema-egenskaper](media/form-properties.png)

Tabellen nedenfor viser skjemaegenskapene:  
  
|Fane|Egenskap|Beskrivelse|  
|---------|--------------|-----------------|  
|**Hendelser**|**Skjemabiblioteker**|Administrer hvilke JavaScript-nettressurser som er tilgjengelige i skjemaet og i hvilken rekkefølge de lastes inn.|  
||**Hendelsesbehandling**|Konfigurer hvilke JavaScript-funksjoner fra skjemabibliotekene som skal kjøres for `OnLoad`- og `OnSave`-skjemahendelsene, og i hvilken rekkefølge de blir kjørt.|  
|**Skjerm**|**Skjemanavn**|Angi et navn som gir mening. Dette navnet vises når noen bruker skjemaet. Hvis de kan bruke flere skjemaer som er konfigurert for enheten, brukes dette navnet til å skille mellom tilgjengelige skjemaer.|  
||**Beskrivelse**|Angi en beskrivelse som forklarer hvordan dette skjemaet er forskjellig fra andre hovedskjemaer. Denne beskrivelsen vises bare i listen over skjemaer for en enhet i løsningsutforskeren.|  
||**Skjemaassistent**|Merk av for om du ønsker å aktivere skjemaassistenten eller vise et utvidet skjema som standard.|
||**Sidenavigasjon**|Du kan velge ikke å vise navigasjonselementer.<br /><br /> Dette betyr at primært navn-verdien for posten som for øyeblikket vises, ikke vises i navigasjonsfeltet for å tillate navigering til tilknyttede visninger, i skjemaer for oppdaterte enheter.<br /><br /> Navigasjonsalternativer for å velge tilknyttede visninger på venstre side av skjemaet, vises ikke i skjemaer som bruker den klassiske presentasjonen.|  
||**Bilde**|Når en enhet har et bildefelt og enhetenes **Primærbilde**-alternativ er angitt, aktiverer denne innstillingen visning av bildefeltet i toppteksten for dette skjemaet.<br /><br /> Se [Aktiver eller deaktiverer enhetsalternativer](../common-data-service/edit-entities.md#enable-or-disable-entity-options) for mer informasjon om enhetsalternativer.|  ||**Skjerm**|**Angi en maksimumsbredde (i piksler)** for å begrense bredden på skjemaet. Standardverdien er 1900.|  
||**Skjerm**|Angi maksimumsbredden du vil bruke for skjemaet her, i piksler.|
|**Parametere**|**Parametere**|Hvert skjema kan åpnes med kode ved hjelp av en nettadresse. Nettadressen kan også inneholde data som kan sendes til skjemaet, ved å velge en spørringsstreng som skal legges til nettadressen. Spørringsstrenger ser ut som i dette eksemplet:<br />`?p_firstName=Jim&p_lastName=Daly`<br /><br /> Som et sikkerhetstiltak godtar ikke skjemaer eventuelle ukjente spørrestrengparametere. Bruk denne parameterlisten til å angi parametere som dette skjemaet skal godta, for å støtte kode som sender data til skjemaene ved hjelp av en spørringsstreng.<br /><br /> Navn og type data vil bli kontrollert, og skjemaet åpnes ikke hvis ugyldige spørringsstrengparametere sendes til det.<br /><br />**Merk:** Navnet kan ikke starte med et understrekingstegn (_) eller crm\_. Det må starte med alfanumeriske tegn, etterfulgt av et understrekingstegn (\_). For eksempel parameter_1 eller 1_parameter. Navnet kan ikke inneholde bindestreker (-), kolon (:), semikolon (;), komma (,) eller punktum (.). <br /><br />|  
|**Avhengigheter som ikke er knyttet til hendelser**|**Avhengige felter**|Hver hendelsesbehandling har en lignende **Avhengige felter**-egenskap, slik at alle felter som skriptet krever, kan registreres. Hvis noen prøver å fjerne de avhengige feltene, lar ikke dette seg gjøre.<br /><br /> Enkelte skript er i bruk på skjemaet, men er ikke konfigurert i en hendelsesbehandling. Skript som er startet fra kommandolinjen, har ikke et sted der avhengige felter kan registreres. Denne skjemaegenskapen gir et sted der disse skriptene kan registreres for avhengige felter.|  

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjema og tilknyttede komponenter](use-main-form-and-components.md)