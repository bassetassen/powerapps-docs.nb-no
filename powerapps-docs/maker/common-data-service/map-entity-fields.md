---
title: Tilordne enhetsfelt i PowerApps | MicrosoftDocs
description: Finn ut hvordan du tilordner enhetsfelt
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
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="map-entity-fields"></a>Tilordne enhetsfelt
 
Du kan tilordne attributter mellom enheter som har en enhetsrelasjon. Dette lar deg angi standardverdier for en oppføring som er opprettet i forbindelse med en annen oppføring. 

## <a name="easier-way-to-create-new-records-in-model-driven-apps"></a>Enklere måte for å opprette nye oppføringer i modelldrevne apper

Anta at noen vil legge til en ny kontaktoppføring for en person som er en ansatt for en bestemt forretningsforbindelse. De kan gjøre dette på to forskjellige måter:  
  
### <a name="the-hard-way"></a>På den vanskelige måten

Én mulighet er ganske enkelt å navigere i appen for å opprette en ny kontaktoppføring fra begynnelsen av. Da må de imidlertid angi den overordnede forretningsforbindelsen og angi flere informasjonselementer (for eksempel informasjon om adresse og telefonnummer) som er sannsynligvis er de samme som den overordnede forretningsforbindelsen. Dette kan være tidkrevende og gir muligheter for feil.  
  
### <a name="the-easier-way"></a>Den enkleste måten

En enklere metode er å starte med en forretningsforbindelsesenhet og bruke delrutenettet **Kontakter** i skjemaet. Velg **+** for å legge til en kontakt. Dette vil først veilede folk til å slå opp eventuelle eksisterende tilknyttede kontakter, slik at de ikke ved et uhell lager en duplikatoppføring. Hvis de ikke finner en eksisterende oppføring, kan de velge **Ny** og opprette en ny kontaktoppføring. 

Det nye kontaktoppføringsskjemaet inneholder noen av de tilordnede attributtverdiene fra forretningsforbindelsen (for eksempel informasjon om adresse og telefon) som standardverdier. Brukere kan redigere disse verdiene før de lagrer oppføringen.

## <a name="how-this-works"></a>Hvordan fungerer dette

Når du tilordner enhetsfelt for en 1:N-enhetsrelasjon, blir bestemte dataelementer fra oppføringen for hovedenheten kopiert til det nye skjemaet for den relaterte enheten for å angi standardverdiene som brukere kan redigere før lagring.
 
  
> [!NOTE]
> Disse tilordningene angir bare standardverdier for en oppføring før den lagres. Brukere kan redigere verdiene før lagring. Dataene som overføres, er dataene på det aktuelle tidspunktet. De er ikke synkronisert hvis kildedataene endres senere.
>   
> Disse tilordningene brukes ikke for relaterte oppføringer som er opprettet ved hjelp av en arbeidsflyt eller dialogprosess. De brukes ikke automatisk til nye oppføringer som opprettes ved hjelp av kode, selv om utviklere kan bruke en spesiell melding som kalles `InitializeFrom` ([InitializeFrom Function](/dynamics365/customer-engagement/web-api/initializefrom?view=dynamics-ce-odata-9) eller [InitializeFromRequest Class](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9)) til å opprette en ny oppføring ved hjelp av tilgjengelige tilordninger.  

## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

Den eneste måten å tilordne enhetsfelt på, er å bruke løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
Tilordning av felt gjøres i sammenheng med en 1:N- eller N:1-enhetsrelasjon, så du må først [vise 1:N- eller N:1-enhetsrelasjoner](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships).

## <a name="view-mappable-fields"></a>Vise felt som kan tilordnes

Felttilordninger er ikke faktisk definert i enhetsrelasjonene, men de vises i brukergrensesnittet for relasjonen. Ikke alle 1:N-enhetsrelasjon har dem. Når du viser en liste over 1:N-enhetsrelasjoner (eller N:!) for en enhet, kan du filtrere relasjoner til å vises etter type. Du kan velge **Alle**, **Egendefinert**, **Kan tilpasses** eller **Kan tilordnes**. Enhetsrelasjoner som kan tilordnes, gir tilgang til å tillate å tilordne enhetsfelt. 

![Vise enhetsrelasjoner som kan tilordnes](media/mappable-entity-relationships.png) 

Når du åpner en enhetsrelasjon som kan tilorndes, kan du velge **Tilordninger** i den venstre navigasjonsruten.

![Velge Tilordninger for enhetsrelasjonen](media/map-entity-fields-ui-solution-explorer.png)

## <a name="delete-mappings"></a>Slette tilordninger

Hvis det finnes tilordninger som du ikke vil bruke, kan du merke dem og klikke ![Slett-ikon](media/delete.gif) .

## <a name="add-new-mappings"></a>Legge til nye tilordninger

Du kan opprette en ny tilordning ved å klikke **Ny** på verktøylinjen. Dette åpner dialogboksen **Opprett felttilordning**.

![Dialogboksen Opprett felttilordning](media/create-field-mapping-dialog.png)

Velg ett kildeenhetsfelt og ett målenhetsfelt med verdier som du vil tilordne. 

![Konfigurere felttilordning](media/configure-field-mapping.png)

Velg deretter **OK** for å lukke dialogboksen.

Reglene nedenfor viser hvilke typer data som kan tilordnes.  
  
- Begge feltene må være av samme type og samme format.  
- Lengden på målfeltet må være lik eller større enn lengden på kildefeltet.  
- Målfeltet kan ikke allerede være tilordnet til et annet felt.  
- Kildefeltet må være synlig i skjemaet.  
- Målfeltet må være et felt som en bruker kan angi data i.  
- Adresse-ID-verdier kan ikke tilordnes.
- Hvis du tilordner til eller fra et felt som ikke vises i et skjema, utføres ikke tilordningen før feltet blir lagt til i et skjema.
- Hvis feltene er alternativsett, må heltallsverdiene for hvert alternativ være identiske.  
  
> [!NOTE]
>  Hvis du vil tilordne alternativsettfelt, anbefaler vi du konfigurerer begge feltene til å bruke samme globale alternativsett. Hvis ikke, kan det være vanskelig å holde to separate sett med alternativer synkroniseres manuelt. Hvis heltallsverdiene for hvert alternativ ikke er riktig tilordnet, kan du introdusere problemer i dataene. Mer informasjon: [Opprette og redigere globale alternativsett for Common Data Service for Apps (valglister)](create-edit-global-option-sets.md)  
  
## <a name="automatically-generate-field-mappings"></a>Automatisk genererte felttilordninger  

Du kan også generere tilordninger automatisk ved å velge **Generer tilordninger** fra menyen **Flere handlinger**.

Du bør være forsiktig når du gjør dette med systemenheter. Bruk dette alternativet når du oppretter egendefinerte enheter og vil dra nytte av tilordning. 

> [!WARNING]
> Dette fjerner eventuelle eksisterende tilordninger og erstatter dem med foreslåtte tilordninger som bare er basert på felt med samme navn og datatyper. Hvis du bruker dette på en systemenhet, kan du miste noen forventede tilordninger. Du kan spare tid for egendefinerte enheter fordi du enklere kan slette alle tilordningene som du ikke vil ha og legge til andre som handlingen for å generere tilordninger ikke opprettet.  


## <a name="publish-customizations"></a>Publisere tilpassinger 

Siden felttilordninger ikke er metadata, må du publisere dem før endringene trer i kraft. 
<!-- TODO Need a general topic about publishing to link to in situations like this -->

### <a name="see-also"></a>Se også
[Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren](create-edit-1n-relationships-solution-explorer.md)<br />
[Dokumentasjon for utviklere: Tilpasse enhets- og attributtilordninger](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)<br />
[Dokumentasjon for utviklere: Web-API, opprette en ny enhet fra en annen enhet](/dynamics365/customer-engagement/developer/webapi/create-entity-web-api#create-a-new-entity-from-another-entity)
