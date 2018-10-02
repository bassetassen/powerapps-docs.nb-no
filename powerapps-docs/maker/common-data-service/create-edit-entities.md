---
title: Opprette og redigere enheter i Common Data Service for Apps | MicrosoftDocs
description: Finn ut hvordan du oppretter og redigerer enheter
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: fa04f99d-a5f9-48cb-8bfb-f0f50718ccee
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-entities-in-common-data-service-for-apps"></a>Opprette og redigere enheter i Common Data Service for Apps

Før du oppretter en egendefinert enhet, kan du vurdere om bruk av en eksisterende enhet vil oppfylle behovene dine. Mer informasjon: [Opprette nye metadata eller bruke eksisterende metadata?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Det finnes to utforminger som du kan bruke til å opprette en enhet:

|Designer| Beskrivelse|
|--|--|
|[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Inneholder en enkel strømlinjeformet opplevelse, men noen spesialinnstillinger er ikke tilgjengelige.<br />Mer informasjon: <br />[Opplæring: Opprette en egendefinert enhet som har komponenter i PowerApps](/powerapps/maker/common-data-service/create-custom-entity)<br />[Opprette og redigere enheter ved hjelp av PowerApps-portalen](create-edit-entities-portal.md)|
|Løsningsutforsker|Ikke så enkel, men den er mer fleksibel når kravene er mindre vanlige. <br />Mer informasjon: [Opprette og redigere enheter ved hjelp av løsningsutforskeren](create-edit-entities-solution-explorer.md)|

> [!NOTE]
> Du kan også opprette enheter i miljøet ved hjelp av følgende:
> - Importer en løsning som inneholder definisjonen av enheten.
> - Bruk Power Query til å opprette nye enheter og fylle dem med data. Mer informasjon: [Legge til data i en enhet i Common Data Service ved hjelp av Power Query](/powerapps/maker/common-data-service/data-platform-cds-newentity-pq).
> - Utviklere kan bruke [Metadata-tjenester](/powerapps/developer/common-data-service/use-web-services#metadata-services) til å skrive et program.


## <a name="entity-options-not-available-in-the-powerapps-portal"></a>Enhetsalternativer som ikke er tilgjengelige i PowerApps-portalen

Informasjonen i dette emnet hjelper deg med å velge hvilken utforming du kan bruke. Du kan bruke PowerApps-portalen til å opprette enheten med mindre du må oppfylle noen av følgende krav.

- Kontrollere tilpassingsprefikset

  En del av navnet på egendefinerte enheter du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md).

- Opprette organisasjonseid enhet

  Som standard oppretter PowerApps-portalen **Bruker eller team**-eide enheter. Bruk Løsningsutforsker til å angi eierskap for **organisasjonen**. Mer informasjon: [Enhetseierskap](types-of-entities.md#entity-ownership)

- Opprette en aktivitetsenhet

  En aktivitetsenhet er en spesiell type enhet som sporer handlinger som en oppføring kan opprettes for i en kalender. Mer informasjon: [Aktivitetsenheter](types-of-entities.md#activity-entities).

- Endre ikonene for en egendefinert enhet

  Som standard har alle egendefinerte enheter i modelldrevne apper de samme ikonene. Du kan opprette bildewebressurser for ikonene du vil ha for de egendefinerte enhetene. Mer informasjon: [Endre ikoner for egendefinerte enheter](../model-driven-apps/change-custom-entity-icons.md). 

- Endre noen av følgende egenskaper som bare kan aktiveres:

  [!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

- Endre noen av følgende egenskaper:

  <!-- Based on ../../includes/cc_entity-changeable-options-table.md 
Removed these:

  /|**Description**/|Provide a meaningful description of the purpose of the entity./|

  /|**Primary Image**/|System entities that support images will already have an **Image** field. You can choose whether to display data in this field as the image for the record by setting this field to **[None]** or **Default Image**.<br /><br /> For custom entities you must first create an image field. Each entity can have only one image field. After you create one, you can change this setting to set the primary image. More information: [Image fields](../maker/common-data-service/types-of-fields.md#image-fields) /|-->

  |Alternativ   |Beskrivelse  |
  |---------|---------|
  |**Tilgangsteam**|Du kan opprette teammaler for denne enheten. |
  |**Tillat hurtigoppretting**|Når du har opprettet og publisert et **Hurtigopprettingsskjema** for enheten, har personer muligheten til å opprette en ny post ved å bruke **Opprett**-knappen i navigasjonsruten. Mer informasjon: [Opprette og utforme skjemaer](../model-driven-apps/create-design-forms.md)<br /><br /> Når dette er aktivert for en egendefinert aktivitetsenhet, vil den egendefinerte aktiviteten være synlig i gruppen med aktivitetsentiteter når brukere bruker **Opprett**-knappen i navigasjonsruten. Siden aktiviteter ikke støtter hurtigopprettingsskjemaer, brukes imidlertid hovedskjemaet når du klikker ikonet for den egendefinerte enheten.|
  |**Områder som viser denne enheten**|I webprogrammet kan du velge ett av de tilgjengelige områdekartområdene for å vise denne enheten. Dette gjelder ikke for modelldrevne apper.|
  |**Sporing av endringer**|Når sporing av endringer er aktivert for organisasjonen, gjør dette at endringer i enhetsoppføringer kan registreres over tid. Når du aktiverer sporing av endringer for en enhet, blir sporing av endringer også aktivert for feltene. Du kan merke av eller fjerne merket for feltene du vil aktivere sporing av endringer for.|
  |**Endringssporing**|Aktiverer datasynkronisering på en god måte ved å registrere hvilke data som er endret etter at dataene opprinnelig ble hentet ut eller ble synkronisert sist.  |
  |**Farge**|Angi en farge som skal brukes for enheten i modelldrevne apper.|
  |**Dokumentbehandling**|Etter at andre oppgaver er utført for å aktivere dokumentbehandling for organisasjonen, vil aktivering av denne funksjonen gjøre det mulig for denne enheten å delta i integrasjon med SharePoint. |
  |**Duplikatregistrering**|Hvis duplikatregistrering er aktivert for organisasjonen, vil aktivering av dette la deg opprette regler for duplikatregistrering for denne enheten.|
  |**Aktiver for mobil**|Gjør denne enheten tilgjengelig for Dynamics 365 for telefoner og nettbrett-apper. Du har også muligheten til å gjøre denne enheten **skrivebeskyttet i mobil**.<br /><br /> Hvis skjemaene for en enhet krever en filtype som ikke støttes i Dynamics 365 for phones- og tablets-apper, bruker du denne innstillingen til å sikre at mobilappbrukere ikke kan redigere dataene for disse enhetene.|
  |**Aktiver for Mobile Express**|Gjør denne enheten tilgjengelig for Dynamics 365 for phones-appen.|
  |**Utskriftsfletting**|Brukere kan bruke denne enheten med utskriftsfletting.|
  |**Frakoblet funksjon for Dynamics 365 for Outlook**|Om dataene i denne enheten skal være tilgjengelige når Dynamics 365 for Outlook-programmet ikke er koblet til nettverket.|
  |**Leserute i Dynamics 365 for Outlook**|Om enheten skal vises i leseruten for Dynamics 365 for Outlook-appen.|
  |**Bruk tilpasset Hjelp**|Når det er aktivert, kan du angi en hjelpe-URL-adresse for å kontrollere hvilken side brukerne ser når de klikker på Hjelp-knappen i programmet. Bruk dette til å gi veiledning spesifikk for dine firmaprosesser for enheten.|


### <a name="see-also"></a>Se også

[Opprette og redigere enheter ved hjelp av løsningsutforskeren](create-edit-entities-solution-explorer.md)<br />
[Opplæring: Opprette en egendefinert enhet som har komponenter i PowerApps](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Redigere en enhet](edit-entities.md)<br />
[Dokumentasjon for utviklere: Opprette en egendefinert enhet](/dynamics365/customer-engagement/developer/org-service/create-custom-entity)
