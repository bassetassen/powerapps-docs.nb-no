---
title: Forhåndsversjonsmiljøer | Microsoft Docs
description: Få tidlig tilgang til funksjoner med forhåndsversjonsprogrammet for PowerApps
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
ms.openlocfilehash: e2c4c735827941b32ce5e019eb8d71e4328e4a7a
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297884"
---
# <a name="powerapps-preview-program"></a>Forhåndsversjonsprogrammet for PowerApps
PowerApps oppdaterer plattformen og funksjonene hver femte dag eller uke. Med forhåndsversjonsprogrammet for PowerApps får du tidlig tilgang til de kommende funksjoner og oppdateringene, før de blir gjort tilgjengelig i andre områder (hvor produksjonsapper for kunder distribueres). 

Med forhåndsversjonsprogrammet for PowerApps kan du:
- **Prøve, lære og teste kommende funksjoner**: Mange funksjoner rulles først ut som forhåndsversjoner i et par dager, slik at vi kan motta tilbakemeldinger. Ved å delta i et forhåndsversjonsprogram kan du finne ut av nye funksjoner tidligere og gi tilbakemeldinger. Du kan også dra rask nytte av de nye funksjonene så snart de er tilgjengelig i områdene der produksjonsappene opprettes.
- **Oppnå forretningskontinuitet ved å sikre at gjeldende apper fortsetter å fungere** med de kommende oppdateringene (vNext) av PowerApps.

## <a name="what-in-powerapps-is-available-for-preview"></a>Hva er tilgjengelig som forhåndsversjon i PowerApps?
Hvis du vil ha tilgang til funksjonene i PowerApps, må du befinne deg i forhåndsversjonsmiljøet. Du får mer informasjon om forhåndsversjonsmiljøet i den neste inndelingen.
For øyeblikket ruller vi ut forhåndsversjon for følgende scenarioer i PowerApps:
1. **Opprett apper**: Du kan opprette lerretbaserte apper ved bruk av neste versjon av PowerApps. Dette kan du gjøre ved å opprette apper i et forhåndsversjonsmiljø. Gjeldende begrensninger er at modelldrevne apper ikke kan bygges i forhåndsversjonsprogrammet – vi arbeider med saken.
2. **Administrer apper**: Du kan administrere og dele apper ved bruk av [PowerApps-nettportalen][2]. Hvis du vil ha tilgang til funksjonene for forhåndsversjonen, trenger du bare å befinne deg i et forhåndsversjonsmiljø. Da blir du omdirigert til forhåndsversjonen av [PowerApps-nettportalen][3].
3. **Spill av apper**: Du må spille av appene i et forhåndsversjonsmiljø ved bruk av nettspilleren. Når du gjør dette, blir du automatisk omdirigert til [forhåndsversjonen av nettspilleren][4]. Apper spilles av med vNext-versjon av PowerApps-nettspilleren. Gjeldende begrensninger er at PowerApps Mobile for iOS, Android og Windows for øyeblikket ikke er tilgjengelige som forhåndsversjon. Det kan hende at det ikke går an å spille av appene som ble opprettet i First Release-miljøet – vi arbeider med saken.
4. **Administrer PowerApps**: Administrasjonsopplevelser er tilgjengelige som forhåndsversjon ved bruk av [forhåndsversjonen av administrasjonssenter for PowerApps][1]

## <a name="how-to-get-early-access-to-the-upcoming-updates"></a>Hvordan får jeg tidlig tilgang til kommende oppdateringer?
Alle appene og tilknyttede ressurser lagres i et miljø for PowerApps. Tidlig tilgang til alle funksjonne til forhåndsversjonen er også tilgjengelige med et miljø som opprettes i et område hvor vNext (forhåndsversjon) er distribuert. Det finnes bare ett område for øyeblikket, **Forhåndsversjon (USA)**, som vist i bildet nedenfor:

![](./media/preview-environment/env3-preview.png)

Velg området for miljøet som **Forhåndsversjon (USA)**. Gi ditt samtykke til å delta i forhåndsversjonsprogrammet for å opprette miljøet, og få tilgang til neste versjon (vNext) av PowerApps.
Alle appene og de andre ressursene som opprettes i dette miljøet, har vNext-versjonen av plattformen (SaaS).

## <a name="how-to-learn-about-the-latest-updates"></a>Hvordan fant du ut om de nyeste oppdateringene?
Du kan se de nye funksjonene som er tilgjengelig som forhåndsversjon på [Hva er nytt i PowerApps][5]. Funksjonene som er tilgjengelig i forhåndsversjonen, har en «Forhåndsversjon»-kode.

## <a name="key-scenarios-to-test-with-the-preview-program"></a>Viktige scenarioer som du tester i forhåndsversjonsprogrammet
1. **Valider produksjonsappene med de kommende PowerApps-oppdateringene (vNext)**

   Det kan være greit å bekrefte produksjonsappene dine, for å se at de fungerer fint med de neste kommende oppdateringene på PowerApps. Du kan [kopiere][6] appene fra et produksjonsmiljø til et miljø i First Release, og spille av appene for å teste ut ulike scenarioer. Vær oppmerksom på at alle de andre nødvendige ressursene som CustomAPI, Flow og så videre også må flyttes sammen med dem. Dette oppretter bare enda en kopi av disse appene og de nødvendige ressursene. Du kan teste de nyeste oppdateringene ved å spille av en app, men du kan også gjøre det mens du redigerer og administrerer dem.
   
2. **Prøv de nye funksjonene som er tilgjengelig som forhåndsversjon**

   Vi lanserer mange nye funksjoner innledningsvis i **Forhåndsversjon (USA)**-området. Du kan prøve de nye funksjonene før de blir gjort tilgjengelig i resten av områdene (og dette kan påvirke produksjonsmiljøet).

## <a name="how-to-provide-feedback-to-the-product-team"></a>Hvordan gir du tilbakemeldinger til produktteamet?
Du kan gi dine tilbakemeldinger på [PowerApps-forumet][8] og kontakte [kundestøtte][9].

## <a name="what-are-the-known-issues-and-limitations"></a>Hva er kjente problemer og begrensninger?
1. **PowerApps-portalene og -klientene er ikke tilgjengelig som forhåndsversjon** 

   Det er bestemte funksjoner, tjenester og portaler som er tilgjengelig som forhåndsversjon:
   
   ![](./media/preview-environment/table.png)

2. **Få tilgang til apper opprettet i First Release-miljøet fra Desktop Studio i Windows**

   Som vi vente ovenfor, så er ikke Desktop Studio i Windows tilgjengelig som forhåndsversjon. Det kan derfor hende at oppretting og redigering av appene i forhåndsversjonsmiljøet ikke er kompatibelt med Desktop Studio, og at du får følgende feilmelding:
   
   ![](./media/preview-environment/error2.jpg)

   I disse tilfellene anbefaler vi deg å bruke Web Studio til å opprette eller redigere en app i forhåndsversjonsmiljøet.

3. **Databaser kan ikke opprettes i forhåndsversjonsområdet**

   Du kan for øyeblikket ikke opprette en database med Common Data Service for apper i et miljø i Forhåndsversjon (USA)-området – vi arbeider med saken.


<!--Reference links in article-->
[1]: https://preview.admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://preview.web.powerapps.com
[4]: https://preview.web.powerapps.com/webplayer
[5]: https://docs.microsoft.com/powerapps/maker/canvas-apps/release-notes
[6]: https://docs.microsoft.com/powerapps/administrator/environment-and-tenant-migration
[7]: https://preview.create.powerapps.com
[8]: https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1
[9]: https://powerapps.microsoft.com/support/

