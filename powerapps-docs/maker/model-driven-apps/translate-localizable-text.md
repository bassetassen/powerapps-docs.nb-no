---
title: Oversett lokaliserbar tekst for modelldrevne apper | MicrosoftDocs
description: Lær hvordan lokaliserbar tekst kan oversettes for å støtte flere språk
ms.custom: ''
ms.date: 06/03/2018
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
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
ms.openlocfilehash: e2e305313f3b86be2ea410f6668676b56aa79d95
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/08/2018
ms.locfileid: "39690800"
---
# <a name="translate-localizable-text-for-model-driven-apps"></a>Oversett lokaliserbar tekst for modelldrevne apper

Hvis du har tilpasset enhet eller en felttekst, for eksempel feltetiketter eller listeverdier for rullegardiner, kan du gi brukerne i miljøet, som ikke jobber med originalspråk-versjonen for miljøet, denne egendefinerte teksten i foretrukket språk. 

Prosessen har følgende trinn:
1. Aktiver andre språk for miljøet
2. Eksporter lokaliserbar tekst
3. Få lokaliserbar tekst oversatt
4. Importer lokalisert tekst

## <a name="enable-other-languages-for-your-environment"></a>Aktiver andre språk for miljøet

Hvis du ikke har aktivert språkene for miljøet, kan du bruke trinnene som er beskrevet i [Aktiver språket](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) for å aktivere dem.

> [!IMPORTANT]
> Hvert språk kan ta flere minutter å aktivere. I denne perioden kan det hende at andre brukere av miljøet ikke kan bruke appen. Du bør aktivere språk på tidspunktet som er minst forstyrrende for brukere.

> [!TIP]
> Merk LCID-verdiene som brukes for hvert språk når du aktiverer språk. Verdien representerer språket for den lokaliserbare teksten i dataene som eksporteres. Språkkoder er ID-er for nasjonal innstilling bestående av fire eller fem sifre. Gyldige ID-er for nasjonale innstillingsverdier finner du i [Diagram for ID for nasjonal innstilling (LCID))](http://go.microsoft.com/fwlink/?LinkId=122128).

## <a name="export-the-localizable-text"></a>Eksporter lokaliserbar tekst

Omfanget av den lokaliserbare teksten som skal eksporteres, er den ubehandlede løsningen som inneholder den lokaliserbare teksten. Dette kan bare gjøres ved hjelp av løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Åpne den ubehandlede løsningen som inneholder den lokaliserbare teksten på menylinjen. Velg **Oversettelser** > **Eksporter oversettelser**. 

![Eksporter oversettelser](media/export-localizable-text.png)

Du skal se et varsel som sier:
> Eksport av egendefinerte etiketter for oversettelse kan ta flere minutter. Ikke klikk på koblingen for eksport på nytt, før den første eksporten er fullført. Er du sikker på at du vil eksportere nå? 

Klikk på**OK** hvis du vil fortsette.

Når eksporten er fullført, kan du finne en fil med et navn som ligner på `CrmTranslations_{0}_{1}.zip` i nedlastingsmappen der `{0}` er det unike navnet på løsningen, og `{1}` er versjonsnummeret for løsningen.

## <a name="get-the-localizable-text-translated"></a>Få lokaliserbar tekst oversatt

Du kan sende denne filen til en lingvistisk ekspert, et oversettelsesbyrå eller lokaliseringsfirma.

Hvis du har kunnskapen til å oversette teksten, eller hvis du bare ønsker å se formatet, kan du pakke ut zip-filen du eksporterte. Du vil se at den inneholder to XML-filer. 
 - `[Content_Types].xml`
 - `CrmTranslations.xml`

Du kan åpne filen CrmTranslations.xml med Microsoft Office Excel.

> [!TIP]
> Med mindre du vanligvis åpner XML-filer med Excel, kan det være enklere å åpne Excel, og deretter velge å åpne filen ved å lime inn banen til den utpakkede CrmTranslations.xml-filen.

> [!IMPORTANT]
> Kontroller at du ikke endrer filformatet. Hvis du lagrer filen i et annet format, kan du ikke importere den tilbake.

Når du viser dataene i Excel, kan du se på fanen **Lokaliserte etiketter**.

![Eksportert tekst for lokalisering](media/localized-labels-tab-exported-languages.png)

Alle egendefinerte enheter eller felter har tomme celler for den lokaliserbare teksten. Legg til de lokaliserte verdiene for elementene.

> [!NOTE]
> Hvis du har endret visningsnavnet eller beskrivelse for en hvilken som helst standardenhet eller et enhetsfelt, vil de lokaliserte strengene fortsatt gjenspeile oversettelser for den opprinnelige verdien. Disse bør være lokalisert for å gjenspeile den nye verdien.

Fanen **Visningsstrenger** inneholder teksten som vises for andre grensesnittelementer, som kommandoer på båndet, feilmeldinger og skjemaetiketter.

### <a name="updating-localizable-text-in-the-base-language"></a>Oppdaterer lokaliserbar tekst på originalspråket

Hvis du endrer visningsnavnet for en hvilken som helst standardenhet eller et enhetsfelt som er inkludert i alle spesielle meldinger, kan du oppdatere informasjon i **Visningsstrenger**-fanen for å bruke det egendefinerte navnet.

> [!TIP]
> Selv om brukergrensesnittet som vises for å redigere enhetsmeldinger for system inneholder mange referanser til enhetsnavn, inneholder det ikke alle. Du kan finne flere ved å bruke denne teknikken. Mer informasjon: [Rediger meldinger for systemenhet](../common-data-service/edit-system-entity-messages.md)

Hvis du for eksempel endrer visningsnavnet for konto-enheten til *Firma*, kan du søke via kolonnen for originalspråk i **Visningsstrenger** for følgende samsvar: `account`, `accounts`, `Account`, og `Accounts`, og deretter gjøre riktige erstatninger for henholdsvis `company`, `companies`, `Company`, og `Companies`.

> [!IMPORTANT]
> Ikke gjør en generell søk og erstatt i filen for dette. Du bør sjekke at den samsvarende teksten faktisk refererer til navnene du har endret.


## <a name="import-the-localized-text"></a>Importer lokalisert tekst
Import av teksten krever komprimering av filene, og at de importeres til systemet.

### <a name="compress-the-files"></a>Komprimer filene

Etter at endringer er gjort for `CrmTranslations.xml`-filen, må du komprimere filen sammen med `[Content_Types].xml`-filen til zip-formatet. Velg *begge filene*, og klikk deretter med den høyre museknappen for å åpne kontekstmenyen. I kontekstmenyen kan du velge **Send til** > **Komprimert (zippet) mappe**.

### <a name="import-the-files"></a>Importer filene

Velg **Oversettelser** > **Importer oversettelser** fra den samme ubehandlede løsningen som du eksporterte oversettelsene fra. 

![Importer oversettelser](media/import-translations.png)

Velg filen som inneholder den komprimerte oversatte teksten, og velg **Import**.

![Importer valgt fil](media/import-translated-text-dialog.png)

Når den oversatte teksten er importert, bør du publisere alle tilpassinger for å se endringene i appene;

## <a name="community-tools"></a>Fellesskapsverktøy

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) er et verktøy som XrmToolBox-fellesskapet utviklet. Bruk Easy Translator til å eksportere og importere oversettelser med begrepsinformasjon. 

> [!NOTE]
> Fellesskapsverktøyet støttes ikke av Microsoft.
> Hvis du har spørsmål om verktøyet, kan du kontakte utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).


## <a name="next-steps"></a>Neste trinn
[Område og språkalternativer for organisasjonen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)<br />
[Rediger meldinger for systemenhet](../common-data-service/edit-system-entity-messages.md)

