---
title: Administrasjon av lisenser i organisasjonen i Microsoft Docs
description: Vanlige spørsmål og svar om lisenser, administrasjon og registrering for PowerApps av brukere i Office 365-tenanten
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: jamesol
ms.openlocfilehash: 5d6db5bded909387b5bc4ef15dc0bf6c163bfa7a
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/06/2018
ms.locfileid: "30998367"
---
# <a name="manage-licenses-in-my-org"></a>Å administere lisenser i organisasjonen
Dette emnet beskriver hvordan brukerne i organisasjonen kan bruke PowerApps, og hvordan du kan kontrollere tilgang til PowerApps-tjenesten.

## <a name="sign-up-for-powerapps"></a>Å registrere deg for PowerApps
### <a name="what-is-powerapps"></a>Hva er PowerApps?
Microsoft PowerApps gjør det mulig for brukere å opprette programmer for Windows-, iOS- og Android-mobilenheter. Ved hjelp av disse programmene, kan du opprette koblinger til vanlige SaaS-tjenester, inkludert Twitter, Office 365, Dropbox og Excel.

### <a name="how-do-users-sign-up-for-powerapps"></a>Hvordan registrerer brukere seg for PowerApps?
Det eneste alternativet for registrering av individuelle brukere i organisasjonen er via prøveversjonen av PowerApps-abonnement 2, som de kan registrere seg for via PowerApps-nettstedet:

##### <a name="option-1"></a>Alternativ 1
Brukere kan registrere seg ved å gå til [powerapps.microsoft.com](https://powerapps.microsoft.com), velge **Registrer deg gratis**, og deretter fullføre registreringsprosessen for PowerApps gjennom [portal.office.com](https://portal.office.com/Start?sku=powerapps).

##### <a name="option-2"></a>Alternativ 2
Brukere kan registrere seg ved å gå til [powerapps.microsoft.com](https://powerapps.microsoft.com), velge **Logg på**, logge på med jobb- eller skolekontoen, og registrere seg for prøveversjonen av PowerApps-abonnement 2 ved å godta vilkårene for bruk av PowerApps.    

Når en bruker i organisasjonen registrerer seg for PowerApps, er denne brukeren automatisk tilordnet en lisens for PowerApps.

> [!NOTE]
> Brukere som registrerer seg for en prøvelisens i PowerApps, vises ikke i administrasjonsportalen for Office 365 som brukere av prøveversjonen av PowerApps-abonnement 2 (med mindre de har en annen lisens for Office 365, Dynamics 365 eller PowerApps).

Se [Selvbetjent registrering for PowerApps](../maker/signup-for-powerapps.md) for mer informasjon.

### <a name="how-can-users-in-my-organization-gain-access-to-powerapps"></a>Hvordan får brukere i organisasjonen tilgang til PowerApps?
Brukere i organisasjonen kan få tilgang til PowerApps på tre forskjellige måter:

* De kan enkeltvis registrere seg for en prøveversjon av PowerApps-abonnement 2 som beskrevet i inndelingen [Hvordan brukere registrerer seg for PowerApps](#how-do-users-sign-up-for-powerapps).
* Du kan tilordne en PowerApps-lisens til dem i Office 365-administrasjonsportalen.
* Brukeren har blitt tilordnet Office 365- og Dynamics 365-abonnementene som inkluderer tilgang til PowerApps-tjenesten. Se [Prissiden for PowerApps](https://powerapps.microsoft.com/pricing) for en liste over Office 365- og Dynamics 365-abonnementer som inkluderer funksjoner for PowerApps.

### <a name="can-i-block-users-in-my-organization-from-signing-up-for-powerapps"></a>Kan jeg blokkere brukere i organisasjonen fra registrering for PowerApps?
Alle kan prøve ut funksjonene i Microsoft PowerApps-abonnement 2 i 30 dager, og det påløper ingen kostnader, som beskrevet i [Hvordan brukere registrerer seg for PowerApps](#how-do-users-sign-up-for-powerapps)-inndelingen.  Dette alternativet er tilgjengelig for alle brukere i en tenant, og kan ikke deaktiveres av en administrator.  Etter at brukerens prøveversjon har utløpt, vil brukeren miste tilgang til funksjonene i PowerApps-abonnement 2.  

Hvis en person registrerer seg for en 30-dagers prøveversjon av Microsoft PowerApps-abonnement 2, og du velger å ikke støtte dem i din organisasjon, påløper det ingen kostnader for bedriften. Når en person registrerer seg for Microsoft PowerApps, blir dette en relasjon mellom enkeltpersonen og Microsoft direkte. På samme måte som for en hvilken som helst offentlig skytjeneste fra Microsoft, for eksempel Bing, Wunderlist, OneDrive eller Outlook.com, og dette betyr ikke på noen måte at tjenesten tilbys av organisasjonen din.

Til slutt, hvis firmaet ønsker å begrense bruken av utelukkende organisatoriske data i Microsoft PowerApps, er dette mulig via policyer for hindring av datatap (DLP). Hvis du vil ha mer informasjon, kan du se [Policyer for hindring av datatap](prevent-data-loss.md).

## <a name="administration-of-powerapps"></a>Administrasjon av PowerApps
### <a name="why-has-the-powerapps-icon-appeared-in-the-office-365-app-launcher"></a>Hvorfor har PowerApps-ikonet dukket opp i startprogrammet for Office 365?
Microsoft PowerApps er en grunnleggende del av Office 365-programserien og er aktivert som en tjeneste som del av eksisterende Office 365 SKU-er. Nå som brukere overalt i verden kan bruke Microsoft PowerApps, vises det i Alle apper i startprogrammet for dem. Se [Lisensieringsoversikt](pricing-billing-skus.md) for å forstå hvilke Office 365-SKU-er som nå inkluderer PowerApps.

Se inndelingen nedenfor hvis du vil fjerne PowerApps-flisen fra Alle apper som standard.

### <a name="how-do-i-remove-powerapps-from-existing-users"></a>Hvordan fjerner jeg PowerApps fra eksisterende brukere?
Hvis en bruker ble tilordnet en lisens for PowerApps-abonnement 1 eller PowerApps-abonnement 2, kan du utføre følgende trinn for å fjerne PowerApps-lisensen for denne brukeren:

1. Gå til [Administrasjonsportalen for Office 365](https://portal.microsoftonline.com/).

2. I navigasjonsfeltet til venstre velger du **Brukere**, og deretter velger du **Aktive brukere**.

3. Finn brukeren du vil fjerne lisensen for, og velg deretter navnet.

4. Velg **Rediger** i detaljruten for brukeren i **Produktlisenser**-delen.

5. Finn lisensen som heter **Microsoft PowerApps-abonnement 1** eller **Microsoft PowerApps-abonnement 2**, sett veksleknappen til **Av** og velg deretter **Lagre**.

    ![](./media/signup-question-and-answer/remove-license.png)

Hvis en bruker har tilgang til PowerApps gjennom sin lisens for Office 365- og Dynamics 365-abonnementet, kan du deaktivere tilgangen deres til PowerApps-tjenesten ved å gjøre følgende:

1. Gå til [Administrasjonsportalen for Office 365](https://portal.microsoftonline.com/).

2. I navigasjonsfeltet til venstre velger du **Brukere**, og deretter velger du **Aktive brukere**.

3. Finn brukeren du vil fjerne tilgang for, og velg deretter navnet.

4. Velg **Rediger** i detaljruten for brukeren i **Produktlisenser**-delen.

5. Utvid brukerens Office 365- eller Dynamics 365-lisens, deaktiver tilgang til tjenesten kalt **PowerApps for Office 365** eller **PowerApps for Dynamics 365** og velg deretter **Lagre**.

    ![](./media/signup-question-and-answer/remove-service-plan.png)

Massefjerning av lisenser er også mulig gjennom PowerShell. Se [Å fjerne lisenser fra brukerkontoer med Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx) for et detaljert eksempel.   Til slutt, ytterligere veiledning om massefjerning av tjenester i en lisens finner du på [Å deaktivere tilgang til tjenester med Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx).

Fjerning av PowerApps-lisenser eller -tjenester for en bruker i organisasjonen fører også til at PowerApps- og Dynamics 365-ikonene fjernes fra følgende plasseringer for denne brukeren:

* [Office.com](https://office.com)

    ![](./media/signup-question-and-answer/office-home.png)
* Startprogrammet for Office 365, «rute»

    ![](./media/signup-question-and-answer/office-waffle.png)

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data-using-powerapps"></a>Hvordan kan jeg begrense brukernes mulighet til å få tilgang til organisasjonens forretningsdata ved hjelp av PowerApps?
PowerApps lar deg opprette datasoner for forretningsdata og ikke-forretningsdata, som vist nedenfor.  Når disse policyene for hindring av datatap implementeres, blir brukere hindret fra å utforme eller kjøre PowerApps som kombinerer forretnings- og ikke-forretningsdata. Hvis du vil ha mer informasjon, kan du se [Policyer for hindring av datatap](prevent-data-loss.md).

![](./media/signup-question-and-answer/data-loss-prevention-policy.png)

### <a name="why-did-10000-licenses-for-microsoft-powerapps-show-up-in-my-office-365-tenant"></a>Hvorfor vises 10 000 lisenser for Microsoft PowerApps i Office 365-tenanten?
Brukere i organisasjonen er kvalifisert for å prøve ut Microsoft PowerApps-abonnement 2 i 30 dager som en kvalifisert organisasjon, og disse lisensene til prøveversjonene representerer tilgjengelig kapasitet for nye PowerApps-brukere i tenanten din. Det påløper ingen kostnader for disse lisensene. Det er spesielt to mulige årsaker til hvorfor du kanskje ser en kapasitet på 10 000 lisenser for prøveversjoner for PowerApps, som vises i Office 365-administrasjonsportalen:

* Hvis minst én bruker i tenanten din har deltatt i PowerApps offentlige forhåndsvisning som varte fra april 2016 til oktober 2016, vil du se 10 000 lisenser som er merket som «Microsoft PowerApps og logisk flyt»

    ![](./media/signup-question-and-answer/licenses_2.png)
* Hvis minst én bruker i tenanten har registrert seg for en prøveversjon av PowerApps-abonnement 2 ved å gå gjennom registrering av prøveversjonen (**Alternativ 1**), som er beskrevet i [Hvordan brukere registrerer seg for PowerApps](#how-do-users-sign-up-for-powerapps)-inndelingen, ser du 10 000 lisenser som er merket med «Microsoft Power-apper og flyt»

    ![](./media/signup-question-and-answer/licenses_1.png)

Du kan velge å tilordne flere lisenser til brukere selv gjennom Office 365-administrasjonsportalen, men vær oppmerksom på at dette er lisenser for prøveversjonen av Microsoft PowerApps-abonnement 2, og de vil utløpe 30 dager etter at de blir tilordnet en bruker.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Er dette gratis? Blir jeg belastet for disse lisensene?
Dette er gratis lisenser for prøveversjonen av Microsoft PowerApps-abonnement 2 i 30 dager, slik at brukerne kan prøve det ut.

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Hvordan vil dette endre måten jeg administrerer identiteter for brukerne på i organisasjonen i dag?
Hvis organisasjonen allerede har et eksisterende Office 365-miljø, og alle brukere i organisasjonen har Office 365-kontoer, endres ikke identitetsbehandlingen.

Hvis organisasjonen allerede har et eksisterende Office 365-miljø, men ikke alle brukerne i organisasjonen har Office 365-kontoer, oppretter vi en bruker i tenanten, og tilordner lisenser basert på brukerens e-postadresse tilknyttet skole eller arbeid. Dette betyr at antallet brukere du administrerer på et bestemt tidspunkt vil vokse etter hvert som brukerne i organisasjonen registrerer seg for tjenesten.

Hvis organisasjonen ikke har et Office 365-miljø som er koblet til e-postdomenet ditt, er det ingen endring i forhold til hvordan du administrerer identiteter. Brukere blir lagt til en ny, utelukkende skybasert brukerkatalog, og du vil ha mulighet til å overta som tenantadministrator og administrere dem.

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Hva er fremgangsmåten for å administrere en tenant opprettet av Microsoft for brukerne mine?
Hvis en tenant ble opprettet av Microsoft, kan du gjøre krav på, og administrere denne tenanten ved å gjøre følgende:

1. Bli med i tenanten ved å registrere deg for PowerApps ved hjelp av et e-postdomene som samsvarer med tenantdomenet du vil administrere. Hvis Microsoft eksempelvis opprettet contoso.com-tenanten, kan du bli med i tenanten med bruk av en e-postadresse som slutter med @contoso.com.
2. Gjør krav på administratorkontroll ved å kontrollere eierskap til domenet: Når du er i tenanten, kan du utpeke deg til administratorrollen ved å kontrollere domeneeierskapet. Hvis du vil gjøre dette, gjør du følgende:
3. Gå til [https://portal.office.com](https://portal.office.com/Start?sku=powerapps).
4. Velg startprogram-ikonet i hjørnet øverst til venstre, og velg deretter Administrator.
5. Les instruksjonene på **Bli administrator**-siden, og velg deretter **Ja, jeg vil være administrator**.  

> [!NOTE]
> Hvis dette alternativet ikke vises, er det allerede en Office 365-administrator på plass.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Hvis jeg har flere domener, kan jeg styre Office 365-tenanten som brukere legges til i?
Hvis du ikke gjør noe, opprettes en tenant for hver brukers e-postdomene og underdomene.

Hvis du vil at alle brukere skal være i samme tenant, uavhengig av e-postadresseutvidelsene:  

* Opprett en måltenant på forhånd eller bruk en eksisterende tenant. Legg til alle eksisterende domener og underdomener som du vil konsolidere i denne tenanten. Deretter vil alle brukere med e-postadresser som slutter på disse domenene og underdomenene automatisk bli med i måltenanten når de registrerer seg.

> [!IMPORTANT]
> Det er ingen støttet automatisk mekanisme for å flytte brukere på tvers av tenantene når de har blitt opprettet. Hvis du vil lære mer om å legge til domener i én enkelt Office 365-tenant, kan du se [Å legge til brukere og domener i Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).
