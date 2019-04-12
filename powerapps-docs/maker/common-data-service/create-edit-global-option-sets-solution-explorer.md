---
title: Opprette og redigere globale alternativsett for Common Data Service ved hjelp av løsningsutforskeren | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-global-option-sets-for-common-data-service-using-solution-explorer"></a>Opprette og redigere globale alternativsett for Common Data Service ved hjelp av løsningsutforskeren

Løsningsutforskeren har én måte å opprette og redigere globale alternativsett for Common Data Service på.

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. <br />Mer informasjon: 
- [Opprette og redigere globale alternativsett for Common Data Service](create-edit-global-option-sets.md)
- [Opprette et alternativsett](custom-picklists.md)

## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på globale alternativsett du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for dette globale alternativsettet. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-global-option-sets"></a>Vise globale alternativsett

Med løsningsutforskeren åpen velger du **Alternativsett** under **Komponenter**.

![Vise globale alternativsett](media/view-global-option-sets-solution-explorer.png)

> [!NOTE]
> Noen globale systemalternativsett kan ikke tilpasses. Disse alternativene kan endres med oppdateringer eller nye versjoner, så det anbefales at du ikke bruker dem med mindre du er sikker på at dine behov er i tråd med måten Common Data Service bruker disse verdiene på.

## <a name="create-a-global-option-set"></a>Opprette et globalt alternativsett

> [!NOTE]
> Du trenger ikke opprette et globalt alternativsett før du bruker det i et egendefinert felt. Når du oppretter et nytt felt for alternativsett, har du muligheten til å opprette en nytt globalt alternativsett eller bruke et eksisterende. Se [Alternativer for felt for alternativsett](create-edit-field-solution-explorer.md#option-set-field-options)

Når du viser globale alternativsett, klikker du på **Ny** for å åpne et skjema for å definere det globale alternativsettet.

![Opprette globalt alternativsett](media/create-global-option-set-solution-explorer.png)

Skriv inn et **visningsnavn** som vil være synlig for personer med rollen systemadministrator eller systemtilpasser, som vil velge dette globale alternativsettet når de definerer nye felt som bruker det. Dette navnet vil ikke være synlig for dem som bruker appene.

En verdi for feltet **Navn** blir generert for deg basert på **visningsnavnet** du angir. Den inkluderer tilpassingsprefikset for løsningsutgiveren i konteksten for løsningen du arbeider i. Du kan endre den genererte delen av verdien for **Navn**-feltet før du lagrer.

Skriv inn en **beskrivelse** for det globale alternativsettet. 

> [!TIP]
> Bruk **beskrivelsen** til å forklare formålet med det globale alternativsettet. Denne verdien er ikke synlig for brukere av programmet, den er ment for andre brukere med rollen systemansvarlig eller systemtilpasser som vil vite hvorfor dette bestemte globale alternativsettet ble opprettet.

### <a name="configure-options"></a>Konfigurere alternativer

[!INCLUDE [cc_configure-option-set-options-solution-explorer](../../includes/cc_configure-option-set-options-solution-explorer.md)]

## <a name="edit-a-global-option-set"></a>Redigere et globalt alternativsett

Når du viser globale alternativsett, velger du alternativsettet du vil redigere for å åpne panelet for å redigere det.

Med unntak av å endre verdien for**Navn**-feltet eller **Verdi** som er tilordnet til et alternativ, kan du gjøre alle endringer du kan ved opprettelse av det globale alternativsettet.

[!INCLUDE [cc_remove-option-warning](../../includes/cc_remove-option-warning.md)]

## <a name="delete-a-global-option-set"></a>Slette et globalt alternativsett

Hvis du vil slette et globalt alternativsett, velger du mens du viser listen ![Slett-kommandoen](media/delete.gif) kommandoen på kommandolinjen.

> [!IMPORTANT]
> Hvis det globale alternativsettet er brukt av et felt, kan du ikke slette det før dette feltet er slettet.
  
### <a name="see-also"></a>Se også
 
[Opprette og redigere globale alternativsett for Common Data Service](create-edit-global-option-sets.md)<br />
[Opprette et alternativsett](custom-picklists.md)<br />
[Opprette og rediger felt](create-edit-fields.md)<br />
[Dokumentasjon for utviklere: Tilpasse globale alternativsett](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)
