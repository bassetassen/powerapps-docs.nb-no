---
title: Bruke hovedskjemaet for modelldrevne apper og komponentene i skjemaet i PowerApps | Microsoft Docs
description: Finn ut hvordan du bruker hovedskjemaet og komponentene i skjemaet i Enhetlig grensesnitt-baserte apper
keywords: 'Hovedskjemaer, Customer Service, Kundeservicehub; Dynamics 365'
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: powerapps
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 43bfface-4dc2-411d-99a1-83e934646989
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-the-model-driven-app-main-form-and-its-components"></a>Bruke hovedskjemaet for modelldrevne apper og komponentene i skjemaet

Skjemaer i Enhetlig grensesnitt-baserte apper har en forbedret brukeropplevelse for optimal agentproduktivitet, og bidrar til å opprettholde sammenhengen når du arbeider med relaterte oppføringer. Du kan se skjemaene som er oppført i løsningsutforskeren. Skjematypen for de nye skjemaene er **Hoved**.

Dette emnet forklarer hvordan du redigerer et hovedskjema og legger til eller endrer ulike elementer i skjemaet.

## <a name="open-the-form-editor"></a>Åpne skjemaredigeringsprogrammet

Hvis du vil redigere et skjema, eller legge til eller endre elementer, kan du bruke skjemaredigeringsprogrammet. I skjemaredigeringsprogrammet kan du redigere skjemaer for alle Enhetlig grensesnitt-baserte apper.

Følg fremgangsmåtene angitt nedenfor for å få tilgang til skjemaredigeringsprogrammet. 

> [!NOTE]
> Hvis du oppretter nye løsningskomponenter i når du redigerer skjemaet, vil navnene på komponentene bruke tilpassingsprefikset for løsningsutgiver for standardløsningen, og disse komponentene inkluderes bare i standardløsningen. Hvis du vil at alle nye løsningskomponenter skal inkluderes i en bestemt uadministrert løsning, åpner du skjemaredigeringsprogrammet gjennom den uadministrerte løsningen.


### <a name="access-the-form-editor-through-app-designer-in-powerapps"></a>Tilgang til skjemaredigeringsprogrammet via apputforming i PowerApps

1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

2.  I navigasjonsruten til venstre velger du **Apper**, velger appen du vil bruke, og velger deretter **Rediger** på verktøylinjen.  

3. På apputformingslerretet velger du pil ned ![Nedoverpil for apputforming](media/down-arrow-app-designer.png) ved siden av en enhet for å se skjemaene som er tilgjengelig for denne enheten. 

4. Velg knappen for å åpne utformingen ![åpne utforming](media/site-map-designer.png)som tilsvarer skjemaet som skal redigeres.

   ![Skjemaredigeringsprogrammet i apputforming](media/app-designer-forms.png)
 
5. Gjør endringene i skjemautformingen, og velg deretter **Lagre** for å lagre endringene, og velg **Publiser** for å publisere dem for bruk i appen. 

> [!NOTE]
> Hvis du har gjort andre endringer i appen, publiserer du dem ved hjelp av alternativet for appnivåpublisering. Se [Validere og publisere en app med apputformingen](validate-app.md) for mer informasjon.

> [!NOTE]
> Hovedskjemaet for webklienten er også kompatibelt med kundeservicehuben, og kan redigeres ved hjelp av apputforming.


### <a name="access-the-form-editor-through-the-default-solution"></a>Åpne skjemaredigeringsprogrammet via standardløsningen

1.  Logg på [PowerApps](https:///?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  

3. I listen over skjemaer åpner du skjemaet av typen **Hoved**.

### <a name="access-the-form-editor-for-an-unmanaged-solution"></a>Åpne skjemaredigeringsprogrammet for en uadministrert løsning

1. Åpne [løsninger](advanced-navigation.md#solutions).
2. Dobbeltklikk den uadministrerte løsningen du vil arbeide med. Løsningsypen, administrert eller uadministrert, vises i **Pakketype**-kolonnen.
3. I listen over komponenter kan du finne enheten med skjemaet du vil redigere. Hvis enheten ikke finnes, må den legges til.

#### <a name="add-an-entity-to-an-unmanaged-solution"></a>Legge til en enhet i en uadministrert løsning

1. Med den uadministrerte løsningen åpnet i løsningsutforskeren, kan du velge **Enheter**-noden og på verktøylinjen over listen velger du **Legg til eksisterende**.

     > [!div class="mx-imgBorder"] 
     > ![Legg til eksisterende enhet](media/add-existing-entity.png)

2. Velg enheten du vil legge til, i dialogboksen **Klikk løsningskomponenter** med **Komponenttype**-velgeren satt til **Enhet**, og velg **OK**.

3. Hvis dialogboksen **Mangler obligatoriske komponenter** vises, kan du velge **Nei, ikke ta med nødvendige komponenter** hvis du ikke har til hensikt å eksportere denne uadministrert løsning til en annen organisasjon. Hvis ikke vil inkludere manglende obligatoriske komponenter på dette tidspunktet, kan du legge dem til senere. Du blir varslet på nytt hvis du eksporterer løsningen senere.

4. I løsningsutforskeren viser du enheten som inneholder skjemaet du vil redigere, og velger **Skjemaer**.

5. I listen over skjemaer åpner du skjemaet av typen **Hoved**.

#### <a name="publish-the-changes-for-use-in-the-app"></a>Publisere endringene for bruk i appen

Noen tilpasninger som gjør endringer i brukergrensesnittet, krever at de publiseres før brukere kan bruke dem i programmet. Velg **Publiser alle tilpassinger** på verktøylinjen i i løsningsutforskeren for å publisere tilpassingen.

## <a name="form-editor-user-interface"></a>Brukergrensesnitt for skjemaredigeringsprogram

For å få flere detaljer om brukergrensesnittet for skjemaredigeringsprogrammet, kan du se [Oversikt over brukergrensesnittet i skjemaredigeringsprogrammet](form-editor-user-interface-legacy.md).

## <a name="form-properties"></a>Skjemaegenskaper

Hvis du vil vite i detalj om skjemaegenskapene, kan du se [Skjemaegenskaper](form-properties-legacy.md).

## <a name="visibility-options"></a>Synlighetsalternativer  
 Flere typer skjemaelementer har muligheten til å vises eller skjules som standard. Både kategorier, inndelinger og felt har dette alternativet. Ved hjelp av skjemaskript eller forretningsregler kan synligheten av disse elementene kontrolleres for å opprette dynamiske skjemaer for å gi et brukergrensesnitt som tilpasser seg til betingelser i skjemaet. 
  
> [!NOTE]
>  Skjuling av skjemaelementer er ikke en anbefalt metode for å håndheve sikkerheten. Det finnes flere metoder for brukere for å vise alle elementene og dataene i skjemaet når elementer er skjult. For mer informasjon, se [Vise eller skjule skjemaelementer](visibility-options-legacy.md). 
  
## <a name="tab-properties"></a>Egenskaper for kategori  

Kategorier utgjør vannrette skiller i brødteksten i skjemaet. Kategorier har en etikett som kan vises. Hvis etiketten vises, kan du vise eller skjule kategorier for å vise eller skjule innholdet i dem, ved å velge etiketten. Hvis du vil vite i detalj om kategoriegenskapene, kan du se [Egenskaper for kategori](tab-properties-legacy.md).


## <a name="section-properties"></a>Egenskaper for inndeling  

En inndeling i et skjema opptar plassen som er tilgjengelig i en kategorikolonne. Inndelinger har en etikett som kan vises, og det kan vises en linje under etiketten. Hvis du vil vite i detalj om inndelingsegenskapene, kan du se [Egenskaper for inndeling](section-properties-legacy.md).
  
## <a name="timeline"></a>Tidslinje  
 Tidslinjen viser relaterte aktiviteter for en bestemt enhet.  
  
 Det er støtte for følgende typer aktiviteter: oppgave, avtale, telefonsamtale, e-post, sosial aktivitet, egendefinert aktivitet.  
  
 Tidslinjen viser også notater og system- og brukerinnlegg. Den viser de aktivitetene som har **Angående**-feltet satt til enheten du viser. For notater vises ikke **Angående**-feltet til brukeren. Det er implisitt når det opprettes fra tidslinjen.  
  
 Hver aktivitet som vises på tidslinjen, vil ha de samme raske handlingene som er tilgjengelige på kommandolinjen for den aktiviteten.  

## <a name="common-field-properties"></a>Vanlige egenskaper for felt  

Hvis du vil vite i detalj om vanlige egenskaper for felt, kan du se [Vanlige egenskaper for felt](common-field-properties-legacy.md). 
  
## <a name="special-field-properties"></a>Egenskaper for spesialfelt  
 Alle felt har egenskapene oppført i [Vanlige egenskaper for felt](common-field-properties-legacy.md), men enkelte felt har flere egenskaper. Hvis du vil vite mer, kan du se [Egenskaper for spesialfelt](special-field-properties-legacy.md).

  
## <a name="sub-grid-properties"></a>Egenskaper for delrutenett  

Du kan konfigurere et delrutenett i et skjema til å vise en liste over oppføringer eller et diagram. Hvis du vil vite i detalj om egenskaper for delrutenett, kan du se [Egenskaper for delrutenett](sub-grid-properties-legacy.md).

## <a name="quick-view-control-properties"></a>Egenskaper for hurtigvisningskontroll  

En hurtigvisningskontroll i et skjema viser data fra en oppføring som er valgt i et oppslag i skjemaet. Hvis du vil se nærmere på egenskapene for hurtigvisningskontroll, kan du se [Egenskaper for hurtigvisningskontroll](quick-view-control-properties-legacy.md).
  
## <a name="web-resource-properties"></a>Egenskaper for webressurs  

Du kan legge til eller redigere webressurser i et skjema for å gjøre det mer tiltalende eller nyttig for appbrukere. Skjemaaktiverte webressurser er bilder, HTML-filer eller Silverlight-kontroller. Vit i detalj om egenskapene for webressurs. Gå til [Egenskaper for webressurs](web-resource-properties-legacy.md). 
  
## <a name="iframe-properties"></a>IFRAME-egenskaper  

Du kan legge til iFrames i et skjema for å integrere innhold fra et annet nettsted i et skjema. Hvis du vil vite mer om IFRAME-egenskapene, kan du se [IFRAME-egenskaper](iframe-properties-legacy.md). 
  
## <a name="edit-navigation"></a> Redigere navigasjon  
 Navigasjon i skjemaet lar brukere vise lister over relaterte oppføringer. Alle enhetsrelasjoner har egenskaper som avgjør om de skal vises. Mer informasjon: [Navigasjonsruteelement for primærenhet ](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)
  
 Enhetsrelasjoner som er konfigurert til vises, kan overstyres i skjemaredigeringsprogrammet.  
  
 Hvis du vil ha trinnvise instruksjoner, kan du se [Legge til skjemanavigasjon for relaterte enheter](add-edit-form-navigation-related-entities.md)
  
 Hvis du vil aktivere navigasjon, må du først velge **Navigasjon** i **Velg**-gruppen i kategorien **Hjem**.  
  
 I **relasjonsutforskeren** kan du filtrere etter 1:N- (én-til-mange) eller N:N-relasjoner (mange-til-mange), eller vise alle tilgjengelige relasjoner. Avmerkingsboksen **Vis bare ubrukte relasjoner for** deaktiveres og velges. Du kan bare legge til hver relasjon én gang.  
  
 Hvis du vil legge til relasjoner fra **relasjonsutforskeren**, dobbeltklikker du den og den vil bli lagt til under den merkede relasjonen i navigasjonsområdet. Dobbeltklikk på en relasjon i navigasjonsområdet, og dermed kan du endre etiketten i kategorien **Vis**. I kategorien **Navn** vises det informasjon om relasjonen. Bruk **Rediger** for å åpne definisjonen av enheten.  
  
 Det er fem grupper i navigasjonsområdet. Du kan dra dem for å flytte dem og dobbeltklikke dem for å endre etiketten, men du kan ikke fjerne dem. Disse gruppene vises bare når det er noe i dem. Hvis du ikke vil at en gruppe skal vises, legger du ikke til noe i den.  
  
## <a name="configure-event-handlers"></a>Konfigurere hendelsesbehandlinger  

En hendelsesbehandling består av en referanse til JavaScript-webressurs og en funksjon som er definert i webressursen, som kjøres når hendelsen oppstår. Hvis du vil vite mer om hvordan du konfigurerer hendelsesbehandlinger, kan du se [Konfigurere hendelsesbehandlinger](configure-event-handlers-legacy.md). 
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette og utforme skjemaer](create-design-forms.md)   
 [Opprette og redigere hurtigopprettingsskjemaer](create-edit-quick-view-forms.md)   
 [Opprette og redigere hurtigvisningsskjemaer](create-edit-quick-view-forms.md)
