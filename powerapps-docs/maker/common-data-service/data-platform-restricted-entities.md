---
title: Begrensede enheter krever Dynamics 365-lisenser | Microsoft Docs
description: En liste over begrensede enheter i Common Data Service som krever Dynamics 365-lisenser.
author: lancedMicrosoft
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 05/01/2018
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="restricted-entities-requiring-dynamics-365-licenses"></a>Begrensede enheter krever Dynamics 365-lisenser
Appopprettere kan bruke de fleste enheter som er tilgjengelige i Common Data Service, til å opprette apper og strømmer for brukere som bare har en PowerApps Plan 1-lisens. Noen enheter inneholder imidlertid kompleks forretningslogikk som krever at appbrukerne har en PowerApps Plan 2- eller Microsoft Flow Plan 2-lisens (for mer informasjon, se [Lisenskrav for enhet](data-platform-entity-licenses.md)). Et mindre sett med enheter knyttet til Dynamics 365-produkter krever at brukere av lerrets- og modelldrevne app har en lisens for det tilsvarende Dynamics 365-produktet hvis de trenger å opprette, oppdatere eller slette oppføringer i enhetene. Dette kalles *begrensede* enheter.

Enheter kan være begrenset til en Dynamics 365-lisens av en av følgende årsaker:

* Enheten brukes til å lagre og vedlikeholde produktspesifikke konfigurasjonsdata som vanligvis ikke brukes utenfor programmet.
* Enheten har avansert logikk som oppretter og vedlikeholder data på en bestemt måte når den brukes i et Dynamics 365-produkt.

Hvis en app eller strøm bare leser informasjon fra en entitet, kreves ikke en Dynamics 365-lisens, og en aktuell PowerApps- eller Microsoft Flow-lisens er alt som er nødvendig. 

## <a name="restricted-entities-for-create-update-and-delete-operations"></a>Begrensede enheter for oppretting, oppdatering og sletting
Tabellen nedenfor viser de begrensede enhetene og de tilknyttede Dynamics 365-lisenskravene for brukere av PowerApps- og Microsoft Flow-apper som oppretter, oppdaterer eller sletter data som er lagret i enhetene. 

|Enhet  |Logisk navn  |Lisens som kreves  |
|---------|---------|---------|
Faktisk |msdyn_actual |Dynamics 365 for Field Service <br> **eller** Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Forretningsprosess for avtale |msdyn_bpf_baa0a411a239410cb8bded8b5fdd88e3 |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Bestillingsjournal | msdyn_bookingjournal|Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Metadata for bestillingsoppsett | msdyn_bookingsetupmetadata|Dynamics 365 for Field Service <br> **eller** Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Bestillingstidsstempel | msdyn_bookingtimestamp|Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Sak | incident | Dynamics 365 for Customer Service, Enterprise edition <br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Sak til forretningsprosess for arbeidsordre |msdyn_bpf_989e9b1857e24af18787d5143b67523b |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Konfigurasjon |msdyn_configuration |Dynamics 365 for Field Service <br> **eller** Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Rettighet | rettighet | Dynamics 365 for Customer Service, Enterprise edition <br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Estimatlinje|msdyn_estimateline|Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Estimat|msdyn_estimate |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Fakta|msdyn_fact |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Field Service-innstilling |msdyn_fieldservicesetting |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Field Service-systemjobb |msdyn_fieldservicesystemjob |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Mål | goal | Dynamics 365 for Sales, Professional <br>**eller** Dynamics 365 for Sales, Enterprise Edition <br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Lagerbeholdningsjournal |msdyn_inventoryjournal |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Fakturaprosess |msdyn_bpf_d8f9dc7f099f44db9d641dd81fbd470d |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Reise | journey | Dynamics 365 for Marketing <br> **eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Kunnskapsartikkel | knowledgearticle | Dynamics 365 for Customer Service, Enterprise edition <br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Organisasjonsenhet |msdyn_organizationalunit |Dynamics 365 for Field Service <br> **eller** Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Produktlager |msdyn_productinventory |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Prosjektparameter|msdyn_projectparameter |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Prosjektfaser| msdyn_bpf_665e73aa18c247d886bfc50499c73b82|Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Avhengighet for prosjektoppgaver|msdyn_projecttaskdependency |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Prosjektoppgave|msdyn_projecttask |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Prosjektteammedlem|msdyn_projecteam |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Forretningsprosess for bestilling | msdyn_bpf_2c5fe86acc8b414b8322ae571000c799|Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Ressurstilordningsdetalj (avskrevet)|msdyn_resourceassignmentdetail |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Ressurstilordning|msdyn_resourceassignment |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Ressursbegrensning (avskrevet) |msdyn_workorderresourcerestriction | Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Rutingsregelsett | routingrule | Dynamics 365 for Customer Service, Enterprise edition <br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Innstilling for planleggingstavle |msdyn_scheduleboardsetting |Dynamics 365 for Field Service <br> **eller** Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Planleggingsparameter |msdyn_schedulingparameter |Dynamics 365 for Field Service <br> **eller** Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Serviceavtale| sla | Dynamics 365 for Customer Service, Enterprise edition <br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Planleggerinnstilling for systembruker |msdyn_systemuserschedulersetting|Dynamics 365 for Field Service <br> **eller** Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Transaksjonstilkobling|msdyn_transactionconnection |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Transaksjonsopprinnelse|msdyn_transactionorigin |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Transaksjonstype|msdyn_transactiontype |Dynamics 365 for Project Service Automation<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Unikt nummer|msdyn_uniquenumber |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Forretningsprosess for arbeidsordre |msdyn_bpf_d3d97bac8c294105840e99e37a9d1c39 |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan
Genereringskø for arbeidsordredetaljer (avskrevet)|msdyn_workorderdetailsgenerationqueue |Dynamics 365 for Field Service<br>**eller** Dynamics 365 Customer Engagement-plan <br> **eller** Dynamics 365-plan

## <a name="licensing"></a>Lisensiering
Hvis du vil ha mer informasjon om PowerApps- og Dynamics 365-lisenser, kan du se [Lisensieringsoversikt](../../administrator/pricing-billing-skus.md)-siden.

