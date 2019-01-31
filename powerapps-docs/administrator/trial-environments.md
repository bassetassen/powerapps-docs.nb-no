---
title: Prøveversjonsmiljøer | Microsoft Docs
description: Få tidlig tilgang til funksjoner med forhåndsversjonsprogrammet for PowerApps
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 01/09/2019
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: bd05c4c1251058d464034de71d9b1c287e714190
ms.sourcegitcommit: 170deba334c922157bbb826c795bed3fa858b85e
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 01/10/2019
ms.locfileid: "54196144"
---
# <a name="about-trial-environments"></a>Om prøveversjonsmiljøer

For øyeblikket kan du opprette to typer Common Data Service (CDS) for Apps-miljøer: Prøveversjon eller produksjon. Et prøveversjonsmiljø er nyttig for å prøve ut Dynamics 365 for Customer Engagement-apper uten kostnader. Prøveversjonsmiljøer utløper etter 30 dager.

Åpne **Miljøer**-siden for å se hvilke miljøer du har, og den kommende utløpsdatoen for prøveversjonsmiljøer:

> [!div class="mx-imgBorder"] 
> ![PowerApps-miljøer](media/powerapps-environments75b.png "PowerApps-miljøer")

## <a name="convert-a-trial-environment-to-production"></a>Konverter et prøveversjonsmiljø til produksjon

Mens du bruker prøveversjonsmiljøet, hvis du opprettet ressurser som du vil beholde i lenger enn 30 dager, kan du konvertere prøveversjonen til et produksjonsmiljø.

Hvis du vil konvertere til et produksjonsmiljø, må disse kriteriene være oppfylt:

**En passende PowerApps-plan**. En plan som gjør det mulig å opprette produksjonsmiljøer, for eksempel PowerApps Plan 2. Se [Velg den riktige planen for teamet ditt](https://powerapps.microsoft.com/pricing/) for informasjon om PowerApps-planer som inkluderer produksjonsmiljøer. Se [Hvordan finner jeg planene mine](#how-do-i-identify-my-plans) for å velge PowerApps-planer.
**Tilgjengelig produksjonskvoter**. Det finnes et fast antall produksjonsmiljøer som du kan opprette med planen din. Med PowerApps Plan 2 kan du for eksempel opprette to produksjonsmiljøer. Hvis du allerede har opprettet to produksjonsmiljøer, kan ikke du opprette flere før du sletter et. Hvis du vil ha mer informasjon, kan du se [Oppretting av miljø](environments-overview.md#creating-an-environment).

Følg disse trinnene for å konvertere et prøveversjonsmiljø til et produksjonsmiljø:

1. Gå til [https://admin.powerapps.com/environments](https://admin.powerapps.com/environments), og logg på som administrator.
 
2. Åpne **Miljøer**-siden, og velg prøveversjonsmiljøet du vil konvertere til produksjon:

    > [!div class="mx-imgBorder"] 
    > ![Velg prøveversjonsmiljø](media/powerapps-environments75b-select-trial.png "Velg prøveversjonsmiljø")

3. Velg **Konverter** på **Detaljer**-fanen:

    > [!div class="mx-imgBorder"] 
    > ![Velg Konverter](media/powerapps-trial-select-convert.png "Velg Konverter")

4. Velg **Bekreft**:

    > [!div class="mx-imgBorder"] 
    > ![Velg Bekreft](media/powerapps-trial-select-confirm.png "Velg Bekreft")

Hvis miljøet har en database, kan det ta flere timer å konvertere til et produksjonsmiljø. Du kan overvåke fremdriften gjennom varselet på **Detaljer**-fanen:

  > [!div class="mx-imgBorder"] 
  > ![Konvertering har startet](media/powerapps-trial-conversion-started.png "Konvertering har startet")

## <a name="frequently-asked-questions"></a>Ofte stilte spørsmål

### <a name="who-can-convert-a-trial-environment-to-a-production-environment"></a>Hvem kan konvertere et prøveversjonsmiljø til et produksjonsmiljø?

Du må oppfylle følgende kriterier for å konvertere et prøveversjonsmiljø til et produksjonsmiljø:

**Ha en passende PowerApps-plan**. Du trenger en plan som gjør det mulig å opprette produksjonsmiljøer, for eksempel PowerApps Plan 2. Se [Velg den riktige planen for teamet ditt](https://powerapps.microsoft.com/pricing/) for informasjon om PowerApps-planer som inkluderer produksjonsmiljøer. Se [Hvordan finner jeg planene mine](#how-do-i-identify-my-plans) for å velge PowerApps-planer.
**Ha en tilgjengelig produksjonskvote**. Det finnes et fast antall produksjonsmiljøer som du kan opprette med planen din. Med PowerApps Plan 2 kan du for eksempel opprette to produksjonsmiljøer. Hvis du allerede har opprettet to, kan ikke du opprette flere før du sletter et.

### <a name="what-if-i-dont-have-available-quota-for-production-environments"></a>Hva om jeg ikke har en tilgjengelig kvote for produksjonsmiljøer?

Be global administrator for Office 365 eller leieradministrator for Azure Active Directory (Azure AD) om å:
- tilordne PowerApps Plan 2 til deg. 
- finne en annen bruker som har en tilgjengelig kvote for produksjonsmiljøer.

Du kan også kjøpe en PowerApps-plan.

### <a name="can-every-office-365-global-admin-or-azure-ad-tenant-admin-convert-a-trial-environment-to-a-production-environment"></a>Kan alle globale administratorer for Office 365 eller leieradministratorer for Azure AD konvertere et prøveversjonsmiljø til et produksjonsmiljø?

Nei. Globale administratorer og Azure AD-leieradministratorer må ha tilgjengelige kvoter for produksjonsmiljøer for å kunne konvertere et prøveversjonsmiljø til et produksjonsmiljø.

### <a name="is-there-a-way-to-recover-a-deleted-trial-environment"></a>Er det mulig å gjenopprette et slettet prøveversjonsmiljø?

Vi kan ikke garantere gjenoppretting av et slettet prøveversjonsmiljø, men vi gjør vårt beste for å gjenopprette det innen 7 dager etter sletting. Vi kan ikke gjenopprette miljødatabasen, men vi kan gjenopprette apper (opprettet med PowerApps) og flyter.

### <a name="how-can-i-retain-my-data-and-resources-if-i-dont-have-a-way-to-convert-the-trial-environment-to-a-production-environment"></a>Hvordan kan jeg beholde dataene og ressursene mine hvis jeg ikke har en metode for å konvertere prøveversjonsmiljøet til et produksjonsmiljø?

Du kan eksportere ressursene og dataene til et annet miljø. Hvis du vil beholde dem i en lengre periode, anbefaler vi at du oppretter et produksjonsmiljø eller et individuelt miljø (med PowerApps Community Plan) og eksporterer ressursene dine til dette miljøet. 

Her er noen retningslinjer for å eksportere ressurser.

|Ressurstypen i miljøet  |Hvordan eksporterer jeg det?  |
|---------|---------|
|Apper (lerret og modelldrevne) og flyter     |Du kan bruke [pakking](environment-and-tenant-migration.md) til å eksportere apper og flyter fra et miljø.         |
|Data i databasen (Common Data Service (CDS) for Apps-miljøet)     |Du har flere alternativer:<br/><ul><li>[Eksporter til Excel](../user/export-data-excel.md) og lagre dataene. Du kan [importere dataene](../user/import-data.md) i et annet miljø.</li><br/><li>Du kan bruke [dataintegreringstjenester](data-integrator.md) og API-er til å eksportere data til et annet miljø.</li></ul> |

Vi sletter prøveversjonsmiljøer hvis det ikke har vært aktivitet i miljødatabasene på 30 dager.

### <a name="how-can-i-create-a-production-or-an-individual-environment"></a>Hvordan kan jeg opprette et produksjonsmiljø eller et individuelt miljø?

Du må ha en PowerApps-plan som gir mulighet til oppretting av produksjonsmiljøer. Hvis du vil ha mer informasjon, kan du se [Oppretting av miljø](environments-overview.md#creating-an-environment).

Du kan opprette et individuelt miljø ved å registrere deg for [PowerApps Community Plan](https://powerapps.microsoft.com/communityplan/). Vær oppmerksom på at det finnes begrensninger på deling av apper i individuelle miljøer – disse miljøene er ment for personlig bruk.

### <a name="how-do-i-identify-my-plans"></a>Hvordan finner jeg ut om planene mine?

Hvis du vil fastslå planene dine, velger du **tannhjul**-ikonet i øvre høyre hjørne på PowerApps-nettstedet, og deretter velger du **Planer**.

> [!div class="mx-imgBorder"] 
> ![Velg planer](media/powerapps-plans.png "Velg planer")

### <a name="see-also"></a>Se også
[Å admnistrere miljøer i PowerApps](environments-administration.md)<br/>
[Oversikt over miljøer](environments-overview.md)<br/>
[Velg de rette planene for teamet ditt](https://powerapps.microsoft.com/pricing/)<br/>
[Lisensieringsoversikt](pricing-billing-skus.md)<br/>
