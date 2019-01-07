---
title: Velge og konfigurere kolonner i modelldrevne appvisninger i PowerApps | MicrosoftDocs
description: Lær hvordan du kan velge og konfigurere visninger for appen
keywords: ''
ms.date: 06/11/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 31bfcf18-58c3-491c-91b5-f9b0f5424852
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 25
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-choose-and-configure-columns-in-model-driven-app-views"></a>Opplæring: Velge og konfigurere kolonner i modelldrevne appvisninger

<a name="BKMK_ChooseAndConfigureColumns"></a>   

 I tillegg til filtervilkårene er kolonnene som vises i en PowerApps-visning, svært viktige for verdien i visningen. I denne opplæringen skal du opprette eller redigere visninger ved å utføre følgende oppgaver:  

-   [Åpne redigeringsprogrammet for visning](choose-and-configure-columns.md#open-the-view-editor)  
   
-   [Legge til kolonner](choose-and-configure-columns.md#BKMK_AddColumns)  
  
-   [Fjerne kolonner](choose-and-configure-columns.md#BKMK_RemoveColumns)  
  
-   [Endre kolonnebredde](choose-and-configure-columns.md#BKMK_ChangeColumnWidth)  
  
-   [Flytte en kolonne](choose-and-configure-columns.md#BKMK_MoveAColumns)  
  
-   [Aktivere eller deaktivere tilstedeværelse for en kolonne](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence)  
  
-   [Legge til søkekolonner](choose-and-configure-columns.md#BKMK_AddFindColumns)  

### <a name="open-the-view-editor"></a>Åpne redigeringsprogrammet for visning

1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Visninger**-kategorien. 

    > [!div class="mx-imgBorder"] 
    > ![Visninger](media/available-views.png)

3. Velg en eksisterende visning for å åpne den, eller velg **Legg visning** på verktøylinjen. 

<a name="BKMK_AddColumns"></a>   
### <a name="add-columns"></a>Legge til kolonner  
 Du kan ta med kolonner fra gjeldende enhet eller noen av de relaterte enhetene som har en 1:N-relasjon til gjeldende enhet.  
  
 Du vil for eksempel kanskje vise eieren av en brukereid enhet i en kolonne. Du kan velge **Eier**-feltet for gjeldende enhet for å vise navnet på eieren. Dette vises som en kobling som åpner **Bruker**-oppføringen for personen som er eier. I dette tilfellet kan du også [aktivere eller deaktivere tilstedeværelse for en kolonne](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence).  
  
 Hvis du vil vise telefonnummeret for eieren av oppføringen, må du velge **Eiende bruker (bruker)** fra rullegardinlisten **Oppføringstype** og deretter velge **Hovedtelefon**-feltet.  
  
#### <a name="add-columns-to-views"></a>Legge til kolonner i visninger  
  
1.  Når du oppretter og redigerer visninger, velger du **Legg til kolonner**. 

    > [!div class="mx-imgBorder"] 
    > ![Legg til kolonner i visningsredigeringsprogrammet](media/view-editor.png)

    Dialogboksen **Legg til kolonner** vises.

    > [!div class="mx-imgBorder"] 
    > ![Legge til kolonner](media/add-columns.png)
  
2.  Velg **Oppføringstype** hvis du vil ta med felt fra relaterte enheter.  
  
3.  Du kan velge flere felt, selv fra relaterte enheter.  
  
4.  Når du har valgt feltene du vil ha, velger du **OK** for å lukke dialogboksen **Legg til kolonner**.  
  
 Når du legger til kolonner, øker du bredden på visningen. Hvis bredden på visningen overskrider den ledige plassen på siden, kan brukere bruke det vannrette rullefelt til å rulle og vise de skjulte kolonnene.  
  
> [!TIP]
>  Hvis visningen filtrerer data etter et bestemt felt slik at bare oppføringer med en bestemt verdi vises, må du ikke ta med denne kolonnen i visningen. Det vil si at hvis du for eksempel bare viser aktive oppføringer, må du ikke ta med statuskolonnen i visningen. Gi i stedet visningen et navn som angir at alle oppføringene som vises i den, er aktive.  
  
> [!NOTE]
>  Når du legger til kolonner i oppslagsvisninger for oppdaterte enheter, vises bare de tre første kolonnene.  
  
<a name="BKMK_RemoveColumns"></a>   
### <a name="remove-columns"></a>Fjerne kolonner  
  
1.  Når du oppretter og redigerer visninger, velger du kolonnen du vil fjerne.  
  
2.  Velg **Fjern** i **Vanlige oppgaver**-området.  
  
3.  Velg **OK** i bekreftelsesmeldingen.  
  
<a name="BKMK_ChangeColumnWidth"></a>   
### <a name="change-column-width"></a>Endre kolonnebredde  
  
1.  Når du oppretter og redigerer visninger, velger du kolonnen du vil endre.  
  
2.  Velg **Endre egenskaper** i **Vanlige oppgaver**-området.  
  
3.  Velg et alternativ for å angi kolonnebredden i dialogboksen **Endre kolonneegenskaper**, og velg deretter **OK**.  
  
<a name="BKMK_MoveAColumns"></a>   
### <a name="move-a-column"></a>Flytte en kolonne  
  
1.  Når du oppretter og redigerer visninger, velger du kolonnen du vil flytte.  
  
2.  I **Vanlige oppgaver**-området bruker du pilene til å flytte kolonnen til venstre eller høyre.  
  
<a name="BKMK_EnableOrDisablePresence"></a>   
### <a name="enable-or-disable-presence-for-a-column"></a>Aktivere eller deaktivere tilstedeværelse for en kolonne  
 Når følgende betingelser er oppfylt, kan personer se en kontroll for tilstedeværelse for Skype for Business på nettet i lister, som viser om personen er tilgjengelig og gjør at andre kan kommunisere med personen via direktemeldinger:  
  
-   Personer bruker Edge eller Internet Explorer.  
  
-   Personer har Skype for Business installert.  
  
-   Personer har Microsoft ActiveX aktivert i Internet Explorer.  
  
-   Organisasjonen din har aktivert tilstedeværelse for systemet i systeminnstillingene.  
  
 Kontrollen for tilstedeværelse og innstillingen for å aktivere den er bare tilgjengelige for kolonner der primære felt for e-postaktiverte enheter (brukere, kontakter, salgsmuligheter, kundeemner eller egendefinerte enheter) vises.  
  
#### <a name="enable-or-disable-skype-for-business-presence-for-a-column"></a>Aktivere eller deaktivere Skype for Business-tilstedeværelse for en kolonne  
  
1.  Når du oppretter og redigerer visninger, velger du kolonnen du vil endre.  
  
2.  Velg **Endre egenskaper** i **Vanlige oppgaver**-området.  
  
3.  Velg eller opphev valget av **Aktiver tilstedeværelse for denne kolonnen** i dialogboksen **Endre kolonneegenskaper**, og velg deretter **OK**.  
  
<a name="BKMK_AddFindColumns"></a>   
### <a name="add-find-columns"></a>Legge til søkekolonner  
 Søkekolonner er kolonner som programmet søker i når brukerne bruker tekstboksen **Søk etter oppføringer** som vises for lister, eller når de kan søke etter oppføringer for en enhet i programmet, for eksempel når de søker etter en oppføring for et oppslagsfelt.  
  
1.  Åpne en **Hurtigsøk**-visning. Hvis du vil ha informasjon om hurtigsøkvisninger, kan du se [Visningstyper](create-edit-views.md#types-of-views).  
  
2.  Velg **Legg til søkekolonner** for å åpne dialogboksen.  
  
3.  Velg feltene som inneholder dataene du vil søke etter.  
  
4.  Velg **OK** for å lukke dialogboksen **Legg til søkekolonner**.  

## <a name="community-tools"></a>Fellesskapsverktøy

**View Layout Replicator** og **View Designer** er verktøy som leveres av XrmToolbox-fellesskapet, som er utviklet for Dynamics 365 Customer Engagement. Se emnet [Utviklerverktøy](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) for verktøy som er utviklet av fellesskapet.

> [!NOTE]
> Fellesskapsverktøy er ikke fra Microsoft Dynamics og det er ikke kundestøtte for disse. Hvis du har spørsmål om verktøyet, kontakter du utgiveren. Mer informasjon: [XrmToolBox](https://www.xrmtoolbox.com). 

## <a name="next-steps"></a>Neste trinn
[Opprette eller redigere visninger](create-edit-views.md)
