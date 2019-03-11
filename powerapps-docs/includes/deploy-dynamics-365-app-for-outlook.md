---
title: Distribuer Dynamics 365-app for Outlook | MicrosoftDocs
ms.custom: ''
ms.date: 2017-04-20
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
ms.openlocfilehash: 98a5ec78b0edf607b954d794b3eef95403926a64
ms.sourcegitcommit: baadb67f5cc962b7c3393f9763959eae3a7649dd
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/05/2019
ms.locfileid: "57346951"
---
# <a name="deploy-dynamics-365-app-for-outlook"></a>Distribuer Dynamics 365-app for Outlook
Folk kan bruke [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] til å slå på [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] mens de bruker [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] på skrivebordet, nettet eller nettbrettet. Du kan for eksempel vise informasjon om e-post- eller avtalemottakere, eller koble til en [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-e-post eller -avtale i en [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]-post som for eksempel en salgsmulighet, konto eller sak. Hvis du vil finne ut mer om hva [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] tilbyr, kan du se [Brukerveiledning for Dynamics 365-app for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
> [!IMPORTANT]
>  [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] er ikke det samme som [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]. Fra og med [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] er [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] paret med [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] den foretrukne måten å integrere [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] med   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] på. **Vær oppmerksom på at sporingsaktiviteter ikke støttes når  [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] og [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)] brukes sammen av samme bruker.** Hvis du vil ha informasjon om  [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]-tilleggsprogrammet, kan du se [Brukerveiledning for Dynamics 365 for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=524751).  
>   
>  [Delegerte brukere](https://support.office.com/article/Allow-someone-else-to-manage-your-mail-and-calendar-9684B670-7588-4EEA-8717-9E5799047540) kan ikke bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] til å spore e-postmeldinger. Vi foreslår at du bruker [sporing på mappenivå eller automatisk sporing](https://www.microsoft.com/en-us/dynamics/crm-customer-center/overview-of-tracking-records-in-dynamics-365-for-outlook.aspx) for delegerte brukere.  
  
<a name="BKMK_Compare"></a>   
## <a name="comparing-dynamics-365-app-for-outlook-with-dynamics-365-for-outlook"></a>Sammenligning av Dynamics 365-appen for Outlook med Dynamics 365 for Outlook  
 Den følgende tabellen sammenligner [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]-funksjoner med [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)] (også kjent som [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-klienten eller -tilleggsprogrammet) fra og med [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)].  
  
||||  
|-|-|-|  
|**Funksjon**|**[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]**|**[!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]**|  
|Spor og angi angående for e-post|Ja|Ja|  
|Spor og angi angående for avtaler|Ja|Ja|  
|Spor og angi angående for kontakter|Ja|Ja|  
|Spor og angi angående for oppgaver|Nei|Ja|  
|Angi angående med ett klikk|Ja|Nei|  
|Viser mottakerens sammendrag|Ja|Nei|  
|Viser sammendraget av angående-posten i e-postmeldingen/avtalen|Ja|Nei|  
|Fungerer med [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)]|Ja|Nei|  
|Fungerer med [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for skrivebord|Ja|Ja|  
|Fungerer med [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for Mac|Ja|Nei|  
|Fungerer med telefoner|Ja|Nei|  
|Åpne og opprett [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]-poster direkte|Ja|Ja|  
|Ta i bruk egendefinerte skjemaer og forretningslogikk|Ja|Ja|  
|Arbeid frakoblet|Nei|Ja|  
|Ta i bruk e-postmaler|Ja|Ja|  
|Ta i bruk salgslitteratur|Ja|Ja|  
|Ta i bruk kunnskapsartikler|Ja|Ja|  
|Mulighet til å overvåke e-postmeldinger etter sending|Ja|Nei|  
|Sorter, filtrer, formater, grupper og kategoriser visninger|Nei|Ja|  
|Opprett dokument for utskriftsfletting i Word|Nei|Ja|  
|Kontroller feltsynkronisering|Nei|Ja|  
  
<a name="BKMK_Requirements"></a>   
## <a name="requirements"></a>Krav  
 Det følgende er påkrevd for å bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]:  
  
-   [!INCLUDE[pn_crm_online_2016_update](../includes/pn-crm-online-2016-update.md)] eller [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)]  
  
-   Synkronisering av innkommende e-post via synkronisering på serversiden. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)][Konfigurer synkronisering på serverside for e-post, avtaler, kontakter og oppgaver](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)  
  
-   Obligatoriske rettigheter beskrives nedenfor  
  
> [!NOTE]
>  Støttede konfigurasjoner og krav for [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)]-funksjoner er oppført i hele dokumentasjonen. Spesifikke konfigurasjoner som ikke er dokumentert, skal anses som ikke støttet.  
  
### <a name="required-privileges"></a>Obligatoriske rettigheter  
 [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] gir tilgang til [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] gjennom rettigheten **Bruk Dynamics 365-appen for Outlook**. Hvis brukeren ikke har denne rettigheten, mottar de følgende feil:  
  
> «Du har ikke fått tillatelse til å bruke denne appen. Kontakt systemansvarlig for å oppdatere innstillingene.»  
  
 Brukerne må også ha lese-/skrivetilgang for følgende enheter.  
  
 Forretningsadministrasjon-fanen:  
  
-   **Postboks**  
  
 Tilpassing-fanen:  
  
-   **Enhet**  
  
-   **Felt**  
  
-   **Relasjon**  
  
-   **Metadata for systemprogram**  
  
-   **Systemskjema**  
  
-   **Metadata for brukerprogram**  
  
-   **Vis**  
  
##### <a name="set-the-privileges-for-a-security-role"></a>Angi rettighetene for en sikkerhetsrolle  
  
1.  [!INCLUDE[proc_settings_security](../includes/proc-settings-security.md)]  
  
2.  Klikk på **Sikkerhetsroller**.  
  
3.  Velg en sikkerhetsrolle, og klikk deretter på **Forretningsadministrasjon**-fanen.  
  
4.  Se gjennom rettighetsinnstillingene for **Postboks** i **Enhet**-delen. Sikkerhetsrollen må ha Bruker eller høyere innstillinger.  
  
5.  Bekreft at **Bruk Dynamics 365-app for Outlook** er angitt til **Organisasjon** i **Personvernsrelaterte innstillinger**-inndelingen. Hvis ikke, så klikker du på**Bruk Dynamics 365-app for Outlook**.  
  
### <a name="supported-configurations-with-microsoft-exchange"></a>Støttede konfigurasjoner med Microsoft Exchange  
 Fra og med [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)]kan du bruke appen med enhver kombinasjon av [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] eller [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)] og [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)] eller [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (lokal), inkludert hybride konfigurasjoner. Dette betyr at du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] i én av følgende konfigurasjoner:  
  
|||  
|-|-|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (lokalt)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (lokalt)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
  
> [!NOTE]
>  Hvis du bruker [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)], må du godkjenne med IFD-godkjenning som beskrives nedenfor.  
  
### <a name="supported-browsers-for-outlook-on-the-web"></a>Støttede nettlesere for Outlook på nettet  
 Du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] med [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] på følgende nettlesere:  
  
-   [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)] eller [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)]  
  
     Følgende konfigurasjon støttes:  
  
    -   Beskyttet modus er aktivert for **Internett**-sikkerhetssonen. Slik aktiverer du Beskyttet modus: i IE 10 eller 11 går du til **Verktøy** > **Alternativer for Internett** > **Sikkerhet-fanen** > **Internett**.  
  
    -   Beskyttet modus er aktivert for **Lokalt intranett**-sikkerhetssonen. Slik aktiverer du Beskyttet modus: i IE 10 eller 11 går du til **Verktøy** > **Alternativer for Internett** > **Sikkerhet-fanen** > **Lokalt internett**.  
  
    -   Nettadressen for [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)] befinner seg i listen over klarerte nettsteder for **Lokalt intranett**-sikkerhetssonen. I IE 10 or 11 går du til **Verktøy** > **Alternativer for internett** > **Sikkerhet-fanen** > **Lokalt intranett** > **Nettsteder** > **Avansert**.  
  
-   [!INCLUDE[tn_Google_Chrome](../includes/tn-google-chrome.md)] (nyeste versjon) på [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]  
  
-   [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] (nyeste versjon) på [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_Safari](../includes/tn-safari.md)] (versjon 9 eller versjon 10) på Mac eller OSX  
  
### <a name="supported-operating-systems-for-outlook-on-the-desktop"></a>Støttede operativsystemer for Outlook på skrivebordet  
 Du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] på disse versjonene av [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for skrivebordet:  
  
-   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2013 og [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016.  
  
-   ’[!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for Mac*.  
  
     *[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] versjon 15.0.847.32 eller nyere kreves.  
  
### <a name="supported-mobile-devices"></a>Støttede mobile enheter  
 Du kan bruke [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] med [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] i mobilleseren på følgende telefoner og operativsystemer:  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_iphone](../includes/tn-iphone.md)]-enheter som kjører iOS-versjon 8, 9 eller 10.  
  
-   [!INCLUDE[tn_android](../includes/tn-android.md)]-telefoner som kjører [!INCLUDE[tn_android](../includes/tn-android.md)] 4.4 (KitKat) eller 5.0 (Lollipop), 6 (Marshmallow) eller 7 (Nougat).  
  
-   [!INCLUDE[pn_windows_phone](../includes/pn-windows-phone.md)]-enheter som kjører [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)] eller [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)].  
  
### <a name="supported-clients-per-feature"></a>Støttede klienter per funksjon  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]-funksjonene som støttes avhenger av klienten du kjører. Den følgende tabellen oppsummerer hvilke funksjoner som støttes for hver klient/konfigurasjon av [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] og [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)].  
  
 ![Klienter som støttes for hver funksjon i Dynamics 365-app for Outlook](media/clients-supported-for-each-dynamics-365-app-for-outlook-feature.png "Klienter som støttes for hver funksjon i Dynamics 365-app for Outlook")  
  
 (1)  [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] støtter [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)], [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)], [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 9, [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 10, [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] og [!INCLUDE[tn_chrome](../includes/tn-chrome.md)].  
  
 (2)  [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)]for mobile enheter støtter [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)], [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)], [!INCLUDE[tn_ios](../includes/tn-ios.md)] 8, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 9, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 10, [!INCLUDE[tn_android](../includes/tn-android.md)] KitKat (4.4), [!INCLUDE[tn_android](../includes/tn-android.md)] Lollipop, [!INCLUDE[tn_android](../includes/tn-android.md)] Marshmallow og [!INCLUDE[tn_android](../includes/tn-android.md)] Nougat.  
  
 (3)  Sporing av e-post i skrivemodus og sporingstilordninger krever [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2013 CU14 eller [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2016.  
  
 (4)  Sporing av kontakter støttes bare på [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)]2016 CU3 og [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.6741.1000 og nyere.  
  
 (5)  Tillegging av e-postmaler, kunnskapsstyringsartikler og salgslitteratur støttes ikke i [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] for mobile enheter.  
  
 (6)  Støttes bare på [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.7426.1049 og nyere.  
  
 (7)  Støttes bare på 16.0.6741.1000 og nyere.  
  
> [!NOTE]
>  Nettbrett støttes ikke for øyeblikket (kommer i CY2017).  
  
 [Les mer informasjon om støttede klienter i denne bloggen: Støttematrise for Dynamics 365-app for Outlook](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)  
  
### <a name="supported-servers"></a>Støttede servere  
 Serverkravene [for å bruke Office-tilleggsprogrammer](https://dev.office.com/docs/add-ins/overview/requirements-for-running-office-add-ins) er [!INCLUDE[pn_Exchange_Server_2013_short](../includes/pn-exchange-server-2013-short.md)], [!INCLUDE[pn_exchange_server_2016_short](../includes/pn-exchange-server-2016-short.md)] eller [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)].  
  
### <a name="supported-languages"></a>Støttede språk  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] støtter følgende språk:  
  
||||  
|-|-|-|  
|Bulgarsk (Bulgaria) – 1026|Hindi (India) – 1081|Portugisisk (Portugal) – 2070|  
|Kinesisk (Folkerepublikken Kina) – 2052|Ungarsk – 1038|Rumensk – 1048|  
|Kinesisk (Taiwan) – 1028|Indonesisk – 1057|Russisk – 1049|  
|Kroatisk (Kroatia) – 1050|Italiensk – 1040|Serbisk – 2074|  
|Tsjekkisk (Tsjekkia) – 1029|Japansk – 1041|Slovakisk - 1051|  
|Dansk – 1030|Kasakhisk – 1087|Slovensk – 1060|  
|Nederlandsk – 1043|Koreansk – 1042|Spansk – 3082|  
|Engelsk – 1033|Latvisk – 1062|Svensk – 1053|  
|Estisk – 1061|Litauisk – 1063|Thai – 1054|  
|Finsk – 1035|Malaysisk – 1086|Tyrkisk – 1055|  
|Fransk – 1036|Norsk – 1044|Ukrainsk – 1058|  
|Tysk – 1031|Polsk – 1045|Vietnamesisk – 1066|  
|Gresk – 1032|Portugisisk (Brasil) – 1046||  
  
<a name="BKMK_Deploy"></a>   
## <a name="deploy-dynamics-365-app-for-outlook"></a>Distribuer Dynamics 365-app for Outlook  
 Etter at du har konfigurert [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] og angitt de nødvendige tillatelsene, kan du sende [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] til noen eller alle brukerne, eller du kan be brukerne installere dette selv ved behov.  
  
> [!NOTE]
>  Hvis du er på [!INCLUDE[pn_dyn_365_op](../includes/pn-dyn-365-op.md)], kan du se inndelingen nedenfor:  [Slik distribuerer du til lokale Dynamics 365-brukere](#BKMK_DeployOnprem)  
  
#### <a name="to-push-the-app-to-users"></a>Slik sender du appen til brukerne  
  
1.  Gå til **Innstillinger** >  **Dynamics 365-app for Outlook**.  
  
2.  Merk av for **Legg til appen automatisk i [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]** på skjermen **Komme i gang med Dynamics 365-app for Outlook**, under **Legg til for kvalifiserte brukere** (det kan hende du må klikke på **Innstillinger** hvis du åpner denne skjermen for andre gang og videre), hvis du ønsker at brukerne skal få appen automatisk. Hvis en bruker har de nødvendige tillatelsene og e-posten er synkronisert gjennom [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)], trenger du ikke gjøre noe mer enn å sende appen til dem. Hvis du for eksempel legger til de nødvendige tillatelsene i Selger-rollen, og deretter tilordner denne rollen til en ny bruker, går de appen automatisk.  
  
3.  Gjør ett av følgende:  
  
    -   Hvis du vil sende appen til kvalifiserte brukere, klikker du på **Legg til for kvalifiserte brukere**.  
  
    -   Hvis du vil sende appen til enkelte brukere, velger du disse brukerne i listen, og klikker deretter på **Legg til app i Outlook**.  
  
    > [!TIP]
    >  Hvis listen viser at en bruker venter eller ikke har blitt lagt til, kan du klikke på **Lær mer**-koblingen ved siden av brukeren. Da ser du mer informasjon om statusen.  
  
4.  Når du er ferdig, klikker du på **Lagre**.  
  
#### <a name="to-have-users-install-the-app-themselves"></a>La brukerne installere appen selv  
  
1.  Brukerne klikker på **Settings**-knappen ![Innstillinger-knapp](media/mp-ua-r16-settings.png "Innstillinger-knapp"), og klikker deretter på **Apper for Dynamics 365**.  
  
2.  Brukerne klikker på **Legg til app [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]** i **Apper for Dynamics 365**-skjermen, under **[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]**.  
  
> [!NOTE]
>  Brukerne kan også deaktivere eller fjerne tilleggprogrammet selv, ved behov. Hvis du vil ha mer informasjon, kan du se [Brukerveiledning for Dynamics 365-app for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
<a name="BKMK_DeployOnprem"></a>   
## <a name="to-deploy-to-dynamics-365-on-premises-users"></a>Slik distribuerer du til lokale Dynamics 365-brukere  
 Følg denne fremgangsmåten hvis du bruker Dynamics 365 lokalt.  
  
-   Konfigurer Dynamics 365-server for Internett-vendt distribusjon. Se [Konfigurer IFD for Microsoft Dynamics 365](https://technet.microsoft.com/library/dn609803.aspx).  
  
-   Hvis du kobler til Exchange lokalt, konfigurerer du OAuth-leverandøren og registrerer klientapper. Se [Konfigurer Windows Server 2012 R2 for Dynamics 365-programmer som bruker OAuth](https://technet.microsoft.com/library/hh699726.aspx).  
  
<a name="BKMK_Troubleshoot"></a>   
## <a name="troubleshooting-installation-problems"></a>Feilsøk installasjonsproblemer  
 Hvis du eller brukerne har problemer med å installere [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)], kan det være fordi [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postboksen for øyeblikket er knyttet til en annen [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)]-organisasjon. En [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postboks (e-postadresse) kan bare synkronisere avtaler, kontakter og oppgaver med én organisasjon, og en bruker som tilhører den organisasjonen, kan bare synkronisere avtaler, kontakter og oppgaver med én [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postboks.  Du kan overskrive innstillingen som er lagret i [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)] hvis du ønsker å endre den primære synkroniseringsorganisasjonen. Hvis du vil ha mer informasjon, kan du se [denne KB-artikkelen](https://support.microsoft.com/en-gb/help/3211627/incomingemailrejected-error-when-attempting-to-install-dynamics-365-app-for-outlook).  
  
<a name="BKMK_Explore"></a>   
## <a name="explore-the-users-guide-and-train-your-users"></a>Utforsk brukerveiledningen og instruer brukerne dine  
 Hvis du vil lære hvordan du bruker [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)], [ kan du se Brukerveiledning Dynamics 365-app for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
 ![Side i brukerveiledningen for Dynamics 365-app for Outlook](media/dynamics-365-app-for-outlook-user-s-guide-page.png "Side i brukerveiledningen for Dynamics 365-app for Outlook")  
  
## <a name="see-also"></a>Se også  
 [Brukerveiledning for Dynamics 365-app for Outlook](http://go.microsoft.com/fwlink/p/?LinkID=613099)   
 [Les mer informasjon om støttede klienter i denne bloggen: Støttematrise for Dynamics 365-app for Outlook](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)   
 [Konfigurer synkronisering på serverside for e-post, avtaler, kontakter og oppgaver](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)   
 [Legg til brukere, lisenser og sikkerhetsroller](http://msdn.microsoft.com/en-us/23612155-f92d-4871-a109-186419d5c19d)   
 [Legg til interoperasjonsfunksjoner til Microsoft Dynamics 365 (på nett)](../DocSets/CRMIGv9_Admin/Toc/Add%20interoperation%20features%20to%20Microsoft%20Dynamics%20365%20\(online\).md)