---
title: Oversikt over Dynamics 365-tilkoblingen | Microsoft Docs
description: Lage en app for å behandle data i Dynamics 365
services: ''
suite: powerapps
documentationcenter: ''
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/12/2017
ms.author: matp
ms.openlocfilehash: 532d165280f3f52b75344b03dc57bc23df3ba56a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 03/22/2018
ms.locfileid: "30997062"
---
# <a name="connect-to-dynamics-365-from-powerapps"></a>Koble til Dynamics 365 fra PowerApps
Med PowerApps kan du raskt generere, tilpasse, dele og kjøre mobilapper med lite eller ingen kode. Ved hjelp av Dynamics 365-koblingen kan du på bare noen minutter opprette nyttige mobilapper til å dele med organisasjonen.

Ved å følge trinnene i dette emnet oppretter du en app der brukere kan bla gjennom, legge til, slette og gjøre oppdateringer til kontakter i Dynamics 365. Brukere kan kjøre appen [i en nettleser](../../../user/run-app-browser.md) eller [på en mobil enhet](../../../user/run-app-client.md) for eksempel en telefon.

## <a name="prerequisite"></a>Forutsetning
For å følge denne opplæringen trenger du en Microsoft Office 365-konto som omfatter et Dynamics 365-abonnement.

## <a name="create-a-connection"></a>Opprette en kobling
1. [Logg deg på PowerApps](https://web.powerapps.com/).
2. Klikk eller trykk på **Tilkoblinger** i venstre navigasjonsrute:
   
    ![Alternativet Tilkobling i Fil-menyen](./media/connection-dynamics-crmonline/file-connections.png)
3. Klikk på **Ny tilkobling** nær hjørnet øverst til høyre.
   
    ![Ny tilkobling](./media/connection-dynamics-crmonline/new-connection.png)
4. Klikk på **Dynamics 365** i listen over tilkoblinger.
   
    ![Alternativet Tilkobling i Fil-menyen](./media/connection-dynamics-crmonline/connection-d365.png)
5. I dialogboksen klikker du på **Opprett**.
   
    ![Opprette tilkobling](./media/connection-dynamics-crmonline/create-connection.png)
6. I dialogboksen **Logg deg på kontoen din** oppgir du legitimasjon for Dynamics 365 (online)-tenant.
   
    En tilkobling er opprettet.

## <a name="generate-an-app-automatically"></a>Generer en app automatisk
1. [Logg deg på PowerApps](https://web.powerapps.com/), og klikk deretter på **Ny app** nær nedre venstre hjørne.
   
    ![Ny app](./media/connection-dynamics-crmonline/new-app.png)
2. Klikk på **Telefonoppsett** under **Start med dataene dine** på **Dynamics 365**-flisen.
   
    ![PowerApps merker Dynamics 365-koblingen](./media/connection-dynamics-crmonline/phonelayout.png)
3. Under **Tilkoblinger** velger du koblingen du vil bruke, og deretter velger du et datasett, som tilsvarer forekomsten av Dynamics 365 som du administrerer i appen.
4. Under **Velg en tabell** klikker du på **Kontakter**, og deretter klikker du på **Koble**.
5. Klikk eller trykk på et ikon i hjørnet øverst til høyre i venstre navigasjonsfelt for å bytte til miniatyrbildevisningen.
   
    ![Veksle mellom visningene](./media/connection-dynamics-crmonline/toggle-view.png)

PowerApps genererer en app med tre skjermer basert på kontaktoppføringene.

* **BrowseScreen1**. Dette skjermbildet vises som standard når brukerne åpner appen. I det venstre navigasjonsfeltet vises et miniatyrbilde for denne skjermen over de andre to skjermbildene.
* **DetailScreen1**. Dette skjermbildet vises når brukere klikker på et element i **BrowseScreen1**.  I det venstre navigasjonsfeltet vises et miniatyrbilde for **DetailScreen1** mellom de andre to skjermbildene.
* **EditScreen1**. Denne skjermen vises når brukere klikker på Rediger-ikonet for et element i **DetailScreen1**. I det venstre navigasjonsfeltet vises et miniatyrbilde for **EditScreen1** under de andre to skjermbildene.

Appen kan kjøre i sin opprinnelige tilstand, men vi kan gjøre den nyttigere ved å begrense informasjonen på hvert skjermbilde.

## <a name="customize-browsescreen1"></a>Tilpasse BrowseScreen1
I denne prosedyren må du konfigurere **BrowseScreen1** til å vise fornavn og etternavn på hver kontakt. Dataene skal sorteres alfabetisk etter etternavn og inkludere bilder i et rutenett med to kolonner.

1. I **BrowseScreen1** velger du galleriet ved å klikke på en hvilken som helst post i det, unntatt den første.
   
    ![Slik velger man oppsett](./media/connection-dynamics-crmonline/select-gallery.png)
2. Klikk eller trykk på **Data**-fanen i ruten til høyre.
3. I listen over oppsett klikker eller trykker du på det som viser bilder og tekst i et rutenett med to kolonner.
   
    Du må kanskje bla nedover for å vise dette alternativet.
   
    ![Slik velger man oppsett](./media/connection-dynamics-crmonline/select-layout.png)
4. Kopiere denne formelen, og deretter, med galleriet fremdeles merket, limer du inn formelen på formellinjen (til høyre for **fx**-knappen):
   
    `SortByColumns(Search(Filter(Contacts,statuscode=1), TextSearchBox1.Text, "lastname"), "lastname", If(SortDescending1, Descending, Ascending))`
5. I ruten til høyre setter du den øverste rullegardinlisten til **Fornavn** og den midterste rullegardinlisten til **Etternavn**.
   
    ![Velg Body1](./media/connection-dynamics-crmonline/firstname-lastname.png)
6. (valgfritt) På **Fil**-menyen klikker du på **Lagre som**, skriver inn et navn for appen, og klikker deretter på **Lagre**.
   
    Som standard lagres appen til skyen. Klikk på **Denne datamaskinen** for å lagre appen lokalt.

## <a name="customize-detailsscreen1-and-editscreen1"></a>Tilpasse DetailsScreen1 og EditScreen1
1. Klikk på det midterste miniatyrbildet i navigasjonsfeltet til venstre for å velge **DetailsScreen1**.
2. Klikk hvor som helst under tittellinjen på **DetailScreen1** for å vise alternativer for tilpasning i ruten til høyre.
   
    ![Vis skjematilpassing](./media/connection-dynamics-crmonline/show-customization.png)
3. Klikk på øyeikonet for hvert felt i ruten til høyre for å skjule feltene.
   
    ![Skjule felt](./media/connection-dynamics-crmonline/hide-field.png)
4. Klikk hvor som helst under tittellinjen for å velge **Form1**.
   
    ![Velg Form1](./media/connection-dynamics-crmonline/select-form1.png)
5. Klikk på øyeikonet for hver av disse feltene i ruten til høyre, slik at skjermbildet viser et bilde (hvis tabellen inneholder et) og fire andre felt for hver kontakt:
   
   * **entityimage**
   * **firstname**
   * **lastname**
   * **mobilephone**
   * **emailaddress1**
     
     Ruten til høyre skal ligne denne grafikken:
     
     ![Velg Form1](./media/connection-dynamics-crmonline/show-fields.png)
6. Velg **EditScreen1** ved å klikke på det nederste miniatyrbildet i navigasjonsfeltet til venstre.
7. Gjenta trinnene i denne fremgangsmåten for å tilpasse **EditScreen1** på samme måte som **DetailsScreen1**.
8. (valgfritt) Lagre appen.

## <a name="next-steps"></a>Neste trinn
* Test appen din i forhåndsvisningsmodus ved å klikke på **BrowseScreen1** i det venstre navigasjonsfeltet og deretter trykke på F5 eller klikke på ![forhåndsvisningsmodus](./media/connection-dynamics-crmonline/runpowerapp.png) nær øvre høyre hjørne.
* [Del appen](../share-app.md).
* [Legg til en annen datakilde](../add-data-connection.md).

