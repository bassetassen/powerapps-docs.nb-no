---
title: Opprette en relasjon mellom enheter ved hjelp av et oppslagsfelt | Microsoft Docs
description: Trinnvise instruksjoner for hvordan du oppretter en relasjon mellom enheter i PowerApps ved hjelp av et oppslagsfelt.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 02/21/2019
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-relationship-between-entities"></a>Opprette en relasjon mellom enheter
Data i én enhet er ofte relatert til data i en annen enhet. Du kan for eksempel ha enheten **Lærere** og enheten **Klasse**, og **Klasse**-enheten kan ha en oppslagsrelasjon til **Lærere**-enheten for å vise hvilken lærer som underviser klassen. Du kan bruke et oppslagsfelt for å vise dataene fra **Lærere**-enheten. Dette kalles vanligvis et oppslagsfelt.

## <a name="define-a-relationship"></a>Definere en relasjon
Du kan opprette flere typer relasjoner fra én enhet til en annen (eller mellom en enhet og seg selv). Hver enhet kan ha en relasjon til flere enheter, og hver enhet kan ha flere relasjoner til en annen enhet. Noen vanlige relasjonstyper er følgende:

* **Mange-til-én** – I denne relasjonstypen kan hver oppføring i enhet A samsvare med mer enn én oppføring i enhet B, men hver oppføring i enhet B kan bare samsvare med én oppføring i enhet A. En klasse har for eksempel et enkelt klasserom. Dette er den vanligste relasjonstypen og vises i feltlisten som et **oppslagsfelt**
* **Én-til-mange** – I denne relasjonstypen kan hver oppføring i enhet B samsvare med mer enn én oppføring i enhet A, men hver oppføring i enhet A kan bare samsvare med én oppføring i enhet B. En enkelt lærer underviser for eksempel mange klasser.
* **Mange-til-mange** – I denne relasjonstypen kan hver oppføring i enhet A samsvare med mer enn én oppføring i enhet B, og omvendt. Elever kan for eksempel delta i mange klasser, og hver klasse kan ha flere elever.

I tillegg kan du angi avansert overlappende funksjonalitet i mange-til-én og én-til-mange-relasjoner når en handling utføres på den overordnede enheten.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>Legge til et oppslagsfelt (mange-til-én-relasjon)

Hvis du vil legge til en oppslagsrelasjon til en enhet, kan du opprette en relasjon under kategorien **Relasjoner** og angi enheten som du vil opprette en relasjon til.

1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten.

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Klikk på **Relasjoner**.

4. Klikk på **Legg til relasjon**. Dette åpner et nytt panel der du kan velge enheten som du vil opprette en relasjon til. Velg enheten fra **Relatert enhet**-rullegardinlisten.

    > [!div class="mx-imgBorder"] 
    > ![Mange-til-én-relasjon](./media/data-platform-cds-newrelationship/manytoone-1.png "Mange-til-én-relasjon")

5. Når du har valgt en enhet, vises oppslagsfeltene på hovedenheten. De er som standard som enhetsnavnene (i dette eksemplet Klasserom), men du kan endre dem etter behov.

    ![Mange-til-én-relasjon](./media/data-platform-cds-newrelationship/manytoone-2.png "Mange-til-én-relasjon")

6. Klikk på **Ferdig** for å legge til relasjonen til enheten, og klikk deretter på **Lagre enhet**.

    > [!div class="mx-imgBorder"] 
    > ![Mange-til-én-relasjon](./media/data-platform-cds-newrelationship/manytoone-3.png "Mange-til-én-relasjon")

## <a name="add-a-one-to-many-relationship"></a>Legge til en én-til-mange-relasjon

Hvis du vil legge til en én-til-mange-relasjon, kan du opprette en relasjon under kategorien **Relasjoner** og angi enheten som du vil opprette en relasjon til.

1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten.

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Klikk på **Relasjoner**.

4. Klikk på pil ned til høyre for **Legg til relasjon**, dermed får du velge begge typer relasjoner. Klikk på **Én-til-mange**. Dette åpner et nytt panel der du kan velge enheten som du vil opprette en relasjon til. Velg enheten fra **Relatert enhet**-rullegardinlisten.
    > [!div class="mx-imgBorder"] 
    > ![Én-til-mange-relasjon](./media/data-platform-cds-newrelationship/onetomany-1.png "Én-til-mange-relasjon")

5. Når du har valgt en enhet, vises oppslagsfeltene på hovedenheten. De er som standard som enhetsnavnene (i dette eksemplet Klasse), men du kan endre dem etter behov.

    > [!NOTE]
    > Når det gjelder en én-til-mange-relasjon, opprettes oppslagsfeltet på den relaterte enheten, ikke enheten du har valgt nå. Hvis du vil ha oppslaget på gjeldende enhet, må du opprette en mange-til-én-relasjon.

    > [!div class="mx-imgBorder"] 
    > ![Én-til-mange-relasjon](./media/data-platform-cds-newrelationship/onetomany-2.png "Én-til-mange-relasjon")

6. Klikk på **Ferdig** for å legge til relasjonen til enheten, og klikk deretter på **Lagre enhet**.

    > [!div class="mx-imgBorder"] 
    > ![Én-til-mange-relasjon](./media/data-platform-cds-newrelationship/onetomany-3.png "Én-til-mange-relasjon")

## <a name="add-a-many-to-many-relationship"></a>Legge til en mange-til-mange-relasjon
Hvis du vil legge til en mange-til-mange-relasjon, kan du opprette en relasjon under kategorien **Relasjoner** og angi enheten som du vil opprette en relasjon til.

1. På [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) utvider du **Data**-delen og klikker eller trykker på **Enheter** i den venstre navigasjonsruten.

2. Klikk eller trykk på en eksisterende enhet, eller [opprett en ny enhet](data-platform-create-entity.md)

3. Klikk på **Relasjoner**.

4. Klikk på pil ned til høyre for **Legg til relasjon**, dermed får du velge begge typer relasjoner. Klikk på **Mange-til-mange**. Dette åpner et nytt panel der du kan velge enheten som du vil opprette en relasjon til. Velg enheten fra **Relatert enhet**-rullegardinlisten.

5. Når du har valgt en enhet, vises navnene for relasjonen og relasjonsenheten. Som standard brukes navnene på enhetene kombinert, men du kan endre dem etter behov.

    > [!div class="mx-imgBorder"] 
    > ![Mange-til-mange-relasjon](./media/data-platform-cds-newrelationship/manytomany-1.png "Mange-til-mange-relasjon")

6. Klikk på **Ferdig** for å legge til relasjonen til enheten, og klikk deretter på **Lagre enhet**.


## <a name="add-advanced-relationship-behavior"></a>Legge til avansert relasjonsfunksjonalitet

Når du bygger en én-til-mange eller en mange-til-én-relasjon, kan du også angi avansert funksjonalitet.

![Avansert funksjonalitet](./media/data-platform-cds-newrelationship/advanced-1.png "Avansert funksjonalitet")

Disse alternativene kalles også overlappende funksjonalitet fordi de overlapper med hierarkiet for relaterte enheter. Det kan for eksempel være ønskelig å slette de relaterte testene og hjemmearbeidet til en student hvis en student er fjernet fra systemet. Denne typen funksjonalitet kalles overordnet relasjon.

På den andre siden ønsker du kanskje ikke at handlinger som overlapper ned i hierarkiet. I lærer til klasse-relasjonen kan du f.eks. bestemme at den underordnede enheten (klasse) *ikke* skal slettes når du sletter en overordnet (lærer). Dette kalles en referensiell relasjon.

Når du modellerer forretningsdataene ved å opprette egendefinerte enheter eller ved å bruke en eksisterende Common Data Model-enheter, vurderer du funksjonaliteten du trenger, og implikasjoner for hele hierarkiet for relaterte enheter, og velg mellom en av følgende standard virkemåter:

* **Referensiell, fjern kobling:** I en referanserelasjon mellom to enheter kan du navigere til alle relaterte oppføringer. Handlinger som utføres på den ene enheten, påvirker imidlertid ikke den andre. Hvis du f.eks. har en én-til-mange-relasjon mellom lærere og klasser, får det ingen innvirkning på den relaterte klassen at en lærer slettes.

* **Referensiell, begrens sletting:** I en relasjon av typen referensiell, begrens sletting kan du navigere til relaterte oppføringer. Handlinger som utføres på den overordnede oppføringen, blir ikke brukt på den underordnede, men den overordnede oppføringen kan ikke slettes så lenge den underordnede oppføringen finnes. Dette er nyttig hvis du ikke vil at underordnede oppføringer skal bli isolert. Dette tvinger brukeren til å slette alle underordnede oppføringer før den overordnede slettes.

    > [!div class="mx-imgBorder"] 
    > ![Referensiell, begrens sletting](./media/data-platform-cds-newrelationship/advanced-3.png "Referensiell, begrens sletting")

* **Overordnet:** I en overordnet relasjon mellom enheter blir alle handlinger som utføres på en oppføring for den overordnede enheten, også utført på alle oppføringer for underordnede enheter som er relatert til oppføringen for den overordnede enheten. Dette fører for eksempel til at alle underordnede oppføringene slettes når overordnet oppføring slettes.

* **Egendefinert:** I en egendefinert relasjon mellom to enheter, velger du virkemåten som er tilknyttet hver av et sett med mulige handlinger. 

    > [!div class="mx-imgBorder"] 
    > ![Egendefinert virkemåte](./media/data-platform-cds-newrelationship/advanced-2.png "Egendefinert virkemåte")

Mer informasjon om standardinnstillinger og egendefinerte virkemåter: [Konfigurere relasjonsatferd for enhet](entity-relationship-behavior.md).



## <a name="use-a-lookup-field-in-an-app"></a>Bruke et oppslagsfelt i en app
Hvis du [oppretter en app automatisk](../canvas-apps/data-platform-create-app.md) fra en enhet som inneholder et oppslagsfelt, vises det som en **rullegardinliste**-kontroll som inneholder data fra **Hovednavn**-feltet for enheten.

## <a name="add-1n-and-nn-relationships-for-canvas-apps"></a>Legg til 1:N- og N:N-relasjoner for lerrettapper
Bruk **Relater**-funksjonen til å koble to oppføringer via en én-til-mange- eller mange-til-mange-relasjon i Common Data Service. Hvis du vil ha mer informasjon: [Funksjonene Relater og Fjern relatering i PowerApps](../canvas-apps/functions/function-relate-unrelate.md)

## <a name="next-steps"></a>Neste trinn
* [Generere en app ved å bruke en Common Data Service-database](../canvas-apps/data-platform-create-app.md)
* [Opprette en app fra bunnen ved å bruke en Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md)

