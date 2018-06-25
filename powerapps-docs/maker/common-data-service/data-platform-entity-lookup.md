---
title: Å bygge en relasjon mellom enheter ved hjelp av et oppslagsfelt | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du oppretter en relasjon mellom enheter i PowerApps ved hjelp av et oppslagsfelt.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: f1952c2349eb54f2c6348f5abc4dee9a4645348a
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168439"
---
# <a name="create-a-relationship-between-entities"></a>Opprette en relasjon mellom enheter
Data i én enhet er ofte knyttet til data i en annen enhet. Du kan for eksempel ha en enhet for **lærere** og en enhet for **klasse**, og enheten for **klasse** kan ha en oppslagsrelasjon til enheten for **lærere** for å vise hvilken lærer som har ansvar for klassen. Du kan bruke et oppslagsfelt som viser data fra enheten for **lærere**. Dette kalles ofte et oppslagsfelt.

## <a name="define-a-relationship"></a>Å definere en relasjon
Du kan opprette flere typer relasjoner fra én enhet til en annen (eller på tvers av samme enhet). Hver enhet kan ha en relasjon med mer enn én enhet, og hver enhet kan ha mer enn én relasjon med en annen enhet. Noen vanlige relasjonstyper er:

* **Mange-til-én** – I denne type relasjon kan hver post i enhet A kan samsvare med mer enn én post i enhet B, men hver post i enhet B kan bare samsvare med én post i enhet A. For eksempel, en klasse som har ett enkelt klasserom. Dette er den vanligste relasjonstypen, og den vises i feltlisten som et **oppslagsfelt**
* **Én-til-mange** – I denne relasjonstypen kan hver post i enhet B samsvare med mer enn én post i enhet A, men hver post i enhet A kan bare samsvare med én post i enhet B. For eksempel én enkelt lærer, som underviser mange klasser.
* **Mange-til-mange** – I denne relasjonstypen kan hver post i enhet A samsvare med mer enn én post i enhet B, og omvendt. Studenter er eksempelvis delaktig i mange klasser, og hver klasse kan ha flere elever.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>Legg til et oppslagsfelt (mange-til-én-relasjon)

Hvis du vil legge til en oppslagsrelasjon til en enhet, kan du opprette en relasjon under **Relasjoner**-fanen og angi enheten du vil opprette en relasjon med.

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Klikk på **Relasjoner**

4. Klikk på **Legg til relasjon**, da åpnes et nytt panel hvor du kan velge enheten du vil opprette en relasjon til. Velg enheten fra rullegardinlisten **Relatert enhet**.

    ![Mange-til-én-relasjon](./media/data-platform-cds-newrelationship/manytoone-1.png "Mange-til-én-relasjon")

5. Når du har valgt en enhet, vises oppslagsfeltene på den primære enheten. De vises som standard med enhetsnavnene (i dette eksemplet Klasserom), men du kan endre dem om nødvendig.

    ![Mange-til-én-relasjon](./media/data-platform-cds-newrelationship/manytoone-2.png "Mange-til-én-relasjon")

6. Klikk på **Ferdig** for å legge til relasjonen til enheten din, og klikk deretter på **Lagre enhet**.

    ![Mange-til-én-relasjon](./media/data-platform-cds-newrelationship/manytoone-3.png "Mange-til-én-relasjon")

## <a name="add-a-one-to-many-relationship"></a>Å legge til en én-til-mange-relasjon

Hvis du vil legge til en én-til-mange-relasjon, kan du opprette en relasjon under **Relasjoner**-fanen og angi enheten du vil opprette en relasjon med.

1. Utvid **Data**-delen på [powerapps.com](https://web.powerapps.com), og trykk eller klikk på **Enheter** i venstre navigasjonsrute.

    ![Enhetsdetaljer](./media/data-platform-cds-create-entity/entitylist.png "Enhetsliste")

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Klikk på **Relasjoner**

4. Klikk på Pil ned til høyre for **Legg til relasjon**, dette gir deg valget mellom  begge typer relasjoner. Klikk på **Én-til-mange**, da åpnes et nytt panel hvor du kan velge enheten du vil opprette en relasjon til. Velg enheten fra rullegardinlisten **Relatert enhet**.

    ![Én-til-mange-relasjon](./media/data-platform-cds-newrelationship/onetomany-1.png "Én-til-mange-relasjon")

5. Når du har valgt en enhet, vises oppslagsfeltene på den primære enheten. De vises som standard med enhetsnavnene (i dette eksemplet Klasse), men du kan endre dem om nødvendig.

    > [!NOTE]
    > Ved en én-til-mange-relasjon vil oppslagsfeltet være opprettet på den relaterte enheten, ikke på enheten du har valgt for øyeblikket. Hvis du må slå opp på den gjeldende enheten, kan du opprette en mange-til-én relasjon.

    ![Én-til-mange-relasjon](./media/data-platform-cds-newrelationship/onetomany-2.png "Én-til-mange-relasjon")

6. Klikk på **Ferdig** for å legge til relasjonen til enheten din, og klikk deretter på **Lagre enhet**.

    ![Én-til-mange-relasjon](./media/data-platform-cds-newrelationship/onetomany-3.png "Én-til-mange-relasjon")

## <a name="add-a-many-to-many-relationship"></a>Å legge til en mange-til-mange-relasjon

Dette er for øyeblikket bare tilgjengelig via Avansert-menyen. Klikk på «Avansert» fra menyen til venstre, fra PowerApps-hjemmesiden. Hvis du vil ha informasjon om hvordan du oppretter relasjonen, kan du se [Å opprette N:N-relasjoner](/dynamics365/customer-engagement/customize/create-and-edit-nn-many-to-many-relationships)

## <a name="use-a-lookup-field-in-an-app"></a>Å bruke et oppslagsfelt i en app
Hvis du [oppretter en app automatisk](../canvas-apps/data-platform-create-app.md) fra en enhet som inneholder et oppslagsfelt, vises den som en **Rullegardin**-kontroll som inneholder data fra **Primærnøkkel**-feltet for enheten.

## <a name="next-steps"></a>Neste trinn
* [Generer en app ved hjelp av en Common Data Service-database](../canvas-apps/data-platform-create-app.md)
* [Å opprette en app fra grunnen av ved hjelp av en Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md)

