---
title: Tilordning av enhetsfelt i PowerApps | MicrosoftDocs
description: Lær hvordan du tilordner enhetsfelter
ms.custom: ''
ms.date: 05/29/2018
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
ms.assetid: 7c5aa1c3-bde9-43f1-a369-fdcdbf14dec0
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: 7e84e10a824ea218063cb2dccdc15ed7ae2340da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696642"
---
# <a name="map-entity-fields"></a>Tilordning av enhetsfelter
 
Du kan tilordne attributter mellom enheter som har en enhetsrelasjon. Dette lar deg angi standardverdier for en post som er opprettet i konteksten til en annen post. 

## <a name="easier-way-to-create-new-records-in-model-driven-apps"></a>Enklere måte for å opprette nye poster i modelldrevne apper

La oss si at personer vil legge til en ny kontaktpost for en person som er en ansatt, for en bestemt konto. De kan gjøre dette på to forskjellige måter:  
  
### <a name="the-hard-way"></a>Den tungvinte måten

Personer kan gå i appen å opprette en ny kontaktpost fra grunnen av. Men deretter må de konfigurere den overordnede kontoen, og angi flere typer informasjon (for eksempel informasjon om adresse og telefonnumre) som sannsynligvis er det samme som for den overordnede kontoen. Dette kan ta lang tid, og gir muligheter for feil.  
  
### <a name="the-easier-way"></a>Den enkle måten

Den enkle måten er å starte med konto-enheten, og ved hjelp av delrutenett for **Kontakter** på skjemaet, kan du velge **+** for å legge til en kontakt. Det hjelper først og fremst personer med å slå opp eksisterende relaterte kontakter, slik at de ikke ved et uhell oppretter en duplikatoppføring. Hvis de ikke finner en eksisterende post, kan de velge **Ny**, og opprett en ny kontakt-post. 

Det nye kontaktskjemaet inkluderer alt av de tilordnede attributtverdiene fra kontoen (for eksempel informasjon om adresse og telefonnumre) som standardverdier. Personer kan redigere disse verdiene før de lagrer posten.

## <a name="how-this-works"></a>Hvordan dette fungerer

Når du tilordner enhetsfelter for en én-til-mange-enhetsrelasjon, blir visse dataelementer fra den primære enhetsposten kopiert til det nye relaterte enhetsskjemaet for å angi standardverdier som personer kan redigere før lagring.
 
  
> [!NOTE]
> Disse tilordningene angir bare standardverdiene for en post før den lagres. Personer kan redigere verdiene før lagring. Dataene som overføres er dataene som finnes på dette tidspunktet. Det blir ikke synkronisert hvis kildedataene endres senere.
>   
> Disse tilordningene brukes ikke for relaterte poster som er opprettet ved hjelp av en arbeidsflyt eller dialogprosess. De blir ikke automatisk tatt i bruk for nye poster som er opprettet ved hjelp av kode, selv om utviklere kan bruke en spesiell melding kalt `InitializeFrom` ([InitializeFrom Function](/dynamics365/customer-engagement/web-api/initializefrom?view=dynamics-ce-odata-9) eller [InitializeFromRequest Class](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9)) til å opprette en ny post ved hjelp av tilgjengelige tilordninger.  

## <a name="open-solution-explorer"></a>Åpne løsningutforsker

Den eneste måten å tilordne felter på, er å bruke løsningsutforsker.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
Tilordning av felter gjøres i kontekst med en enhetsrelasjon på én-til-mange eller mange-til-én, så først må du [vise enhetsrelasjoner for én-til-mange eller mange-til-én](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships).

## <a name="view-mappable-fields"></a>Vis felter som kan tilordnes

Felttilordninger er faktisk ikke definert i enhetsrelasjonene, men vises i brukergrensesnittet for relasjonen. Ikke alle enhetsrelasjoner for én-til-mange har dem. Når du viser en liste over enhetsrelasjoner for én-til-mange (eller mange-til-én) for en enhet, kan du filtrere relasjonene som vises etter type. Du kan velge enten **Alle**, **Egendefinert**, **Kan tilpasses**, eller **Kan tilordnes**. Enhetsrelasjoner som kan tilordnes gir tilgang til å tillate tilordning av enhetsfelter. 

![Vis enhetsrelasjoner som kan tilordnes](media/mappable-entity-relationships.png) 

Velg **Tilordninger** i navigasjonsruten til venstre når du åpner en enhetsrelasjon som kan tilordnes.

![Velg tilordninger for enhetsrelasjonen](media/map-entity-fields-ui-solution-explorer.png)

## <a name="delete-mappings"></a>Slett tilordninger

Hvis det finnes noen tilordninger du ikke vil bruke, kan du velge dem og klikke på ![Slett-ikonet](media/delete.gif) Ikon.

## <a name="add-new-mappings"></a>Legg til nye tilordninger

Klikk på **Ny** på verktøylinjen for å opprette en ny tilordning. Dette åpner dialogboksen **Opprette felttilordning**.

![Opprett dialogboksen for felttilordning](media/create-field-mapping-dialog.png)

Velg et enhetsfelt med én kilde og et enhetsmålfelt med verdiene du vil tilordne. 

![Konfigurer felttilordning](media/configure-field-mapping.png)

Velg **OK** for å lukke dialogboksen.

Følgende regler viser hvilke typer data som kan tilordnes.  
  
- Begge feltene må være av samme type, og samme format.  
- Lengden på målfeltet må være lik eller større enn lengden på kildefeltet.  
- Målfeltet kan ikke allerede tilordnes til et annet felt.  
- Kildefeltet må være synlig i skjemaet.  
- Målfeltet må være et felt som en bruker kan skrive inn data i.  
- Kan ikke tilordne verdier for adresse-ID.
- Hvis du tilordner til eller fra et felt som ikke vises i et skjema, vil ikke tilordningen gjøres før feltet er lagt til i et skjema.
- Hvis feltene er alternativsett, skal heltallsverdiene for hvert alternativ være identiske.  
  
> [!NOTE]
>  Hvis du trenger å tilordne felter for alternativetsett, anbefaler vi at du konfigurerer begge feltene til å bruke det samme globale alternativsettet. Hvis ikke, kan det være vanskelig å beholde to separate sett med alternativer som er synkronisert manuelt. Du kan introdusere problemer i dataene hvis heltallsverdiene for hvert alternativ ikke er tilordnet på riktig måte. Mer informasjon: [Opprett og rediger globale alternativsett for Common Data Service for Apps (nedtrekksmenyer)](create-edit-global-option-sets.md)  
  
## <a name="automatically-generate-field-mappings"></a>Generer felttilordninger automatisk  

Du kan også generere tilordninger automatisk ved å velge **Generer tilordninger** fra **Flere handlinger**-menyen.

Vær forsiktig når du gjør dette med systemenheter. Bruk dette når du oppretter egendefinerte enheter og ønsker å dra nytte av tilordning. 

> [!WARNING]
> Dette fjerner alle eksisterende tilordninger og erstatter dem med foreslåtte tilordninger som bare er basert på feltene som har lignende navn og datatyper. Hvis du bruker dette på en systemenhet, kan du miste noen forventede tilordninger. Dette hjelper med å spare tid for egendefinerte enheter fordi du enklere kan slette tilordninger du ikke vil bruke, og legge til eventuelle andre som handlingen Generer tilordninger ikke har opprettet.  


## <a name="publish-customizations"></a>Publiser tilpassinger 

Fordi felttilordninger ikke er metadata, må du publisere dem før endringene trer i kraft. 
<!-- TODO Need a general topic about publishing to link to in situations like this -->

### <a name="see-also"></a>Se også
[Opprett og rediger enhetsrelasjoner for én-til-mange eller mange-til-én ved hjelp av løsningsutforsker](create-edit-1n-relationships-solution-explorer.md)<br />
[Utviklerdokumentasjon: Tilpass enhets- og attributt-tilordninger](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)<br />
[Utviklerdokumentasjon: Nett-API Opprett en ny enhet fra en annen enhet](/dynamics365/customer-engagement/developer/webapi/create-entity-web-api#create-a-new-entity-from-another-entity)
