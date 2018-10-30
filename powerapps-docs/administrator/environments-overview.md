---
title: Oversikt over miljøer | Microsoft Docs
description: Finn ut mer om miljøer i PowerApps og hvordan du bruker dem
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 08/29/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: e160098075b78a0a4de98da9c9915d0bef26d183
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297332"
---
# <a name="environments-overview"></a>Oversikt over miljøer
Et miljø er et område der du kan lagre, administrere og dele organisasjonens forretningsdata, apper og flyter. De fungerer også som beholdere til å skille apper som kan ha ulike roller, sikkerhetskrav eller målgrupper. Måten du velger å dra nytte av miljøer på, avhenger av organisasjonen og appene du prøver å bygge. Eksempel:

* Du kan velge å bare utvikle apper i et enkelt miljø.
* Du kan opprette separate miljøer som grupperer test- og produksjonsversjonene av appene dine.
* Du kan opprette separate miljøer som samsvarer med bestemte grupper eller avdelinger i firmaet, hvorpå alle inneholder relevante data og apper for hver målgruppe.
* Du kan også opprette separate miljøer for forskjellige globale filialer av firmaet.  
* Få tidlig tilgang til de kommende PowerApps-funksjonene ved å delta i [forhåndsversjonsprogrammet for PowerApps](preview-environments.md).

## <a name="environment-scope"></a>Omfang av miljøet
Hvert miljø opprettes under en Azure AD-tenant, og ressursene kan bare åpnes av brukere i denne tenanten. Et miljø er også bundet til en geografisk plassering, for eksempel USA. Når du oppretter et program i et miljø, rutes appen bare til datasentre i denne geografiske plasseringen. Alle elementer som du oppretter i dette miljøet (inkludert tilkoblinger, gatewayer, flyter som bruker Microsoft Flow og så videre), er også bundet til plasseringen av det tilhørende miljøet.

Hvert miljø kan ha ingen eller én Common Data Service-database, som gir lagring for appene dine. Muligheten til å opprette en database for miljøet avhenger av lisensen du kjøper for PowerApps og tillatelsen din i dette miljøet. Se [Prisinformasjon](pricing-billing-skus.md) for mer informasjon.

Når du oppretter et program i et miljø, har denne appen kun tillatelse til å koble til datakildene som også er distribuert i det samme miljøet, inkludert tilkoblinger, gatewayer, flyter og Common Data Service-databaser.  La oss for eksempel anta et scenario der du har opprettet to miljøer med navnet «Test» og «Utvikling» og opprettet en Common Data Service-database i hvert av miljøene. Hvis du oppretter en app i «Test»-miljøet, har den bare tillatelse til å koble til «Test»-databasen, og den vil ikke kunne koble til «Utvikling»-databasen.

Det finnes også en prosess for å flytte ressurser mellom miljøer. Hvis du vil ha mer informasjon, kan du se [Overføre ressurser](environment-and-tenant-migration.md).

![](./media/environments-overview/Environments.png)

## <a name="environment-permissions"></a>Miljøtillatelser
Miljøer har to innebygde roller som gir tilgang til tillatelser i et miljø:

* Miljøadministratorrollen kan utføre alle administrative handlinger i et miljø, inkludert følgende:

    * Å legge til eller fjerne en bruker eller gruppe fra enten rollen som miljøadministrator eller miljøoppretter

    * Å klargjøre en Common Data Service-database for miljøet

    * Å vise og administrere alle ressurser som er opprettet i et miljø

    * Å angi policyer for hindring av datatap. Hvis du vil ha mer informasjon, kan du se [Policyer for hindring av datatap](prevent-data-loss.md).

    Når du har opprettet databasen i miljøet, kan du bruke Systemansvarlig-rollen i stedet for Miljøetadministrator-rollen.

* Miljøoppretter kan opprette ressurser i et miljø, inkludert apper, tilkoblinger, egendefinerte koblinger, gatewayer og flyter ved hjelp av Microsoft Flow.

Miljøopprettere kan også distribuere apper de bygger i et miljø for andre brukere i organisasjonen, ved å dele appen med individuelle brukere, sikkerhetsgrupper eller for alle brukere i organisasjonen. Du finner mer informasjon i [Å dele en app i PowerApps](../maker/canvas-apps/share-app.md).

Brukere eller grupper som er tilordnet til disse miljørollene, får ikke automatisk tilgang til miljødatabasen (hvis den finnes), og må gis tilgang separat av en eier av databasen. Hvis du vil ha mer informasjon, kan du se [Å konfigurere miljøsikkerhet](database-security.md).

Brukere eller sikkerhetsgrupper kan tilordnes til en av disse to rollene av en miljøadministrator fra [administrasjonssenteret for PowerApps][1]. Du finner mer informasjon i [Å administrere miljøer i PowerApps](environments-administration.md).

![](./media/environments-overview/EnvironmentRoles.png)

## <a name="the-default-environment"></a>Standardmiljøet
Ett enkelt standardmiljø blir automatisk opprettet av PowerApps for hver tenant og deles av alle brukerne i denne leietakeren. Når en ny bruker registrerer seg for PowerApps, legges vedkommende til automatisk med rollen Oppretter for standardmiljøet. Standardmiljøet opprettes i det nærmeste området til standardområdet for AAD-leietakeren.

> [!NOTE]
> Ingen brukere legges automatisk til med rollen Miljøadministrator for standardmiljøet. Du finner mer informasjon i [Å administrere miljøer i PowerApps](environments-administration.md).
>
>

Standardmiljøet er navngitt på følgende måte: «{Azure AD-leietakernavn} (standard)»

![](./media/environments-overview/DefaultEnvironment.png)

## <a name="production-and-trial-environments"></a>Produksjons- og prøveversjonsmiljøer
Du kan opprette miljøer for ulike formål. Hensikten med et prøveversjonsmiljø er å prøve ut miljøet og databasen med Common Data Service-opplevelsen. Det utløper etter bestemt periode. Du finner mer informasjon i [Å administrere miljøer i PowerApps](environments-administration.md).

## <a name="choosing-an-environment"></a>Å velge et miljø
Med lanseringen av miljøer vil du nå se en ny opplevelse når du kommer til [https://web.powerapps.com https://web.powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  Appene, tilkoblingene og andre elementer som er synlige i området filtreres nå, basert på det gjeldende miljøet som er valgt.  Det gjeldende miljøet er angitt i velgeren for miljøet nær høyre kant av toppteksten. Hvis du vil velge et annet miljø, kan du klikke eller trykke på velgeren, slik at en liste over tilgjengelige miljøer vises. Klikk eller trykk på det du vil åpne.

Et miljø vises i velgeren hvis du oppfyller én av følgende betingelser:

* Du er medlem av rollen som miljøadministrator for miljøet.
* Du er medlem av rollen som miljøoppretter for miljøet.
* Du er ikke en miljøadministrator eller miljøoppretter for miljøet, men du har fått bidragsytertilgang til minst én app i miljøet. Du finner mer informasjon i [del en app](../maker/canvas-apps/share-app.md). I dette tilfellet vil du ikke kunne opprette apper i dette miljøet. Du vil bare kunne endre eksisterende apper som har blitt delt med deg.

![](./media/environments-overview/EnvironmentPicker.png)

## <a name="creating-an-environment"></a>Å opprette et miljø
### <a name="who-can-create-environments"></a>Hvem kan opprette miljøer?
Lisensen fastsetter om du kan opprette miljøer.

| Lisens | Oppretting av miljøer er tillatt |
| --- | --- |
| PowerApps-abonnement 2 |√ (to produksjonsmiljøer og to prøveversjonsmiljøer)|
| Prøveversjon av PowerApps-abonnement 2 |√ (to prøveversjonsmiljøer)|
| PowerApps-abonnement 1 |x |
| Prøveversjon av PowerApps-abonnement 1 |x |
| Dynamics 365-abonnementer |x |
| Office 365-abonnementer |x |
| Dynamics 365-apper og Teams-abonnementer |x |


### <a name="where-can-environments-be-created"></a>Hvor kan miljøer opprettes?
Du vil kunne opprette nye miljøer fra [PowerApps.com][2] og fra [administrasjonssenteret for PowerApps][1]. Hvis du oppretter et miljø, blir du automatisk lagt til med rollen miljøadministrator for dette miljøet. Det finnes ikke noen grense for hvor mange miljøer du kan delta i som medlem av rollen miljøadministrator eller miljøoppretter. Du finner mer informasjon i [Å administrere miljøer i PowerApps](environments-administration.md). For instruksjoner om hvordan du oppretter et miljø, kan du se [Å opprette et miljø](create-environment.md).

![](./media/environments-overview/CreateEnvironmentDialog-New.png)


## <a name="managing-environments-for-your-organization"></a>Å administrere miljøer for organisasjonen din
I administrasjonssenteret for PowerApps kan du administrere miljøer du har opprettet, samt miljøer der du har blitt lagt til i rollen som miljøadministrator. Du kan utføre alle administrative handlinger i et miljø fra administrasjonssenteret, inkludert følgende:

* Legge til eller fjerne en bruker eller gruppe fra enten rollen miljøadministrator eller miljøoppretter.  Du finner mer informasjon i [Å administrere miljøer i PowerApps](environments-administration.md).
* Klargjøre en Common Data Service-database for miljøet. Hvis du vil ha mer informasjon, kan du se [Å opprette en Common Data Service-database](create-database.md).
* Å angi policyer for hindring av datatap. Hvis du vil ha mer informasjon, kan du se [Policyer for hindring av datatap](prevent-data-loss.md).
* Angi sikkerhetspolicyer for databasen (som åpen eller begrenset av databaseroller). Hvis du vil ha mer informasjon, kan du se [Å konfigurere miljøsikkerhet](database-security.md).
* Medlemmer av den globale administratorrollen for Azure AD-tenanten (inkluderer globale administratorer for Office 365) kan også administrere alle miljøer som er opprettet i leietakeren, og angi policyer for hele tenanten fra administrasjonssenteret for PowerApps.

<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://aka.ms/cdspreviewtoga
