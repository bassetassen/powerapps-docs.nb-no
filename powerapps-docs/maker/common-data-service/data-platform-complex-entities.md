---
title: Komplekse enheter som krever lisenser for PowerApps-abonnement 2 | Microsoft Docs
description: En liste over komplekse enheter i Common Data Service for apper som krever en lisens for PowerApps-abonnement 2.
author: clwesene
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 07/17/2018
ms.author: clwesene
ms.openlocfilehash: 76c101f35e236ac6bf037d2b5b748ca1b943d61d
ms.sourcegitcommit: efea7ed5ad8e80c87ba423fb094fa94b4e864d75
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 07/26/2018
ms.locfileid: "39266265"
---
# <a name="complex-entities-and-licensing"></a>Komplekse enheter og lisensiering
Enheter som inkluderer følgende kompleks serversidelogikk krever at brukere av en app eller flyt som bruker disse enhetene har en lisens for PowerApps Plan 2 eller Microsoft Flow Plan 2:

* Kodeplugin-moduler. Mer informasjon: [Utvikling av plugin-modul](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development)
* Sanntidsarbeidsflyter. Mer informasjon: [Arbeidsflytprosesser](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)

    > [!IMPORTANT]
    >  Bare arbeidsflyter som konverteres til en sanntidsarbeidsflyt vurderes i sanntid og er synkrone. Arbeidsflyter som kjører i bakgrunnen kan fortsatt brukes med den riktige PowerApps-planen, og krever ikke flere lisenser.

Hvis du vil vite om du har lagt til kompleks forretningslogikk til enheter, se gjennom listen over plugin-modulsamlinger og arbeidsflyter som er konfigurert i miljøet ditt.

## <a name="complex-entities-installed-with-dynamics-365"></a>Komplekse enheter som ble installert med Dynamics 365
Tabellen nedenfor viser enheter som inneholder kompleks serversidelogikk fra produsenten som en del av Dynamics 365-programinstallasjonen. Denne listen er ment som en veiledning. Listen over komplekse enheter kan variere avhengig av hvilke Dynamics 365-programmer og -versjoner er installert i miljøet ditt.

> [!NOTE]
>  Hvis du bruker Common Data Service og ikke har installert et Dynamics 365-program eller en tredjepartsløsning, inneholder ikke miljøet ditt enheter med kompleks serversidelogikk.

* Konto
* Avtale
* Avtalebestillingsdato
* Avtalebestillingshendelse
* Avtalebestillingsprodukt
* Avtalebestillingstjeneste
* Tjenesteoppgave for avtalebestilling
* Avtalebestillingsoppsett
* Dato for avtalefaktura
* Produkt for avtalefaktura
* Avtalefakturaoppsett
* Understatus for avtale
* Ressurs som kan reserveres
* Bestilling av ressurs som kan reserveres
* Bestillingsoverskrift for ressurs som kan reserveres
* Kategori for ressurs som kan reserveres
* Kategori for ressurse som kan reserveres
* Karakteristikk for ressurs som kan reserveres
* Ressursgruppe som kan reserveres
* Bestillingsvarsling
* Status for bestillingsvarsling
* Bestillingsstatus
* Tilfelle
* Karakteristikk
* Kompetansekrav (avskrevet)
* Konkurrent
* Kontakt
* Kundeaktiva
* Delegering
* Utgift
* Feltberegning
* Prislisteelement for felttjeneste
* Filter
* Følg
* Hendelsestype
* Produkt for hendelsestype
* Hendelsestypetjeneste
* Tjenesteoppgave for hendelsestype
* Integreringsjobb
* Integreringsjobbdetaljer
* Beholdningsjustering
* Produkt for beholdningsjustering
* Beholdningsoverføring
* Faktura
* Fakturafrekvens
* Fakturalinje
* Fakturalinjedetalj
* Journal
* Journallinje
* Kundeemne
* Obs!
* Datakilde OData v4
* Salgsmulighet
* Salgsmulighetslinje
* Detalj for salgsmulighetslinje
* Ordre
* Produkt for ordrefakturering
* Oppsett av ordrefakturering
* Ordrelinje
* Betaling
* Betalingsdetalj
* Innleggskonfigurasjon
* Konfigurasjon av innleggsregel
* Postnummer
* Prisliste
* Prislisteelement
* Produkt
* Prosjekt
* Prosjektgodkjennelse
* Detalj for prosjektkontraktlinje
* Milepæl for prosjektkontraktlinje
* Ressurskategori for prosjektkontraktlinje
* Transaksjonskategori for prosjektkontraktlinje
* Prosjektparameter
* Prosjektfaser
* Statusbruker for prosjektoppgave
* Registrering av prosjektgruppemedlem
* Bestilling
* Regning for bestilling
* Produkt for bestilling
* Kvittering for bestilling
* Produktkvittering for bestilling
* Understatus for bestilling
* Køelement
* Tilbud
* Tilbudsbestillingshendelse
* Produkt for tilbudsbestilling
* Tilbudsbestillingstjeneste
* Tjenesteoppgave for tilbudsbestilling
* Oppsett av tilbudsbestilling
* Produkt for tilbudsfakturering
* Oppsett av tilbudsfakturering
* Tilbudslinje
* Tilbudslinjedetalj
* Milepæl for tilbudslinje
* Ressurskategori for tilbudslinje
* Transaksjonskategori for tilbudslinje
* Prisliste for tilbudsprosjekt
* Vurderingsmodell
* Vurderingsverdi
* Kravkarakteristikk
* Ressurskategori for krav
* Ressurspreferanse for krav
* Kravstatus
* Ressursforespørsel
* Ressurskrav
* Ressurskravdetalj
* RMA
* RMA-produkt
* RMA-kvittering
* Produkt for RMA-kvittering
* Understatus for RMA
* Kompetansekrav til rolle
* Rollepris
* RTV
* RTV-produkt
* Understatus for RTV
* Mva-kode
* Mva-kodedetalj
* Tidsoppføring
* Tidsgruppe
* Tidsgruppedetalj
* Fraværsforespørsel
* Pris for transaksjonskategori
* Bruker
* Vis
* Veggvisning
* Lager
* Arbeidsordre
* Arbeidsordrehendelse
* Produkt for arbeidsordre
* Arbeidsordretjeneste
* Tjenesteoppgave for arbeidsordre
* Understatus for arbeidsordre
* Arbeidsmal


## <a name="licensing"></a>Lisensiering
Hvis du vil ha mer informasjon om PowerApps- og Dynamics 365-lisenser, kan du se siden [Lisensoversikt](../../administrator/pricing-billing-skus.md).

