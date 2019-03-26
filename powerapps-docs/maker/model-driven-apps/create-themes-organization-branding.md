---
title: Endre fargevalget eller legge til en logo som samsvarer med organisasjonens merke | MicrosoftDocs
ms.custom: ''
ms.date: 02/19/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 21a166a0-d25e-4260-a1e4-2ddc528787c2
caps.latest.revision: 17
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-theme"></a>Opprett et tema

Du kan opprette et egendefinert utseende og virkemåte (et tema) for appen ved å endre standardfarger og visuelle elementer i det ikke-tilpassede systemet. Du kan for eksempel skape din egen personlige produktmerking ved å legge til en firmalogo og bruke enhetsspesifikk fargelegging. Et tema opprettes ved hjelp av tilpassingsverktøyene i brukergrensesnittet, uten at det kreves at en utvikler skriver kode. Du kan opprette, endre eller slette temaer som brukes i organisasjonen. Tematilpasningen støttes i webskjemaene i Dynamics 365 for Outlook. Du kan definere flere temaer, men bare ett kan angis og publiseres som standardtema.  
  
<a name="UseThemes"></a>   
## <a name="use-themes-to-enhance-the-user-interface-and-create-your-product-branding"></a>Bruke temaer til å forbedre brukergrensesnittet og opprette produktmerkenavn  
 Temaer brukes til å forbedre appbrukergrensesnittet, ikke til å endre det vesentlig. Temafargene brukes globalt i hele programmet. Du kan for eksempel forbedre følgende visuelle elementer i brukergrensesnittet:  
  
-   Endre farger på produktlogoer og navigasjonsfelt for å bygge merkevaren  
  
-   Justere uthevingsfarger, for eksempel for pekerfølsomme eller valgte elementer  
  
-   Angi enhetsspesifikke farger  
    
-   Logo  
  
-   Verktøytips for logo  
  
-   Navigasjonsfeltfarge  
  
-   Farge på navigasjonsfeltnivå

-   Farge på hovedkommandolinje i enhetlig grensesnitt
  
-   Topptekstfarge  
  
-   Global koblingsfarge  
  
-   Effekt for valgt kobling  
  
-   Effekt for pekerfølsom kobling  
  
-   Forrige uthevingsfarge (primær bakgrunnsfarge for prosesskontroller)  
  
-   Standardenhetsfarge  
  
-   Standard egendefinert enhetsfarge  
  
-   Kontrollskygge  
  
-   Kontrollkantlinje  
  
<a name="Solution"></a>   
## <a name="solution-awareness"></a>Bevissthet om løsninger  
 Temaet er ikke løsningsorientert. Endringene som gjøres for et organisasjonstema, inkluderes ikke i løsninger som eksporteres fra organisasjonen. Dataene er lagret i temaenheten som kan eksporteres og importeres på nytt i annet miljø. Temaet som er importert, må publiseres for å tre i kraft.  
  
<a name="CloneAlter"></a>   
## <a name="copy-and-alter-the-existing-theme"></a>Kopiere og endre det eksisterende temaet  
 Den enkleste og raskeste måten å opprette et nytt tema på, er å klone og endre et eksisterende tema, deretter lagre det, forhåndsvise og publisere. 
 
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

2.  Velg **Modelldrevet** (nederst til venstre). 

3.  Velg ![Innstillinger-ikonet](../model-driven-apps/media/powerapps-gear.png) (øverst til høyre) > **Avanserte tilpassinger**. 

4. Under **Temaer** velger du **Alle temaer**. 

5. Velg **Standardtema for CRM**. 

Følgende skjermbilde viser en del av standardtemaets oppsett.  

> [!div class="mx-imgBorder"] 
> ![Standardtema](media/default-theme.png) 
  
 Vi klonet standardtemaet og endret fargene. Følgende skjermbilder viser de nye fargene for navigering og merking. Du kan også velge en ny logo for produktet.  
  
 Følgende skjermbilde viser den nye fargen for navigering.  
 
 > [!div class="mx-imgBorder"] 
 > ![Lysegrønne temafarger](media/theme-gentle-green.png "Lysegrønne temafarger")  
  
 Følgende skjermbilde viser rutenettet til enheten for forretningsforbindelsen med den nye markeringsfargen.  
 
 > [!div class="mx-imgBorder"] 
 > ![Lysegrønt rutenett for tema for forretningsforbindelse](media/themes-gentle-green-account-grid.png "Lysegrønt rutenett for tema for forretningsforbindelse")  
  
<a name="Publish"></a>   
## <a name="preview-and-publish-a-theme"></a>Forhåndsvise og publisere et tema  
 Hvis du vil forhåndsvise og publisere et tema, gjør du følgende:  
  
-   Opprett et nytt tema fra grunnen av, eller klon et eksisterende.  
  
-   Forhåndsvis det nye temaet ved å velge **Forhåndsvisning** på kommandolinjen. For å avslutte forhåndsvisning, velger du **Avslutt forhåndsvisning** på kommandolinjen, ved siden av **Forhåndsvisning**.  
  
-   Publiser et tema. Velg **Publiser tema** på kommandolinjen.  
  
 Følgende skjermbilde viser knappene på kommandolinjen for forhåndsvisning og publisering.  
  
 ![Bruk forhåndsvisningsknapper til å angi/avslutte forhåndsvisningsmodus](media/themes-preview-buttons.PNG "Bruk forhåndsvisningsknapper til å angi/avslutte forhåndsvisningsmodus")  
  
<a name="BestPracticies"></a>   
## <a name="best-practices"></a>Gode fremgangsmåter  
 Her er noen anbefalinger for utforming av temakontraster og fargevalg.  
  
### <a name="theme-contrast"></a>Temakontrast  
 Vi anbefaler følgende metode for å angi kontrastfarger:  
  
-   Velg kontrastfargene med omhu. Det medfølgende Common Data Service for Apps-standardtemaet har riktig kontrastforhold for å sikre optimal brukervennlighet. Bruk lignende forhold for dine nye temaer.  
  
-   Bruk standard fargeinnstillinger for høykontrast-modus.  
  
### <a name="theme-colors"></a>Temafarger  
 Vi anbefaler deg å ikke bruke mange forskjellige farger. Selv om du kan angi en forskjellig farge for hver enhet, anbefaler vi ett av to mønstre:  
  
-   Ha alle enheter i nøytrale farger, og uthev viktige enheter.  
  
-   Bruk den samme fargen for lignende enheter eller beslektede enheter, for eksempel kø og køelement, eller enheter i produktkatalogen. Hold tet totale antallet grupper lavt.  
  
<a name="Considerations"></a>   
## <a name="custom-theme-considerations"></a>Vurderinger for egendefinert tema  
 Når du planlegger å bruke egendefinerte temaer, bør du vurdere følgende:  
  
-   De mest oppdaterte bruker brukergrensesnittområdene vises i de egendefinerte temafargene.  
  
-   Selv om temafargene brukes globalt i programmet, vil noen eldre områder i brukergrensesnittet, for eksempel graderingsknapper, beholde standardfargene.  
  
-   Visse områder må bruke mørke eller lyse farger for kontrast med ikonets standardfarger. Ikonfargen kan ikke tilpasses.  
  
-   En enhet kan ikke vises i forskjellige farger under forskjellige områdekartnoder.  
  
-   Områdekartnodenes farger kan ikke tilpasses.  
  
## <a name="see-also"></a>Se også  
         
 [Video: Temaer i Dynamics 365 Customer Engagement](http://go.microsoft.com/fwlink/p/?LinkId=529568) [Spørre og redigere et organisasjonstema](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/query-and-edit-an-organization-theme)

