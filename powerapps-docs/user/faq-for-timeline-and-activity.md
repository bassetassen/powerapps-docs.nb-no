---
title: Vanlige spørsmål om aktiviteter og tidslinjeveggen | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 01/29/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 08859f70e047d1c53379e8a79f56997d6beedc58
ms.sourcegitcommit: 982cab99d84663656a8f73d48c6fae03e7517321
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/28/2019
ms.locfileid: "67457003"
---
# <a name="frequently-asked-questions-about-activities-and-the-timeline-wall"></a>Vanlige spørsmål om aktiviteter og tidslinjeveggen  

## <a name="is-a-title-required-when-adding-a-new-note"></a>Kreves det en tittel når et nytt notat legges til?

nei. Når du legger til et notat for en aktivitet, er tittelfeltet merket som et obligatorisk felt, men det kreves ingen tittel. Dette er et kjent problem i den eldre nettklienten.

## <a name="for-an-appointment-when-i-choose-the-option-to-save-as-draft-it-doesnt-show-that-the-appointment-has-been-saved-as-a-draft"></a>Det vises ikke at avtalen er lagret som en kladd når jeg velger alternativet for å *Lagre som kladd* for avtaler.

Når du lagrer en avtale som en kladd i den eldre nettklienten, vises ikke tittelen **[KLADD]** , noe som indikerer at avtalen er lagret som en kladd.

## <a name="can-i-add-activities-to-read-only-records"></a>Kan jeg legge til aktiviteter for skrivebeskyttede poster?

ja. Du kan legge til aktiviteter for skrivebeskyttede enheter, for eksempel notater, telefonsamtaler, oppgaver og mer. 

## <a name="are-html-tags-supported-in-notes"></a>Støttes HTML-koder i **Notater**?

nei. Når du oppretter en notataktivitet for en hvilken som helst post eller enhet, støttes ikke HTML-koder. Hvis du for eksempel legger `<TAG> </TAG>` til et Notat felt, vises det som. `<TAG_XXX="XX"> </TAG>`

## <a name="how-can-i-improve-performance-on-timeline-wall"></a>Hvordan kan jeg forbedre ytelsen for tidslinjeveggen?

Du kan forbedre ytelsen for tidslinjeveggen ved å optimere hvor mye data som returneres av en bestemt enhetspost. 

1.  Konfigurer enhetsskjemaer til bare å vise aktiviteter som er i bruk.  Dette kan gjøres på skjemanivå, slik at bare nyttige aktiviteter vises.  Hvis du ikke bruker oppgaver for saker, kan du for eksempel konfigurere tidslinjeveggen i saksskjemaet til ikke å vise aktiviteter.
2.  Reduser antall standardposter som vises på tidslinjeveggen.  Den er som standard satt til å returnere 10, mer enn 10 kan føre til ytelsesproblemer.  Vi anbefaler å ikke overstige standardgrensen. 

## <a name="activity-wall-is-not-supported-in-print-preview"></a>Aktivitetsveggen støttes ikke i forhåndsvisning.

Når du velger alternativet **Forhåndsvisning** i Dynamics 365, vises ikke **tidslinjeveggen** i listen over tilgjengelige alternativer. Du vil se **Notater**, men oppgaver eller e-postmeldinger vises ikke.





