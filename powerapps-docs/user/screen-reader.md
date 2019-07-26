---
title: " Bruk en skjerm leser i modell drevne apper | MicrosoftDocs"
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
- D365CE
ms.openlocfilehash: 555a587a3c0eeb599439f713c9a99a7ace6b205a
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/19/2019
ms.locfileid: "61545124"
---
# <a name="use-a-screen-reader"></a>Bruk en skjermleser 


Skjerm lesere gjør modell drevne apper tilgjengelige for personer som har lav eller ingen visjon eller som kanskje trenger ekstra støtte for et midlertidig scenario, for eksempel øye tretthet. Ofte brukte skjerm lesere som skjerm leser, JAWS og NVDA støttes. 

- [Lær mer om å arbeide med Microsoft-skjermleser](https://support.microsoft.com/help/22798)
- [Lær mer om å arbeide med JAWS](http://www.freedomscientific.com/Products/Blindness/JawsDocumentation)


- [Lær mer om å arbeide med NVDA](https://www.nvaccess.org/get-help/)


## <a name="basic-tasks-using-a-screen-reader"></a>Grunnleggende oppgaver ved hjelp av en skjerm leser 

### <a name="open-an-app"></a>Å åpne en app

1.  Bruk tabulatortasten i navigasjons feltet til  å gå til rulle gardin menyen for kontrollen, og trykk **Enter** for å åpne område kartet.
2.  Trykk **tab** -tasten til du hører navnet på programmet du vil åpne, for eksempel «salg». Trykk på **Enter** for å åpne appen.

### <a name="use-scan-mode-in-narrator"></a>Bruk skanne modus i skjerm leser
Du kan bruke skanne modus til raskt å navigere i apper ved hjelp av pil tastene og vanlige hurtig taster. Hopp raskt til overskrifter, koblinger, lande merker, skjema felt, kontroller og tabeller i denne modusen. Slå skanne modus på og av ved å trykke på **Caps Lock + mellomrom**. Mer informasjon: [Bruke skanne modus](https://support.microsoft.com/en-us/help/22809/windows-10-narrator-using-scan-mode)

### <a name="find-your-way-around-the-app"></a>Finn ut mer om appen

#### <a name="navigation-bar"></a>Navigasjonsfelt
Når du åpner en app, vises en loddrett linje med område ikoner til venstre. Du kan enten bruke **tabulatortasten** til å flytte gjennom disse ikonene til du hører navnet på del området du ønsker, for eksempel «kontoer,», eller du kan bruke kontrollen for område kart. Du kan for eksempel trykke på **tab** -tasten til du hører «kontoer», og deretter trykke på **Enter** for å åpne konto visningen.

#### <a name="grids"></a>Rute nett
Skjerm lesere navigerer i rute nett mer pålitelig og konsekvent, og annonser rad-og Kol onne overskrifter, i tillegg til posisjonen i rute nettet. Når du åpner et rute nett, er standard tabu lat ORS topp visnings velgeren. 

Når du angir en celle i rute nettet fra utenfor rute nettet, annonserer skjermleser navnet på tabellen, rad-og Kol onne antallet og plasseringen av markøren i tabellen.

Hvis markøren er innenfor tabell overskriften, kan du raskt navigere mellom topp tekster ved hjelp av **tab** -tasten eller **SKIFT + TAB**. Skjerm leser annonserer navnet på hver topp tekst når du skriver inn overskrifts cellen. Den inplasseringer også celle typen (for eksempel «Kol onne overskrift»), plasseringen av kolonnen (for eksempel «kolonne 1 av 6»), og om kolonnen er sortert eller merket. Hvis du trykker på **Enter** i en tabell overskrift, sorteres tabellen etter den kolonnen. Skjerm leser annonserer sorterings rekkefølgen, og du kan trykke **Enter** på nytt for å endre rekkefølgen.

Når du flytter ut av den siste kolonnen i tabellen, flyttes markøren til den andre raden i rute nettet, og fra dette punktet må du bruke pil opp-og nedpilen til å navigere mellom celler uten overskrift. Hvis du i stedet trykker på **tab** -tasten på nytt, flyttes markøren til det neste interaktive elementet, vanligvis tabell Filter listen. Når du flytter mellom rad celler som ikke er overskrifter, annonserer skjerm leseren Kol onne navnet, plasseringen av kolonnen og teksten i cellen.

#### <a name="forms"></a>Skjemaer
Flere navigasjons modi er tilgjengelige for å navigere i et skjema med skjerm leser, med de vanligste modusene som lander, overskrifter og skjema felt. Hvis du vil endre navigasjons modus, trykker du på **Caps Lock + pil opp**. Hold nede Caps Lock-tasten mens du trykker på pil opp-tasten for å gå gjennom modiene til du hører modusen du vil bruke. Deretter bruker du Caps Lock + pil venstre/høyre til å navigere gjennom de ulike elementene. Hvis du for eksempel vil gå til Etternavn-feltet i kontakt informasjon-delen av en kontakt, gjør du følgende:

1.  Trykk og hold nede **Caps Lock** -tasten, og trykk deretter på **pil opp** til du hører «lande merker».
2.  Trykk og hold nede **Caps Lock** -tasten, og trykk på **pil høyre** til du hører «kontakt informasjon».
3.  Endre modus ved å trykke på og holde nede **Caps Lock** -tasten og trykke på **pil opp** -tasten til du hører form-felt.
4.  Gå til Etternavn-feltet ved hjelp av Caps Lock + pil venstre/høyre til du hører «etter navn.» Skjerm leser annonserer også kontroll type, verdi, tilstand og eventuelle spesielle instruksjoner for feltet.

Du kan også bruke TAB-tasten til å navigere raskt til interaktive elementer i skjemaet. Noen skjema felt har et ikon som vil utføre standard handlingen når du trykker CTRL + ENTER. Et e-postskjema-felt kan for eksempel ha et konvolutt ikon som åpner et redigerings program for e-post. 

#### <a name="dashboardscharts"></a>Instrument bord/diagrammer
Du kan navigere gjennom instrument bord diagrammene ved hjelp av TAB-tasten og Caps Lock + pil taster. Trykk på **tab** for å gå raskt til de interaktive elementene, og bruk Caps Lock, en pil tast for navigasjon av ikke-interaktive elementer, for eksempel overskrifter, lande merker og elementer.


> [!NOTE]
> Du må ha den nyeste [Windows 10](http://www.microsoft.com/enable/products/windows10/default.aspx) -oppdateringen installert for å få alle tilgjengelighets funksjonene som er tilgjengelige for diagrammer.

#### <a name="interactive-dashboard-streams"></a>Interaktive instrument bord strømmer
Du kan bruke **tab** -tasten eller **SKIFT + TAB** -tastene til å flytte mellom interaktive instrument bord strømmer, som funnet på instrument bordet for kontoer, eller bare endre navigasjons modus til du hører «overskrifter», og deretter bruke **tab** -tasten til å flytte raskt mellom instrument bord strømmer.

Bruk pil opp/ned-tastene til å navigere gjennom hvert element i en instrument bord strøm. Skjerm leser leser typen kontroll og tittelen på kontrollen.

#### <a name="business-process-flows"></a>Forretnings prosess flyter
Du kan navigere i en forretnings prosess flyt, for eksempel den som finnes øverst i Kundeemne-skjemaet, ved å trykke på **tab** -tasten for å flytte fremover, og **SKIFT + TAB** for å flytte bakover mellom enhetene. Bruk **Enter** -tasten på **Flytt til venstre** eller **Flytt til høyre-** knappene for å vise flere enheter i prosess flyten. Skjermleser leser enhets type, fase, status, tittel, element nummer ut av total elementer og om det er valgt for øyeblikket.

#### <a name="dialog-boxes"></a>Dialog bokser

Når en dialog boks åpnes, annonserer skjerm leser tittelen. Når det gjelder dialog bokser med inn data felt, har **Lukk** -knappen standard fokus, slik at du kan lukke dialog boksen ved å trykke på **Enter**. Når det gjelder dialog bokser som krever bruker handling, er fokuset på den primære handlings knappen, for eksempel **delete** eller **OK**.

Du kan navigere gjennom kontrollene ved hjelp av **tabulatortasten** . Markøren går over hvert element i dialog boksen, og du kan trykke på **ESC** for å lukke det.


