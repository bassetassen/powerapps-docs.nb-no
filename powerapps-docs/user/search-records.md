---
title: Søk etter poster i modell drevne apper | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 26903543232025f43f935a403800ed27170e3123
ms.sourcegitcommit: 7c46e7ce889e2f1c5352ed2e705b0bb8968f2a89
ms.translationtype: MT
ms.contentlocale: nb-NO
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940887"
---
# <a name="search-for-records-in-an-app"></a>Søk etter poster i en app

Du kan søke etter poster på tvers av flere enheter ved å bruke Relevanss søk eller kategorisert søk i Common Data Service. 

- Relevanss søk leverer raske og omfattende resultater på tvers av flere enheter, i én liste, sortert etter relevans. Den bruker en dedikert søke tjeneste eksternt til å Common Data Service (drives av [!INCLUDE[pn_Windows_Azure](../includes/pn-windows-azure.md)]) for å øke søke ytelsen. 
- Kategorisert søk returnerer søke resultater som er gruppert etter enhets typer, for eksempel kontoer, kontakter eller kundeemner.

Kategorisert søk er vanligvis standard søke alternativ. Men hvis Relevanss søk er aktivert av organisasjonen, blir den standard søke opplevelse.  

Hvis du vil finne poster av én type, kan du bruke hurtig søk visning i enhetens rute nett.
  
## <a name="normal-quick-find-categorized-search"></a>Normal hurtig søk (kategorisert søk) 

Med kategorisert kan du søke etter poster som begynner med et bestemt ord, eller bruke et Joker tegn.
  
- **Begynner med**: Resultatene inkluderer poster som begynner med et bestemt ord. Hvis du for eksempel vil søke etter «Alpine Ski House, skriver du inn **Alp** i søke boksen. Hvis du skriver inn **ski**, vises ikke posten.  
  
- **Joker tegn**: For eksempel * ski or * ski @ no__t-0. 
  
## <a name="relevance-search"></a>Relevanss søk
  
  Relevanss søk er tilgjengelig i tillegg til andre Common Data Service søk som du allerede er kjent med. Du kan fortsette å bruke hurtig søk med én enhet på enhets rute nettet eller hurtig søk i flere enheter (kalt kategorisert søk hvis du har Relevanss søk aktivert). Vi anbefaler at du bruker Relevanss søk for mer omfattende og raskere resultater.  

 Relevanss søk gir følgende forbedringer og fordeler:  
  
- Forbedrer ytelsen med ekstern indekserings-og [!INCLUDE[pn_azure_shortest](../includes/pn-azure-shortest.md)] søke teknologi.  
  
- Finner treff for alle ord i søke ordet i hvilket som helst felt i enheten. Treff kan inkludere inflectional ord som **stream**, **strømming**eller **strømming**.  
  
- Returnerer resultater fra alle søkbare enheter i én enkelt liste som er sortert etter relevans, basert på faktorer som antall ord som er tilpasset eller forskrifts samsvar til hverandre i teksten.  
  
- Uthever treff i resultat listen.  

- Du finner søke resultater for tekst i et dokument som er lagret i Common Data Service, inkludert tekst i notater, e-postvedlegg eller avtaler. Følgende fil formater støttes for søk: PDF, Microsoft Office dokumenter, HTML, XML, ZIP, EML, ren tekst og JSON.  
  
- Du kan søke etter poster som er delt med deg, og poster som du eier.  
  
  > [!NOTE]
  >  Hierarkiske sikkerhets modeller støttes ikke.  Selv om du ser en rad i Common Data Service fordi du har tilgang til den via hierarkisk sikkerhet, vil du ikke kunne se resultatet i Relevanss søket.  
  
- Du kan også søke etter alternativ sett og oppslag. La oss for eksempel si at du ønsker å finne en detaljist butikk konto som har **medisiner** i navnet. Når du søker etter **Pharmaceutical detalj handel**, finner du resultatet fordi det er et treff for bransje feltet, som er et søkbart alternativ sett.  
  
  Fordi resultatene kan inneholde en blanding av enheter, kan du begrense søke resultatene til en bestemt enhet ved å velge en enhet i rulle gardin listen **filter** . Når du filtrerer etter en bestemt Posttype, kan du inkludere aktiviteter og notater relatert til den valgte posten i søke resultatene. Hvis du vil gjøre dette, velger du avmerkings boksen **Søk i aktiviteter og notater for valgte poster** til høyre for **filter med** rulle gardin listen. Avmerkings boksen er merket av når du har valgt en post i **filter med** rulle gardin listen. det fjernes hvis du ikke valgte en enhet i **filter med** -listen. Aktivitetene og notatene returneres som resultater på øverste nivå.
  
  > [!NOTE]
  > - Relevanss søk er deaktivert som standard. Administratoren må aktivere den for organisasjonen. Etter at Relevanss søk er aktivert, kan det hende du må vente opptil en time eller mer, avhengig av størrelsen på organisasjonen, før du begynner å se relevante søke resultater for appene dine. Mindre endringer i indekserte data kan ta opptil 15 minutter å vises i systemet.
  > - Hvis du aktiverer Relevanss søk, kan alle brukere i organisasjonen bruke det.  
  > - Relevanss søk er tekst BAS ert og kan bare søke i felt av typen enkelt linje med tekst, flere tekst linjer, alternativ sett eller oppslag. Det støtter ikke søk i felt med numerisk datatype eller dato data typen. 
  
 Selv om Relevanss søket finner treff for alle ord i søke ordet i hvilket som helst felt i en enhet, kan du finne @ no__t-0even med full tekst søk aktivert @ no__t-1all ord fra søke ordet i ett felt.  
  
 I Relevanss søk er jo bedre treff, jo høyere vises i resultatene. Et treff har et høyere Relevancy hvis flere ord fra søke ordet finnes i nær liggende nærhet til hverandre. Jo mindre tekst hvor søke ordene blir funnet, jo høyere er Relevancy. Hvis du for eksempel finner søke ordene i et firma navn og en adresse, kan det være et bedre treff enn de samme ordene i en stor artikkel, langt fra hverandre. Fordi resultatene returneres i én liste, kan du se en blanding av poster som vises etter hverandre, for eksempel kontoer, muligheter, kundeemner og så videre. De samsvarende ordene i listen er uthevet.  
  
 Bruk syn tak sen i søke ordet for å få resultatene du ønsker. Skriv for eksempel inn **bil sølv 2 – dør** for å inkludere treff for et hvilket som helst ord i søke ordet i søke resultatene. Skriv inn **bil + sølv +2** for å finne bare treff som inkluderer alle de tre ordene. Skriv **inn&#124;bil&#124;sølv 2 – døren** for å få resultater som inneholder **Car** eller **sølv** eller **2 dører**, eller alle de tre ordene. Mer informasjon om syn tak sen du kan bruke i søke spørringene: [Enkel spørrings syn taks i Azure Search](https://docs.microsoft.com/rest/api/searchservice/simple-query-syntax-in-azure-search)


> [!NOTE]
> Du vil se treff utheving når søke ordet Sams varer med en term i appen din. Treff høylyset vises som fet og kursivert tekst i søke resultatene. Disse returneres ofte som en del av den fullstendige verdien i et felt, fordi bare de samsvarende vilkårene er uthevet. 
  
  
<a name=" #BKMK_DefaultOption "></a>
## <a name="switch-between-relevance-and-categorized-search"></a>Bytt mellom relevans og kategorisert søk

Hvis organisasjonen har aktivert både søke alternativer (relevans og kategorisert søk), kan du bytte mellom disse to.

1. Hvis du vil bytte mellom søke typer, velger du **Søk** -knappen i navigasjons feltet.

2. Til venstre velger du rulle gardin menyen for å veksle mellom **relevanss søk** eller **kategorisert søk**.

   > [!div class="mx-imgBorder"]
   > ![Bytt mellom relevans og kategoriserte søke](media/switch-search.png "Bytt mellom relevans og kategorisert søk") 
    
### <a name="set-a-default-experience"></a>Angi en standard opplevelse

Hvis organisasjonen har aktivert begge søke alternativene, kan du velge en standard søke opplevelse i de personlige innstillingene.

1. Velg **Innstillinger** i hjørnet øverst til høyre på siden, og velg deretter innstillinger for **personlige data**.  
  
   > [!div class="mx-imgBorder"]
   > ![Velg standard søke opplevelse](media/relevance-search-personal-settings.png "Velg standard søke opplevelse")  

2. På **Generelt** -fanen, i delen **Velg standard søke opplevelse** , velger du standard-opplevelsen for **standard søke opplevelse**. 

   > [!div class="mx-imgBorder"]
   > ![Velg standard søke opplevelse](media/default.png "Velg standard søke opplevelse")  
 


## <a name="start-a-search"></a>Start et søk 
 
1.  Velg **Søk** -knappen fra det øverste navigasjons feltet.  
  
2.  Skriv inn søke ordene i søke boksen, og velg deretter **Søk** -knappen.   

    > [!div class="mx-imgBorder"]
    > (media/search-option.png "Søke alternativ") for ![søke alternativ]  
  
## <a name="filter-categorized-search-results"></a>Filtrer kategoriserte søke resultater 
  
-   Hvis du vil filtrere resultatene etter én oppførings type, velger du en Posttype fra rulle gardin listen **filter** på søke skjermen.  
  
-   Hvis du vil søke i alle oppførings typer, velger du **ingen** i rulle gardin listen **filter med** .  

    > [!div class="mx-imgBorder"]
    > (media/filter-search.png "Søk etter") ![filter søke]filter  

## <a name="filter-records-with-facets-works-with-relevance-search"></a>Filtrere poster med faser (fungerer med Relevanss søk)  
 Med Common Data Service kan du nå forbedre søke resultatene ved å bruke faser og filtre. Egenskaper er tilgjengelige i den venstre ruten. Umiddelbart etter at du har utført et søk, er følgende globale faser tilgjengelige for fire vanlige felt:  
  
-   Oppførings type  
  
-   Eier  
  
-   Opprettet den  
  
-   Endret  
  
### <a name="record-type-facets"></a>Oppførings type egenskaper  
 Hvis du vil begrense søke resultatene til en bestemt enhet, velger du enheten under **oppførings type** .  
 
  > [!div class="mx-imgBorder"]
  > ![Record type-fasetten til å begrense](media/relevance-search-record-type-facet.png "oppførings type egenskapen for søke resultater som skal brukes til å begrense søke resultater")  
  
 Når du filtrerer etter en bestemt Posttype, kan du inkludere aktiviteter og merknader som er relatert til den valgte posten i søke resultatene. Hvis du vil gjøre dette, merker du av for **Beslektede notater & aktiviteter** . Aktivitetene og notatene vises i resultater på øverste nivå.  
  
 
  > [!div class="mx-imgBorder"]
  > ![Inkluder notater og aktiviteter som er relatert til en oppførings type i søke resultatene](media/relevance-search-record-type-facet-related-notes-activities.png ", inkluderer notater og aktiviteter som er relatert til en oppførings type i søke resultatene")  
  
 Søke resultater som finnes i e-postvedlegg eller avtale enheter vises i søke resultatene under sin overordnede oppføring, enten e-post eller avtale.  
  
 Når du begrenser etter Posttype, blir fase omfanget bytter til den valgte enheten, og opptil fire faser som er spesifikke for enheten, vises. Hvis du for eksempel velger kontoen enhet, ser du den **primære kontakt** -fasetten i tillegg til de globale egenskapene.  
  
 I dialog boksen **Angi personlige alternativer** kan du også velge andre egenskaper fra de som systemansvarlig eller kunden har tilgjengelig for deg. Bruker innstillingen overstyrer standard innstillingen. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Konfigurer faser og filtre for søket](#BKMK_ConfigureFacets)  
  
### <a name="text-based-facets"></a>Tekstbaserte egenskaper  
 Alle oppslag, alternativ sett og oppførings typer er tekstbaserte egenskaper. Eieren av den tekstbaserte fasetten består for eksempel av en liste med felt verdier og deres tilsvarende antall.  
 
  > [!div class="mx-imgBorder"]
  > ![Tekst BAS ert egenskap i](media/relevance-search-text-based-facets.png "tekst BAS ert egenskap for relevans i relevanss søk")  
  
 Filtre i disse fasetten er sortert i synkende rekkefølge etter antall. De fire høyeste fase verdiene vises som standard. Når det er mer enn fire fase verdier, ser du en **Vis flere** koblinger du kan velge for å utvide listen og se opptil 15 Top fase verdier. Velg hver verdi for å filtrere søke resultatene for å vise bare postene der feltet har verdien du har valgt. Hvis du for eksempel velger **Kim Abercrombie**, vil søke resultatene vise alle poster der eieren er Kim Abercrombie. Når du velger en egenskaps verdi for oppslag eller alternativ sett, filtreres søke resultatene til bare å ta med poster med verdien du har angitt.  
  
### <a name="date-and-time-facets"></a>Faser for dato og klokkeslett  
 I likhet med andre egenskaper kan du bruke dato-og klokkeslett-faser til å filtrere og se søke resultater for et bestemt tidspunkt. Dra Glide bryte ren eller velg en av de lodd rette Kol onnene for å velge et verdi område.  
 
  > [!div class="mx-imgBorder"]
  > ![Dato-og klokkeslett-faser for relevans søk]etter(media/relevance-search-date-time-facets.png "dato-og klokkeslett faser for relevanss søk")  
  
<a name="BKMK_ConfigureFacets"></a>   
### <a name="configure-facets-and-filters-for-the-search"></a>Konfigurer faser og filtre for søket  
 Faser og filtre lar deg drille inn og utforske resultatene av gjeldende søk uten å måtte begrense søke ordet gjentatte ganger. Konfigurer fasene og filtrene du vil bruke, i dialog boksen **Angi personlige alternativer** .  
  
> [!NOTE]
>  Systemtilpasser kan angi standard opplevelsen for alle enheter, men du kan konfigurere dine egne faser og filtre.  
  
#### <a name="to-configure-facets-for-yourself"></a>Slik konfigurerer du faser for deg selv  
  
1. Velg **Innstillinger** i hjørnet øverst til høyre på siden, og velg deretter innstillinger for **personlige data**.  
  
   > [!div class="mx-imgBorder"]
   > ![Velg standard søke opplevelse](media/relevance-search-personal-settings.png "Velg standard søke opplevelse")  
  
2. På **Generelt** -fanen i **Velg standard inndelingen for søke opplevelse** i **faser-og filtre** -feltet velger du **Konfigurer**.  
  
3. I dialog boksen **Konfigurer faser og filtre** angir du fasetten som du vil se etter en enhet. Systemansvarlig eller tilpassarheten kan angi en standard opplevelse for alle enheter, men du kan angi din egen her.  
  
   - Velg en enhet du vil konfigurere faser for i rulle gardin listen **Velg enhet** . Denne rulle gardin listen inneholder bare enheter som er aktivert for Relevanss søk.  
  
   - Velg opptil fire egenskaps felt for den valgte enheten. Som standard velges de fire første egenskaps feltene i **hurtig søk** visning for den valgte enheten i listen. Du kan når som helst ha fire felter valgt som faser.  
  
     Du kan oppdatere flere enheter samtidig. Når du velger **OK**, lagres endringene for alle enheter du har konfigurert. Hvis du vil gå tilbake til standard virke måte for en enhet som du tidligere har konfigurert, velger du **standard**.  
  
   > [!NOTE]
   > - Hvis en systemtilpasser sletter et felt eller gjør det ikke lenger søkbart, og du har lagret en egenskap for dette feltet, vises det ikke lenger som en egenskap.  
   >   -   Du ser bare feltene som finnes i standard løsningen, og som er konfigurert som søkbart av Systemtilpasser.  
  
 
