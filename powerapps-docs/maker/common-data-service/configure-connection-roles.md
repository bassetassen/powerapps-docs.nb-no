---
title: Konfigurer tilkoblingsroller | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.author: matp
manager: brycho
ms.openlocfilehash: 4faf195f1c751e3796267d52725c1cb753c4889d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696074"
---
# <a name="configure-connection-roles"></a>Konfigurer tilkoblingsroller

Med Common Data Service for apper kan du definere **tilkoblinger** mellom enhetsoppføringer uten å opprette en enhetsrelasjon. I modelldrevne apper kan du opprette en navngitt tilkobling mellom poster for å opprette en mindre formell relasjon som ikke rettferdiggjør at man skaper en faktisk enhetsrelasjon. Noen eksempler er blant annet *venn*, *søsken*, *ektefelle*, *deltaker* og *interessent*. Noen tilkoblinger kan også være gjensidige enheter, som *barn* og *forelder*, *mann* og *kone* eller *lege* og *pasient*.

Når personer angir en kobling mellom to poster, kan de også legge til en beskrivelse og tilleggsinformasjon, som for eksempel start- og sluttdatoer for relasjonen. Mer informasjon: [Opprett tilkoblinger for å definere og vise relasjoner mellom poster](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)

Alle som har skrivetilgang til **tilkoblingsrolle**-enheten, kan definere hvilken tilkobling som er tilgjengelige.

## <a name="view-connection-roles"></a>Vis tilkoblingsroller

Det finnes en rekke standardtilkoblingsroller som allerede er konfigurerte i CDS for apper. Du må gå til Innstillinger for å vise den. 

### <a name="navigate-to-the-settings-area"></a>Gå til Innstillinger-området

1. Mens du viser en modelldrevet app, kan du redigere nettadressen for å fjerne alt etter `dynamics.com`, og deretter oppdatere siden.
1. Gå til **Innstillinger** > **Forretning** > **Forretningsadministrasjon**, og velg deretter **Tilkoblingsroller**.

![Tilkoblingsroller i innstillingene for forretningsadministrasjon](media/navigate-settings-connection-roles.png)

I denne visningen kan du se alle tilkoblingsrollene som er tilgjengelige for dette miljøet, og du kan også redigere dem her.

> [!NOTE]
> Hvis du vil distribuere tilkoblingsroller med en løsning, må du kontrollere at de er inkluderte i løsningen som du vil distribuere. Mer informasjon: [Legg til tilkoblingsroller til en løsning](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>Vis tilkoblingsroller i løsningsutforskeren.

Fordi tilkoblingsrollene er *løsningsorienterte*, noe som betyr at de kan være inkludert i en løsning, kan du også legge til tilkoblingsroller i en løsning som du distribuerer.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

De fleste av tilkoblingsrollene du kan se på **Innstillinger**-området, er definert i den *interne* **standardløsningen** (må ikke forveksles med **standardløsningen for Common Data Services**). Denne interne **standardløsningen** inneholder alle tilpassinger i systemet. Hvis du vil vise **standardmiljøet**, velger du visningen **Alle løsninger – intern**.

## <a name="add-connection-roles-to-a-solution"></a>Legg til tilkoblingsroller i en løsning

Generelt er det ikke anbefalt å redigere komponenter i den interne **standardløsningen**. Du kan bruke kommandoen **Legg til eksisterende** for å hente noen av standardtilkoblingsrollene til løsningen din i **standardløsningen for Common Data Services** eller andre løsninger som du har opprettet for å arbeide i.

![Legg til eksisterende tilkoblingsrolle](media/add-existing-connection-role.png)

Når du har lagt tilkoblingsrollen inn i løsningen din, kan du alltid redigere den når den er synlig.

## <a name="create-or-edit-connection-roles"></a>Opprett eller rediger tilkoblingsroller.

> [!IMPORTANT]
> Hvis du har tenkt å distribuere en løsning som inkluderer nye tilkoblingsroller eller endringer i eksisterende tilkoblingsroller, må du legge dem til i løsningen du skal distribuere. Hvis du redigerer eller legger til nye tilkoblingsroller ved hjelp av **innstillinger**-området, blir disse tilkoblingsrollene lagt til i den interne **standardløsningen**, og de blir ikke inkludert i løsningen du vil distribuere, med mindre du først legger dem til i løsningen din. Mer informasjon: [Legg til tilkoblingsroller til en løsning](#add-connection-roles-to-a-solution)

Velg en av tilkoblingsrollene i **tilkoblingsroller**-listen for å redigere den.
Det er tre trinn for å definere en tilkoblingsrolle som er satt tydelig opp i skjemaet.

![Opprett tilkoblingsrolleskjema](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>Beskriv tilkoblingsrollen

Angi følgende i feltene nedenfor:

|Felt|Beskrivelse|
|--|--|
|**Navn**|(Obligatorisk) Teksten som beskriver tilkoblingen.|
|**Kategorien for tilkoblingsrolle**|En gruppe som beskriver kategorien for tilkoblingen. Mer informasjon: [Kategoriverdier for tilkoblingsrolle](#connection-role-category-values)|
|**Beskrivelse**|Oppgi en definisjon av rollen.|

#### <a name="connection-role-category-values"></a>Kategoriverdier for tilkoblingsrolle

Standardverdiene for **kategorien for tilkoblingsroller** er:
- Bedriften din
- Familie
- Sosialt
- Salg
- Annet
- Bruker
- Salgsteam
- Tjeneste

Du kan legge til nye eller endre eksisterende kategorier ved å redigere det globale alternativsettet **Kategori**. Mer informasjon: [Opprett og rediger globale alternativsett for Common Data Service for apper (nedtrekksmenyer)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>Velg posttyper

Velg hvilke posttyper som skal være tilgjengelige for tilkobling.

> [!NOTE]
> Selv om **alle** er valgt som standard, bør du vurdere hvilke typer som er riktige for tilkoblingsrollen du legger til.

### <a name="matching-connection-roles"></a>Samsvar tilkoblingsroller

I dette valgfrie trinnet kan du definere roller som skal brukes på en gjensidig måte. Det er ikke et krav, men tilkoblingene blir mer meningsfylte hvis disse er definert.

Du kan for eksempel angi at Glen er en *venn* av Mary, men betyr det at Mary er en *venn* av Glen? La oss håpe det. Men at Glen er *faren* til Mary betyr ikke at Mary er *faren* til Glen. Oppretting av riktig gjensidighet krever dette ekstra trinnet.

Når du angir en tilkoblingsrolle som ikke har en samsvarende tilkoblingsrolle, vises rollen bare når du viser tilkoblingen fra posten som tilkoblingen ble brukt på. Når rollene vises fra den tilkoblede posten, vil rollen være tom hvis ikke en tilsvarende rolle er angitt.

For rolledefinisjoner som *venn*, *ektefelle*, *kollega*, eller *søsken*, er det best å tilordne den gjensidige rollen til definisjonene. Hvis bare en gjensidig tilkoblingsrolle er konfigurert, brukes denne tilkoblingsrollen i begge retninger.

> [!IMPORTANT]
> Du må lagre en ny tilkoblingsrolle uten den samsvarende rollen før du kan angi den samsvarende rollen til rollen som er allerede er angitt.

Du vil se at noen tilkoblingsroller allerede er konfigurert med samsvarende tilkoblingsroller. *Tidligere ansatt* samsvarer med *tidligere arbeidsgiver* og omvendt. Denne typen én-til-én-samsvarende tilkoblingsrolle er mest vanlig.

Du kan konfigurere flere samsvarende tilkoblingsroller for å beskrive komplekse relasjoner. Hvis du oppretter en tilkoblingsrolle som *far*, kan du konfigurere to roller til, for eksempel *datter* og *sønn*, og bruke begge som samsvarende tilkoblingsroller til  *far*. Videre bør både *datter*- og *sønn*-tilkoblingsrollen samsvare med *far*. Da bør du selvfølgelig også definere en tilsvarende rolle for *mor* som på samme måte samsvarer med *datter* og *sønn*.

> [!TIP]
> Før du oppretter et omfattende sett med tilkoblingsroller, bør du vurdere om et enklere sett med roller er nok. For eksempel kan du kan du vurdere om det ganske enkelt å bruke *forelder* og *barn* vil fungere bedre for deg enn å opprette et omfattende sett med tilkoblingsroller som *far*, *mor*, *sønn* og *datter*.

Hvis mer enn en samsvarende tilkoblingsrolle er konfigurert, representerer disse tilkoblingsrollene de eneste gjensidige rollene som er gyldige. Den første vil automatisk bli brukt som standardverdi. Hvis standardverdien ikke er riktig, må du redigere tilkoblingen manuelt og velge mellom gyldige alternativer som er definert i konfigurasjonen.

### <a name="see-also"></a>Se også
<!-- This is in the basics guide. It needs to be migrated -->
[Opprette tilkoblinger for å definere og vise relasjoner mellom poster](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[Opprette og redigere globale alternativsett for Common Data Service for apper (nedtrekksmenyer)](create-edit-global-option-sets.md)<br />
[Opprett og rediger relasjoner mellom enheter](create-edit-entity-relationships.md)


