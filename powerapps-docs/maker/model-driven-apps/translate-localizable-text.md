---
title: Oversette oversettbar tekst for modelldrevne apper | MicrosoftDocs
description: Lær hvordan du får oversettbar tekst oversatt for å støtte flere språk
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="translate-localizable-text-for-model-driven-apps"></a>Oversette oversettbar tekst for modelldrevne apper

Hvis du har tilpasset enhets- eller felttekst, for eksempel feltetiketter eller rullegardinlisteverdier, kan du gi brukere i miljøet som ikke arbeider med originalspråkversjonen for miljøet ditt, denne tilpassede teksten på deres foretrukne språk. 

Prosessen har følgende trinn:
1. Aktivere andre språk for miljøet ditt
2. Eksportere oversettbar tekst
3. Få den oversettbare teksten oversatt
4. Importere den oversatte teksten

## <a name="enable-other-languages-for-your-environment"></a>Aktivere andre språk for miljøet ditt

Hvis du ikke allerede har aktivert språken for miljøet ditt, kan du bruke trinnene beskrevet i [Aktivere språket](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) for å aktivere dem.

> [!IMPORTANT]
> Hvert språk kan ta flere minutter å aktivere. I dette tidsrommet kan andre brukere av miljøet kanskje ikke bruke appen. Du bør aktivere språk på et tidspunkt som i minst mulig grad vil forstyrre brukerne.

> [!TIP]
> Når du aktiverer språkene, må du notere LCID-verdiene som brukes for hvert språk. Denne verdien representerer språket i de eksporterte dataene for den oversettbare teksten. Språkkoder er ID-er for nasjonal innstilling med fire eller fem sifre. Du finner gyldige ID-verdier for nasjonal innstilling på [Diagram over ID for nasjonale innstillinger (LCID)](http://go.microsoft.com/fwlink/?LinkId=122128).

## <a name="export-the-localizable-text"></a>Eksportere oversettbar tekst

Omfanget av den oversettbare teksten som eksporteres, er den uadministrerte løsningen som inneholder den oversettbare teksten. Dette kan bare gjøres i løsningsutforskeren.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Åpne den uadministrerte løsningen som inneholder den oversettbare teksten, og velg **Oversettelser** > **Eksporter oversettelser** på menylinjen. 

![Eksportere oversettelser](media/export-localizable-text.png)

Du skal se et varsel:
> Eksport av egendefinerte etiketter for oversettelse kan ta flere minutter. Ikke klikk koblingen Eksporter på nytt før første eksport er fullført. Er du sikker på at du vil eksportere nå? 

Klikk **OK** hvis du vil fortsette.

Når eksporten er fullført, kan du finne en fil kalt for `CrmTranslations_{0}_{1}.zip` i nedlastingsmappen, der `{0}` er det unike navnet på løsningen og `{1}` er versjonsnummeret til løsningen.

## <a name="get-the-localizable-text-translated"></a>Få den oversettbare teksten oversatt

Du kan sende denne filen til en språkekspert, et oversettingsbyrå eller et lokaliseringsselskap.

Hvis du har kunnskap til å oversette teksten, eller hvis du bare vil se formatet, kan du pakke ut zip-filen du eksporterte. Du ser at den inneholder to XML-filer. 
 - `[Content_Types].xml`
 - `CrmTranslations.xml`

Du kan åpne filen CrmTranslations.xml med Microsoft Office Excel.

> [!TIP]
> Med mindre du vanligvis åpner XML-filer i Excel, kan det være enklere å åpne Excel og deretter velge å åpne filen ved å lime inn banen til den utpakkede CrmTranslations.xml-filen.

> [!IMPORTANT]
> Kontroller at du ikke endrer formatet. Hvis du lagrer filen i et annet format, kan du ikke importere den tilbake.

Når du viser dataene i Excel, se på kategorien **Lokaliserte etiketter**.

![Eksportere tekst for lokalisering](media/localized-labels-tab-exported-languages.png)

Egendefinerte enheter eller felt har tomme celler for den oversettbare teksten. Legg til de lokaliserte verdiene for disse elementene.

> [!NOTE]
> Hvis du har endret visningsnavnet eller beskrivelsen for en standardenhet eller et enhetsfelt, skal de lokaliserte strengene fortsatt gjenspeile oversettelsene for den opprinnelige verdien. Disse bør oversettes for å vise den nye verdien.

Kategorien **Visningsstrenger** inneholder tekst som vises for andre elementer i brukergrensesnittet, for eksempel kommandoer, feilmeldinger og skjemaetiketter på båndet.

### <a name="updating-localizable-text-in-the-base-language"></a>Oppdatere oversettbar tekst i originalspråket

Hvis du endrer visningsnavnet for en hvilken som helst standardenhet eller et enhetsfelt som er inkludert i en spesialmelding, kan du oppdatere informasjonen i kategorien **Visningsstrenger** for å bruke det egendefinerte navnet.

> [!TIP]
> Selv om brukergrensesnittet som brukes til redigering av systemenhetsmeldinger, inneholder mange referanser til enhetsnavn, er ikke alle inkludert. Denne teknikken kan finne mer. Mer informasjon: [Redigere systemenhetsmeldinger](../common-data-service/edit-system-entity-messages.md)

Hvis du for eksempel endrer visningsnavnet for forretningsforbindelsesenheten til *Firma*, kan du søke via originalspråk-kolonnen i **Visningsstrenger** etter følgende treff: `account`, `accounts`, `Account` og `Accounts` og deretter foreta aktuelle erstatninger i henholdsvis `company`, `companies`, `Company` og `Companies`.

> [!IMPORTANT]
> Ikke gjør en generell søk/erstatt i filen for dette. Du må passe på at den samsvarende teksten faktisk refererer til navnene du har endret.


## <a name="import-the-localized-text"></a>Importere den oversatte teksten
Importering av teksten krever komprimering av filene og å importere dem i systemet.

### <a name="compress-the-files"></a>Komprimere filene

Når det er gjort endringer i `CrmTranslations.xml`-filen, må du komprimere filen sammen med `[Content_Types].xml`-filen i zip-format. Velg *Begge filer*, og høyreklikk deretter for å åpne hurtigmenyen. Velg **Send til** > **Komprimert (zippet) mappe** på hurtigmenyen.

### <a name="import-the-files"></a>Importere filene

Fra den samme uadministrerte løsningen som du eksporterte oversettelsene fra, velger du **Oversettelser** > **Importer oversettelser** på menyen. 

![Importer oversettelser](media/import-translations.png)

Velg filen som inneholder den komprimerte, oversatte teksten, og velg deretter **Importer**.

![Importere valgt fil](media/import-translated-text-dialog.png)

Når den oversatte teksten er importert, må du publisere alle tilpassinger for å se endringene i apper.

## <a name="community-tools"></a>Fellesskapsverktøy

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) er et verktøy som XrmToolBox-fellesskapet utviklet. Bruk Easy Translator til å eksportere og importere oversettelser med kontekstavhengig informasjon. 

> [!NOTE]
> Fellesskapsverktøyene støttes ikke av Microsoft.
> Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com).


## <a name="next-steps"></a>Neste trinn
[Alternativer for region og språk for organisasjonen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)<br />
[Redigere systemenhetsmeldinger](../common-data-service/edit-system-entity-messages.md)

