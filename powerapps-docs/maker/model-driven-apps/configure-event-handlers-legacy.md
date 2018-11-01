---
title: Konfigurere hendelsesbehandling for hovedskjemaer for modelldrevet app i PowerApps | MicrosoftDocs
description: Forstå hvordan du konfigurerer hendelsesbehandling i Dynamics 365 for Customer Engagement
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-model-driven-app-form-event-handlers"></a>Konfigurere hendelsesbehandling for modellfremdrevet appskjema

 Hendelsesbehandlinger for PowerApps-skjema kan konfigureres for følgende områder i et skjema:  
  
|Element|Hendelse|Beskrivelse|  
|-------------|-----------|-----------------|  
|Skjema|`OnLoad`|Oppstår når skjemaet lastes inn.|  
||`OnSave`|Oppstår når dataene lagres.|  
|Kategori|`TabStateChange`|Oppstår når kategorien vises eller skjules.|  
|Felt|`OnChange`|Oppstår når data i feltet endres og kontrollen mister fokus.|  
|IFRAME|`OnReadyStateComplete`|Oppstår når innholdet i en IFRAME lastes inn.|  
  
 En hendelsesbehandling består av en referanse til JavaScript-webressurs og en funksjon som er definert i webressursen, som kjøres når hendelsen oppstår. Hvert element kan ha konfigurert opptil 50 separate hendelsesbehandlinger.  
  
> [!IMPORTANT]
>  Feil konfigurasjon av en hendelsesbehandling kan det føre til skriptfeil som kan føre til at skjemaet ikke laste inn eller fungerer slik det skal. Hvis du ikke er utvikleren av skriptet, må du passe på at du må vite nøyaktig hva slags konfigurasjonsalternativer skriptet krever.  
>   
>  Ikke Konfigurer en hendelsesbehandling for skript ved å bruke et bibliotek som ikke kommer fra en kilde du stoler på. Skript kan brukes til å utføre alle handlinger brukeren kan utføre, og et dårlig skrevet skript kan redusere ytelsen betydelig til et skjema.  
>   
>  Når du konfigurerer en hendelsesbehandling, må du alltid teste den for å kontrollere at den fungerer slik den skal.  
  
### <a name="to-configure-an-event-handler"></a>Slik konfigurerer du en hendelsesbehandling 
  
1.  I skjemaredigeringsprogrammet velger du elementet med hendelsen du vil konfigurere en behandling for.  
  
2.  I kategorien [Hjem](form-editor-user-interface-legacy.md#home-tab) i **Rediger**-gruppen velger du **Endre egenskaper** eller dobbeltklikker elementet.  
  
3.  Velg kategorien **Hendelser** i dialogboksen for egenskaper for elementet.  
  
4.  Vis området **Skjemabiblioteker**. Hvis biblioteket som inneholder funksjonen du vil angi som hendelsesbehandlingen ikke allerede vises, legger du til biblioteket.  
  
5.  Slik legger du til et skjemabibliotek i en hendelsesbehandling:  
    1.  I **Skjemabiblioteker**-delen i **Hendelsesliste** velger du **Legg til**.  
  
    2.  Finn JavaScript-webressursen i listen over tilgjengelige webressurser. Velg det, og velg deretter **Legg til**.  
  
         Hvis JavaScript-webressurs du vil bruke ikke finnes, velger du **Ny** for å åpne et nytt webressursskjema og opprette en.  
  
    3.  Slik oppretter du en JavaScript-webressurs:  
        1.  Angi følgende egenskaper i webressursskjemaet:  
  
            |Egenskap|Verdi|  
            |--------------|-----------|  
            |Navn|**Required**. Skriv inn navnet på webressursen.|  
            |Visningsnavn|**Required**. Skriv inn navnet som vises i listen over webressurser.|  
            |Beskrivelse|Valgfritt. Skriv inn en beskrivelse av webressursen.|  
            |Type|**Required**. Velg **Skript (JScript)**.|  
            |Språk|Valgfritt. Velg ett av språkene som er tilgjengelige for organisasjonen.|  
  
        2.  Hvis du har fått et skript, anbefaler vi på det sterkeste at du bruker **Bla gjennom** for å finne filen og laste det opp.  
  
             Du kan også velge knappen **Tekstredigeringsprogram** og lime inn eller skrive inn innholdet i skriptet i dialogboksen **Rediger innhold**.  
  
            > [!NOTE]
            >  Siden dette enkelt tekstredigeringsprogrammet ikke inneholder funksjoner for å kontrollere at skriptet er riktig, bør du vanligvis alltid prøve å bruke et separat program, for eksempel Visual Studio, til å redigere skript og deretter laste dem opp.  
  
        3.  Velg **Lagre**, og lukk dialogboksen for webressursen.  
  
        4.  Webressursen du opprettet er nå valgt i dialogboksen **Oppslagsoppføring**. Velg **Legg til** for å lukke dialogboksen.  
6.  I inndelingen **Hendelsesbehandlinger** velger du hendelsen du vil angi en hendelsesbehandling for.  
  
7.  Velg **Legg til** for å åpne dialogboksen **Egenskaper for behandling**.  
  
8. I kategorien **Detaljer** velger du riktig bibliotek og skriver inn navnet på funksjonen som skal utføres for hendelsen.  
  
9. Hendelsesbehandlingen er aktivert som standard. Fjern merket vor **Aktivert** hvis du ikke vil aktivere hendelsen.  
  
     Noen funksjoner krever at det sendes en utføringskontekst til funksjonen. Velg **Send utføringskontekst som første parameter** ved behov.  
  
     Noen funksjoner kan godta et sett med parametere for å styre virkemåten til en funksjon. Hvis dette er nødvendig, skriver du dem inn i **Kommadelt liste over parametere som sendes til funksjonen**.  
  
10. I kategorien **Avhengigheter** legger du til felt som skriptet avhenger av i området **Avhengige felt**.  
  
11. Velg **OK** for å lukke dialogboksen **Egenskaper for behandling**.  
  
12. Når hendelsesbehandlingen åpnes, kan du justere utførelsesrekkefølgen for funksjonen i forhold til andre funksjoner ved å bruke de grønne pilene til å flytte den opp eller ned.  
  
13. Velg **OK** for å lukke dialogboksen for egenskaper for elementet.  
  
14. Velg **Lagre** for å ta i bruk endringene. Velg **Publiser** for å publisere skjemaet.  
  
> [!NOTE]
>  Selv om brukergrensesnittet (UI) lar deg justere rekkefølgen skriptene lastes i ved hjelp av de grønne pilene opp og ned, lastes ikke skriptene sekvensielt i virkeligheten.   

## <a name="next-steps"></a>Neste trinn

[Bruk hovedskjemaet og komponentene i skjemaet](use-main-form-and-components.md)
