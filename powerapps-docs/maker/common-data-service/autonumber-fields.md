---
title: Nummerere felt automatisk i Common Data Service | MicrosoftDocs
description: 'Forstå hvordan du oppretter, administrerer og bruker autonummereringsfelt'
keywords: ''
ms.date: 02/26/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: daemelia
ms.assetid: null
ms.author: daemelia
manager: kvivek
ms.reviewer: Mattp123
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="autonumber-fields"></a>Autonummereringsfelt

Autonummereringsfelt er felt som automatisk genererer alfanumeriske strenger når de opprettes. Opprettere kan tilpasse formatet til disse feltene slik de vil, og bruke systemet til å generere samsvarende verdier som automatisk fyller dem ut under kjøretid.

Mens autonummereringsfelt formelt sett bare er tekstfelt med tilleggsfunksjoner som er bygd oppå, forenkler [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) dette konseptet ved å vise bare **Autonummer** som en egen datatype under **Tekst**-kategorien. Det er viktig å huske at den [klassiske løsningsutforskeren](use-solution-explorer.md#classic-solution-explorer) ikke støtter oppretting eller administrasjon av autonummereringsfelt.

Du oppretter et autonummereringsfelt ved å følge den samme fremgangsmåten som [oppretting av et felt](create-edit-field-portal.md#create-a-field), og du velger bare **Autonummerering** fra **Datatype**-rullegardinlisten. 

Du kan også aktivere autonummereringsfunksjonalitet på et eksisterende tekstfelt ved å åpne feltet og velge **Autonummerering** fra **Datatype**-rullegardinlisten. På samme måte kan autonummereringsfunksjonalitet deaktiveres når som helst ved å åpne feltet og velge et annet alternativ i **Datatype**-rullegardinlisten.

## <a name="autonumber-types"></a>Autonummereringstyper

For å gjøre opprettelsen av autonummereringsfelt enklere finnes det noen forhåndsdefinerte standard autonummereringstyper som fanger opp de vanligste scenarioene. 

### <a name="string-prefixed-number"></a>Tall med strengprefiks

Det mest vanlige autonummereringsformatet er et tall med strengprefiks. Når denne typen som er valgt, består autonummerering av et automatisk stigende tall med et prefiks med valgfri strengkostant. Et strengprefikstall med prefikset *Contoso* vil generere oppføringer som *Contoso-1000*, *Contoso 1001*, *Contoso 1002* og så videre.

### <a name="date-prefixed-number"></a>Tall med datoprefiks

Et annet vanlig autonummereringsformat er et tall med datoprefiks. Når denne typen som er valgt, består autonummerering av et automatisk stigende tall med et prefiks med formatert dato. Datodelen av oppføringen skal gjenspeile gjeldende dato og klokkeslett oppføringen ble opprettet i UTC-tid. Vi har lagt til en rekke ulike datoformater å velge blant.
For eksempel vil et tall med datoprefiks generere oppføringer som *2019-26-02-1000*, *2019-27-02-1000*, *2019-28-02-1000* og så videre, avhengig av gjeldende dato og valgt datoformat.

### <a name="custom"></a>Egendefinert

For mer avanserte opprettere med spesifikke brukstilfeller gir vi mulighet til å tilpasse formatet fullstendig til ønsket format for et autonummereringsfelt. Formatet kan bestå av strengkonstanter, automatisk stigende tall, formaterte datoer eller tilfeldige alfanumeriske sekvenser.
Hvis du vil ha detaljert informasjon om hvordan du definerer egendefinerte, kan du se [AutoNumberFormat-alternativer](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/create-auto-number-attributes#autonumberformat-options).

## <a name="seed-values"></a>Startverdier

Startverdien for et autonummereringsfelt er startnummeret som brukes for nummerdelen av formatet. Hvis du vil at et autonummereringsfelt skal generere oppføringer som for eksempel *Contoso-1000*, *Contoso 1001*, *Contoso 1002* og så videre, er ønsket startverdi 1000, fordi dette er verdien som nummersekvensen starter med. Autonummereringfelt har en standard startverdi på 1000, men du kan opprette en egendefinert startverdi hvis du ønsker. 


> [!IMPORTANT]
> Angivelse av en egendefinert startverdi støttes for øyeblikket bare når du oppretter et nytt autonummereringsfelt. 
>
> Angivelse av startverdien endrer bare den gjeldende nummerverdien for det angitte attributtet i det gjeldende miljøet. Den innebærer ikke en felles startverdi for attributtet. Startverdien er ikke inkludert i en løsning når den importeres i et annet miljø. 

## <a name="create-an-autonumber-field"></a>Opprette et autonummereringsfelt
  
1.  Logge på [PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
  
2.  Utvid **Data** og velg **Enheter** i venstre rute.
  
3.  Velg enheten du vil legge til et autonummereringsfelt i, og deretter velger du **Felt**-kategorien.
  
4.  Velg **Legg til**-feltet på verktøylinjen.  
  
5.  I den høyre ruten angir du **Visningsnavn** og velger **Autonummer** for **Datatype**.

    > [!div class="mx-imgBorder"] 
    > ![](media/create-autonumber-field.png "Opprette et autonummereringsfelt")
  
6. Angi valgfrie felt etter behov. Mer informasjon: [Opprette og redigere felt](create-edit-field-portal.md#create-a-field)

7. Velg en autonummereringstype eller behold standardalternativet **Tall med strengprefiks**.

8. Tilpass en startverdi eller behold standardverdien **1000**.

9. Velg **Ferdig**.

## <a name="see-also"></a>Se også
 [Opprette og redigere felt for Common Data Service ved hjelp av PowerApps-portalen](create-edit-field-portal.md)
