---
title: Fremgangsmåter for appbygging i Common Data Service for apper | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e9810433-224b-4bde-851a-e581cf5fb8a4
caps.latest.revision: 21
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1eda4b591a3296001ffa62b16e185b421a197e75
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nb-NO
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865045"
---
# <a name="common-data-service-for-apps-supported-and-unsupported-app-building-practices"></a>Støttede og ikke støttede fremgangsmåter for appbygging i Common Data Service for apper

<!--
The way your organization works is unique. Some organizations have well-defined business processes that they apply using PowerApps apps. Others aren’t happy with their current business processes and use PowerApps to apply new data and processes to their business. Whatever situation you find yourself in, you’ll find a lot of customization capabilities in PowerApps so that it can work for your organization.  
  
 Of course you’re eager to get started, but please take a few minutes to read the content in this section. This will introduce you to important terms, give you some background about why things are done a certain way, and help you avoid potential problems in the future.  

## What is metadata and why should you care?  
 In the past, you may have customized business applications by editing the source code. This created complications because each organization had unique changes and it was very difficult, or extremely expensive, to upgrade. Then application developers started exposing application programming interfaces (APIs) so that other developers could interact with the application and add their own logic without touching the source code. This was moderately better because it means developers can extend the application without changing it. But it still requires a developer to write code.  -->
  
 Moderne forretningsprogrammer bruker en metadatadrevet arkitektur slik at folk kan opprette apper uten å skrive kode. Metadata betyr «data om data» og definerer strukturen på dataene som er lagret i Common Data Service for apper. Med disse metadataene vet et program om eventuelle endringer i datastrukturen. Dette gjør at programmet kan tilpasse seg etter hvert som datastrukturen endres. Siden metadataene er kjent, kan ytterligere funksjoner inkluderes som er knyttet til metadataene.  

Det å endre komponenter for Common Data Service for apper, som enheter, visninger, felter, diagrammer og instrumentbord til å bygge apper som fungerer slik du ønsker, heter *tilpassinger*.  
 
Når du bygger og tilpasser appene ved bruk av verktøyene i PowerApps, legger du til eller oppdaterer metadataene, eller data som brukes av funksjoner som er avhengige av metadataene. Fordi vi kjenner til dataene som brukes til å opprette apper, kan vi ta hensyn til disse dataene. Vi kan også legge til nye funksjoner i miljøet til Common Data Service for apper, uten at appene dine blir ødelagt. <!-- This way you should always be able to apply an update rollup or upgrade to the latest version and enjoy the best new features.  -->

<!--  
> **Customize or Configure?**   
> Most people say they want to customize the application, so we use the word “customize” to describe changing the system to make it work the way you want. Some people prefer to use the word “configure” because it suggests that no code was required to make changes. Call it whatever you like, we just want to make it clear that you don’t need to be a developer to customize or create PowerApps apps.  -->
  
Du trenger ikke å være en utvikler for å bygge og tilpasse PowerApps-apper. PowerApps inneholder imidlertid er sett med nettjenester og API-er som lar utviklere skrive kode. Når koden skrives ved bruk av støttede metoder, kan du forvente at den fortsetter å fungere når miljøet i Common Data Service for apper blir oppdatert.  
  
<a name="BKMK_SupportedCust"></a>   
## <a name="what-kinds-of-customizations-are-supported"></a>Hva slags tilpassinger støttes?  
 Vi forventer at du kan bygge de fleste appene og tilpasse dem ved bruk av de tilgjengelige PowerApps-verktøyene. Hvis tilpassingsverktøyene ikke oppfyller behovene dine, kan du installere en løsning fra en tredjepart, eller du kan ansette en utvikler til å kode appen din. Hvis du trenger å investere i en løsning som krever kode, må du sørge for at koden skrives ved bruk av bare støttede API-er. Dette gjør at du kan beskytte investeringen i både appene og eventuelle løsninger du skaffer deg.  
  
 Utviklere som utvider PowerApps-apper, har et ansvar for å følge regler og anbefalte fremgangsmåter som er dokumentert i SDK-en: [Anbefalte fremgangsmåter for utvikling med Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/developer/best-practices-sdk). SDK-en dokumenterer API-ene som er tilgjengelig for utviklere, og gir en veiledning om hvordan de brukes. Microsoft støtter bare API-ene og fremgangsmåtene som er dokumentert i SDK-en. Det kan hende du finner noe på Internett som beskriver hvordan du kan løse et problem, men hvis det ikke drar nytte av API-ene som er dokumentert i SDK-en, støttes det ikke av Microsoft. Før du får en utvikler til å ta i bruk en endring, må du bekrefte at den bruker støttede metoder.  
  
 Hvis utviklere bruker API-ene og de anbefalte fremgangsmåtene som er beskrevet i SDK-en, kan vi teste om endringene vi gjør i Common Data Service for apper kan føre til brudd på eksisterende tilpassinger. Vårt mål er at kodetilpassinger som er skrevet ved bruk av støttede metoder skal fortsette å fungere, når nye versjoner eller oppdateringer til Common Data Service for apper utgis. Du drar nytte av dette fordi du kan oppgradere til nye versjoner med forbedrede funksjoner, uten at utviklerne må endre koden hver gang.  
  
 Hvis vi oppdager at en endring i en ny versjon av Common Data Service for apper fører til et brudd på en støttet tilpassing, dokumenterer vi innvirkningene, og vi forklarer hvordan folk kan endre koden for å rette det opp.  
  
<a name="BKMK_Unsupported"></a>   
## <a name="what-kinds-of-customizations-arent-supported"></a>Hva slags tilpassinger støttes ikke?  
 Selv om bestemte API-er og fremgangsmåter for programmering ikke støttes av Microsoft, betyr det ikke at de ikke fungerer. <!--  “Unsupported by Microsoft” means exactly what it says: you can’t get support about these APIs or programming practices from Microsoft. We don’t test them and we don’t know if something we change will break them. We can’t predict what will happen if someone changes code in our application.  -->  Utviklere som bruker ikke støttede API-er og fremgangsmåter for programmering, tar på seg ansvaret for å støtte sin egen kode. De må teste koden for å sikre at den fungerer.  
  
 Hvis du velger å bruke ikke støttede tilpassinger i miljøet til Common Data Service for apper, må du dokumentere det som ble gjort og utforme en strategi for å fjerne disse tilpassingene før du kontakter Miljø kundestøtte. Hvis du trenger hjelp med ikke støttede tilpassinger, kontakter du utvikleren eller organisasjonen som forberedte tilpassingene.  
  
<a name="BKMK_CommonUnsupportedCustomizations"></a>   
### <a name="common-unsupported-customization-practices"></a>Vanlige fremgangsmåter for tilpassing som ikke støttes  
 Det følgende er en liste over vanlige fremgangsmåter for tilpassing som ikke støttes. Dette er ikke en fullstendig liste. Mer informasjon: [Støttede utvidelser for Dynamics 365: tilpassinger som ikke støttes](https://docs.microsoft.com/dynamics365/customer-engagement/developer/supported-extensions#Unsupported). 
 
**Samhandle med elementer i nettprogrammet Document Object Model (DOM) ved bruk av JavaScript**  
 Eventuelle JavaScript-biblioteker som brukes i programmet, må bare samhandle med de dokumenterte API-ene. Når JavaScript-utviklere arbeider med programmer, bruker de ofte DOM-elementer ved bruk av spesifikke navn. Siden PowerApps-apper er nettprogrammer, fungerer disse teknikkene, men de kommer sannsynligvis til å brytes i løpet av en oppdatering. Det er fordi navnene til elementene de henviser til, kan endres når som helst. Vi forbeholder oss retten til å forete eventuelle endringer som er nødvendig i programmet, og dette betyr ofte å endre hvordan siden er laget. Hvis du legger til endringer som er avhengige av den gjeldende strukturen til siden, må du investere i testing og kanskje endre den egendefinerte koden i disse skriptene hver gang du tar i bruk en oppdatering i programmet.  
  
 jQuery er et veldig vanlig bibliotek som brukes av JavaScript-utviklere. De fleste av fordelene med å bruke JQuery er at det forenkler utviklerens evne til å bruke og opprette DOM-elementer. Dette er nøyaktig det vi ikke støtter i programsider for Common Data Service for apper. jQuery anbefales når utviklere oppretter egendefinerte brukergrensesnitt med HTML-nettressurser. De støttede API-ene krever imidlertid ikke at JQuery brukes på selve PowerApps-programsidene.  
  
 **Bruk av udokumenterte interne objekter eller metoder ved bruk av JavaScript**  
Common Data Service for apper bruker mange JavaScript-objekter på sider. En JavaScript-utvikler kan oppdage disse objektene ved å feilsøke en side, og deretter få tilgang til å gjenbruke disse objektene. Vi forbeholder oss retten til å foreta eventuelle nødvendige endringer til disse objektene, inkludert å fjerne dem eller endre navnet på metodene. Hvis et skript henviser til disse objektene, brytes skriptet hvis de ikke blir funnet.  <a name="BKMK_Metadata"></a>   
 
<a name="BKMK_CombineCustomizations"></a>   
## <a name="combine-customization-capabilities"></a>Kombiner tilpassingsfunksjoner  
 Emnene i disse inndelingene beskriver individuelle tilpassingsfunksjoner i betydelig dybde. Men det er viktig å huske at løsninger for å oppfylle forretningskravene dine, ofte kommer til å bruke én av funksjonene sammen med én eller flere funksjoner.  
  
<a name="BKMK_ChooseTheRightCustomization"></a>   
### <a name="choose-the-right-customization-capability-for-the-job"></a>Velg den riktige tilpassingsfunksjonen for jobben  
 Med alle de ulike tilpassingsfunksjonene som er tilgjengelig i PowerApps, er det enkelt å bli kjent med én av dem og ta den i bruk for å løse hvert problem. Mens du evaluerer forretningsproblemene du ønsker å løse, må du tenke over sluttresultatet du ønsker å oppnå. Og deretter jobber du deg bakover for å se hvordan du kan oppnå resultatene.  
 
<a name="BKMK_changesinperformance"></a>   
## <a name="changes-that-affect-common-data-service-for-apps-environment-performance"></a>Endringer som påvirker miljøytelsen til Common Data Service for apper  
 Hvis du importerer løsninger og tar i bruk tilpassinger som kan endre metadata, kan det påvirke miljøytelsen til Common Data Service for apper. Handlinger som kan forstyrre normale systemoperasjoner inkluderer:  
  
-   Legg til, fjern eller endre enheter, alternative nøkler, attributter eller relasjoner.   
-   Importløsninger
  
-   Publisering av tilpassinger 
  
Hvis du tar i bruk disse endringene i et produksjonssystem, anbefaler vi at du planlegger disse operasjonene på et tidspunkt som passer best for brukerne.   
  
  
## <a name="next-steps"></a>Neste trinn  
[Hva er modelldrevne apper i PowerApps?](../../maker/model-driven-apps/model-driven-app-overview.md)

