---
title: Å åpne enhetsdata i Excel | Microsoft Docs
description: Å åpne enhetsdata i Excel for interaktiv visning og redigering.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
ms.openlocfilehash: 8dbf6088104270d9251b70eec9adf0642de2f879
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/26/2018
ms.locfileid: "34445873"
---
# <a name="open-entity-data-in-excel"></a>Å åpne enhetsdata i Excel
Ved at du åpner enhetsdata i Microsoft Excel, kan du raskt og enkelt vise og redigere data ved å bruke Excel-tillegget for Microsoft PowerApps. Excel-tillegget for PowerApps krever Microsoft Excel 2016.

![Excel-tillegg](./media/data-platform-cds-excel-addin/ExcelAddin.png "Excel-tillegg for PowerApps")

## <a name="open-entity-data-in-excel"></a>Å åpne enhetsdata i Excel
1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute. Alle enhetene vises.
2. Klikk på ellipsen (...) til høyre for enheten du er interessert i.
3. Klikk på **Åpne i Excel**, og deretter åpner du arbeidsboken som er generert. Denne arbeidsboken har bindingsinformasjon for enheten, en peker til miljøet ditt, og en peker til Excel-tillegget for PowerApps.  
4. Klikk på **Aktiver redigering** i Excel for å aktivere Excel-tillegget for PowerApps til å kjøre. Excel-tillegget kjører i en rute til høyre for Excel-vinduet.
5. Hvis dette er første gang du kjører Excel-tillegget for PowerApps, klikker du på **Stol på dette tillegget** for at Excel-tillegget kan kjøre.
6. Hvis du blir bedt om å logge deg på, kan du klikke på **Logg på**, og deretter logger du deg på ved bruk av den samme legitimasjonen du brukte på[powerapps.com](https://web.powerapps.com). Excel-tillegget tar i bruk en tidligere påloggingskontekst, og logger deg automatisk på hvis dette er mulig. Bekreft derfor brukernavnet øverst til høyre i Excel-tillegget.

Excel-tillegget leser automatisk dataene for enheten du valgte. Vær oppmerksom på at det ikke er noe data i arbeidsboken før Excel-tillegget leser det inn.

## <a name="view-and-refresh-data-in-excel"></a>Å vise og oppdatere data i Excel
Etter at Excel-tillegget leser enhetsdataene inn i arbeidsboken, kan du oppdatere dataene når som helst ved å klikke på **Oppdater** i Excel-tillegget.

## <a name="edit-data-in-excel"></a>Å redigere data i Excel
Du kan endre enhetsdata ved behov, og deretter publisere det ved å klikke på **Publiser** i Excel-tillegget.

Hvis du vil redigere en post, velger du en celle i arbeidsboken, og deretter endrer du celleverdien.

Hvis du vil legge til en ny post, følger du ett av disse trinnene:

* Klikk hvor som helst i arbeidsboken, og klikk deretter på **Ny** i Excel-tillegget.
* Klikk i den siste raden i arbeidsboken, og trykk deretter på TAB til pekeren har beveget seg utenfor den siste kolonnen i den raden. Dette oppretter en ny rad.
* Klikk i raden umiddelbart nedenfor arbeidsboken, og begynn å skrive inn data i en celle. Du kan flytte fokus vekk fra cellen, og arbeidsboken utvides for å inkludere den nye raden.

Hvis du vil slette en post, følger du ett av disse trinnene:

* Høyreklikk på radtallet ved siden av arbeidsbokraden for å slette, og klikk deretter på **Slett**.
* Høyreklikk i arbeidsraden for å slette, og klikk deretter på **Slett** > **Tabellrader**.

## <a name="add-or-remove-columns"></a>Å legge til og fjerne kolonner
Du kan bruke utformingsprogrammet til å justere kolonnene og enhetene som automatisk legges til i arbeidsboken.

1. Aktiver utformingsprogrammet for datakilden i Excel-tillegget ved å klikke på **Options**-knappen (tannhjulsymbolet), og merk deretter av for **Aktiver utforming**.
2. Klikk **Utforming** i Excel-tillegget. Alle datakildene er oppført.
3. Klikk på **Edit**-knappen (blyantsymbolet) ved siden av datakilden.
4. Juster listen i **Utvalgte felt**-feltet ved behov:
   * Hvis du vil legge til et felt fra **Tilgjengelige felt**-feltet til **Utvalgte felt**-feltet, klikk på feltet, og klikk deretter på **Legg til**. Du kan alternativt dobbeltklikke på feltet.
   * Hvis du vil fjerne et felt fra **Valgte felt**-feltet, klikker på feltet, og klikker deretter på **Fjern**. Du kan alternativt dobbeltklikke på feltet.
   * Hvis du vil endre rekkefølgen til felt, klikker du på feltet i **Valgte felt**-feltet, og klikk deretter på **Opp** eller **Ned**.
5. Ta i bruk endringene til datakildene ved å klikke på **Oppdater**, og klikk deretter på **Ferdig** for å avslutte utformingsprogrammet. Hvis du la til et felt (kolonne), klikker du på **Oppdater** for å hente et oppdatert sett med data.

> [!NOTE]
> Kontroller at du alltid inkluderer ID-en og obligatoriske felt i arbeidsboken, da du kan motta feilmeldinger når du publiserer.

> [!NOTE]
> Når du legger til oppslagsfelt, må du kontrollere at du legger til både ID-en og Vis-feltene.

## <a name="troubleshooting"></a>Feilsøking
Du kan løse et par problemer gjennom et par enkle trinn.

* Ikke alle enheter støtter redigering og oppretting av nye poster. Disse enhetene åpnes i Excel og lar deg vise data, men publisering vil bli deaktivert.
* Oppslagsfelt må redigeres ved hjelp av tillegget for å sikre at den riktige posten er referert til. Oppdatering av disse feltene via kopiering og innliming eller ved å skrive direkte inn i feltet støttes ikke.


Hvis det oppstår noe problemer som ikke er beskrevet her, kontakter du oss via [kundestøttesidene](https://powerapps.microsoft.com/support/).

## <a name="next-steps"></a>Neste trinn
* [Administrer felter i en enhet](data-platform-manage-fields.md)
* [Definer relasjoner mellom enheter](data-platform-entity-lookup.md)
* [Å generere en app ved hjelp av Common Data Service for apper](../canvas-apps/data-platform-create-app.md)
* [Å opprette en app fra grunnen av ved hjelp av Common Data Service for apper](../canvas-apps/data-platform-create-app-scratch.md)

