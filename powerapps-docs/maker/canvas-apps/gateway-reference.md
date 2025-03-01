---
title: Lokale datagatewayer for lerretsapper | Microsoft Docs
description: Referanseinformasjon om lokale datagatewayer, inkludert installasjon i PowerApps og feilsøking
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/20/2017
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4ac1df1d6a2901345436b899e3c7088f746eb2aa
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983346"
---
# <a name="understand-on-premises-data-gateways-for-canvas-apps"></a>Lokale datagatewayer for lerretsapper
## <a name="installation-and-configuration"></a>Installasjon og konfigurasjon
**Forutsetninger**

Minimum:

* .NET 4.5 Framework
* 64-biters versjon av Windows 7 eller Windows Server 2008 R2 (eller nyere)

Anbefalt:
* 8-kjerners CPU
* 8 GB minne
* 64-bitersversjon av Windows 2012 R2 (eller nyere)

Vurderinger angående design:

* Du kan ikke installere en gateway på en domenekontroller.
* Du bør ikke installere en gateway på en datamaskin, for eksempel en bærbar datamaskin, som kan bli slått av, gå i dvale, eller som ikke er tilkoblet Internett, siden gatewayen ikke kan kjøre under noen av disse omstendighetene. I tillegg kan gatewayens ytelse svekkes over et trådløst nettverk.

**Å installere en gateway**

1. [Last ned installasjonsprogrammet](http://go.microsoft.com/fwlink/?LinkID=820931), og kjør det.

    ![Kjør installasjonsprogrammet](./media/gateway-reference/run-installer.png)

2. Klikk eller trykk på **Neste** på det første skjermbildet i installasjonsveiviseren for å bekrefte påminnelsen om installasjon av en gateway på en bærbar datamaskin.

    ![Påminnelsesskjerm](./media/gateway-reference/laptop-reminder.png)

3. Angi plasseringen der du vil installere gatewayen, og merk av for å akseptere bruksvilkårene og personvernerklæringen. Klikk eller trykk deretter på **Installer**.

4. Klikk eller trykk på **Ja** i dialogboksene **Brukerkontokontroll** for å fortsette.

5. På den neste skjermen i veiviseren klikker eller trykker du på **Logg på** og angir samme legitimasjon som du bruker til å logge deg på PowerApps.

    ![logg inn](./media/gateway-reference/sign-in.png)

6. Klikk eller trykk på alternativet for å registrere en ny gateway eller for å overføre, gjenopprette eller ta over en eksisterende gateway, og klikk eller trykk deretter på **Neste**.

    ![Velg ny eller eksisterende](./media/gateway-reference/new-existing.png)

   * Når du skal konfigurere en gateway, skriver du inn et **navn** for gatewayen og en **gjenopprettingsnøkkel**. Klikk eller trykk på **Konfigurer**, og klikk eller trykk deretter på **Lukk**.

       ![Konfigurasjon av ny gateway](./media/gateway-reference/configure-new.png)

       Angi en gjenopprettingsnøkkel som inneholder minst åtte tegn, og oppbevar den på et sikkert sted. Du trenger denne nøkkelen hvis du vil overføre, gjenopprette eller ta over gatewayen den hører til.

   * Når du vil overføre, gjenopprette eller ta over en eksisterende gateway, skriver du inn navnet på gatewayen og den tilhørende gjenopprettingsnøkkelen, deretter klikker eller trykker du på **Konfigurer** og følger eventuelle ytterligere instruksjoner.

       ![Gjenoppretting av eksisterende gateway](./media/gateway-reference/recover-existing.png)

**Start gatewayen på nytt**

Gatewayen kjøres som en Windows-tjeneste, så du kan starte og stoppe den på flere måter. Du kan for eksempel åpne en ledetekst med høyere tillatelser på den maskinen gatewayen kjører på, og deretter kjøre hvilken som helst av disse kommandoene:

* Kjør denne kommandoen for å stoppe tjenesten:<br>
  **net stop PBIEgwService**

* Kjør denne kommandoen for å starte tjenesten:<br>
  **net start PBIEgwService**

**Konfigurasjon av brannmur eller proxy**

Du finner mer informasjon om hvordan du angir proxy-informasjon for gatewayen under [Konfigurasjon av proxy-innstillinger](https://docs.microsoft.com/power-bi/service-gateway-proxy).

Du kan bekrefte om brannmuren eller proxyen kanskje blokkerer tilkoblinger, ved å kjøre den følgende kommandoen fra en PowerShell-ledetekst. Denne kommandoen tester tilkoblingen til Azure Service Bus. Dette tester bare nettverkstilkoblingen og har ikke noe å gjøre med den skybaserte tjenesten eller gatewayen. Den hjelper deg med å finne ut om maskinen din faktisk kan kobles til Internett.

**Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350**

Resultatet skal minne om dette eksempelet. Hvis **TcpTestSucceeded** ikke er **sann**, kan det hende at du blokkeres av en brannmur.

```
ComputerName           : watchdog.servicebus.windows.net
RemoteAddress          : 70.37.104.240
RemotePort             : 5672
InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
SourceAddress          : 10.120.60.105
PingSucceeded          : False
PingReplyDetails (RTT) : 0 ms
TcpTestSucceeded       : True
```

Hvis du vil være grundig, kan du skifte ut verdiene for **ComputerName** og **Port** med verdiene som står oppført under **Konfigurasjon av porter** senere i dette emnet.

Brannmuren kan også blokkere tilkoblingene som Azure Service Bus foretar til Azure-datasentrene. Hvis dette er tilfellet, bør du hviteliste (oppheve blokkeringen for) IP-adressene for regionen din for disse datasentrene. Du finner en liste over Azure-IP-adresser [her](https://www.microsoft.com/download/details.aspx?id=41653).

**Konfigurasjon av porter**

Gatewayen oppretter en utgående tilkobling til Azure Service Bus. Den kommuniserer på utgående porter: TCP 443 (standard), 5671, 5672, 9350 gjennom 9354. Gatewayen krever ikke innkommende porter.

Finn ut mer om [hybridløsninger](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/).

Det er anbefalt at du hvitelister IP-adressene for regionen din i brannmuren. Du kan laste ned [IP-listen for Microsoft Azure Datacenter](https://www.microsoft.com/download/details.aspx?id=41653), som oppdateres ukentlig.

> [!NOTE]
> På IP-listen for Azure Datacenter er adressene oppført i [CIDR-notasjon](http://whatismyipaddress.com/cidr). 10.0.0.0/24 betyr for eksempel ikke 10.0.0.0 til og med 10.0.0.24.

Her er en liste over de fullstendig kvalifiserte domenenavnene som brukes av gatewayen.

| Domenenavn | Utgående porter | Beskrivelse |
| --- | --- | --- |
| *.analysis.windows.net |443 |URL |
| *.login.windows.net |443 |URL |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Lyttere på Service Bus Relay over TCP (krever 443 for innhenting av Access Control-token) |
| *.frontend.clouddatahub.net |443 |URL |
| *.core.windows.net |443 |URL |
| \* login.microsoftonline.com |443 |URL |
| *.msftncsi.com |443 |Brukes til å teste Internett-tilkobling hvis gatewayen ikke kan nås av Power BI-tjenesten. |

**Påloggingskonto**

Brukere logger seg på med en jobb- eller skolekonto. Dette er organisasjonskontoen din. Hvis du registrerte deg for å få et Office 365-tilbud og ikke oppga den faktiske jobbkontoen din, kan den se ut som nancy@contoso.onmicrosoft.com. Kontoen din, i en skytjeneste, er lagret i en tenant i Azure Active Directory (AAD). I de fleste tilfeller vil ADD-kontoens UPN samsvare med e-postadressen.

**Windows-tjenestekonto**

Den lokale gatewaykontoen er konfigurert til å bruke *NT SERVICE\PBIEgwService* for legitimasjonen for Windows-tjenesten. Den har som standard rettigheten for pålogging som en tjeneste. Dette er i sammenheng med maskinen du installerer gatewayen på.

Dette er ikke konten som brukes til å koble til de lokale datakildene eller jobb- eller skolekontoen, som du bruker til å logge deg på skytjenesten.

Hvis det oppstår problemer med proxy-serveren på grunn av godkjenning, kan du endre Windows-tjenestekontoen til en domenebrukerkonto eller en administrert tjeneste-konto som beskrevet av [proxy-konfigurasjonen](https://docs.microsoft.com/power-bi/service-gateway-proxy#changing-the-gateway-service-account-to-a-domain-user).

## <a name="tenant-level-administration"></a>Administrasjon på tenantnivå 

Det finnes for øyeblikket ikke ett enkelt sted der tenantadministratorer kan behandle alle gatewayene som andre brukere har installert og konfigurert.  Hvis du er en tenantadministrator, anbefaler vi at du ber brukerne i organisasjonen om å legge deg til som en administrator for hver gatewayer de installerer. Dette lar deg administrere alle gatewayer i organisasjonen, gjennom siden for gatewayinnstillinger eller via [PowerShell-kommandoer](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters).

## <a name="frequently-asked-questions"></a>Vanlige spørsmål
#### <a name="general"></a>Fane
**Tegn** Hvilke data kilder støtter gatewayen?  
**Telefon** I skrivende stund:

* SQL Server
* Services
* Oracles
* Informix
* Filsystem
* ORACLE

**Tegn** Trenger jeg en gateway for data kilder i skyen, for eksempel SQL Azure?  
**Telefon** nei. En gateway kobles bare til lokale datakilder.

**Tegn** Hva er den faktiske Windows-tjenesten kalt?  
**Telefon** I tjenester kalles gatewayen **lokal datagateway-tjeneste**.

**Tegn** Finnes det inn kommende tilkoblinger til gatewayen fra skyen?  
**Telefon** nei. Gatewayen bruker utgående tilkoblinger til Azure Service Bus.

**Tegn** Hva skjer hvis jeg blokkerer utgående tilkoblinger? Hva må jeg åpne?  
**Telefon** Se listen over porter og verter som gatewayen bruker ovenfor.

**Tegn** Må gatewayen være installert på samme maskin som data kilden?  
**Telefon** nei. Gatewayen vil koble til datakilden ved hjelp av tilkoblingsinformasjonen som ble angitt. Tenk på gatewayen som et klientprogram i denne sammenhengen. Den vil bare kunne koble til det servernavnet som ble angitt.

**Tegn** Hva er vente tiden for å kjøre spørringer til en data kilde fra gatewayen? Hvilken arkitektur er best?  
**Telefon**  Hvis du vil redusere nettverks vente tiden, kan du installere gatewayen så nær data kilden som mulig. Hvis du kan installere gatewayen på den faktiske datakilden, vil dette minimere ventetiden. Ta også hensyn til datasentre. For eksempel, hvis tjenesten bruker datasenteret USA, vest og du bruker en Azure VM som vert for SQL Server, bør du også ha Azure VM i USA, vest. Dette minimerer ventetiden, og du unngår kostnader for utgående trafikk på Azure VM.

**Tegn** Finnes det noen krav for nettverks bånd bredde?  
**Telefon** Det anbefales å ha god gjennomstrømming for nettverks tilkoblingen. Alle miljøer er forskjellige, og mengden data som sendes vil påvirke resultatene. Bruk av ExpressRoute kan bidra til å garantere et gjennomstrømmingsnivå mellom de lokale datasentrene og Azure-datasentrene.

Du kan bruke tredjepartsverktøyet [Azure Speed Test-appen](http://azurespeedtest.azurewebsites.net/) til å måle gjennomstrømmingen.

**Tegn** Kan gateway-Windows-tjenesten kjøres med en Azure Active Directory-konto?  
**Telefon** nei. Windows-tjenesten må ha en gyldig Windows-konto. Den kjører med tjeneste-SID, *NT SERVICE\PBIEgwService* som standard.

**Tegn** Hvordan sendes resultatene tilbake til skyen?  
**Telefon** Dette gjøres ved hjelp av Azure Service Bus. Hvis du vil ha mer informasjon, kan du se [Slik fungerer det](gateway-reference.md#how-the-gateway-works).

**Tegn** Hvor lagres legitimasjonen min?  
**Telefon** Legitimasjonen du angir for en data kilde, lagres kryptert i Sky tjenesten for gatewayen. Legitimasjonen dekrypteres i den lokale gatewayen.

**Tegn** Kan jeg plassere gatewayen i et perimeternettverk (også kjent som DMZ, demilitarisert-sone og et skjerm del nettverk)?  
**Telefon** Gatewayen krever tilkobling til data kilden. Hvis datakilden ikke er i perimeternettverket, er det ikke sikkert at gatewayen kan koble til den. For eksempel kan ikke datamaskinen som kjører SQL Server, være i perimeternettverket, og du kan ikke koble til denne datamaskinen fra perimeternettverket. Hvis du plasserer gatewayen i perimeternettverket, kan ikke gatewayen nå datamaskinen som kjører SQL Server.

#### <a name="high-availabilitydisaster-recovery"></a>Høy tilgjengelighet / nødgjenoppretting
**Tegn** Finnes det planer for å aktivere scenarier med høy tilgjengelighet med gatewayen?  
**Telefon** Høy tilgjengelighet er aktivert ved å koble sammen 2 eller flere gatewayer til samme klynge.  Gatewayklynger med høy tilgjengelighet krever oppdateringen fra november 2017 eller nyere for lokal datagateway.  Se [kunngjøringen i blogginnlegget](https://powerapps.microsoft.com/en-us/blog/gateway-high-availability-for-powerapps-and-flow) for mer informasjon.

**Tegn** Hvilke alternativer er tilgjengelige for nød gjenoppretting?  
**Telefon** Du kan bruke gjenopprettings nøkkelen til å gjenopprette eller flytte en gateway. Angi gjenopprettingsnøkkelen når du installerer gatewayen.

**Tegn** Hva er fordelen med gjenopprettings nøkkelen?  
**Telefon** Det gjør det mulig å overføre eller gjenopprette Gateway-innstillingene dine etter en nød katastrofe.

#### <a name="troubleshooting"></a>Feil søking
**Tegn** Hvor er gateway-loggene?  
**Telefon** Se [verktøy](gateway-reference.md#tools) senere i dette emnet.

**Tegn** Hvordan kan jeg se hvilke spørringer som sendes til den lokale data kilden?  
**Telefon** Du kan aktivere spørrings sporing, som inneholder spørringene som sendes. Husk å endre den tilbake til den opprinnelige verdien når du er ferdig med feilsøkingen. Hvis du lar sporing av spørringer være aktivert, vil loggene bli større.

Du kan også se på verktøyene datakilden har for sporing av spørringer. Du kan for eksempel bruke Utvidede hendelser eller SQL Profiler for SQL Server og Analysis Services.

## <a name="how-the-gateway-works"></a>Slik fungerer gatewayen
![Slik fungerer det](./media/gateway-reference/gateway-arch.png)

Når en bruker samhandler med et element som er tilkoblet en lokal datakilde:  

1. Skytjenesten oppretter en spørring og sender spørringen, sammen med den krypterte legitimasjonen for datakilden, til køen for at gatewayen skal behandle den.

2. Gatewayens skytjeneste analyserer spørringen og sender forespørselen til [Azure Service Bus](https://azure.microsoft.com/documentation/services/service-bus/).

3. Den lokale datagatewayen avspør Azure Service Bus for ventende forespørsler.

4. Gatewayen mottar spørringen, dekrypterer legitimasjonen og bruker denne legitimasjonen til å koble til datakilden(e).

5. Gatewayen sender spørringen til datakilden for kjøring.

6. Datakilden sender resultatene tilbake til gatewayen og deretter til skytjenesten. Deretter brukes resultatene av tjenesten.

## <a name="troubleshooting"></a>Feil søking
#### <a name="update-to-the-latest-version"></a>Oppdatering til den nyeste versjonen
Hvis gateway-versjonen er utdatert, kan det oppstå mange problemer.  Det er generelt god praksis å sørge for at du bruker den nyeste versjonen.  Hvis du ikke har oppdatert gatewayen på en måned eller mer, bør du vurdere å installere den nyeste versjonen og se om du klarer å reprodusere problemet.

#### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Feil Kan ikke legge til bruker i gruppe.  (-2147463168   PBIEgwService   Performance Log Users   )
Du kan få denne feilen hvis du prøver å installere gatewayen på en domenekontroller som ikke støttes. Du må distribuere gatewayen på en maskin som ikke er en domenekontroller.

## <a name="tools"></a>Tegneverktøy
#### <a name="collecting-logs-from-the-gateway-configurator"></a>Samle inn logger fra gateway-konfiguratoren
Du kan samle inn flere logger for gatewayen. Start alltid med loggene!

**Installasjonslogger**

%localappdata%\Temp\On-premises_data_gateway_*.log

**Konfigurasjonslogger**

%localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log

**Tjenestelogger for Enterprise-gateway**

C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log

**Hendelseslogger**

Du finner hendelsesloggene fra **den lokale datagateway-tjenesten** under **Programmer og tjenestelogger**.

![Hendelseslogger](./media/gateway-reference/event-logs.png)

#### <a name="fiddler-trace"></a>Fiddler-sporing
[Fiddler](http://www.telerik.com/fiddler) er et gratis verktøy fra Telerik, som overvåker HTTP-trafikk.  Du kan se trafikken som går frem og tilbake mellom Power BI-tjenesten og klientmaskinen. Dette kan vise feil og annen tilhørende informasjon.
