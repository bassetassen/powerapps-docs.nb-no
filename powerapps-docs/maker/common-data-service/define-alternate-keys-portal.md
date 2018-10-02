---
title: Definere alternative nøkler ved hjelp av PowerApps-portalen | MicrosoftDocs
description: Finn ut hvordan du definerer alternative nøkler ved hjelp av PowerApps-portalen.
ms.custom: ''
ms.date: 05/31/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-alternate-keys-using-powerapps-portal"></a>Definere alternative nøkler ved hjelp av PowerApps-portalen

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gir en enkel måte å vise og opprette alternative nøkler for enheter med Common Data Service for Apps.

Portalen gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. <br />Mer informasjon: 
- [Definere alternative nøkler for å referere til oppføringer](define-alternate-keys-reference-records.md)
- [Definere alternative nøkler ved hjelp av løsningsutforskeren](define-alternate-keys-solution-explorer.md)

## <a name="view-alternate-keys"></a>Vise alternative nøkler

1. I [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) velger du utformingsmodusen **Modelldrevet** eller **Lerret**.
2. Velg **Data** > **Enheter**, og velg enheten du vil vise.
3. Velg **Nøkler** for å vise en liste over alle alternative nøkler som er definert.

    ![Vise alternative nøkler](media/view-alternate-keys-portal.png)

## <a name="create-an-alternate-key"></a>Opprette en alternativ nøkkel

1. Når du [viser alternative nøkler](#view-alternate-keys), velg **Legg til-tasten**.
2. Bruk panelet til å angi et **visningsnavn**, og velg feltene du vil bruke til å opprette alternative nøkkelen.

    **Navn**-feltet fylles ut basert på visningsnavnet.

    ![Eksempel på definisjon av alternativ nøkkel](media/alternate-key-account-number-sic-code.png)

1. Velg **Fullført** for å lukke panelet.
2. Klikk **Lagre enhet** for å opprette den alternative nøkkelen.

> [!NOTE]
> Den alternative nøkkelen er ikke tilgjengelig umiddelbart. En systemjobb startes når du lagrer enheten for å opprette databaseindeksene for å støtte den alternative nøkkelen.

## <a name="delete-an-alternate-key"></a>Slette en alternativ nøkkel

Når du [viser alternative nøkler](#view-alternate-keys), velger du nøkkelen du vil slette, og velger **Slett-tasten** fra kommandolinjen.

### <a name="see-also"></a>Se også

[Definere alternative nøkler for å referere til oppføringer](define-alternate-keys-reference-records.md)<br />
[Definere alternative nøkler ved hjelp av løsningsutforskeren](define-alternate-keys-solution-explorer.md)<br />
[Dokumentasjon for utviklere: Definere alternative nøkler for en enhet](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)
