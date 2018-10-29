---
title: Bruk forretningslogikk med kode | Microsoft Docs
description: Lær hvordan utviklere kan bruke kode til å ta i bruk forretningslogikk i Common Data Service for apper.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/26/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 9abcbf25d2376e28f83988ceb3797d3891ca53bc
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42843341"
---
# <a name="apply-business-logic-with-code"></a>Bruke forretningslogikk med kode

Du bør først, når dette er mulig, ta i bruk én av mange deklarative prosessalternativer når et krav innebærer å definere forretningslogikk. Se [Tilpassingsveiledning for Dynamics 365 Customer Engagement: Opprett egendefinert forretningslogikk ved bruk av prosesser](/dynamics365/customer-engagement/customize/guide-staff-through-common-tasks-processes)

Når en deklarativ prosess ikke oppfyller kravene, har du som utvikler flere alternativer. Dette emnet introduserer vanlige alternativer for å skrive kode.

## <a name="create-a-workflow-extension"></a>Opprett en arbeidsflytutvidelse

Du kan skrive en .NET-samling for å gi nye alternativer i prosessutformingsverktøyet. Denne metoden gir et nytt alternativ for personer som bruker arbeidsflytutformeren til å ta i bruk en betingelse eller utføre en ny handling. En arbeidsflytutvidelse kan deretter brukes på nytt av personer som ikke er utviklere, slik at de kan ta i bruk logikk i koden.

Mer informasjon: [Dynamics 365 Customer Engagement – Veiledning for utviklere: Egendefinerte arbeidsflytaktiviteter (arbeidsflytsamlinger)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies)

## <a name="create-a-plug-in"></a>Opprett et programtillegg

Du kan skrive en .NET-samling for å koble til datatransaksjonsflyten, hvis du ønsker å ta i bruk forretningslogikk på serveren. Med Common Data Service for apper bruker du et rammeverk til å registrere bestemte hendelser for å kjøre kode. Denne koden er definert inni en klasse i en samling. Den klassen arver et bestemt grensesnitt som viser en [kjøringsmetode](/dotnet/api/microsoft.xrm.sdk.iplugin.execute). Når den registrerte hendelsen skjer, aktiveres `Execute`-metoden i klassen, og den sender kontekstavhengige data om hendelsen.

Du bruker *Registreringsverktøyet* (programtillegg) til å registrere samlingene.

Med `Execute`-metoden kan du bruke objektmodellen som er definert i SDK-samlingene, til å evaluere de kontekstavhengige hendelsesdataene og utføre nødvendige handlinger, for å gjøre følgende:
- Bestem om du vil avbryte operasjonen ved å utløse en feil
- Foreta endringer til de kontekstavhengige dataene som sendes til kjøringsmetoden
- Foreta ytterligere operasjoner for å automatisere prosesser ved bruk av organisasjonstjeneste

### <a name="synchronous-and-asynchronous-plug-ins"></a>Synkrone og asynkrone programtillegg
Programtillegg kan registreres for å kjøre synkront i transaksjonen eller utsette og sende til en kø som tar i bruk logikken, på et tidspunkt som fører til mindre innvirkning på serveren. På grunn av dette foretrekkes asynkrone programtillegg.

Når du registrerer programtillegget til å kjøre synkront for en hendelse, har du alternativer om når koden skal kjøres. Det finnes tre trinn:

|Arrangement  |Beskrivelse  |
|---------|---------|
|Forhåndsvalidering|Skjer før databasetransaksjonen begynner. Her er det lurt å ta i bruk forretningslogikk for å bestemme om operasjonen skal avbrytes før transaksjonen begynner, for å unngå ytelsesstraffen der du må rulle tilbake transaksjonen.|
|Under selve operasjonen|Skjer etter at databasetransaksjonen har startet. Hvis du avbryter en operasjon på dette stadiet, må du rulle tilbake transaksjonen.|
|Etter operasjonen|Skjer innenfor databasetransaksjonen etter at den primære dataoperasjonen er fullført. Inkluderer eventuelle endringer som kan ha blitt tatt i bruk i tidligere hendelser, men det fører til en større straff når du avbryter operasjonen.|

> [!NOTE]
> Synkrone programtillegg har begrensninger på mengden systemressurser de kan bruke. Hvis et programtillegg overskrider tersklene eller ikke svarer, iverksettes et unntak, noe som avbryter operasjonen.

Mer informasjon: [Dynamics 365 Customer Engagement – Veiledning for utviklere: Skrive-programtillegg for å utvide forretningsprosesser](/dynamics365/customer-engagement/developer/write-plugin-extend-business-processes)

### <a name="see-also"></a>Se også

[Oversikt for utviklere – Common Data Service for apper](overview.md)
