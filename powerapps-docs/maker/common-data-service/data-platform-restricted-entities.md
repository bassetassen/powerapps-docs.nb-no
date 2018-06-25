---
title: Begrensede enheter som krever Dynamics 365-lisenser | Microsoft Docs
description: En liste over begrensede enheter i Common Data Service for apper som krever Dynamics 365-lisenser.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 79b6e386154b15ae6c625afbebbed18a8a86c420
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168002"
---
# <a name="restricted-entities-requiring-dynamics-365-licenses"></a>Begrensede enheter som krever Dynamics 365-lisenser
Applagere kan bruke de fleste enheter som er tilgjengelige i Common Data Service (CDS) for apper for å opprette apper og flyt for brukere som bare har en PowerApps Plan 1-lisens. Noen enheter inneholder imidlertid kompleks forretningslogikk som krever at appbrukere har en PowerApps Plan 2 eller Microsoft Flow Plan 2-lisens (Hvis du vil ha mer informasjon, se [Enhetslisenskrav](data-platform-entity-licenses.md)). Et enda mindre sett av enheter knyttet til Dynamics 365-produkter krever at lerret- og modelldrevne appbrukere har en lisens for korresponderende Dynamics 365-produkt hvis de må opprette, oppdatere eller slette poster i enhetene. Disse kalles *begrensede* enheter.

Enheter kan være begrenset til en Dynamics 365-lisens av følgende årsaker:

* Enheten brukes til å lagre og vedlikeholde produktspesifikke konfigurasjonsdata som vanligvis ikke brukes utenfor programmet.
* Enheten etterfølges av avansert logikk som oppretter og vedlikeholder data på en bestemt måte når den brukes i et Dynamics 365-produkt.

Hvis en app eller flyt bare leser informasjon fra en enhet, kreves ikke en Dynamics 365-lisens og en passende PowerApps- eller Microsoft Flow-lisens er alt som er nødvendig. 

## <a name="restricted-entities-for-create-update-and-delete-operations"></a>Begrensede enheter for å opprette, oppdatere og slette operasjoner
Tabellen nedenfor viser de begrensede enhetene og de tilknyttede Dynamics 365-lisenskravene for PowerApps og Microsoft Flow-appbrukere som oppretter, oppdaterer eller sletter data lagret i enhetene. 

|Enhet  |Logisk navn  |Lisens kreves  |
|---------|---------|---------|
Faktisk |msdyn_actual |Dynamics 365 for feltservice <br> **eller** Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Avtal forretningsprosess |msdyn_bpf_baa0a411a239410cb8bded8b5fdd88e3 |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Bestillingsjournal | msdyn_bookingjournal|Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Bestilling av metadataoppsett | msdyn_bookingsetupmetadata|Dynamics 365 for feltservice <br> **eller** Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Bestilling tidsstempel | msdyn_bookingtimestamp|Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Tilfelle for arbeidsordre forretningsprosess |msdyn_bpf_989e9b1857e24af18787d5143b67523b |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Konfigurasjon |msdyn_configuration |Dynamics 365 for feltservice <br> **eller** Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Rettigheter | rettigheter | Dynamics 365 for kundeservice, Enterprise-utgave <br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Overslagslinje|msdyn_estimateline|Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Overslag|msdyn_estimate |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Faktum|msdyn_fact |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Innstilling for felttjeneste |msdyn_fieldservicesetting |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Systemjobb felttjeneste |msdyn_fieldservicesystemjob |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Mål | mål | Dynamics 365 for selger, <br>**eller** Dynamics 365 for salg, Enterprise-utgave, <br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Hendelse | hendelse | Dynamics 365 for kundeservice, Enterprise-utgave <br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Lagerlogg |msdyn_inventoryjournal |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Fakturaprosess |msdyn_bpf_d8f9dc7f099f44db9d641dd81fbd470d |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Reise | reise | Dynamics 365 for markedsføring <br> **eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Kunnskapsartikkel | kunnskapsartikkel | Dynamics 365 for kundeservice, Enterprise-utgave <br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Organisasjonsenhet |msdyn_organizationalunit |Dynamics 365 for feltservice <br> **eller** Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Produktlager |msdyn_productinventory |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Prosjektparameter|msdyn_projectparameter |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Prosjektfaser| msdyn_bpf_665e73aa18c247d886bfc50499c73b82|Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Prosjektoppgaveavhengighet|msdyn_projecttaskdependency |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Prosjektoppgave|msdyn_projecttask |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Gruppemedlem|msdyn_projecteam |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Innkjøpsordre forretningsprosess | msdyn_bpf_2c5fe86acc8b414b8322ae571000c799|Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Ressurstildelingsdetalj (avskrevet)|msdyn_resourceassignmentdetail |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Ressurstildeling|msdyn_resourceassignment |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Ressursbegrensning (avskrevet) |msdyn_workorderresourcerestriction | Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Ruting av regelsett | rutingregel | Dynamics 365 for kundeservice, Enterprise-utgave <br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Planlegg tavleinnstilling |msdyn_scheduleboardsetting |Dynamics 365 for feltservice <br> **eller** Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Planlegging av parameter |msdyn_schedulingparameter |Dynamics 365 for feltservice <br> **eller** Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
SLA| sla | Dynamics 365 for kundeservice, Enterprise-utgave <br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Systembruker planleggerinnstilling |msdyn_systemuserschedulersetting|Dynamics 365 for feltservice <br> **eller** Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Transaksjonstilkobling|msdyn_transactionconnection |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Transaksjonsopprinnelse|msdyn_transactionorigin |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Transaksjonstype|msdyn_transactiontype |Dynamics 365 for prosjekttjenesteautomatisering<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Unikt nummer|msdyn_uniquenumber |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Arbeidsordre forretningsprosess |msdyn_bpf_d3d97bac8c294105840e99e37a9d1c39 |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan
Arbeidsordredetaljer generering av kø (avskrevet)|msdyn_workorderdetailsgenerationqueue |Dynamics 365 for feltservice<br>**eller** Dynamics 365 kundeengasjementsplan <br> **eller** Dynamics 365-plan

## <a name="licensing"></a>Lisensiering
Hvis du vil ha mer informasjon om PowerApps og Dynamics 365-lisenser, se [Lisensoversikt](../../administrator/pricing-billing-skus.md)-siden.

