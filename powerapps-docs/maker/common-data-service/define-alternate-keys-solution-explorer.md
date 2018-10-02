---
title: Definere alternative nøkler ved hjelp av løsningsutforskeren | MicrosoftDocs
description: 'Lær hvordan du definerer alternative nøkler som kan brukes til å referere til oppføringer i Common Data Service for Apps, ved hjelp av løsningsutforskeren'
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
# <a name="define-alternate-keys-using-solution-explorer"></a>Definere alternative nøkler ved hjelp av løsningsutforskeren

Løsningsutforskeren har en måte for å vise og opprette alternative nøkler for Common Data Service for Apps.

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. <br />Mer informasjon: 
- [Definere alternative nøkler for å referere til oppføringer](define-alternate-keys-reference-records.md)<br />
- [Definere alternative nøkler ved hjelp av PowerApps-portalen](define-alternate-keys-portal.md)

## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på en alternativ nøkkel du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-alternate-keys"></a>Vise alternative nøkler

1. Med løsningsutforskeren åpen, under **Komponenter**, utvider du **Enheter** og velger enheten der du vil vise alternative nøkler.
2. Utvid enheten, og velg **Nøkler**.

    ![Vise alternative nøkler](media/view-alternate-keys-solution-explorer.png)

## <a name="create-an-alternate-key"></a>Opprette en alternativ nøkkel

1. Når du [viser alternative nøkler](#view-alternate-keys), velg **Ny**.
1. Angi **visningsnavnet** på skjemaet. **Navn**-feltet fylles ut automatisk basert på **visningsnavnet**. 
2. Fra listen **Tilgjengelige attributter** velger du hvert attributt og deretter **Legg til >** for å flytte attributtet til listen **Valgte attributter**.
    ![Opprette en alternativ nøkkel](media/create-alternate-key-solution-explorer.png)
1. Velg **OK** for å lukke skjemaet.

### <a name="optional-view-the-system-job-tracking-creation-of-indexes"></a>(Valgfritt) Vise systemjobbsporing under oppretting av indekser
1. Når du [viser alternative nøkler](#view-alternate-keys) etter at du har opprettet en ny alternativ nøkkel, du vil se en rad for nøkkelen du opprettet.
2. I kolonnen **Systemjobb** finner du en kobling til systemjobben som overvåker opprettingen av indeksene for å støtte den alternative nøkkelen. 
    
    Systemjobben har et navn som følger dette mønsteret: `Create index for {0} for entity {1}` der `0` er **visningsnavnet** for den alternative nøkkelen, og `1` er navnet på enheten.

    Koblingen til systemjobben vises ikke etter at en systemjobb er fullført. Mer informasjon: [Overvåke og administrere systemjobber](/dynamics365/customer-engagement/admin/monitor-manage-system-jobs)


## <a name="delete-an-alternate-key"></a>Slette en alternativ nøkkel

Når du [viser alternative nøkler](#view-alternate-keys), velg ![Slett](media/delete.gif).

### <a name="see-also"></a>Se også

[Definere alternative nøkler for å referere til oppføringer](define-alternate-keys-reference-records.md)<br />
[Definere alternative nøkler ved hjelp av PowerApps-portalen](define-alternate-keys-portal.md)<br />
[Dokumentasjon for utviklere: Definere alternative nøkler for en enhet](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)
