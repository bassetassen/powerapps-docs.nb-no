---
title: Modelldrevne eksempelapper
description: 'Forstå hvordan du kan skaffe, tilpasse og fjerne modelldrevne eksempelapper.'
documentationcenter: na
author: caburk
manager: kvivek
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: caburk
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="model-driven-sample-apps"></a>Modelldrevne eksempelapper

I [powerapps.com](https://powerapps.com), bruk en eksempelapp til å utforske utformingsmuligheter og oppdage konsepter som du kan bruke når du utvikler egne apper. Hver eksempelapp bruker oppdiktede data til å vise et virkelighetsnært scenario. 

Se dokumentasjonen spesifikk for hver eksempelapp for å få mer informasjon. 

![Eksempelapp – pengeinnsamling](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>Skaffe eksempelapper

For å se på eller redigere modelldrevne eksempelapper må først appene klargjøres i en Common Data Service-database. Opprett først et prøveversjonsmiljø og en database, og merk av for **Inkluderer eksempelapper og data**.

![Opprett database](media/overview-model-driven-samples/create-database1.png)


> [!IMPORTANT]
> Dette alternativet installerer alle tilgjengelige eksempelapper i databasen. Eksempelapper er til opplæring og demonstrasjon, og vi anbefaler ikke installasjonen av dem i produksjonsdatabaser. 

## <a name="customize-a-sample-app"></a>Tilpasse en eksempelapp

1. Logg på [powerapps.com](https://powerapps.com), og velg **Modelldrevet** for utformingsmodusen. 

    ![Velg utformingsmodus](media/overview-model-driven-samples/choose-design-mode.png)

2. Fra startsiden beveger du musen over eksempelappen og klikker **Tilpass**.
3. Apputformingen åpnes og gir deg flere alternativer for å tilpasse appen. 
4. For flere tilpassingsalternativer klikker du **Avansert** fra den venstre navigasjonsruten i portalen.

## <a name="remove-sample-apps-and-data"></a>Fjerne eksempelapper og data 
- Sletting av en eksempelapp krever sletting av den tilsvarende [administrerte løsningen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution). 
- Hvis du sletter en løsning, slettes også eventuelle eksempeldata som er spesifikke for de egendefinerte enhetene for appen.
- Hvis tilpassinger ble gjort i eksempelappen, kan det være [avhengigheter](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components), som må fjernes før løsningen slettes.

### <a name="steps"></a>Trinn.
1. Logge på [PowerApps-administrasjonsportalen](https://admin.powerapps.com).

2. Velg et miljø.

3. Klikk **Dynamics 365 Administration Center** 

    ![Administrasjonssenter for Dynamics 365](media/overview-model-driven-samples/admin-center.png)

4. Velg databasen fra listen, og klikk **Åpne**.

    ![Velge database](media/overview-model-driven-samples/select-database.png)

5. Naviger til **Innstillinger/Løsninger**.

6. Velg løsningen for appen som skal slettes, og klikk **Slett**.

    ![Slette løsning](media/overview-model-driven-samples/delete-solution.png)

*Du kan også gå til listen over løsninger ved å klikke **Avansert** i utviklingsportalen og slette alt i URL-adressen etter .dynamics.com/*.

> [!IMPORTANT]
> Ikke slett andre systemløsninger med mindre du er oppmerksom på virkningen.

## <a name="install-or-uninstall-sample-data"></a>Installere eller avinstallere eksempeldata
1. Følg trinn 1–4 ovenfor.
2. Naviger til **Innstillinger / Databehandling / Eksempeldata**.
3. Hvis eksempeldata er installert, er det mulig å fjerne dem. Ellers er alternativet for installering tilgjengelig. 

    ![fjerne eksempeldata](media/overview-model-driven-samples/remove-sample-data.png)




