---
title: Oversikt over Microsoft Translator-tilkoblingen | Microsoft Docs
description: Se hvordan du kobler til Microsoft Translator, gå gjennom noen eksempler, og se alle funksjonene
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 07/12/2017
ms.author: lanced
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 405dcf432526206aa3a5f341a38e2ae5547cea1f
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 04/23/2019
ms.locfileid: "61545704"
---
# <a name="connect-to-microsoft-translator-from-powerapps"></a>Koble til Microsoft Translator fra PowerApps
![Microsoft Translator](./media/connection-microsoft-translator/translatoricon.png)

Legg til Microsoft Translator-koblingen for å vise oversatt tekst i en **Etikett**-kontroll i appen din. Du kan for eksempel opprette en tekstboks for inndata som ber brukeren om å skrive inn en tekst som skal oversettes. Du kan vise den oversatte teksten i en annen etikett.

Dette emnet viser deg hvordan du oppretter Microsoft Translator-tilkoblingen og bruker Microsoft Translator-tilkoblingen i en app. Her finner du også en oversikt over de tilgjengelige funksjonene.

> [!NOTE]
> Denne koblingen er begrenset til 150 oppkall per bruker per dag.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-microsoft-translator"></a>Slik kobler du til Microsoft Translator
1. Åpne PowerApps, velg **Ny** og opprett en **Blank app**. Velg oppsett for telefon eller nettbrett. Oppsettet for nettbrett gir deg et større arbeidsområde:  

   ![Åpne en tom app](./media/connection-microsoft-translator/blank-app.png)
2. Klikk eller trykk på **Data**-fanen i den høyre ruten, og klikk eller trykk på **Legg til datakilde**.
3. Velg **Ny tilkobling**, og velg deretter **Microsoft Translator**:  

    ![Slik kobler du til Microsoft Translator](./media/connection-microsoft-translator/addconnection.png)

    ![Slik kobler du til Microsoft Translator](./media/connection-microsoft-translator/add-translator.png)
4. Velg **Connect**. Tilkoblingen din vises under **Datakilder**:  

    ![Slik kobler du til Microsoft Translator](./media/connection-microsoft-translator/translatordatasource.png)

## <a name="use-the-microsoft-translator-connection-in-your-app"></a>Slik bruker du Microsoft Translator-tilkoblingen i appen din
### <a name="translate-text"></a>Oversett tekst
1. Velg **Tekst** på **Sett inn**-menyen, og velg **Tekstinndata**. Gi kontrollen for tekstinndata **Source** som nytt navn:  

    ![Gi nytt navn](./media/connection-microsoft-translator/renametosource.png)
2. Legg til en **Rullegardinliste** (**Sett inn**-menyen > **Kontroller**), gi den **TargetLang** som nytt navn, og flytt den til under **Source**.
3. Angi **[Items](../controls/properties-core.md)**-egenskapen for **TargetLang** som følgende formel:  

    `MicrosoftTranslator.Languages()`
4. Legg til en etikett, flytt den under **TargetLang**, og angi **[Text](../controls/properties-core.md)**-egenskapen som følgende formel:  

    `MicrosoftTranslator.Translate(Source.Text, TargetLang.Selected.Value)`
5. Skriv inn en vilkårlig tekst i **Source**, og velg et språk i **TargetLang**. Etiketten viser teksten du skrev inn på språket du valgte:  

    ![Slik oversetter du fra engelsk til spansk](./media/connection-microsoft-translator/translate-text.png)

### <a name="speak-translated-text"></a>Les opp oversatt tekst
Hvis du ikke allerede har gjort det, følger du trinnene i forrige del for å oversette en vilkårlig tekst. Disse neste trinnene bruker de samme kontrollene.

1. Angi **[Items](../controls/properties-core.md)**-egenskapen for rullegardinlisten **TargetLang** som følgende formel:  

    `MicrosoftTranslator.SpeechLanguages()`
2. Gi den andre etiketten (ikke **Source**-boksen) **Target** som nytt navn.
3. Legg til en **Lyd**-kontroll (**Sett inn**-menyen > **Media**), og angi kontrollens **Media**-egenskap som følgende formel:  

    `MicrosoftTranslator.TextToSpeech(Target.Text, TargetLang.Selected.Value)`
4. Trykk på F5, eller velg forhåndsvisningsknappen (![](./media/connection-microsoft-translator/preview.png)). Skriv inn vilkårlist tekst i **Source**, velg et språk i **TargetLang**, og velg avspillingsknappen i lydkontrollen.

    Appen spiller av en lydversjon av teksten som du skrev inn på språket du valgte.
5. Trykk på Esc for å gå tilbake til standardarbeidsområdet.

### <a name="detect-the-source-language"></a>Gjenkjenne kildespråket
Disse neste trinnene bruker samme **Source**-tekstinndata- og **Target**-tekstkontroller. Hvis du ønsker det, kan du opprette nye kontroller. Bare oppdater navnene i formelen.

1. Velg **Target**-tekstkontrollen og angi **[Text](../controls/properties-core.md)**-egenskapen som følgende formel:  

    `MicrosoftTranslator.Detect(Source.Text).Name`
2. Skriv inn en vilkårlig tekst i **Source**.

    Etiketten viser språket til teksten du skrev inn. Etiketten viser for eksempel **French** hvis du skriver inn **bonjour**, eller **Italian** Hvis du skriver inn **ciao**.

## <a name="view-the-available-functions"></a>Vise de tilgjengelige funksjonene
Denne tilkoblingen har følgende funksjoner:

| Funksjonsnavn | Beskrivelse |
| --- | --- |
| [Languages](connection-microsoft-translator.md#languages) |Henter alle språkene som Microsoft Translator støtter |
| [Translate](connection-microsoft-translator.md#translate) |Oversetter tekst til et angitt språk ved hjelp av Microsoft Translator |
| [Detect](connection-microsoft-translator.md#detect) |Gjenkjenner kildespråket til en gitt tekst |
| [SpeechLanguages](connection-microsoft-translator.md#speechlanguages) |Henter språkene som er tilgjengelige for talesyntese |
| [TextToSpeech](connection-microsoft-translator.md#texttospeech) |Konverterer en gitt tekst til tale som en lydstrøm i digitallydformat |

### <a name="languages"></a>Språk
Hent språk: Henter alle språkene som Microsoft Translator støtter

#### <a name="input-properties"></a>Inndataegenskaper
Ingen.

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| Kode |streng |nei | |
| navn |streng |nei | |

### <a name="translate"></a>Translate
Translate text: Oversetter tekst til et angitt språk ved hjelp av Microsoft Translator

#### <a name="input-properties"></a>Inndataegenskaper

| navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| query |tekststreng |ja |Tekst som skal oversettes |
| languageTo |tekststreng |ja |Målspråkkoden (eksempel: nb-no) |
| languageFrom |tekststreng |nei |Kildespråket (hvis det ikke angis, forsøker Microsoft Translator å oppdage det automatisk) (eksempel: en) |
| category |tekststreng |nei |Oversettelseskategori (standardinnstilling: generell) |

#### <a name="output-properties"></a>Egenskaper for utdata
Ingen.

### <a name="detect"></a>Detect
Gjenkjenn språk: Gjenkjenner kildespråket til en gitt tekst

#### <a name="input-properties"></a>Inndataegenskaper

| navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| query |tekststreng |ja |Teksten som språket skal gjenkjennes for |

#### <a name="output-properties"></a>Egenskaper for utdata

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| Kode |streng |nei | |
| navn |streng |nei | |

### <a name="speechlanguages"></a>SpeechLanguages
Hent talespråk: Henter språkene som er tilgjengelige for talesyntese

#### <a name="input-properties"></a>Inndataegenskaper
Ingen.

#### <a name="output-properties"></a>Utdataegenskaper

| Egenskapsnavn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| Kode |streng |nei | |
| navn |streng |nei | |

### <a name="texttospeech"></a>TextToSpeech
Tekst til tale: Konverterer en gitt tekst til tale som en lydstrøm i digitallydformat

#### <a name="input-properties"></a>Inndataegenskaper

| navn | Datatype | Kreves | Beskrivelse |
| --- | --- | --- | --- |
| query |tekststreng |ja |Tekst som skal konverteres |
| language |tekststreng |ja |Språkkode tale skal genereres for (eksempel: nb-no) |

#### <a name="output-properties"></a>Egenskaper for utdata
Ingen.

## <a name="helpful-links"></a>Nyttige koblinger
Se alle [tilgjengelige tilkoblinger](../connections-list.md).  
Finn ut hvordan du [legger til tilkoblinger](../add-manage-connections.md) i appene dine.

