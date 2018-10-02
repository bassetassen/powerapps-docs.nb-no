---
title: Komplekse enheter som krever PowerApps Plan 2-lisenser | Microsoft Docs
description: En liste over komplekse enheter i Common Data Service (CDS) for Apps som krever en PowerApps Plan 2-lisens.
author: clwesene
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 07/17/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="complex-entities-and-licensing"></a>Komplekse enheter og lisensiering
Enheter som inneholder følgende komplekse serversidelogikk, krever at brukere av en app eller flyt som bruker disse enhetene, har en PowerApps Plan 2- eller Microsoft Flow Plan 2-lisens:

* Plugin-moduler med kode. Hvis du vil ha mer informasjon: [Utvikling av plugin-moduler](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development)
* Sanntidsarbeidsflyter. Mer informasjon: [Arbeidsflytprosesser](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)

    > [!IMPORTANT]
    >  Bare arbeidsflyter som er konvertert til en sanntidsarbeidsflyt, vurderes som i sanntid og synkroniserte. Arbeidsflyter som kjører i bakgrunnen, kan fremdeles brukes med riktig PowerApps-plan og krever ikke flere lisenser.

Hvis du vil vite om du har lagt til kompleks forretningslogikk i enhetene, kan du se listen over plugin-modulsamlinger og arbeidsflyter som er konfigurert i miljøet.

## <a name="complex-entities-installed-with-dynamics-365"></a>Komplekse enheter som er installert med Dynamics 365
Tabellen nedenfor viser enheter som inneholder medfølgende kompleks serversidelogikk som en del av Dynamics 365-programinstallasjonen. Denne listen er ment som en veiledning. Listen over komplekse enheter kan variere avhengig av hvilke Dynamics 365-programmer og -versjoner som er installert i miljøet ditt.

> [!NOTE]
>  Hvis du bruker Common Data Service og ikke har installert et Dynamics 365-program eller en tredjepartsløsning, vil ikke miljøet ha enheter som inneholder kompleks serversidelogikk.

* Forretningsforbindelse
* Avtale
* Avtalebestillingsdato
* Hendelse for avtalebestilling
* Avtalebestillingsprodukt
* Avtalebestillingsservice
* Serviceoppgave for avtalebestilling
* Avtalebestillingsoppsett
* Avtalefakturadato
* Avtalefakturaprodukt
* Avtalefakturaoppsett
* Delstatus for avtale
* Ressurs som kan reserveres
* Bestilling av ressurs som kan reserveres
* Overskrift for bestilling av ressurs som kan reserveres
* Kategori for ressurs som kan reserveres
* Kategoritilknytning for ressurs som kan reserveres
* Kjennetegn for ressurs som kan reserveres
* Ressursgruppe som kan reserveres
* Bestillingsvarsel
* Bestillingsvarselstatus
* Bestillingsstatus
* Kjennetegn
* Kompetansekrav (avskrevet)
* Konkurrent
* Kontakt
* Kundeaktiva
* Delegering
* Utgift
* Feltberegning
* Prislisteelement for Field Service
* Filtrer
* Følg
* Hendelsestype
* Produkt for hendelsestype
* Service for hendelsestype
* Serviceoppgave for hendelsestypen
* Integreringsjobb
* Integreringsjobbdetalj
* Lagerjustering
* Lagerjusteringsprodukt
* Overføring av lagerbeholdning
* Faktura
* Fakturafrekvens
* Fakturalinje
* Fakturalinjedetalj
* Logg
* Journallinje
* Kundeemne
* Obs!
* OData v4-datakilde
* Salgsmulighet
* Salgsmulighetslinje
* Detalj for salgsmulighetslinjer
* Ordre
* Ordrefaktureringsprodukt
* Ordrefaktureringsoppsett
* Ordrelinje
* Betaling
* Betalingsdetalj
* Innleggskonfigurasjon
* Konfigurasjon for regel for innlegg
* Postnummer
* Prisliste
* Prislisteelement
* Produkt
* Prosjekt
* Prosjektgodkjenning
* Detalj for prosjektkontraktlinjer
* Milepæl for prosjektkontraktlinje
* Ressurskategori for prosjektkontraktlinjer
* Transaksjonskategori for prosjektkontraktlinjer
* Prosjektparameter
* Prosjektfaser
* Statusbruker for prosjektoppgave
* Registrering for prosjektteammedlem
* Bestilling
* Bestillingsfaktura
* Bestillingsprodukt
* Bestillingsbekreftelse
* Produkt for bestillingsbekreftelse
* Underordnet status for bestilling
* Køelement
* Tilbud
* Tilbudsbestillingshendelse
* Tilbudsbestillingsprodukt
* Tilbudsbestillingsservice
* Serviceoppgave for tilbudsbestilling
* Tilbudsbestillingsoppsett
* Tilbudsfaktureringsprodukt
* Tilbudsfaktureringsoppsett
* Tilbudslinje
* Tilbudslinjedetalj
* Milepæler for tilbudslinjer
* Ressurskategori for tilbudslinje
* Transaksjonskategori for tilbudslinje
* Prosjektprisliste for tilbud
* Rangeringsmodell
* Rangeringsverdi
* Kravkjennetegn
* Kravressurskategori
* Kravressurspreferanse
* Kravstatus
* Ressursforespørsel
* Ressurskrav
* Detalj om ressurskrav
* ARM
* ARM-produkt
* ARM-mottak
* ARM-mottaksprodukt
* Delstatus for ARM
* Rollekompetansekrav
* Rollepris
* RTV
* RTV-produkt
* Delstatus for RTV
* Avgiftskode
* Detalj for avgiftskode
* Tidsoppføring
* Tidsgruppe
* Detalj for tidsgruppe
* Forespørsel om fritid
* Pris for transaksjonskategorier
* Bruker
* Visning
* Veggvisning
* Lager
* Arbeidsordre
* Arbeidsordrehendelse
* Arbeidsordreprodukt
* Arbeidsordreservice
* Serviceoppgave for arbeidsordre
* Delstatus for arbeidsordre
* Arbeidsmal


## <a name="licensing"></a>Lisensiering
Hvis du vil ha mer informasjon om PowerApps- og Dynamics 365-lisenser, kan du se [Lisensieringsoversikt](../../administrator/pricing-billing-skus.md)-siden.

