---
title: Opprette og redigere én-til-mange- eller mange-til-én-relasjoner ved hjelp av PowerApps-portalen | MicrosoftDocs
description: Finn ut hvordan du oppretter én-til-mange- eller mange-til-én-relasjoner ved hjelp av PowerApps-portalen
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: powerapps
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
# <a name="create-and-edit-one-to-many-or-many-to-one-entity-relationships-using-powerapps-portal"></a>Opprette og redigere én-til-mange- eller mange-til-én-relasjoner ved hjelp av PowerApps-portalen

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gir en enkel måte å opprette og redigere 1:N- (én-til-mange) eller N:1-relasjoner (mange-til-én) for Common Data Service.

Portalen gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. Mer informasjon: 
- [Opprette og redigere 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én)](create-edit-1n-relationships.md)
- [Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren](create-edit-1n-relationships-solution-explorer.md).

## <a name="view-entity-relationships"></a>Vise enhetsrelasjoner

1. I [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) velger du utformingsmodusen **Modelldrevet** eller **Lerret**.
2. Velg **Data** > **Enheter**, og velg enheten som har relasjonene du vil vise.
3. Med **Relasjoner**-kategorien valgt kan du velge følgende visninger: 

 |Visning|Beskrivelse|
 |--|--|
 |**Alle**| Viser alle relasjonene for enheten|
 |**Egendefinert**|Viser bare egendefinerte relasjoner for enheten|
 |**Standard**|Viser bare standardrelasjonene for enheten|
<!-- TODO: What is the actual difference between All and Default? -->

![Relasjoner for forretningsforbindelsesenheten](media/view-account-relationships-portal.png)

## <a name="create-relationships"></a>Opprette relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du **Legg til relasjon** på kommandolinjen og velger **Mange-til-én** eller **Én-til-mange**.

![Velg relasjonstype](media/add-relationship-menu-portal.png)

> [!NOTE]
> Hvis du vil ha informasjon om **Mange-til-mange**-relasjoner, kan du se [Opprette N:N-relasjoner (mange-til-mange)](create-edit-nn-relationships.md)

<!-- This may change going forward, but this is the way it is now. #2534972 -->
> [!Important]
> Portalen bruker annen terminologi enn løsningsutforskeren. Termene er omvendt. Løsningsutforskerens **Relatert enhet** er **Hovedenhet** i portalen. Tilsvarende er **Hovedenhet** i løsningsutforskeren **Relatert enhet** i portalen.

Avhengig av hva du har valgt, ser du enten:

<!-- These are the correct screenshots from the UI as of 6/11/18 -->
|Type|Panel|
|--|--|
|**Mange-til-én**|![Panelet for mange-til-én-relasjon](media/many-to-one-relationship-panel.png)|
|**Én-til-mange**|![Panelet for én-til-mange-relasjon](media/one-to-many-relationship-panel.png)|

Velg **Relatert enhet** eller **Hovedenhet** for relasjonen du vil opprette mellom de to enhetene. 

> [!NOTE]
> Med begge valgene opprettes et oppslagsfelt i *hoved*enheten.

Når du velger enheten, kan du redigere detaljene for relasjonen. I dette eksemplet kan flere kontaktenhetsoppføringer knyttes til én forretningsforbindelse.

<!-- These are the correct screenshots from the UI as of 6/11/18 -->
![Forretningsforbindelse og kontakt for én-til-mange-relasjon](media/One-to-many-account-contact.png)

Du kan redigere standardverdiene som er angitt, før du lagrer. Velg **Flere alternativer** for å vise verdiene **Relasjonsnavn** og **Beskrivelse av oppslagsfelt**

|Felt|Beskrivelse|
|--|--|
|**Visningsnavn for oppslagsfelt**|Den lokaliserbare teksten for oppslagsfeltet som opprettes på den relaterte enheten.<br />Dette kan redigeres senere.|
|**Navn på oppslagsfelt**|Navnet på oppslagsfeltet som opprettes på den relaterte enheten.|
|**Relasjonsnavn**|Navnet på relasjonen som blir opprettet.|
|**Beskrivelse av oppslagsfelt**|Beskrivelse for oppslagsfeltet. I modelldrevne apper vises dette som et verktøytips når brukere holder musen over feltet. <br />Dette kan redigeres senere.|

Du kan fortsette med å redigere enheten. Velg **Lagre enhet** for å opprette relasjonen du har konfigurert.

## <a name="edit-relationships"></a>Redigere relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du relasjonen du vil redigere.

> [!NOTE]
> Du kan finne hver relasjon i hovedenheten eller den relaterte enheten som en **Mange-til-én**- eller **Én-til-mange**-relasjon. Selv om den kan redigeres begge steder, er det samme relasjon.
>
> Utgiveren av en administrert løsning kan hindre noen tilpassinger av relasjoner som er en del av deres løsning.

De eneste feltene du kan redigere, er **Visningsnavn for oppslagsfelt** og **Beskrivelse av oppslagsfelt**. Disse kan også redigeres i egenskapene for oppslagsfeltet i den relaterte enheten. Mer informasjon: [Redigere et felt](create-edit-field-portal.md#edit-a-field)

## <a name="delete-relationships"></a>Slette relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du relasjonen du vil slette.

![Slette enhetsrelasjon](media/delete-entity-relationship-portal.png)

Du kan bruke **Slett relasjon**-kommandoen på kommandolinjen eller på radkontekstmenyen når du klikker ellipsene (**...**).

Hvis du sletter relasjonen, slettes oppslagsfeltet på den relaterte enheten.

> [!NOTE]
> Du vil ikke kunne slette en relasjon som har avhengigheter. Hvis du for eksempel har lagt til oppslagsfeltet i et skjema for den relaterte enheten, må du fjerne feltet fra skjemaet før du sletter relasjonen.

### <a name="see-also"></a>Se også

[Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)<br />
[Opprette og redigere 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én)](create-edit-1n-relationships.md)<br />
[Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren](create-edit-1n-relationships-solution-explorer.md)<br />
[Redigere et felt](create-edit-field-portal.md#edit-a-field)
