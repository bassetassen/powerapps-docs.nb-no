---
title: 'Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren | MicrosoftDocs'
description: Finn ut hvordan du oppretter én-til-mange- eller mange-til-én-enhetsrelasjoner ved hjelp av PowerApps-løsningsutforskeren
ms.custom: ''
ms.date: 10/28/2018
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

# <a name="create-and-edit-1n-one-to-many-or-n1-many-to-one-entity-relationships-using-solution-explorer"></a>Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) med løsningsutforskeren 

Løsningsutforskeren gir én måte å opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) for Common Data Service for Apps.

[PowerApps-portalen](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) gjør det mulig for konfigurasjon av de vanligste alternativene, men enkelte alternativer kan bare angis ved hjelp av løsningsutforskeren. Mer informasjon: 
- [Opprette 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én)](create-edit-1n-relationships.md)
- [Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) i PowerApps-portalen](create-edit-1n-relationships-portal.md)
  
## <a name="open-solution-explorer"></a>Åpne løsningsutforskeren

En del av navnet på egendefinerte relasjoner du oppretter, er tilpassingsprefikset. Dette angis basert på løsningsutgiveren for løsningen du arbeider i. Hvis du er interessert i tilpassingsprefikset, må du kontrollere at du arbeider i en ikke-administrert løsning der tilpassingsprefikset er det du vil bruke for denne enheten. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entity-relationships"></a>Vise enhetsrelasjoner

I løsningsutforskeren utvider du **Enheter** og velger en enhet. I denne enheten, velg **1:N-relasjoner** eller **N:1-relasjoner**

![Vise enhetsrelasjoner](media/view-1n-entity-relationships-solution-explorer.png)

## <a name="create-relationships"></a>Opprette relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du **Ny én-til-mange-relasjon** eller **Ny mange-til-én-relasjon** på kommandolinjen.

> [!NOTE]
> Hvis kommandoene ikke er tilgjengelige, er ikke enheten kvalifisert for å opprette en egendefinert relasjon.

Begge alternativene åpner et skjema som det følgende. Forskjellen er om feltet **Hovedenhet** eller **Relatert enhet** er angitt.

![Ny én-til-mange-relasjon-skjema](media/new-1n-entity-relationship-form-solution-explorer.png)

- Med **1:N-relasjon** settes **Hovedenhet** til den gjeldende enheten.
- Med **N:1-relasjon** settes **Relatert enhet** til den gjeldende enheten.

Følgende felt må angis for å lagre enhetsrelasjonen:

|Obligatorisk felt|Beskrivelse|
|--|--|
|**Hovedentitet**|Enheten blir måltypen for oppslagsfeltet som opprettes på den relaterte enheten.|
|**Relatert entitet**|Enheten vil ha et oppslagsfelt lagt til for å knytte enhetsoppføringene til oppføringen for hovedenhet.|
|**Navn**|Navnet på relasjonen. En verdi genereres basert på verdiene for hovedoppføring og relatert enhet. Dette feltet får prefiks fra tilpassingsprefikset for løsningsutgiveren.|
|**Visningsnavn for oppslagsfelt**|Den lokaliserbare teksten for oppslagsfeltet som opprettes for den relaterte enheten. Dette er vanligvis den samme som visningsnavnet for hovedenheten. <br /> Dette kan endres senere.|
|**Navn på oppslagsfelt**|Navnet på oppslagsfeltet som opprettes på den relaterte enheten. Det blir generert en verdi basert på **visningsnavnet for oppslagsfelt**. Dette feltet får prefiks fra tilpassingsprefikset for løsningsutgiveren.|

Du kan klikke på ![Lagre enhetsrelasjon-knappen](media/save-entity-icon-solution-explorer.png) for å lagre enheten og fortsette å redigere. Mer informasjon: [Redigere relasjoner](#edit-relationships)

> [!NOTE]
> Hvis verdien **Navn** eller **Navn på oppslagsfelt** allerede finnes i systemet, får du en feil når du lagrer. Rediger verdiene slik at de er unike, og prøv på nytt.

## <a name="edit-relationships"></a>Redigere relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du enheten du vil redigere. Følgende egenskaper for enhetsrelasjon kan redigeres når relasjonen opprettes.

> [!NOTE]
> Utgiveren av en administrert løsning kan hindre noen tilpassinger av relasjoner som er en del av deres løsning.

### <a name="entity-relationship-properties"></a>Egenskaper for enhetsrelasjon

Disse egenskapene er om relasjonen.

|Felt|Beskrivelse|
|--|--|
|**Søkbar**|Om denne relasjonen skal vises i Avansert søk i modelldrevne apper. Velg **Nei** hvis dette er en relasjon som ikke er viktig for bedriften din.|
|**Hierarkisk**|Dette alternativet er bare aktivert for selvreferensielle relasjoner. Om enheten skal anses å definere et hierarki for enheten.<br />**Viktig**: Når du har angitt feltene for beregnet verdi for egenskaper, kan prosesser og visninger konfigureres til å avhenge av denne egenskapen. Hvis du senere endrer denne verdien, vil ikke de funksjonene som er avhengige av hierarkiet, fungere. <br />Mer informasjon: [Definere og spørre etter hierarkisk relaterte data](define-query-hierarchical-data.md)|

### <a name="lookup-field"></a>Oppslagsfelt

Dette er egenskapene for oppslagsfeltet som er opprettet på den relaterte enheten. Egenskapene kan redigeres her, eller ved å redigere oppslagsfeltet direkte. Noen feltegenskaper kan ikke redigeres fra relasjonen. Mer informasjon: [Redigere et felt](create-edit-field-solution-explorer.md#edit-a-field)

|Felt|Beskrivelse|
|--|--|
|**Visningsnavn**|Den lokaliserbare teksten for oppslagsfeltet som opprettes for den relaterte enheten.|
|**Feltkrav**|Om feltet må ha data før et skjema i en modelldrevet app kan lagres. Mer informasjon: [Feltkravalternativer](create-edit-field-solution-explorer.md#field-requirement-options)|
|**Beskrivelse**|Skriv inn instruksjoner til brukeren om hva feltet er for. Disse beskrivelsene vises som verktøytips for brukeren i modelldrevne apper når de holder musen over etiketten for feltet.|

### <a name="navigation-pane-item-for-primary-entity"></a>Navigasjonsruteelement for hovedentitet

Du kan navigere for å se de tilknyttede oppføringene fra hovedenheten. Disse dataene brukes i modelldrevne apper for å styre hvordan de relaterte enhetsoppføringene vises. Disse innstillingene kan også redigeres ved hjelp av skjemaredigeringsprogrammet.

|Felt|Beskrivelse|
|--|--|
|**Visningsalternativ**|Hvordan listen med relaterte enheter skal vises. Mer informasjon: [Visningsalternativer](#display-options)|
|**Tilpasset etikett**|Angi den lokaliserbare teksten som skal brukes i stedet for flertallsnavnet når du velger **Bruk egendefinert etikett** som **Visningsalternativ**.|
|**Visningsområde**|Velg en av de tilgjengelige grupperingene for å vise listen. De tilgjengelige alternativene er: **Detaljer** (for *Felles*-gruppen), **Markedsføring**, **Salg** og **Service**. |
|**Visningsrekkefølge**|Styrer hvor navigasjonselementet skal plasseres innenfor det valgte visningsområdet. Området med tillatte tall starter med 10 000. Navigasjonsruteelementer med en lavere verdi vises over andre relasjoner med høyere verdier.|

<!-- TODO: Not sure whether Display Area or Display Order are still used anymore. Might only be used in the Outlook client?-->

#### <a name="display-options"></a>Visningsalternativer

Dette er de tilgjengelige visningsalternativene:

|Alternativ|Beskrivelse|
|--|--|
|**Ikke vis**|Ikke vis de relaterte enhetene for denne relasjonen.|
|**Bruk tilpasset etikett**|Når dette alternativet er valgt, aktiveres **Egendefinert etikett**-feltet slik at du kan angi den lokaliserbare teksten som skal brukes i stedet for flertallsnavnet.|
|**Bruk flertallsnavn**|Bruk flertallsvisningsnavnet som definert for den relaterte enheten.|

### <a name="relationship-behavior"></a>Relasjonsfunksjonalitet

Dette er der du kan definere standard funksjonalitet for relaterte enheter. Denne informasjonen er viktig fordi den sikrer dataintegritet og kan automatisere forretningsprosesser for selskapet.

La oss se på et eksempel.  
  
Anta at du har en ny selger, og du vil tilordne vedkommende en rekke eksisterende salgsmuligheter som er tilordnet en annen selger. Hver salgsmulighetsoppføring kan ha en rekke tilknyttede oppgaveaktiviteter. Du kan enkelt finne de aktive salgsmulighetene du vil tilordne på nytt, og tilordne dem til den nye selgeren. Men hva skal skje med oppgaveaktivitetene som er knyttet til salgsmulighetene? Vil du åpne hver oppgave og avgjøre om den også skal tilordnes den nye selgeren? Sannsynligvis ikke. I stedet kan du la relasjonen automatisk bruke noen standardregler for deg. Disse reglene gjelder bare for oppgaveoppføringer som er knyttet til salgsmuligheter som du tilordner på nytt. Alternativene er:  
  
- Tilordne alle aktive oppgaver på nytt.  
- Tilordne alle oppgaver på nytt. 
- Tilordne ingen av oppgavene på nytt.  
- Tilordne alle oppgaver på nytt som er tilordnet til den tidligere eieren av salgsmuligheten.  
  
Relasjonen kan styre hvordan handlingene som utføres på en oppføring for hovedenhetsoppføringen, overlapper ned til eventuelle relatert oppføringer.   

Det finnes flere typer virkemåter som kan brukes når bestemte handlinger forekommer.

#### <a name="behaviors"></a>Virkemåter

Dette er virkemåtene som kan konfigureres.

|Virkemåte|Beskrivelse|
|--|--|
|**Overlapp aktive**|Utfør handlingen på alle aktive relatert enhetsoppføringer.|
|**Overlapp alle**|Utfør handlingen på alle relatert enhetsoppføringer.|
|**Overlapp ingen**|Ikke gjør noe.|
|**Fjern kobling**|Fjern oppslagsverdien for alle relaterte oppføringer.|
|**Begrens**|Hindre at hovedenhetsoppføringen slettes når det finnes relaterte enhetsoppføringer.|
|**Overlapp brukereide**|Utfør handlingen på alle relatert enhetsoppføringer som eies av samme bruker som hovedenhetsoppføringen.|

#### <a name="actions"></a>Handlinger

Dette er handlinger som kan utløse enkelte virkemåter:

|Felt|Beskrivelse|Alternativer|
|--|--|--|
|**Tilordne**|Hva skal skje når hovedenhetsoppføringen tilordnes til noen andre?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Overordne på nytt**|Hva skal skje når oppslagsverdien for en relatert enhet i en overordnet relasjon endres?<br />Mer informasjon: [Overordnede enhetsrelasjoner](#parental-entity-relationships)|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Dele**|Hva skal skje når hovedenhetsoppføringen deles?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Slett**|Hva skal skje når hovedenhetsoppføringen slettes?|Overlapp alle<br />Fjern kobling<br />Begrens|
|**Oppheve deling**|Hva skal skje når delingen av en hovedenhetsoppføring oppheves?|Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|
|**Slå sammen**|Hva skal skje når en hovedenhetsoppføring slås sammen?|Overlapp alle<br />Overlapp ingen|
|**Visning av beregnet verdi**|Hva er ønsket virkemåte for visningen av beregnet verdi knyttet til denne relasjonen? |Overlapp alle<br />Overlapp aktive<br />Overlapp brukereide<br />Overlapp ingen|

<!-- TODO: I find no official docs related to rollup views, but plenty of hits online: https://www.google.com/search?q=Dynamics+365++%27rollup+view%27 -->



#### <a name="type-of-behavior-options"></a>Alternativer for funksjonalitetstype

Bruk **Funksjonalitetstype**-feltet for å velge mellom et sett med standardfunksjonalitet, eller om du vil konfigurere dem hver for seg. 

|Alternativ|Beskrivelse|
|--|--|
|**Overordnet**|**Tilordne:** Overlapp alle<br />**Overordne på nytt**: Overlapp alle<br />**Del**: Overlapp alle<br />**Slett**: Overlapp alle<br />**Opphev deling**: Overlapp alle<br />**Flett**: Overlapp ingen<br />**Visning av beregnet verdi**: Overlapp ingen \| Overlapp alle<br />|
|**Referensiell**|**Tilordne:** Overlapp ingen<br />**Overordne på nytt**: Overlapp ingen<br />**Del**: Overlapp ingen<br />**Slett**: Fjern kobling<br />**Opphev deling**: Overlapp ingen<br />**Flett**: Overlapp ingen<br />**Visning av beregnet verdi**: Overlapp ingen \| Overlapp alle<br />|
|**Referensiell, begrens sletting**|**Tilordne:** Overlapp ingen<br />**Overordne på nytt**: Overlapp ingen<br />**Del**: Overlapp ingen<br />**Slett**: Begrens<br />**Opphev deling**: Overlapp ingen<br />**Flett**: Overlapp ingen<br />**Visning av beregnet verdi**: Overlapp ingen \| Overlapp alle<br />|
|**Konfigurerbar overlapping**|Du kan konfigurere funksjonaliteten du ønsker for hver handling avhengig av de tilgjengelige alternativene|

> [!NOTE]
> Du kan kanskje ikke velge **Overordnet** hvis noen av enhetene allerede deltar i en overordnet enhetsrelasjon. Mer informasjon: [Overordnede enhetsrelasjoner](#parental-entity-relationships)
> 
> Hvis du bruker **Konfigurerbar overlapping** for å angi virkemåtene for handlingene slik at det samsvarer med virkemåten for handlingene som er tilknyttet annen **Funksjonalitetstype**, settes **Funksjonalitetstype** automatisk til den samsvarende typen når du lagrer relasjonen.  



## <a name="delete-relationships"></a>Slette relasjoner

Når du [viser enhetsrelasjoner](#view-entity-relationships), velger du enhetsrelasjonen du vil slette, og klikker på ![Slett-kommandoen](media/delete.gif)-kommandoen.

Hvis du sletter relasjonen, slettes oppslagsfeltet på den relaterte enheten.

> [!NOTE]
> Du vil ikke kunne slette en relasjon som har avhengigheter. Hvis du for eksempel har lagt til oppslagsfeltet i et skjema for den relaterte enheten, må du fjerne feltet fra skjemaet før du sletter relasjonen.

## <a name="parental-entity-relationships"></a>Overordnede enhetsrelasjoner

Hvert par med enheter som er kvalifiserte for en 1:N-relasjon, kan ha flere 1:N-relasjoner mellom dem. Vanligvis kan bare én av disse relasjonene anses som en overordnet enhetsrelasjon.

En overordnet enhetsrelasjon er en 1:N-enhetsrelasjon der ett av overlappingsalternativene i **Overordnet**-kolonnen i den følgende tabellen er sann.

|Handling|Overordnet|Ikke overordnet|  
|------------|--------------|------------------|  
|**Tilordne**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Slett**|Overlapp alle|Fjern kobling<br />Begrens|  
|**Overordne på nytt**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Dele**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  
|**Oppheve deling**|Overlapp alle<br />Overlapp brukereide<br />Overlapp aktive|Overlapp ingen|  

Hvis du for eksempel oppretter en ny egendefinert enhet og legger til en 1:N-enhetsrelasjon med forretningsforbindelsesenheten der den egendefinerte enheten er den relaterte enheten, kan du konfigurere handlingene for denne enhetsrelasjonen slik at den bruker alternativene i **Overordnet**-kolonnen. Hvis du senere legger til en ny 1:N-enhetsrelasjon med den egendefinerte enheten som den refererende enheten, kan du bare konfigurere handlingene for bruk av alternativene i **Ikke overordnet**-kolonnen.

Dette betyr vanligvis at for hvert enhetspar er det bare én overordnet relasjon. Det finnes enkelte tilfeller der oppslaget på den relaterte enheten kan tillate en relasjon til mer enn én type enhet.

For eksempel hvis en enhet har et kundeoppslag som kan referere til en kontakt- eller forretningsforbindelsesenhet. Det finnes to separate overordnede 1:N-enhetsrelasjoner.

En aktivitetsenhet har et lignende sett med overordnede enhetsrelasjoner for enheter som kan tilknyttes ved hjelp av oppslagsfeltet Angående.

<a name="BKMK_RelationshipBehaviorLimitations"></a>   

### <a name="limitations-on-behaviors-you-can-set"></a>Begrensninger for virkemåter som du kan angi
  
På grunn av overordnede relasjoner finnes det enkelte begrensninger som du bør ha i tankene når du definerer enhetsrelasjoner.  
  
- En egendefinert enhet kan ikke være hovedenhet i en relasjon med en relatert systemenhet som overlapper. Dette betyr at du ikke kan ha en relasjon med handling satt til **Overlapp alle**, **Overlapp aktive** eller **Overlapp brukereide** mellom en egendefinert hovedenhet og en relatert systemenhet.  
- Nye relasjoner kan ikke ha handling satt til **Overlapp alle**, **Overlapp aktiv** eller **Overlapp brukereide** hvis den relaterte enheten i relasjonen allerede finnes som en relatert enhet i en annen relasjon, som har en handling satt til **Overlapp alle**, **Overlapp aktiv** eller **Overlapp brukereide**. Dette hindrer relasjoner som har relasjoner med flere overordnede.  

### <a name="see-also"></a>Se også

[Opprette og redigere relasjoner mellom enheter](create-edit-entity-relationships.md)<br />
[Opprette og redigere 1:N-relasjoner (én-til-mange) eller N:1-relasjoner (mange-til-én)](create-edit-1n-relationships.md)<br />
[Opprette og redigere 1:N- (én-til-mange) eller N:1-enhetsrelasjoner (mange-til-én) i PowerApps-portalen](create-edit-1n-relationships-portal.md)<br />
[Opprette N:N-relasjoner (mange-til-mange)](create-edit-nn-relationships.md)

