---
title: Velge og konfigurere kolonner i modelldrevne appvisninger i PowerApps | MicrosoftDocs
description: Lær hvordan du kan velge og konfigurere visninger for appen
keywords: ''
ms.date: 11/27/2018
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

# <a name="choose-and-configure-columns-in-model-driven-app-views"></a>Velge og konfigurere kolonner i modelldrevne appvisninger

<a name="BKMK_ChooseAndConfigureColumns"></a>   

 I tillegg til filtervilkårene er kolonnene som vises i en PowerApps-visning, svært viktige for verdien i visningen. I dette emnet skal du opprette eller redigere visninger ved å utføre følgende oppgaver:  

-   [Åpne redigeringsprogrammet for visning](choose-and-configure-columns.md#open-the-view-editor)  
   
-   [Legge til kolonner](choose-and-configure-columns.md#BKMK_AddColumns)  
  
-   [Fjerne kolonner](choose-and-configure-columns.md#BKMK_RemoveColumns)  
  
-   [Endre kolonnebredde](choose-and-configure-columns.md#BKMK_ChangeColumnWidth)  
  
-   [Flytte en kolonne](choose-and-configure-columns.md#BKMK_MoveAColumns)  
    
  > [!IMPORTANT]
  > Den nyeste versjonen av visningsutforming kan nå forhåndsvises. Noen funksjoner, som å aktivere eller deaktivere tilstedeværelse for en kolonne, og legge til søkekolonner, støttes ikke. For å utføre disse oppgavene [åpne visningen i den klassiske visningsutformingen](/dynamics365/customer-engagement/customize/create-and-edit-views#open-the-classic-view-designer).
  >  -   [Aktivere eller deaktivere tilstedeværelse for en kolonne](/dynamics365/customer-engagement/customize/choose-and-configure-columns#BKMK_EnableOrDisablePresence)  
  >
  >  -   [Legge til søkekolonner](choose-and-configure-columns.md#BKMK_AddFindColumns)  



### <a name="open-the-view-editor"></a>Åpne redigeringsprogrammet for visning

1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Visninger**-kategorien. 

    > [!div class="mx-imgBorder"] 
    > ![Visninger](media/available-views.png)

3. Velg en eksisterende visning for å åpne den, eller velg **Legg visning** på verktøylinjen. 

<a name="BKMK_AddColumns"></a>   
### <a name="add-columns"></a>Legge til kolonner  
 Du kan ta med kolonner fra gjeldende enhet eller noen av de relaterte enhetene som har en 1:N-relasjon til gjeldende enhet.  
  
 Du vil for eksempel kanskje vise eieren av en brukereid enhet i en kolonne. Du kan velge **Eier**-feltet for gjeldende enhet for å vise navnet på eieren. Dette vises som en kobling som åpner **Bruker**-oppføringen for personen som er eier.  
  
 Hvis du vil vise telefonnummeret for eieren av oppføringen, må du velge **Eiende bruker (bruker)** fra rullegardinlisten **Oppføringstype** og deretter velge **Hovedtelefon**-feltet.  
  
#### <a name="add-columns-to-views"></a>Legge til kolonner i visninger  
  
1.  Når du oppretter og redigerer visninger, sørg for at **Felt**-panelet er åpent. Hvis ikke velg **Legg til felt** på verktøylinjen. 

    > [!div class="mx-imgBorder"] 
    > ![Legg til kolonner i visningsredigeringsprogrammet](media/fields-drawer-view-designer.png)

2.  Velg feltene du vil legge til i visningsutforming. Dette legger til feltet som en kolonne til høyre i visningen.

3.  Velg **Relatert**-kategorien for å se relaterte enheter og tilhørende felt.
  
 Når du legger til kolonner, øker du bredden på visningen. Hvis bredden på visningen overskrider den ledige plassen på siden, kan brukere bruke det vannrette rullefelt til å rulle og vise de skjulte kolonnene.  
  
> [!TIP]
>  Hvis visningen filtrerer data etter et bestemt felt slik at bare oppføringer med en bestemt verdi vises, må du ikke ta med denne kolonnen i visningen. Det vil si at hvis du for eksempel bare viser aktive oppføringer, må du ikke ta med statuskolonnen i visningen. Gi i stedet visningen et navn som angir at alle oppføringene som vises i den, er aktive.  
  
> [!NOTE]
>  Når du legger til kolonner i oppslagsvisninger for oppdaterte enheter, vises bare de tre første kolonnene.  
  
<a name="BKMK_RemoveColumns"></a>   
### <a name="remove-columns"></a>Fjerne kolonner  
  
1.  Velg kolonneoverskriften du vil fjerne.  
  
2.  Velg **Fjern** i rullegardinlisten.  
  
<a name="BKMK_ChangeColumnWidth"></a>   
### <a name="change-column-width"></a>Endre kolonnebredde  
  
1.  Hold markøren over området mellom kolonnene i visningen.  
  
2.  En linje vises, og markøren blir en dobbeltpil.  
  
3.  Dra kolonnen til riktig bredde.  
  
<a name="BKMK_MoveAColumns"></a>   
### <a name="move-a-column"></a>Flytte en kolonne  
  
Klikk og dra kolonneoverskriften til riktig posisjon.
  
> [!TIP]
>   Du kan også velge overskriften for kolonnen du vil flytte, og velg fra rullegardinlisten **Flytt til høyre** eller **Flytt til venstre**.  
  
## <a name="next-steps"></a>Neste trinn
[Opprette eller redigere visninger](create-edit-views.md)
