---
title: Konfigurer hendelsesbehandlinger for den modelldrevne appen Hovedskjemaer i PowerApps |MicrosoftDocs
description: Forstå hvordan du konfigurerer hendelsesbehandlinger i Dynamics 365 for kundeengasjement
Keywords: Main form; Configure event handlers; Dynamics 365
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
ms.assetid: dc0ebb3f-0c00-413a-968f-9cfd107055c0
ms.openlocfilehash: e05e9d840a2b3ad7d8d5c74e8e3b670504f739b0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39694832"
---
# <a name="configure-model-driven-app-form-event-handlers"></a>Konfigurer skjemahendelsesbehandlinger for modelldrevet app

 Skjemahendelsesbehandlinger for PowerApps-skjemaer kan konfigureres for de følgende områdene i et skjema:  
  
|Element|Arrangement|Beskrivelse|  
|-------------|-----------|-----------------|  
|Skjema|`OnLoad`|Forekommer når skjemaet lastes inn.|  
||`OnSave`|Forekommer når dataene er lagret.|  
|Fane|`TabStateChange`|Forekommer når fanen er vist eller skjult.|  
|Felt|`OnChange`|Forekommer når data i feltet endres og kontrollen mister fokus.|  
|IFRAME|`OnReadyStateComplete`|Forekommer når innholdet i en IFRAME lastes inn.|  
  
 En hendelsesbehandling består av en referanse til en JavaScript-webressurs og en funksjon som er definert i denne webressursen, som skal utføres når hendelsen inntreffer. Hvert element kan ha opptil 50 separate hendelsesbehandlinger konfigurert.  
  
> [!IMPORTANT]
>  Hvis du konfigurerer en hendelsesbehandling feil, kan det resultere i skriptfeil som kan føre til at skjemaet ikke lastes inn eller fungerer på riktig måte. Hvis du ikke er utvikleren av skriptet, må du vite nøyaktig hvilke konfigurasjonsalternativer skriptet krever.  
>   
>  Ikke konfigurer en hendelsesbehandling for skriptet ved hjelp av et bibliotek som ikke kommer fra en kilde du stoler på. Skript kan brukes til å utføre enhver handling som en bruker kan utføre, og et dårlig skrevet skript kan medføre en betydelig redusert skjemaytelse.  
>   
>  Når du konfigurerer en hendelsesbehandling, må du alltid teste den for å bekrefte at den fungerer på riktig måte.  
  
### <a name="to-configure-an-event-handler"></a>Slik konfigurerer du en hendelsesbehandling 
  
1.  Velg elementet med hendelsen du vil konfigurere et behandlingsprogram for, i redigeringsprogrammet for skjema.  
  
2.  Velg **Endre egenskaper**, eller ganske enkelt dobbeltklikk på elementet på [Hjem-fanen](form-editor-user-interface-legacy.md#home-tab) i **Rediger**-gruppen.  
  
3.  Velg **Hendelser**-fanen i dialogboksen for elementegenskaper.  
  
4.  Utvid **Skjemabiblioteker**-området. Hvis biblioteket som inneholder funksjonen du vil angi som hendelsesbehandling, ikke er oppført allerede, kan du legge det til i biblioteket.  
  
5.  Slik legger du til et skjemabibliotek i en hendelsesbehandling:  
    1.  Velg **Legg til** i **Skjemabiblioteker**-inndelingen av **Hendelsesliste**.  
  
    2.  Finn JavaScript-webressursen i listen over tilgjengelige webressurser. Velg den, og velg deretter **Legg til**.  
  
         Hvis JavaScript-webressursen du trenger ikke finnes, velger du **Ny** for å åpne et nytt skjema for webressursen og for å opprette det.  
  
    3.  Slik oppretter du en JavaScript-webressurs:  
        1.  Angi følgende egenskaper i skjemasettet for webressursen:  
  
            |Egenskap|Verdi|  
            |--------------|-----------|  
            |Navn|**Obligatorisk**. Skriv inn navnet på webressursen.|  
            |Visningsnavn|**Obligatorisk**. Skriv inn navnet som skal vises i listen over webressurser.|  
            |Beskrivelse|Valgfritt. Skriv inn en beskrivelse av webressursen.|  
            |Type|**Obligatorisk**. Velg **Skript (JScript)**.|  
            |Språk|Valgfritt. Velg ett av språkene som er tilgjengelige for organisasjonen.|  
  
        2.  Hvis du har mottatt et skript, anbefaler vi at du bruker **Bla gjennom**-knappen for å finne filen og laste den opp.  
  
             Du kan også velge **Tekstredigeringsprogram**-knappen og lime eller skrive inn innholdet i skriptet i dialogboksen **Rediger innhold**.  
  
            > [!NOTE]
            >  Fordi dette enkle tekstredigeringsprogrammet ikke inneholder noen funksjoner for å kontrollere at skriptet er riktig, bør du som regel alltid bruke et separat program som Visual Studio for å redigere skript og laste dem opp.  
  
        3.  Velg **Lagre**, og lukk dialogboksen for webressurs.  
  
        4.  Webressursen du opprettet nå er valgt i dialogboksen **Slå opp post**. Velg **Legg til** for å lukke dialogboksen.  
6.  I **Hendelsesbehandlinger**-inndelingen velger du hendelsen du vil angi en hendelsesbehandling for.  
  
7.  Velg **Legg til** for å åpne dialogboksen **Behandlingsprogramegenskaper**.  
  
8. Velg riktig bibliotek fra **Detaljer**-fanen, og skriv inn navnet på funksjonen som skal utføres for hendelsen.  
  
9. Hendelsesbehandlingen er aktivert som standard. Fjern merket for **Aktivert** hvis du ikke vil aktivere denne hendelsen.  
  
     Noen funksjoner krever at en utføringskontekst sendes til funksjonen. Velg **Send utføringskontekst som den første parameteren** hvis det er nødvendig.  
  
     Noen funksjoner kan godta et sett med parametere for å kontrollere virkemåten til en funksjon. Hvis disse er obligatorisk, angir du dem i **Kommadelt liste over parametere som skal sendes til funksjonen**.  
  
10. Legg til felt som skriptet avhenger av i **Avhengige felt**-området, på **Avhengigheter**-fanen.  
  
11. Velg **OK** for å lukke dialogboksen **Behandlingsprogramegenskaper**.  
  
12. Når du oppgir hendelsesbehandlingen, kan du tilpasse rekkefølgen som funksjonen vil bli utført, i forhold til eventuelle andre funksjoner, ved hjelp av de grønne pilene for å flytte den opp eller ned.  
  
13. Velg **OK** for å lukke dialogboksen Elementegenskaper.  
  
14. Velg **Lagre** for å lagre endringene. Velg **Publiser** for å publisere skjemaet.  
  
> [!NOTE]
>  Mens brukergrensesnittet (UI) lar deg justere rekkefølgen som skriptene lastes, ved å bruke de grønne piltastene opp og ned, lastes skriptene faktisk ikke inn sekvensielt.   

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjema og tilknyttede komponenter](use-main-form-and-components.md)
