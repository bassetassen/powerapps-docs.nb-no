---
title: Vise historikken til en løsning | MicrosoftDocs
description: Lær hvordan du viser historikken til en løsning
keywords: null
ms.date: 05/19/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
  - powerapps
ms.assetid: null
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="view-the-history-of-a-solution"></a>Vise historikken til en løsning
Du kan vise detaljer om løsningsoperasjoner fra området **Løsninger** i en modelldrevet app. En operasjon kan være en løsningsimport, -eksport eller -sletting. Løsningshistorikken viser informasjon som løsningsversjon, løsningsutgiver, operasjonstype, start- og sluttidspunkt for operasjonen samt operasjonsstatus.

> [!div class="mx-imgBorder"] 
> ![](media/solutions-history-custom-view.png "Tilpasset visning av løsningshistorikk")

## <a name="view-solution-history"></a>Vis løsningshistorikk
1. Velg **Innstillinger** og deretter **Løsningshistorikk**.

     > [!div class="mx-imgBorder"] 
     > ![](media/solution-history-sitemap.png "Løsningshistorikkområde")

     > [!NOTE]
     > For å komme deg til området **Innstillinger** i en PowerApps-enhetlig grensesnitt modelldrevet app velger du **Innstillinger** ![Innstillinger](../model-driven-apps/media/powerapps-gear.png) på verktøylinjen for appen og deretter **Avanserte innstillinger**. 

2. Som standard vises **Tilpasset løsningshistorikk**-visningen. Følgende visninger er tilgjengelige fra området **Løsningshistorikk**. 
- **All løsningshistorikk**. Viser løsningshistorikken til både interne system- og tilpassede løsninger. 
- **Historikk for tilpassede løsninger**. Viser bare løsningshistorikken til tilpassede løsninger. 
- **Historikk for interne løsninger**. Viser løsningshistorikken til bare interne systemløsninger. 

Hver enkelt løsningshistorikkoppføring er skrivebeskyttet og inneholder følgende egenskaper: 
- **Starttidspunkt**. Tidspunktet da operasjonen startet. 
- **Sluttidspunkt**: tidspunktet da operasjonen ble avsluttet. 
- **Løsningsversjon**. Løsningsversjonen. 
- **Navn på utgiver**. Navnet på utgiveren som er knyttet til operasjonen. Mer informasjon: [Endre løsningsutgiverprefikset](change-solution-publisher-prefix.md)  
- **Operasjon**. Operasjonen, for eksempel import, eksport eller sletting. Mer informasjon: [Importere, oppdatere og eksportere løsninger](import-update-export-solutions.md)
- **Underoperasjon**: angir operasjonstypen, for eksempel at en ny løsning importeres eller at en eksisterende løsning oppdateres. 
- **Status**. Gjeldende status for operasjonen, for eksempel **Fullført** eller **Ikke fullført**. 
- **Resultat**. Resultatet av operasjonen, for eksempel om den var **Vellykket** eller **Mislykket**. 
- **Feilkode**: feilkode returnert fra operasjonen. En feilkode på 0 betyr at operasjonen ble fullført. 

### <a name="view-solution-operation-error-details"></a>Vis feildetaljer for løsningsoperasjonen 
Når en løsningsoperasjon inkluderer en feil, kan du velge den for å vise en side med flere feildetaljer. 

> [!div class="mx-imgBorder"] 
> ![](media/solution-history-with-failure.png "Løsningshistorikk med operasjonsfeil")

Detaljsiden inneholder informasjon som inkluderer **Unntaksmeldingen** som kan hjelpe deg med å diagnostisere den underliggende årsaken til at operasjonen mislyktes. Noen feil, blant annet feil i løsningsavhengigheten, kan også inneholde koblinger til **løsningslag** for å gjøre det enklere for deg å diagnostisere problemet. **Aktivitets-IDen** kan være nyttig i tilfeller der du må kontakte Microsofts kundestøtte. 

> [!div class="mx-imgBorder"] 
> ![](media/solution-history-error-details.png "Feildetaljer for løsningsoperasjonen")

### <a name="see-also"></a>Se også
[Vise løsningslag](solution-layers.md)  <br />
[Løsningsoversikt](solutions-overview.md) 


