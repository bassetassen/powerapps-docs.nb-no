---
title: Virkemåte og format for dato og klokkeslett-feltet i Common Data Service | MicrosoftDocs
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: 73d691c7-344e-4c96-8979-c661c290bf81
caps.latest.revision: 47
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="behavior-and-format-of-the-date-and-time-field"></a>Virkemåte og format for feltet Dato og klokkeslett

I Common Data Service brukes dato- og klokkeslettypen i mange standard enhetsfelt. Du kan velge flere forskjellige virkemåter, avhengig av hvilken dato feltet representerer: **Brukerlokal**, **Bare dato** eller **Tidssoneuavhengig**.  
  
<a name="Behavior"></a>   

## <a name="date-and-time-field-behavior-and-format"></a>Virkemåte og format for feltet Dato og klokkeslett  

Tabellen nedenfor inneholder informasjon om Dato og klokkeslett-feltets virkemåte og format.  
  
|Virkemåte|Format|Beskrivelse|  
|--------------|------------|-------------------------------|  
|**Brukerlokal** |**Bare dato**<br />- eller -<br />**Dato og klokkeslett**|Dette er standardvirkemåten for egendefinerte dato- og klokkeslettfelt.<br /><br />Feltverdiene vises i lokal tid for den gjeldende brukeren.<br />I webtjenester blir disse verdiene returnert ved hjelp av et vanlig UTC-tidssoneformat.<br /><br />Hvis du velger standard virkemåte, kan du endre denne én gang. Mer informasjon [Endre brukerlokal virkemåte](#change-user-local-behavior)|  
|**Bare dato**|**Bare dato**|Ingen tidssonekonvertering.<br /><br />Klokkeslettdelen av verdien er alltid 12:00<br />Datodelen av verdien lagres og hentes slik det er angitt i brukergrensesnittet og webtjenestene.|  
|**Tidssoneuavhengig**|**Bare dato**<br />- eller -<br />**Dato og klokkeslett**|Ingen tidssonekonvertering.<br /><br />Dato og klokkeslett-verdiene lagres og hentes slik det er angitt i brukergrensesnittet og webtjenestene.|  

## <a name="change-user-local-behavior"></a>Endre brukerlokal virkemåte:

Med mindre utgiveren av en administrert løsning hindrer dette, kan du endre virkemåten for eksisterende egendefinerte datofelt fra **Brukerlokal** til **Bare dato** eller **Tidssoneuavhengig**. Dette er en engangs endring.

Endringen av feltets virkemåte påvirker feltverdiene som er lagt til eller endret etter at feltets virkemåte ble endret. De eksisterende feltverdiene forblir i databasen i UTC-tidssoneformatet. Hvis du vil endre de eksisterende feltverdienes virkemåte fra UTC til Bare dato, trenger du kanskje hjelp av en utvikler for å gjøre det programmatisk. Mer informasjon: [Konvertere virkemåte for eksisterende verdier for dato og klokkeslett i databasen](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute#convert-behavior-of-existing-date-and-time-values-in-the-database). 

> [!WARNING]
> Før du endrer virkemåten for et eksisterende dato og klokkeslett-felt, bør du gå gjennom alle avhengighetene for feltet, f.eks. forretningsregler, arbeidsflyt og beregnede felt eller felt for beregnet verdi, for å sørge for at det ikke oppstår problemer som følge av endringen av virkemåte. Når du har endret virkemåten til et felt for dato og klokkeslett, bør du åpne hver forretningsregel, arbeidsflyt, hvert beregnede felt og felt for beregnet verdi som er avhengig av feltet du endret, se gjennom informasjonen, og lagre den for å sikre at det er den nyeste virkemåten og verdien for dato og klokkeslett-felt, som brukes. 

### <a name="change-behavior-during-a-solution-import"></a>Endre virkemåte under en løsningsimport

Når du importerer en løsning som inneholder et datofelt ved hjelp **Brukerlokal** virkemåte, har du mulighet til å endre virkemåten til **Bare dato** eller **Tidssoneuavhengig**.  

### <a name="prevent-changing-behavior"></a>Hindre endring av virkemåte

Hvis du distribuerer et egendefinert datofelt i en administrert løsning, kan du hindre personer som bruker løsningen, fra å endre virkemåten ved å sette den administrerte egenskapen **CanChangeDateTimeBehavior** til **Usann**. Mer informasjon: [Feltadministrerte egenskaper](set-managed-properties-metadata.md#field-managed-properties)
  
## <a name="use-cases"></a>Brukssaker

Vurder følgende brukssaker for virkemåten **Bare dato** og **Tidssoneuavhengig**.

### <a name="date-only-scenario-birthdays-and-anniversaries"></a>Scenario for Bare dato: fødselsdager og merkedager

Virkemåten Bare dato er god for tilfeller der opplysninger om klokkeslett og tidssone ikke er nødvendig, for eksempel fødselsdager eller merkedager. Med dette valget vil alle appbrukere over hele verden se nøyaktig samme datoverdi.  
  
### <a name="time-zone-independent-scenario-hotel-check-in"></a>Scenario for tidssoneuavhengig: sjekke inn på hotell

Du kan bruke denne virkemåten når tidssoneinformasjon ikke er nødvendig, for eksempel innsjekkingstid på hotell. Med dette valget vil alle appbrukere over hele verden se nøyaktig samme dato og klokkeslett-verdi.  


## <a name="date-and-time-query-operators-not-supported-for-date-only-behavior"></a>Spørringsoperatorer for dato og klokkeslettet støttes ikke for virkemåten Bare dato  

Følgende dato- og klokkeslettrelaterte spørringsoperatorer er ugyldige for virkemåten **Bare dato**. Det oppstår en feil med ugyldig operator når en av disse operatorene brukes i spørringen.  
  
- Eldre enn X minutter  
- Eldre enn X timer  
- Siste X timer  
- Neste X timer  

  
### <a name="see-also"></a>Se også

[Opprette og rediger felt](create-edit-fields.md)<br />
[Definere beregnede felt for å automatisere manuelle beregninger](define-calculated-fields.md)<br />
[Feltadministrerte egenskaper](set-managed-properties-metadata.md#field-managed-properties)<br />
[Forvaltede egenskaper](solutions-overview.md#managed-properties)

