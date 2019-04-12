---
title: Bruke egendefinerte kontroller for datavisualiseringer i modelldrevne apper i PowerApps | MicrosoftDocs
description: Finn ut hvordan du bruker egendefinerte kontroller for felt
ms.custom: ''
ms.date: 06/07/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 0d6064cd-4d38-4fc2-a564-735cb453a4b2
caps.latest.revision: 8
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-custom-controls-for-model-driven-app-data-visualizations"></a>Bruke egendefinerte kontroller for datavisualiseringer i modelldrevne apper

I dette emnet lærer du hvordan du konfigurerer en egendefinert kontroll for et felt. 

Egendefinerte kontroller lar deg transformere komponenter i brukergrensesnittet for appen, for eksempel et felt eller en visning som vanligvis inneholder tekst, til visualiseringer. Egendefinerte kontroller kan konfigureres i felt, skjemaer, instrumentbord, visninger og rutenett. En glidebryterkontroll kan for eksempel konfigureres i et tallfelt.

   > [!div class="mx-imgBorder"] 
   > ![Egendefinert glidebryterkontroll](media/slider-control.PNG "Glidebryterkontroll for et felt")

Eller den redigerbare rutenettkontrollen kan konfigureres i en visning. 

   > [!div class="mx-imgBorder"] 
   > ![Redigerbar rutenettkontroll](media/editable-grid-example.png)

Du kan angi at én type egendefinert kontroll skal vises i nettleserklienten, mens en annen egendefinert kontroll skal vises i mobilapper på telefonen eller nettbrett i Dynamics 365. Du kan for eksempel bruke en egendefinert tallinndatakontroll for et felt i nettleserklienter og en egendefinert glidekontroll for telefonappen. Når tilpassingen er publisert, kan brukere samhandle fullstendig med kontrollen for å endre verdien, for eksempel ved å dra kontrollen når du bruker den egendefinerte lineære glidekontrollen. Endringene lagres automatisk når skjemaet lukkes, på samme måte som når du endrer et vanlig felt i et skjema.  
  
## <a name="use-a-custom-control-to-add-visualizations-to-a-field"></a>Bruke en egendefinert kontroll for å legge til visualiseringer et felt  
 Ved å følge fremgangsmåten i denne prosedyren endres standard etikett- og tekstboksfeltet i **Budsjettbeløp**-feltet til den egendefinerte glidekontrollen i Salgsmulighet-enheten. Du kan bruke samme fremgangsmåte for å erstatte et eksisterende felt med en egendefinert kontroll eller konfigurere en egendefinert kontroll for et egendefinert felt.  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

     

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  
  
2.  Åpne et skjema, for eksempel **Hoved**-skjemaet for salgsmulighetsenheten. 
  
3.  Dobbeltklikk feltet der du vil legge til en egendefinert kontroll i skjemaredigeringsprogrammet, for eksempel **Budsjettbeløp**-feltet i hovedskjemaet for salgsmulighet. Alternativt kan du opprette et egendefinert felt. 
  
4.  På siden **Feltegenskaper** velger du kategorien **Kontroller** og velger deretter **Legg til kontroll**.  
  
5.  På siden Legg til kontroll velger du kontrollen du vil bruke, for eksempel kontrollen **Lineær glidebryter** som vises her, og velger deretter **Legg til**.  

   > [!div class="mx-imgBorder"] 
   > ![Legg til kontroll for lineær glidebryter](media/add-slider.PNG "Legg til kontroll for lineær glidebryter")  
  
6.  Velg klienten der du vil at kontrollen skal vises.  
  
    - **Web**. Hvis du vil gjøre den egendefinerte kontrollen tilgjengelig fra en webleser, velger du **Web**-alternativet ved siden av kontrollen. Vær oppmerksom på at **Web**-alternativet omfatter at kontrollen gjengis i weblesere i PC-er, Mac-er og mobile enheter.  
  
    - **Telefon**. Hvis du vil gjøre den egendefinerte kontrollen tilgjengelig på telefoner som kjører Dynamics 365 for phones, velger du alternativet **Telefon** ved siden av kontrollen.  
  
    - **Nettbrett**. Hvis du vil gjøre den egendefinerte kontrollen tilgjengelig på nettbrett som kjører Dynamics 365 for tablets, velger du alternativet **Nettbrett** ved siden av kontrollen.  
  
   > [!div class="mx-imgBorder"] 
   > ![Velg klientappene for å vise den egendefinerte kontrollen](media/choose-client.png "Velg klientappene for å vise den egendefinerte kontrollen")  
  
7.  Velg blyantikonet ![Ikon for redigering av egenskapene for egendefinert kontroll](media/ccf-pencil-icon.png "Ikon for redigering av egenskapene for egendefinert kontroll") ved siden av **Min**, **Maks** og **Trinn**, angi egenskapsalternativet nedenfor, og velg deretter **OK**.  
  
   > [!div class="mx-imgBorder"] 
   > ![Legg til egenskaper for egendefinert kontroll](media/ccf-add-properties.png "Legg til egenskaper for egendefinert kontroll")
  
   - **Min**. Angi den minste godtatte verdien. Du kan binde en statisk verdi du angir, eller binde verdien til et eksisterende felt. I dette eksemplet er **Bind til en statisk verdi** **Valuta** og minimumsverdien som kan angis, er *null*.  
  
       - **Bind til en statisk verdi**. Velg datatypen, for eksempel heltall (Whole.None), valuta, flytende punkt (FP) eller desimal. Deretter angir du et tall som representerer den minste godtatte verdien for feltet.  
  
       - **Bind til verdier i et felt**. Velg et felt fra listen som skal brukes som den godkjente minimumsverdien.  
  
   - **Maks**. Angi maksverdien som godtas for feltet. I likhet med minimumsverdien kan du binde en statisk verdi du angir, eller binde verdien til et eksisterende felt som beskrevet tidligere. I dette eksemplet er **Bind til en statisk verdi** **Valuta** og maksverdien som kan angis, er **1 milliard**.  
  
   - **Trinn**. Dette er enheten som brukes til å øke eller redusere når du legger til eller trekker fra den gjeldende verdien. Du kan for eksempel velge 100 dollar økninger\reduksjoner for budsjettbeløp.  
  
   - **Skjul standardkontroll**. Hvis du velger dette alternativet, skjules kontrollen slik at verken kontrollen eller dataene vises i noen av klientene som ikke støtter den egendefinerte kontrollen. Legg merke til at den klassiske Dynamics 365-webklienten ikke støtter de fleste egendefinerte kontroller. Dette alternativet er ikke er valgt som standard, og den klassiske Dynamics 365-webklienten viser standardkontrollen, vanligvis tekstbasert.  
  
       > [!NOTE]
       >  Standardkontrollen identifiseres med **(standard)** etter navnet på kontrollen.  
       >   
       > > [!div class="mx-imgBorder"] 
       > > ![Standardkontroll](media/default-control.png "Standardkontroll")  
  
8.  Velg **OK** for å lukke siden **Feltegenskaper**.  
  
9. Velg **Lagre**, og velg deretter **Publiser** i enhetsskjemaet for å aktivere tilpassingen.  
  
10. Velg **Lagre og lukk** for å lukke skjemaredigeringsprogrammet.  
  
### <a name="see-the-custom-control-in-action"></a>Se den egendefinerte kontrollen i aksjon  
 Åpne en oppføring som inneholder feltet med den egendefinerte kontrollen, for eksempel Salgsmulighet-skjemaet, fra det forrige eksemplet, og vis hvordan feltet er endret.  
  
   > [!div class="mx-imgBorder"] 
   > ![Glidekontrollen som vises på skjemaet](media/slider-control.PNG "Glidekontrollen som vises på skjemaet")  
  
 Feltet vises nå som en glidekontroll i stedet for tekstfeltet. 

## <a name="use-the-editable-grid-control-on-a-view-or-sub-grid"></a>Bruk den redigerbare rutenettkontrollen i en visning eller et delrutenett.

Med redigerbare rutenett kan brukere gjøre omfattende redigering direkte fra visninger og delrutenett, enten de bruker en webapp, et nettbrett eller en telefon. Mer informasjon: [Gjøre rutenett (lister) redigerbare ved hjelp av Egendefinert kontroll for redigerbart rutenett](make-grids-lists-editable-custom-control.md) 
  
## <a name="next-steps"></a>Neste trinn  
[Opprette og rediger felt](../common-data-service/create-edit-fields.md)
