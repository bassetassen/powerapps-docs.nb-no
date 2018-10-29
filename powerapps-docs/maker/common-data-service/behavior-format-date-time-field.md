---
title: Virkemåte og format for feltet Dato og klokkeslett i Common Data Service for Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: 73d691c7-344e-4c96-8979-c661c290bf81
caps.latest.revision: 47
ms.author: matp
manager: kvivek
ms.openlocfilehash: 2f62f2433fe959e3713df544628db186b801731e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39696498"
---
# <a name="behavior-and-format-of-the-date-and-time-field"></a>Virkemåte og format for feltet Dato og klokkeslett

I Common Data Service for Apps brukes datatypen Dato og klokkeslett i mange standardenhetsfelter. Avhengig av hva slags dato som representeres i feltet, kan du velge andre virkemåter for felt: **Brukerlokal**, **Bare dato** eller **Uavhengig av tidssone**.  
  
<a name="Behavior"></a>   

## <a name="date-and-time-field-behavior-and-format"></a>Virkemåte og format for feltet Dato og klokkeslett  

Tabellen nedenfor inneholder informasjon om virkemåte og format for feltet Dato og klokkeslett.  
  
|Virkemåte|Format|Beskrivelse|  
|--------------|------------|-------------------------------|  
|**Brukerlokal** |**Bare dato**<br />– eller –<br />**Dato og klokkeslett**|Dette er standard virkemåte for egendefinert dato og klokkeslett-felter.<br /><br />Feltverdiene vises i lokal tid for den gjeldende brukeren.<br />Disse verdiene returneres i nettjenester ved hjelp av et vanlig format for UTC-tidssone.<br /><br />Du kan endre dette én gang hvis du velger standardvirkemåte. Mer informasjon [Endre virkemåte for Brukerlokal](#change-user-local-behavior)|  
|**Bare dato**|**Bare dato**|Ingen konvertering av tidssone.<br /><br />Klokkeslettdelen av verdien er alltid 12:00 AM.<br />Datodelen av verdien lagres og hentes som angitt i brukergrensesnittet og nettjenester.|  
|**Uavhengig av tidssone**|**Bare dato**<br />– eller –<br />**Dato og klokkeslett**|Ingen konvertering av tidssone.<br /><br />Verdier for dato og klokkeslett lagres og hentes som angitt i brukergrensesnittet og nettjenester.|  

## <a name="change-user-local-behavior"></a>Endre virkemåte for brukerlokal:

Med mindre utgiveren av en administrert løsning hindrer dette, kan du endre virkemåten til et eksisterende egendefinert datofelter fra **Brukerlokal** til **Bare dato** eller **Uavhengig av tidssone**. Dette er en engangsendring.

Endring av virkemåte for feltet, påvirker feltverdiene som legges til eller blir endret, etter at virkemåten for feltet ble endret. De eksisterende feltverdiene forblir i databasen i formatet for UTC-tidssone. Hvis du vil endre virkemåten til de eksisterende feltverdiene fra UTC til bare dato, må du kanskje ha hjelp fra en utvikler for å gjøre det programmatisk. Mer informasjon: [Konverter virkemåte for eksisterende verdier for dato og klokkeslett i databasen](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute#convert-behavior-of-existing-date-and-time-values-in-the-database). 

> [!WARNING]
> Før du endrer virkemåten for et eksisterende felt for dato og klokkeslett, bør du se gjennom alle avhengigheter for feltet, for eksempel forretningsregler, arbeidsflyter, beregnede felter eller felter for beregnet verdi, for å sikre at det ikke er noen problemer som et resultat av å endre virkemåten. Når du har endret virkemåten til et felt for dato og klokkeslett, bør du åpne hver forretningsregel, arbeidsflyt, beregnet felt og felt for beregnet verdi, som avhenger av feltet som du har endret. Se gjennom informasjonen, og lagre den for å sikre at de siste virkemåtene og verdiene for feltet dato og klokkeslett brukes. 

### <a name="change-behavior-during-a-solution-import"></a>Endre virkemåte under en løsningsimport

Når du importerer en løsning som inneholder et datofelt ved hjelp av virkemåten **Brukerlokal**, får du kanskje muligheten til å endre virkemåten til **Bare dato** eller **Uavhengig av tidssone**.  

### <a name="prevent-changing-behavior"></a>Hindre endring av virkemåte

Hvis du distribuerer et tilpasset datofelt i en administrert løsning, kan du hindre at personer som bruker løsningen endrer virkemåten ved å angi den forvaltede egenskapen **CanChangeDateTimeBehavior** til **Usann**. Hvis du vil ha mer informasjon, kan du se [Forvaltede egenskaper for felt](set-managed-properties-metadata.md#field-managed-properties)
  
## <a name="use-cases"></a>Brukseksempler

Vurder følgende brukstilfeller for virkemåtene **Bare dato** og **Uavhengig av tidssone**.

### <a name="date-only-scenario-birthdays-and-anniversaries"></a>Bare dato-scenario: fødselsdager og jubileer

Bare dato-virkemåten er bra for tilfeller hvor informasjon om tid på dagen og tidssonen ikke er nødvendig, for eksempel fødselsdager eller jubileer. Med dette valget kan alle appbrukere over hele verden se nøyaktig den samme datoverdien.  
  
### <a name="time-zone-independent-scenario-hotel-check-in"></a>Tidssoneuavhengig scenario: Innsjekking på hotell

Du kan bruke denne virkemåten når tidssoneinformasjon ikke er nødvendig, for eksempel for innsjekkingstidspunkt for hotell. Med dette valget kan alle appbrukere over hele verden se nøyaktig den samme verdien for dato og klokkeslett.  


## <a name="date-and-time-query-operators-not-supported-for-date-only-behavior"></a>Spørringsoperatorer for dato og klokkeslett som ikke støttes for bare dato-virkemåte  

Følgende dato og klokkeslett-relaterte spørringsoperatorer er ugyldig for **Bare dato**-virkemåten. Det oppstår en unntaksfeil med ugyldig operator når en av disse operatorene er brukt i spørringen.  
  
- Eldre enn X minutter  
- Eldre enn X timer  
- Siste X timer  
- Neste X timer  

  
### <a name="see-also"></a>Se også

[Opprette og redigere felter](create-edit-fields.md)<br />
[Definer beregnede felter for å automatisere manuelle beregninger](define-calculated-fields.md)<br />
[Feltforvaltede egenskaper](set-managed-properties-metadata.md#field-managed-properties)<br />
[Forvaltede egenskaper](solutions-overview.md#managed-properties)

