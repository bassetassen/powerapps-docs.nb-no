---
title: Legg til en avtale, e-postmelding, telefonsamtale, notater eller oppgaveaktivitet på tidslinjen i en modelldrevet app | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 11/26/2018
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 308e36938c673a5f6ba83be02591a7199af20432
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 06/19/2019
ms.locfileid: "61529567"
---
# <a name="add-an-appointment-email-phone-call-note-or-task-activity-to-the-timeline"></a>Legg til en avtale, e-postmelding, telefonsamtale, notat eller oppgaveaktivitet på tidslinjen 

Legg til **Aktiviteter** på **Tidslinje**-veggen for å holde oversikten over all kommunikasjon med en kunde eller kontakt. Du kan for eksempel ta notater, legge til innlegg, legge til en oppgave, sende e-postmelding, legge til detaljer om en telefonsamtale eller gjøre avtaler. Systemet tidsstempler hver aktivitet automatisk og viser hvem som opprettet den. Du og andre personer på teamet kan bla gjennom aktivitetene for å se loggen mens du jobber med en kunde. 

- Aktiviteter du legger til i en oppføring, vises på **Tidslinje**-veggen til oppføringen. 
- Hvis **Angående**-feltet til en aktivitet er angitt, vises aktiviteten i oppføringen den er knyttet til. 
- Du kan også velge filtreringsruten for å filtrere aktivitetene etter oppføringstype og -dato. 
- Når en ny aktivitet opprettes, får du et **Dette gikk glipp av**-varsel på **Tidslinje**-veggen.

  > [!div class="mx-imgBorder"]
  > ![Tidslinjevisning av aktiviteter i PowerApps](media/TimelineViewOfActivity.png "Tidslinjevisning av aktiviteter i PowerApps")  
 
## <a name="add-an-activity-from-the-nav-bar"></a>Legg til en aktivitet fra navigasjonsfeltet
 
Den raskeste måten å legge til en aktivitet på, er å bruke snarveien i navigasjonsfeltet og deretter koble den til en oppføring. Du kan for eksempel opprette en telefonsamtaleaktivitet og deretter koble den til en kontakt i systemet ved å bruke **Angående**-feltet.

1. Velg **plusstegnet** ![Opprett oppføring-knapp](media/create-record-button.png "Opprett oppføring-knapp"), i navigasjonsfeltet, og velg deretter **Aktiviteter**. 

   > [!div class="mx-imgBorder"]
   > ![Snarvei for å legge til en aktivitet i PowerApps](media/QuickCreate.png "Snarvei for å legge til en aktivitet i PowerApps")  
 
2. Velg typen aktivitet du vil legge til.

3. Fyll ut den nødvendige informasjonen. Bruk **Angående**-feltet til å assosiere aktiviteten med oppføringen.

4. Når du er ferdig, velger du **Lagre**.

 
## <a name="add-a-phone-call"></a>Legg til en telefonsamtale  
  
1. Åpne oppføringen der du vil legge til aktiviteten. For eksempel en kontaktpost.
  
2. Velg **plusstegn** > **Telefonsamtale** på **Tidslinje**-veggen. 


   > [!div class="mx-imgBorder"]
   > ![Legg til en telefonaktivitet i PowerApps](media/addphonecall.png "Legg til en telefonaktivitet i PowerApps")
  
3. Fyll ut **Emnet** for samtalen.

     Oppgi et sammendrag av samtalen med kunden i **Notater**-området. 
  
     **Samtale til**-feltet fylles automatisk ut med oppføringen der du la til telefonsamtaleaktiviteten. Du kan legge til en ny oppføring hvis det er nødvendig.  
  
4. Som standard er retningen angitt til **Utgående**. Du kan endre den til **Innkommende** ved å velge **Utgående**. 
  
5. Når du er ferdig med å fylle ut skjemaet, velger du **Lagre** for å lagre aktiviteten.  
  
## <a name="add-a-task"></a>Legg til en oppgave  
  
1. Åpne oppføringen der du vil legge til aktiviteten. For eksempel en kontaktpost.
  
2. Velg **plusstegn** > **Oppgave** på **Tidslinje**-veggen.
  
3. **Eier**-feltet er angitt til gjeldende bruker som standard. Hvis du vil tilordne oppgaven på nytt, velger du oppslagsikonet, og deretter velger du en annen bruker eller et annet team.  
  
4. Når du er ferdig med å fylle ut skjemaet, velger du **Lagre** for å lagre aktiviteten. 
  
## <a name="add-an-email"></a>Legg til en e-postadresse  

Hvis du vil legge til en e-postaktivitet i en oppføring, må du først lagre oppføringen der du legger til aktiviteten.  
  
1. Åpne oppføringen der du vil legge til aktiviteten. For eksempel en kontaktpost.
  
2. Velg **plusstegn** > **E-post** på **Tidslinje**-veggen. 

3. Fyll ut emnet for e-postmeldingen, og bruk det angitte området til å skrive e-postmeldingen.
  
4. Hvis du vil legge til et vedlegg i e-postmeldingen, må du lagre e-postmeldingen. Velg deretter **+** i **Vedlegg**-inndelingen for å legge til et vedlegg.  
  
5. Hvis du vil bruke en mal på hele brødteksten i e-postmeldingen, klikker du på **Sett inn mal** på kommandolinjen, og velger deretter malen.   
  
6. Når du er ferdig med å fylle ut skjemaet, velger du **Send**. 
  
## <a name="add-an-appointment"></a>Legg til en avtale  

Hvis du vil legge til en avtaleaktivitet i en oppføring, må du først lagre oppføringen der du legger til aktiviteten.  
  
1. Åpne oppføringen der du vil legge til aktiviteten. For eksempel en kontaktpost.
  
2. Velg **plusstegn** > **Avtale** på **Tidslinje**-veggen.  
  
3. Bruk verktøytipsene til å fylle ut den nødvendige informasjonen.
  
4. Når du er ferdig med å fylle ut skjemaet, velger du **Lagre** for å lagre avtalen.

## <a name="add-notes"></a>Å legge til notater

Du kan også enkelt legge til notater i aktivitetsområdet.
  
1. Åpne oppføringen der du vil legge til aktiviteten. For eksempel en kontaktpost.
  
2. Begynn å skrive inn notater på **Tidslinje**-veggen. Bruk **Legg til et vedlegg** for å legge til et vedlegg i notatet.

3. Når du er ferdig med å fylle ut skjemaet, velger du **Legg til notat** for å lagre notatet.

   > [!div class="mx-imgBorder"]
   > ![Legg til et notat](media/addnote.png "Legg til et notat")

Når notatet er lagt til, kan du slette eller redigere notatet. Du kan også legge til et notat ved å bruke **plusstegnet** i den øvre delen av **Tidslinje**-veggen.


> [!div class="mx-imgBorder"]
> ![Oppdater et notat](media/addnote2.png "Oppdater et notat")

## <a name="add-a-post"></a>Legg til et innlegg 

1. Åpne oppføringen der du vil legge til innlegget. For eksempel en kontaktpost.

2. Velg **plusstegn** > **Innlegg** på **Tidslinje**-veggen. 

3. Skriv inn innlegget i tekstfeltet 

4. Når du er ferdig med å fylle ut skjemaet, velger du **Legg til** for å lagre innlegget.

> [!div class="mx-imgBorder"]
> ![Oppdater et innlegg](media/post.png "Legg til et innlegg")
  
  Når du har lagret innlegget, vises det øverst på tidslinjeveggen.
  
## <a name="refresh-the-timeline"></a>Oppdater tidslinjen 

Du kan oppdatere tidslinjeveggen for å se den mest oppdaterte informasjonen.

Velg ![Mer-knappen](media/MoreButton.png "Mer-knappen") på **Tidslinje**-veggen, og velg deretter **Oppdater tidslinje**.

> [!div class="mx-imgBorder"]
> ![Oppdater tidslinjen ](media/refresh.png "Oppdater tidslinjen")


## <a name="use-the-filter-pane"></a>Bruk filtreringsruten

Bruk filtreringsruten til raskt å filtrere aktiviteter, notater eller innlegg på tidslinjeveggen etter oppføringstype eller aktivitetstype og -dato.

1. Velg ![Mer-knappen](media/MoreButton.png "Mer-knappen") på **Tidslinje**-veggen, og velg deretter **Åpne filtreringsruten**.

> [!div class="mx-imgBorder"]
> ![Filtreringsruten på tidslinjen](media/filterpane.png "Filtreringsruten på tidslinjen")

2. Når du er ferdig med å vise den filtrerte informasjonen, velger du traktikonet**Fjern alle filtre** for å fjerne filteret. Dette tilbakestiller filteret og viser all informasjonen på tidslinjeveggen.

> [!div class="mx-imgBorder"]
> ![Tilbakestill filteret](media/resetfilter.png "Tilbakestill filteret")

## <a name="manage-activities"></a>Administrer aktiviteter
Administrer aktiviteter direkte fra tidslinjeveggen. Du kan blant annet tilordne en aktivitet til en annen person, slette eller lukke en aktivitet, legge til en aktivitet i en kø, åpne en tilknyttet oppføring eller redigere notater og innlegg.


> [!div class="mx-imgBorder"]
> ![Manage Activities.png](media/ManageActivities.png "ManageActivities.png")



