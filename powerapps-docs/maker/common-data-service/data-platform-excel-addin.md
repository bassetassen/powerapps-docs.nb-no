---
title: Åpne enhetsdata i Excel | Microsoft Docs
description: Åpne enhetsdata i Excel for interaktiv visning og redigering.
author: lancedMicrosoft
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="open-entity-data-in-excel"></a>Åpne enhetsdata i Excel
Ved å åpne enhetsdata i Microsoft Excel, kan du raskt og enkelt vise og redigere data ved hjelp av Microsoft PowerApps Excel-tillegget. PowerApps Excel-tillegget krever Microsoft Excel 2016.

![Excel-tillegg](./media/data-platform-cds-excel-addin/ExcelAddin.png "PowerApps Excel-tillegg")

## <a name="open-entity-data-in-excel"></a>Åpne enhetsdata i Excel
1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten. Alle enhetene vises.
2. Klikk på ellipsen (…) til høyre for enheten som du er interessert i.
3. Klikk på **Åpne i Excel**, og åpne deretter arbeidsboken som er generert. Denne arbeidsboken har bindingsinformasjon for enheten, en peker til miljøet ditt og en peker til PowerApps Excel-tillegget.  
4. Klikk på **Aktiver redigering** i Excel for å aktivere PowerApps Excel-tillegget for kjøring. Excel-tillegget kjører i en rute til høyre i Excel-vinduet.
5. Hvis dette er første gang du har kjørt PowerApps Excel-tillegget, klikker du på **Klarer dette tillegget** for å tillate at Excel-tillegget kjører.
6. Hvis du blir bedt om å logge på, klikker du på **Logg på**, og logger deretter på ved å bruke den samme legitimasjonen som du brukte på [powerapps.com](https:///?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Excel-tillegget vil bruke en tidligere påloggingskontekst og logge deg på automatisk hvis det er mulig. Bekreft derfor brukernavnet øverst til høyre i Excel-tillegget.

Excel-tillegget leser automatisk dataene for enheten du valgte. Vær oppmerksom på at det ikke er data i arbeidsboken før Excel-tillegget leser dem inn.

## <a name="view-and-refresh-data-in-excel"></a>Vise og oppdatere data i Excel
Når Excel-tillegget har lest enhetsdata til arbeidsboken, kan du oppdatere dataene når som helst ved å klikke på **Oppdater** i Excel-tillegget.

## <a name="edit-data-in-excel"></a>Redigere data i Excel
Du kan endre enhetsdata ved behov, og deretter publisere dem tilbake ved å klikke på **Publiser** i Excel-tillegget.

Hvis du vil redigere en oppføring, merker du en celle i regnearket, og endrer deretter celleverdien.

Hvis du vil legge til en ny oppføring, følger du én av disse fremgangsmåtene:

* Klikk hvor som helst i regnearket, og klikk deretter på **Ny** i Excel-tillegget.
* Klikk i den siste raden i regnearket, og trykk deretter på Tab-tasten til markøren flytter ut av den siste kolonnen i denne raden, og det opprettes en ny rad.
* Klikk i raden like nedenfor regnearket, og begynn å skrive inn data i en celle. Når du flytter fokuset ut av denne cellen, utvides regnearket for å ta med den nye raden.

Hvis du vil slette en oppføring, følger du én av disse fremgangsmåtene:

* Høyreklikk på radnummeret ved siden av regnearkraden du vil slette, og klikk deretter på **Slett**.
* Høyreklikk i regnearkraden du vil slette, og klikk deretter på **Slett** > **Tabellrader**.

## <a name="add-or-remove-columns"></a>Legge til eller fjerne kolonner
Du kan bruke utformingen for å justere kolonnene og enhetene som automatisk legges til i regnearket.

1. Aktiver datakildeutformingen i Excel-tillegget ved å klikke på **Alternativer**-knappen (tannhjulsymbolet) og deretter merke av for **Aktiver utforming**.
2. Klikk på **Utforming** i Excel-tillegget. Alle datakildene vises.
3. Ved siden av datakilden klikker du på **Rediger**-knappen (blyantsymbolet).
4. Juster listen i feltet **Valgte felt** etter behov:
   * Hvis du vil legge til et felt fra **Tilgjengelige felt**-feltet i **Valgte felt**-feltet, klikker du på feltet og deretter på **Legg til**. Du kan også dobbeltklikke på feltet.
   * Hvis du vil fjerne et felt fra **Valgte felt**-feltet, klikker du på feltet, og klikker deretter på **Fjern**. Du kan også dobbeltklikke på feltet.
   * Hvis du vil endre rekkefølgen på felt, klikker du på feltet i **Valgte felt**-feltet, og klikker deretter på **Opp** eller **Ned**.
5. Bruk endringene i datakilden ved å klikke på **Oppdater**, og klikk deretter på **Ferdig** for å avslutte utformingen. Hvis du la til et felt (kolonne), klikker du på **Oppdater** for å hente inn et oppdatert sett med data.

> [!NOTE]
> Sørg for at du alltid tar med ID-en og obligatoriske felt i arbeidsboken, siden du kan få feil når du publiserer.

> [!NOTE]
> Når du legger til oppslagsfelt, må du sørge for å legge til både ID-en og Visnings-feltene.

## <a name="troubleshooting"></a>Feilsøking
Det er noen få problemer som kan løses gjennom noen enkle trinn.

* Ikke alle enheter støtter redigering og oppretting av nye oppføringer. Disse enhetene åpnes i Excel og lar deg vise data, men publisering blir deaktivert.
* Oppslagsfelt må redigeres ved hjelp av tillegget for å sikre at det refereres til riktig oppføring. Oppdatering av disse feltene via kopier og lim inn eller ved å skrive inn direkte i feltet, støttes ikke.


Hvis du opplever et problem som ikke er beskrevet her, kan du kontakte oss via [støttesidene](https://powerapps.microsoft.com/support/).

## <a name="next-steps"></a>Neste trinn
* [Administrere felt i en enhet](data-platform-manage-fields.md)
* [Definere relasjoner mellom enheter](data-platform-entity-lookup.md)
* [Generere en app ved å bruke Common Data Service](../canvas-apps/data-platform-create-app.md)
* [Opprette en app fra bunnen ved å bruke Common Data Service](../canvas-apps/data-platform-create-app-scratch.md)

