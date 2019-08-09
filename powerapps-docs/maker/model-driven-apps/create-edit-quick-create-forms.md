---
title: Opprette eller redigere hurtigopprettingsskjemaer for modelldrevne apper i PowerApps | MicrosoftDocs
description: Lær hvordan du oppretter eller redigerer et hurtigopprettingsskjema
ms.custom: ''
ms.date: 05/14/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 68ca9059-cc5a-45e7-88bd-cc57186bbb48
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-quick-create-forms-for-a-streamlined-data-entry-experience"></a>Opprette eller redigere hurtigopprettingsskjemaer for modelldrevne apper for en strømlinjeformet dataregistreringsopplevelse

I dette emnet kan du opprette og redigere et hurtigopprettingsskjema.

 Med hurtigopprettingsskjemaer har appen en strømlinjeformet dataregistreringsopplevelse med full støtte for logikk som defineres med skjemaskript og forretningsregler. I en modelldrevet PowerApps-app vises hurtigopprettingsskjemaer når du velger **Opprett**-knappen i navigasjonsfeltet, eller når du velger **+ Ny** når du oppretter en ny post fra et oppslag eller delrutenett.
  
 Mobilappene for Dynamics 365 customer engagement bruker hurtigopprettingsskjemaer for å opprette nye oppføringer. Hvis et hurtigopprettingsskjema allerede er konfigurert for en enhet, bruker mobilappene dette skjemaet. Hvis en enhet ikke har et hurtigopprettingsskjema, genererer PowerApps et hurtigopprettingsskjema for å opprette poster i mobilappene basert på definisjonen av hovedskjemaet.  
  
<a name="BKMK_QuickCreateFormEntities"></a>   
## <a name="entities-with-quick-create-forms"></a>Enheter med hurtigopprettingsskjemaer  
 Bare følgende systemenheter har som standard hurtigopprettingsskjemaer.  
  
|||||  
|-|-|-|-|  
|Forretningsforbindelse|Kampanjesvar|Sak|Konkurrent|  
|Kontakt|Emne|Salgsmulighet||  
  
Selv om du kan opprette hurtigopprettingsskjemaer for systemaktivitetsenheter, støtter de ikke hurtigopprettingsskjemaer, med unntak av avtaleenheten. Med utgivelse av Dynamics 365, versjon 9.0, inneholder avtaleenheten et hurtigopprettingsskjemaet for bruk med Enhetlig grensesnitt. For øyeblikket støttes ikke alternativet for å deaktivere hurtigopprettingsskjemaet for avtaleenheten. Du kan aktivere støtte for disse skjemaene for alle andre [oppdaterte enheter](create-design-forms.md) og alle egendefinerte enheter, ved å velge **Tillat hurtigoppretting** i enhetsdefinisjonen og opprette et hurtigopprettingsskjema for enheten. 

Du kan aktivere støtte for hurtigopprettingsskjemaer for egendefinerte aktivitetsenheter, og du kan opprette hurtigopprettingsskjemaer for disse enhetene. Hurtigopprettingsskjemaet for egendefinerte aktivitetsenheter brukes imidlertid ikke når brukere velger **Opprett** i navigasjonsfeltet. Disse hurtigopprettingsskjemaene kan bare brukes når noen legger til en ny oppføring for et delrutenett som viser den egendefinerte aktivitetsenheten.  
  
<a name="BKMK_CreateQuickCreate"></a>   
## <a name="create-a-quick-create-form"></a>Opprette et hurtigopprettingsskjema  
 Selv om du kan definere flere hurtigopprettingsskjemaer, er det bare ett hurtigopprettingsskjema som kan brukes av alle. Skjemarekkefølgen brukes til å angi skjemaet som alle skal bruke. Hurtigopprettingsskjemaer kan ikke tilordnes sikkerhetsroller, og de gjør det ikke mulig for brukeren å bytte skjemaer.  
  
> [!NOTE]
>  - Enheten må ha alternativet **Tillat hurtigoppretting** aktivert for at hurtigopprettingsskjemaet skal vises. 
>  - Noen felt, for eksempel feltet CREATEDON, er ikke tilgjengelige for å legge til et hurtigopprettingsskjema.  
  
### <a name="how-to-create-a-quick-create-form"></a>Opprette et hurtigopprettingsskjema  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).


> [!IMPORTANT]
> "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  

3.  Velg **Legg til skjema** > **Hurtigopprettingsskjema** på verktøylinjen.  
  
4.  Dra et felt fra **Feltutforsker** inn til delene i skjemaet, i skjemautformingen.  
  
5.  Velg **Lagre** når du er ferdig.  
  
6.  Velg **Publiser** for å se det nye skjemaet i programmet.  
  
<a name="BKMK_EditQuickCreate"></a>   
## <a name="edit-a-quick-create-form"></a>Redigere et hurtigopprettingsskjema  
 Hurtigopprettingsskjemaer støtter skjemaskript og forretningsregler, men de har et annet formål enn i hovedskjemaer, og de støtter ikke alle funksjonene som er i hovedskjemaer. Hurtigopprettingsskjemaer har alltid én del med tre kolonner. Du kan ikke legge til flere deler eller kolonner.  
  
 Følgende kontroller kan ikke legges til i hurtigopprettingsskjemaer:  
  
-   Delrutenett  
  
-   Hurtigvisningsskjemaer  
  
-   Webressurser  
  
-   iFrames  
  
-   Merknader  
  
-   Bing-kart  
  
Hvis du legger til et sammensatt felt i et hurtigopprettingsskjema, vises det som separate felt.  
  
### <a name="to-edit-a-quick-create-form"></a>Slik redigerer du et hurtigopprettingsskjema:  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

> [!IMPORTANT]
> "Hvis utformingsmodusen **Modelldrevet** ikke er tilgjengelig, må du kanskje [opprette et miljø](https://docs.microsoft.com/powerapps/administrator/create-environment).    
  
2. Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.    

3. Velg et skjema i skjemalisten der **Type** skjema er **Hurtigoppretting**.  
  
3.  Dra et felt fra **Feltutforsker** inn til delene i skjemaet.  
  
     Se [Konfigurere hendelsesbehandlinger](configure-event-handlers-legacy.md) hvis du vil ha informasjon om hvordan du redigerer hendelsesbehandling for skjemaskript.  
  
4.  Velg **Lagre** når du er ferdig.  
  
5.  Velg **Publiser** for å se det endrede skjemaet i programmet.  

## <a name="allow-quick-create-property-form-behavior-for-activities"></a>Skjemavirkemåten Tillat hurtigoppretting-egenskapen for aktiviteter
**Tillat hurtigoppretting**-egenskapen ble introdusert i 9.1.0.2007-oppdateringen og kan aktiveres eller deaktiveres for alle standardaktiviteter bortsett gjentakende avtaler. Med denne egenskapen kan du endre skjemaet som vises som standard for de fleste aktiviteter. Som standard aktiveres **Tillat hurtigoppretting**, og hurtigopprettingsskjemaet er skjemaet som vises i appområdene og aktivitetsenhetene som støtter den. 

> [!div class="mx-imgBorder"] 
> ![](media/allow-quick-create.png "Tillat hurtigoppretting-egenskapen for avtaleenhet")


### <a name="unified-interface-client-form-display-behavior"></a>Skjemavisningsvirkemåte for Enhetlig grensesnitt-klient
Følgende tabell viser hvilket skjema som vises som standard når **Tillat hurtigoppretting**-egenskapen er *aktivert* i Enhetlig grensesnitt-klienten.
 
|Stedet der skjemaet åpnes  |Skjema som vises  |
|---------|---------|
|Tilknyttet rutenett for spesifikk aktivitet  | Hurtigoppretting      |
|Delrutenett for spesifikk aktivitet   |  Hurtigoppretting     |
|Aktivitetsrutenett (activitypointer)     | Hurtigoppretting     |
|Tilknyttet rutenett for aktiviteter (activitypointer)   | Hurtigoppretting    |
|Delrutenett for aktivitet (activitypointer)  | Hurtigoppretting    |
|Global kommandolinje + knapp<sup>1</sup>    | Hurtigoppretting    |
|Tidslinjevegg   | Hurtigoppretting    |
|Aktivitetsrutenett (activitypointer)   | Hovedskjema   |
|Rutenett for spesifikk aktivitet    | Hovedskjema   |

<sup>1</sup>Aktiviteter vises i de globale **Opprett**- eller **+ Ny**-knappene når **Tillat hurtigoppretting**-egenskapen er aktivert. I dette tilfellet brukes hurtigopprettingsskjemaet hvis det finnes, eller i hovedskjema hvis det ikke finnes. Hvis **Tillat hurtigoppretting** er deaktivert, vil oppføringen for enheten ikke vises.

### <a name="classic-web-client-form-display-behavior"></a>Virkemåte for skjemavisning for klassisk webklientskjema

Følgende tabell viser hvilket skjema som vises som standard når **Tillat hurtigoppretting**-egenskapen er *aktivert* i klassisk webklient.

|Stedet der skjemaet åpnes  |Skjema som vises  |
|---------|---------|
|Tilknyttet rutenett for spesifikk aktivitet  | Hurtigoppretting      |
|Delrutenett for spesifikk aktivitet   |  Hurtigoppretting     |
|Aktivitetsrutenett (activitypointer)     | Hovedskjema     |
|Tilknyttet rutenett for aktiviteter (activitypointer)   | Hovedskjema    |
|Delrutenett for aktivitet (activitypointer)  | Hovedskjema    |
|Global kommandolinje + knapp    | Hovedskjema    |
|Rutenett for spesifikk aktivitet   | Hovedskjema    |

 #### <a name="classic-web-client-social-pane-behavior"></a>Virkemåte for sosial-rute for klassisk webklient
 
Sosial-ruten er et spesialtilfelle, fordi den ikke bruker **Tillat hurtigoppretting**-egenskapen, men bruker ulike skjemaer for ulike aktivitetsenheter, som angitt her.


|Aktivitet  |Skjema som vises  |
|---------|---------|
|Oppgave     | Hurtigoppretting    |
|Telefonsamtale   | Hurtigoppretting     |
|E-post   | Hovedskjema     |
|Avtale  | Hovedskjema     |
|Egendefinert aktivitet     | Hovedskjema      |

### <a name="solution-import-allow-quick-create-value-behavior"></a>Virkemåte for løsningsimport for Tillat hurtigoppretting-verdi

Når du importerer en løsning fra versjon 8.2 uavhengig av verdien for **Tillat hurtigoppretting**-egenskapen i løsningen, vil følgende enheter tilbakestilles til visningsverdien for standardskjema, og hovedskjemaet vil vise: oppgave, telefonsamtale, e-post og avtale. I slike tilfeller må du først tilbakestille **Tillat hurtigoppretting**-alternativet til *Aktivert* for disse aktivitetsenhetene etter importen.
 
Hvis det er gjort en tilpassing i en versjon 9.0-løsning for enheter der **Tillat hurtigoppretting** er aktivert, vil verdien ikke endres etter importen.  Hvis du imidlertid har satt **Tillat hurtigoppretting** til *deaktivert* for oppgaven, telefonsamtalen, e-posten og avtaleenhetene, vil verdien overskrives til aktivert. I slike tilfeller må du først tilbakestille **Tillat hurtigoppretting**-alternativet til dektivert for disse aktivitetsenhetene etter importen. 
  
### <a name="see-also"></a>Se også  
[Oversikt over brukergrensesnittet i skjemaredigeringsprogrammet](form-editor-user-interface-legacy.md)
