---
title: Distribuer Dynamics 365 App for Outlook | MicrosoftDocs
ms.custom: ''
ms.date: '2017-04-20'
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
ms.assetid: 09736e14-e744-48ca-a755-1b05bb55340e
caps.latest.revision: 39
author: jimholtz
ms.author: jimholtz
manager: brycho
---
# <a name="deploy-dynamics-365-app-for-outlook"></a>Distribuer Dynamics 365 App for Outlook
Brukerne kan bruke [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] til å utnytte kraften i [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] mens de bruker [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] på skrivebordet, nettet eller nettbrettet. Vis for eksempel informasjon om e-post- eller avtalemottakere, eller koble en [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-e-post eller -avtale til en [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]-oppføring, for eksempel en salgsmulighet, forretningsforbindelse eller sak. Hvis du vil finne ut mer om hva [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] tilbyr, kan du se [brukerhåndboken for Dynamics 365 App for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
> [!IMPORTANT]
>  [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] er ikke det samme som [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]. Fra og med [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] er [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] sammen med [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] den foretrukne måten å integrere [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] med [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]. **Vær oppmerksom på at sporing av aktiviteter ikke støttes når [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] og [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)] brukes sammen av den samme brukeren.** Hvis du vil ha informasjon om [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]-tillegget, kan du se [brukerhåndboken for Dynamics 365 for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=524751).  
>   
>  [Delegerte brukere](https://support.office.com/article/Allow-someone-else-to-manage-your-mail-and-calendar-9684B670-7588-4EEA-8717-9E5799047540) kan ikke bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] til å spore e-post. Det foreslås at du bruker [sporing på mappenivå eller automatisk sporing](https://www.microsoft.com/en-us/dynamics/crm-customer-center/overview-of-tracking-records-in-dynamics-365-for-outlook.aspx) for delegerte brukere.  
  
<a name="BKMK_Compare"></a>   
## <a name="comparing-dynamics-365-app-for-outlook-with-dynamics-365-for-outlook"></a>Sammenligne Dynamics 365 App for Outlook med Dynamics 365 for Outlook  
 Følgende tabell sammenligner [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]-funksjoner med [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)] (også kjent som [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-klienten eller -tillegget) for [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)].  
  
||||  
|-|-|-|  
|**Funksjon**|**[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]**|**[!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]**|  
|Spore og angi som angående for e-post|Ja|Ja|  
|Spore og angi som angående for avtaler|Ja|Ja|  
|Spore og angi som angående for kontakter|Ja|Ja|  
|Spore og angi som angående for oppgaver|Nei|Ja|  
|Ett klikk og angi som angående|Ja|Nei|  
|Viser mottakernes sammendrag|Ja|Nei|  
|Viser sammendraget av den angående oppføringen i e-posten/avtalen|Ja|Nei|  
|Fungerer med [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)]|Ja|Nei|  
|Fungerer med [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-skrivebord|Ja|Ja|  
|Fungerer med [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for Mac|Ja|Nei|  
|Fungerer med telefoner|Ja|Nei|  
|Åpne og opprette [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]-oppføring direkte|Ja|Ja|  
|Bruke egendefinerte skjemaer og forretningslogikk|Ja|Ja|  
|Arbeide frakoblet|Nei|Ja|  
|Bruke e-postmaler|Ja|Ja|  
|Bruke salgsmateriell|Ja|Ja|  
|Bruke kunnskapsartikler|Ja|Ja|  
|Evne til å overvåke e-postmeldinger etter sending|Ja|Nei|  
|Sortere, filtrere, formatere, gruppere og kategorisere visninger|Nei|Ja|  
|Opprette utskriftsflettingsdokumenter i Word|Nei|Ja|  
|Synkronisering av kontrollfelt|Nei|Ja|  
  
<a name="BKMK_Requirements"></a>   
## <a name="requirements"></a>Krav  
 Følgende komponenter kreves for å bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]:  
  
-   [!INCLUDE[pn_crm_online_2016_update](../includes/pn-crm-online-2016-update.md)], eller [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)]  
  
-   Synkronisering av innkommende e-post via synkronisering på serversiden. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)][Konfigurere synkronisering på serversiden av e-post, avtaler, kontakter og oppgaver](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)  
  
-   Nødvendige rettigheter som beskrevet nedenfor  
  
> [!NOTE]
>  Støttede konfigurasjoner og krav for [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)]-funksjoner er oppført i dokumentasjonen vår. Bestemte konfigurasjoner som ikke er dokumentert, skal regnes som ikke å være støttet.  
  
### <a name="required-privileges"></a>Krav til rettigheter  
 [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] gir tilgang til [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] gjennom rettigheten **Bruk Dynamics 365 App for Outlook**. Hvis en bruker ikke har denne rettigheten, vil vedkommende motta følgende feilmelding:  
  
> "Du er ikke autorisert til å bruke denne appen. Kontakt systemansvarlig for å få oppdatert innstillingene."  
  
 Brukerne må også ha lese/skrive-rettigheter for følgende enheter.  
  
 Kategorien Forretningsbehandling:  
  
-   **Postboks**  
  
 Kategorien Tilpassing:  
  
-   **Enhet**  
  
-   **Felt**  
  
-   **Relasjon**  
  
-   **Metadata for systemprogram**  
  
-   **Systemskjema**  
  
-   **Metadata for brukerprogram**  
  
-   **Visning**  
  
##### <a name="set-the-privileges-for-a-security-role"></a>Angi rettighetene for en sikkerhetsrolle  
  
1.  [!INCLUDE[proc_settings_security](../includes/proc-settings-security.md)]  
  
2.  Klikk **Sikkerhetsroller**.  
  
3.  Velg en sikkerhetsrolle, og klikk deretter kategorien **Forretningsbehandling**.  
  
4.  I **Enhet**-delen kan du se gjennom innstillingene for **Postboks**-rettigheten. Sikkerhetsrollen bør ha Bruker eller en høyere innstilling.  
  
5.  I delen **Personvernrelaterte rettigheter** bekrefter du at **Bruk Dynamics 365 App for Outlook** er satt til **Organisasjon**. Hvis ikke, klikker du **Bruk Dynamics 365 App for Outlook**.  
  
### <a name="supported-configurations-with-microsoft-exchange"></a>Støttede konfigurasjoner med Microsoft Exchange  
 Fra og med [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] kan du bruke appen med en kombinasjon av [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] eller [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)] og [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)] eller [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (on-premises), inkludert hybridkonfigurasjoner. Dette betyr at du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] i noen av følgende konfigurasjoner:  
  
|||  
|-|-|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (on-premises)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (on-premises)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
  
> [!NOTE]
>  Hvis du bruker [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)], må du godkjenne med IFD-godkjenning, som beskrevet nedenfor.  
  
### <a name="supported-browsers-for-outlook-on-the-web"></a>Støttede lesere for Outlook på nettet  
 Du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] med [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] i følgende nettlesere:  
  
-   [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)] eller [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)]  
  
     Følgende konfigurasjon støttes:  
  
    -   Beskyttet modus er aktivert for sikkerhetssonen **Internett**. Slik aktiverer du beskyttet modus: I IE 10 eller 11 går du til **Verktøy** > **Alternativer for Internett** > **kategorien Sikkerhet** > **Internett**.  
  
    -   Beskyttet modus er aktivert for sikkerhetssonen **Lokalt intranett**. Slik aktiverer du beskyttet modus: I IE 10 eller 11 går du til **Verktøy** > **Alternativer for Internett** > **kategorien Sikkerhet** > **Lokalt Internett**.  
  
    -   URL-adressen for [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)] er i sikkerhetssonelisten **Lokalt intranett** over klarerte nettsteder. I IE 10 eller 11 går du til **Verktøy** > **Alternativer for Internett** > **kategorien Sikkerhet** > **Lokalt intranett** > **Områder** > **Avansert**.  
  
-   [!INCLUDE[tn_Google_Chrome](../includes/tn-google-chrome.md)] (nyeste versjon) på [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]  
  
-   [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] (nyeste versjon) på [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_Safari](../includes/tn-safari.md)] (versjon 9 eller 10) på Mac eller OSX  
  
### <a name="supported-operating-systems-for-outlook-on-the-desktop"></a>Operativsystem som støttes for Outlook på skrivebordet  
 Du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] i disse versjonene av [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for skrivebordet:  
  
-   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2013 og [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016.  
  
-   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for Mac*.  
  
     *[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] versjon 15.0.847.32 eller nyere kreves.  
  
### <a name="supported-mobile-devices"></a>Mobile enheter som støttes  
 Du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]med [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] i mobilnettleseren på noen av de følgende telefoner og operativsystemene:  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_iphone](../includes/tn-iphone.md)]-enheter som kjører iOS versjon 8, 9 eller 10.  
  
-   [!INCLUDE[tn_android](../includes/tn-android.md)]-telefoner som kjører [!INCLUDE[tn_android](../includes/tn-android.md)] 4.4 (KitKat) eller 5.0 (Lollipop), 6 (Marshmallow) eller 7 (Nougat).  
  
-   [!INCLUDE[pn_windows_phone](../includes/pn-windows-phone.md)]-enheter som kjører [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)] eller [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)].  
  
### <a name="supported-clients-per-feature"></a>Støttede klienter per funksjon  
 Funksjonene i [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]som støttes, avhenger av klienten du kjører. Tabellen nedenfor oppsummerer hvilke funksjoner som støttes for hver klient/konfigurasjon av [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] og [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)].  
  
 ![Klienter støttes for hver Dynamics 365 App for Outlook-funksjon](media/clients-supported-for-each-dynamics-365-app-for-outlook-feature.png "Klienter støttes for hver Dynamics 365 App for Outlook-funksjon")  
  
 (1) [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] støtter [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)], [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)], [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 9, [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 10, [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] og [!INCLUDE[tn_chrome](../includes/tn-chrome.md)].  
  
 (2) Mobile [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] støtter [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)], [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)], [!INCLUDE[tn_ios](../includes/tn-ios.md)] 8, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 9, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 10, [!INCLUDE[tn_android](../includes/tn-android.md)] KitKat (4.4), [!INCLUDE[tn_android](../includes/tn-android.md)] Lollipop, [!INCLUDE[tn_android](../includes/tn-android.md)] Marshmallow og [!INCLUDE[tn_android](../includes/tn-android.md)] Nougat.  
  
 (3) Sporing av e-postmeldinger i skrivemodus og sporing av avtaler krever [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2013 CU14 eller [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2016.  
  
 (4) Sporing av kontakter støttes bare på [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)]2016 CU3 og [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.6741.1000 og senere.  
  
 (5) Å legge til e-postmaler, kunnskapsstyringsartikler og salgsmateriell støttes ikke i Mobile [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)].  
  
 (6) Støttes bare på [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.7426.1049 og senere.  
  
 (7) Støttes bare på 16.0.6741.1000 og senere.  
  
> [!NOTE]
>  Nettbrett støttes ikke på dette tidspunktet (kommer CY2017).  
  
 [Lese mer om støttede klienter i denne bloggen: Dynamics 365 App for Outlook Support Matrix](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)  
  
### <a name="supported-servers"></a>Støttede servere  
 [Serverkravene for bruk av Office-tillegg](https://dev.office.com/docs/add-ins/overview/requirements-for-running-office-add-ins) er [!INCLUDE[pn_Exchange_Server_2013_short](../includes/pn-exchange-server-2013-short.md)], [!INCLUDE[pn_exchange_server_2016_short](../includes/pn-exchange-server-2016-short.md)] eller [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)].  
  
### <a name="supported-languages"></a>Språk som støttes  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] støtter følgende språk:  
  
||||  
|-|-|-|  
|Bulgarsk (Bulgaria) – 1026|Hindi (India) – 1081|Portugisisk (Portugal) – 2070|  
|Kinesisk (Folkerepublikken Kina) – 2052|Ungarsk – 1038|Rumensk – 1048|  
|Kinesisk (Taiwan) – 1028|Indonesisk – 1057|Russisk – 1049|  
|Kroatisk (Kroatia) – 1050|Italiensk – 1040|Serbisk – 2074|  
|Tsjekkisk (Tsjekkia) – 1029|Japansk – 1041|Slovakisk – 1051|  
|Dansk – 1030|Kasakhisk – 1087|Slovensk – 1060|  
|Nederlandsk – 1043|Koreansk – 1042|Spansk – 3082|  
|Engelsk – 1033|Latvisk – 1062|Svensk – 1053|  
|Estisk – 1061|Litauisk – 1063|Thai – 1054|  
|Finsk – 1035|Malaysisk – 1086|Tyrkisk – 1055|  
|Fransk – 1036|Norsk – 1044|Ukrainsk – 1058|  
|Tysk – 1031|Polsk – 1045|Vietnamesisk – 1066|  
|Gresk – 1032|Portugisisk (Brasil) – 1046||  
  
<a name="BKMK_Deploy"></a>   
## <a name="deploy-dynamics-365-app-for-outlook"></a>Distribuer Dynamics 365 App for Outlook  
 Når du har konfigurert [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] og angitt de nødvendige rettighetene, kan du push-varsle om [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] til noen av eller alle brukerne, eller du kan få brukerne til å installere det selv etter behov.  
  
> [!NOTE]
>  Hvis du er på [!INCLUDE[pn_dyn_365_op](../includes/pn-dyn-365-op.md)], kan du se delen nedenfor: [Distribuere til lokale brukere av Dynamics 365](#BKMK_DeployOnprem)  
  
#### <a name="to-push-the-app-to-users"></a>Slik push-varsler du om appen til brukere  
  
1.  Gå til **Innstillinger** >  **Dynamics 365 App for Outlook**.  
  
2.  Under **Legg til for berettigede brukere** i skjermbildet **Komme i gang med Dynamics 365 App for Outlook** (du må kanskje klikke **Innstillinger** hvis du åpner dette skjermbildet for andre gang eller mer) merker du av for **Legg til appen automatisk i [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]** hvis du vil at brukerne skal få appen automatisk. Hvis brukeren har de nødvendige rettighetene og e-post synkroniseres via [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)], trenger du ikke å gjøre noe mer for å push-varsle om appen til dem. Hvis du for eksempel legger til de nødvendige rettighetene til Selger-rollen og deretter tilordner denne rollen til en ny bruker, får de appen automatisk.  
  
3.  Gjør ett av følgende:  
  
    -   Hvis du vil overføre appen til alle berettigede brukere, klikker du **Legg til app for alle berettigede brukere**.  
  
    -   Hvis du vil overføre appen til bestemte brukere, velger du brukerne i listen og klikker deretter **Legg til app i Outlook**.  
  
    > [!TIP]
    >  Hvis listen viser at en bruker venter eller ikke har blitt lagt til, kan du klikke koblingen **Finn ut mer** ved siden av brukeren for å finne mer informasjon om statusen.  
  
4.  Klikk **Lagre** når du er ferdig.  
  
#### <a name="to-have-users-install-the-app-themselves"></a>Slik lar du brukerne installere appen selv  
  
1.  Brukerne må klikke **Innstillinger**-knappen ![Innstillinger-knapp](media/mp-ua-r16-settings.png "Innstillinger-knapp") og deretter klikke **Apper for Dynamics 365**.  
  
2.  På skjermen **Apper for Dynamics 365**, under **[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]**, må brukerne klikke **Legg til app i [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]**.  
  
> [!NOTE]
>  Brukere kan også deaktivere eller fjerne tillegget selv, om nødvendig. Du finner mer informasjon i [brukerhåndboken for Dynamics 365 App for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
<a name="BKMK_DeployOnprem"></a>   
## <a name="to-deploy-to-dynamics-365-on-premises-users"></a>Distribuere til lokale Dynamics 365-brukere  
 Følg disse trinnene hvis du bruker Dynamics 365 on-premises.  
  
-   Konfigurer Dynamics 365 Server for Internett-rettet distribusjon. Se [Konfigurere IFD for Microsoft Dynamics 365](https://technet.microsoft.com/library/dn609803.aspx).  
  
-   Hvis du kobler til Exchange on-premises, konfigurerer du OAuth-leverandøren og registrerer klientapper. Se [Konfigurere Windows Server 2012 R2 for Dynamics 365-apper som bruker OAuth](https://technet.microsoft.com/library/hh699726.aspx).  
  
<a name="BKMK_Troubleshoot"></a>   
## <a name="troubleshooting-installation-problems"></a>Feilsøke installasjonsproblemer  
 Hvis du eller andre brukere har problemer med å installere [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)], kan det være fordi deres [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postboks er koblet til en annen [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)]-organisasjon. En [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postboks (e-postadresse) kan bare synkronisere avtaler, kontakter og oppgaver med én organisasjon, og en bruker som tilhører denne organisasjonen, kan bare synkronisere avtaler, kontakter og oppgaver med én [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postboks.  Du kan overskrive innstillingen som er lagret i [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)], hvis du vil endre den primære organisasjonen for synkronisering. Hvis du vil ha mer informasjon, kan du se [denne KB-artikkelen.](https://support.microsoft.com/en-gb/help/3211627/incomingemailrejected-error-when-attempting-to-install-dynamics-365-app-for-outlook)  
  
<a name="BKMK_Explore"></a>   
## <a name="explore-the-users-guide-and-train-your-users"></a>Utforske brukerhåndboken og lære opp brukere  
 Hvis du vil finne ut hvordan du bruker [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)], kan du se [brukerhåndboken for Dynamics 365 App for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
 ![Side for brukerhåndbok for Dynamics 365 App for Outlook](media/dynamics-365-app-for-outlook-user-s-guide-page.png "Side for brukerhåndbok for Dynamics 365 App for Outlook")  
  
## <a name="see-also"></a>Se også  
 [Brukerhåndbok for Dynamics 365 App for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099)   
 [Lese mer om støttede klienter i denne bloggen: Dynamics 365 App for Outlook Support Matrix](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)   
 [Konfigurere synkronisering på serversiden av e-post, avtaler, kontakter og oppgaver](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)   
 [Legge til brukere, lisenser og sikkerhetsroller](https://msdn.microsoft.com/23612155-f92d-4871-a109-186419d5c19d)   
 [Legge til samhandlingsfunksjoner i Microsoft Dynamics 365 (online)](../DocSets/CRMIGv9_Admin/Toc/Add%20interoperation%20features%20to%20Microsoft%20Dynamics%20365%20\(online\).md)