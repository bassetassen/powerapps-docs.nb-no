---
title: Opprette din egen veiledningshjelp (læringsforløp) (Dynamics 365 for Customer Engagement-apper) | MicrosoftDocs
description: ''
keywords: null
ms.date: 04/30/2019
ms.service: dynamics-365
ms.topic: article
applies_to:
  - Dynamics 365 for Customer Engagement (online)
ms.assetid: 8ee3c432-5f76-4086-b9cc-6cd467ae056b
author: Mattp123
ms.author: matp
manager: kvivek
topic-status: Drafting
search.audienceType:
  - customizer
search.app:
  - D365CE
---

# <a name="create-guided-help-learning-path-for-your-app"></a>Opprette veiledningshjelp (læringsforløp) for appen

Bruk Læringsforløp til å gi brukerne en tilpasset hjelpeopplevelse i appen som er skreddersydd til miljøet, bruken og arbeidsflyten i organisasjonen. Læringsforløp gjør det enklere å lære og ta i bruk apper og organisatoriske prosesser, sikrer at data angis og tolkes konsekvent, og reduserer antall feil og kundestøttehenvendelser fra brukere. [Se en kort video (1:50) om læringsforløp](https://community.dynamics.com/crm/b/crmvideos/archive/2016/05/09/introducing-learning-path-for-dynamics-crm).  

<a name="CustomHelp"></a>   

## <a name="how-is-learning-path-different-from-customizable-help"></a>Hvordan er læringsforløp forskjellig fra hjelp som kan tilpasses?  
 Hjelp som kan tilpasses, lar deg overstyre standard [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-apphjelp og henviser brukere i organisasjonen til en annen URL-adresse for hjelp. Eller du kan overstyre hjelpen for en svært tilpasset enhet slik at du kan beskrive arbeidsflyten på en bedre måte. 

 Læringsforløp lar deg legge til tilpasningsbar hjelp som brukerne ser i appen når de åpner en side, utfører en handling eller velger Hjelp-knappen (?).   

 Hvis du vil ha mer informasjon om hjelp som kan tilpasses, kan du se [Tilpasse Hjelp-opplevelsen](https://technet.microsoft.com/library/dn832079.aspx).  

<a name="Avail"></a>   
## <a name="prerequisites"></a>Forhåndskrav  

 For å opprette læringsforløpsinnhold, må du:  

- Bruke PowerApps eller [!INCLUDE[pn_crm_online_shortest](../../includes/pn-crm-online-shortest.md)].  

- Ha valgt å bruke læringsforløp. Denne innstillingen er aktivert som standard, men kan være deaktivert.  

   Slik sørger du for at læringsforløp er på: I navigasjonsfeltet, gå til **Innstillinger** ![Innstillinger-ikonet](media/optionsbutton.png "Innstillinger-ikonet") > **Bruk læringsforløp**.  

   Hvis du vil ha mer informasjon, kan du se [På/av-bryter for læringsforløp (veiledningshjelp)](/dynamics365/customer-engagement/admin/on-off-switch-for-learning-path-guided-help).  

- Ha systemtilpasser- eller systemansvarligrollen eller en annen rolle som har redigeringsrettigheter for læringsforløp.  

- Aktiver redigering av læringsforløp. Dermed opprettes sikkerhetsgruppen for forfattere for læringsforløp i [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)].  

- Være medlem av sikkerhetsgruppen for forfattere for læringsforløp i [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)].  

  Du kan skrive læringsforløpinnhold for webappmoduler og appmoduler for enhetlig grensesnitt. Dette omfatter [!include[](../../includes/pn-dyn-365-tablets.md)].  

<a name="TurnOnLP"></a>   
## <a name="turn-on-learning-path-for-your-organization"></a>Aktivere læringsforløp for organisasjonen  
 Læringsforløp er en valgfri funksjon som kan slås på eller av for organisasjonen. Du kan vise læringsforløpsinnhold sammen med [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)], lage ditt eget læringsforløpinnhold for brukerne, eller begge deler.  

1. Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) eller [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] med en administratorkonto.  

2. Gå til **Innstillinger**, og velg deretter **Administrasjon** under **System**. Mer informasjon: [Innstillinger](/powerapps/maker/model-driven-apps/advanced-navigation#settings)

3. Velg **Systeminnstillinger** på siden **Administrasjon**.  

4. I **Generelt**-fanen under **Angi URL-adresse for tilpasset Hjelp** velger du **Ja** for **Aktiver læringsforløp** og **Aktiver redigering av læringsforløp**.  

    Du kan aktivere læringsforløp eller tilpassbar hjelp, men ikke begge deler samtidig. Kontroller at **Bruk tilpasset Hjelp for enheter som kan tilpasses** og **Tilføy parametere i URL-adresse** er satt til **Nei**.  

     ![Dialogboksen Systeminnstillinger som viser alternativene for å velge å aktivere redigering av læringsforløp](media/lp-system-settings.png "Dialogboksen Systeminnstillinger som viser alternativene for å velge å aktivere redigering av læringsforløp")  

5. Velg **OK**.  

<a name="ReqsAuth"></a>   
## <a name="add-a-user-to-the-office-365-learning-path-authors-security-group"></a>Legge til en bruker i sikkerhetsgruppen for forfattere for Office 365-læringsforløp  
 Hvis du ikke er medlem av sikkerhetsgruppen for forfattere for læringsforløp i [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)], vil du se følgende feilmelding når du åpner innholdsbiblioteket i læringsforløp.  

 ![Feilmelding som indikerer at du ikke er medlem av sikkerhetsgruppen Læringsforløp](media/lp-o365-security-group.png "Feilmelding som indikerer at du ikke er medlem av sikkerhetsgruppen Læringsforløp")  

#### <a name="add-a-user"></a>Legge til en bruker  

1. Gå til administrasjonsportalen for [!INCLUDE[pn_Office_365](../../includes/pn-office-365.md)]-leieren ved å velge knappen **Naviger til andre programmer** i hjørnet øverst til venstre på siden når du er logget på [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)], og velg deretter **Administrator**.  

    Du kan bli bedt om å skrive inn passordet på nytt.  

2. I **administrasjonssenteret** velger du **Grupper**.  

3. På **Grupper**-siden velger du sikkerhetsgruppen for **forfattere for læringsforløp**.  

4. I **Medlemmer**-raden velger du **Rediger** for å legge til brukere i gruppen.  

5. Velg **+ Legg til medlemmer**, og angi deretter eller søk etter brukeren/brukerne du vil legge til i gruppen.  

6. Velg **Lagre** når du er ferdig å legge til brukere.  

> [!NOTE]
>  En annen måte å tilordne gruppen til en brukerkonto på, er å velge **Brukere** > **Aktive brukere**, velge brukeren du vil legge til, og deretter velge **Rediger** ved siden av **Gruppemedlemskap** for å velge gruppen/gruppene du vil legge til brukeren i.  

<a name="MultipleOrgs"></a>   
## <a name="how-does-learning-path-work-with-multiple-organizations"></a>Hvordan fungerer læringsforløp med flere organisasjoner?  
 Når du publiserer læringsforløpinnhold, kan du bruke publiseringsmiljøer til å styre hvilke organisasjoner som er knyttet til leietakeren innholdet publiseres til. Hvis du vil publisere forskjellig innhold til ulike organisasjoner, kan du opprette flere publiseringsmiljøer og legge til hver organisasjon i én eller flere av dem.  

<a name="SecurityRoles"></a>   
## <a name="learning-path-and-dynamics-365-for-customer-engagement-apps-security-roles"></a>Sikkerhetsroller for læringsforløp og Dynamics 365 for Customer Engagement-apper  
 [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] bruker sikkerhetsroller til å finne ut hvilket læringsforløpinnhold som vises når en bruker velger Hjelp-knappen, navigerer til en side eller utfører en definert handling i [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)].  

 Rollene som brukes i læringsforløp, er de samme rollene som brukes i [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-organisasjonen din for sikkerhet og datatilgang, men du kan opprette læringsforløpinnhold for en eller alle [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-sikkerhetsrollene.  Du vil vanligvis at sikkerhetsrollene i utformingen av læringsforløp skal samsvare med [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-forekomsten din. Du kan imidlertid forenkle brukergrensesnittet i utformingen ved å skjule noen [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-sikkerhetsroller fra utformingen. Hvis du senere bestemmer at du vil bruke en sikkerhetsrolle som du har slettet fra læringsforløp, kan du synkronisere rollene mellom læringsforløp og [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)].  

 Hvis organisasjonen har flere forretningsenheter, kan sikkerhetsroller ha overordnede/underordnede relasjoner. Bare sikkerhetsrollene i forretningsenheten på rotnivå synkroniseres.  

 Mer informasjon om sikkerhetsroller: [Sikkerhetsroller og tilgangsrettigheter](/dynamics365/customer-engagement/admin/security-roles-privileges).  

<a name="Precedence"></a>   
### <a name="learning-path-role-precedence"></a>Rolleprioritet for læringsforløp  
 Hvis en bruker i organisasjonen er tilordnet mer enn én sikkerhetsrolle, brukes prioritet til å bestemme hvilken tilordnet sikkerhetsrolle som skal brukes for å vise læringsforløpinnhold. Hvis læringsforløpinnhold er tilknyttet en sikkerhetsrolle, kan alle brukere tilordnet denne rollen se læringsforløpinnholdet, selv om de er tilordnet en sikkerhetsrolle med høyere prioritet som ikke er knyttet til læringsforløpinnholdet.  

 Hver rolle som er inkludert i læringsforløp, har en numerisk verdi. Den første rollen i listen har høyest prioritet, og etterfølgende roller har lavere prioritet. Når en bruker er tilordnet en rolle som utløser visningen av læringsforløpinnhold, vil brukeren se dette innholdet selv om brukeren har vært tilordnet en rolle med lavere prioritet som ikke er knyttet til innholdet. For eksempel, hvis en bruker er tilordnet en rolle med prioritet 1 og en rolle med prioritet 20, vil brukeren se læringsforløpinnhold som bare er definert for rollen med prioritet 1.  

 Hvis du oppretter forskjellig innhold for ulike roller på samme [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-side eller skjerm, vil brukerne se innholdet som er forbundet med rollen med høyere prioritet.  

<a name="ManageRoles"></a>   
### <a name="manage-security-roles-and-precedence"></a>Behandle sikkerhetsroller og prioritet  
 Du kan kontrollere hvilke sikkerhetsroller som er tilgjengelige, i utformingen for læringsforløp, og angi rekkefølgen på roller for å bestemme prioritet når læringsforløp kjører. Hvis en bruker har to roller, og det er forskjellig innhold som er publisert for en gitt kontekst for hver av disse rollene, vil brukeren se innholdet for rollen som vises høyere oppe på listen.  

<a name="ConfigureRoles"></a>   
#### <a name="configure-security-roles"></a>Konfigurere sikkerhetsroller  

1. Logg inn på [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] med en konto som har redigeringstillatelse for læringsforløp.  

2. Åpne **Innholdsbibliotek**.  

3. Velg **Konfigurasjon** øverst på skjermen.  

4. Hvis du vil synkronisere sikkerhetsrollene med [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-sikkerhetsrollene dine, velger du **Synkroniseringsroller**.  

5. Hvis du vil angi prioritetsrekkefølgen for rollene som brukes sammen med læringsforløp, bruker du pil opp eller pil ned for å flytte en rolle lenger opp eller lenger ned i listen.  

    Prioriteten bestemmes av rekkefølgen på rollene som er oppført på denne siden.  

6. Hvis du vil slette en rolle slik at den ikke brukes med læringsforløp, velger du **Slett** ved siden av rollen.  

   > [!NOTE]
   >  Dette sletter ikke rollen fra [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]. Det sletter rollen i utformingen av læringsforløp for å definere hvordan innhold vises for brukerne. Du kan alltid gjenopprette en skjult rolle ved å velge **Synkroniseringsroller**.  

7. Når du er ferdig med endringene, velger du **Lagre**.  

8. Velg **Tilbake** for å gå tilbake til i innholdsbiblioteket.  

<a name="MobileApp"></a>   
## <a name="create-learning-path-controls-for-includepn_dyn_365_tabletsincludespn-dyn-365-tabletsmd"></a>Opprette læringsforløpskontroller for [!INCLUDE[pn_dyn_365_tablets](../../includes/pn-dyn-365-tablets.md)]  
 Du kan opprette læringsforløpkontroller for [!INCLUDE[pn_dyn_365_tablets](../../includes/pn-dyn-365-tablets.md)] på samme måte som du oppretter kontroller for webklienten. For å gjøre dette må du bruke mobilappsimulatoren i en nettleser slik at du har tilgang til mobilgrensesnittet for festing av læringsforløpskontrollene. Denne simulatoren skal bare brukes for dette formålet.  


### <a name="display-the-mobile-app-interface-simulator-in-a-web-browser"></a>Vise simulator for mobilappgrensesnitt i en nettleser  

1. Logg på [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)].  

2. Kopier servernavnet for [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-organisasjonen fra URL-adressen som vises i nettleseren, for eksempel *<https://contososales.crm.dynamics.com/>*.  

    Sørg for å inkludere skråstrek (/) etter. com.  

3. Finn det unike navnet for organisasjonen (også kalt forekomst) du vil opprette læringsforløpskontroller for. Du kan hente det unike navnet ved å velge **Innstillinger** > **Tilpassinger** på områdekartet, og deretter klikke **Ressurser for utviklere** på **Tilpassing**-siden. Kopier verdien for feltet **Unikt navn** som vises i delen **Forekomstreferanse**.  

   ![Dynamics-organisasjonsnavn som vises i brukerinformasjonsruten](media/lp-org-name.png "Dynamics-organisasjonsnavn som vises i brukerinformasjonsruten")  

4. Legg følgende til den første delen av URL-adressen for organisasjonen din, og erstatt \<organisasjonsnavn> med det unike navnet for organisasjonen som er fastsatt i forrige trinn:  

    nga/main.htm?org=*\<organisasjonsnavn>*  

    URL-adressen skal ligne på følgende: https://contososales.crm.dynamics.com/nga/main.htm?org=orgb557e46a  

5. Legg til følgende i URL-adressen fra det forrige trinnet, og bytt ut \<servernavn> med servernavnet fra det første trinnet i denne fremgangsmåten:  

    &server=*\<servernavn>*  

    URL-adressen skal ligne på følgende: https://contososales.crm.dynamics.com/nga/main.htm?org=orgb557e46a&server=https://contososales.crm.dynamics.com/.  

6. Åpne en ny kategori eller nettleservindu, og kopier den fullstendige URL-adressen du opprettet. Lim den inn i en ny kategori eller nettleservindu, og velg deretter Enter.  

    Første gang du kobler til mobilappgrensesnittet, vises en velkomstskjerm mens systemet behandler metadata og laster ned tilpassinger. Når dette er fullført, vises arbeidsområdet.  

   > [!NOTE]
   >  Når du kobler til mobilappversjonen av grensesnittet, brukes legitimasjonen fra påloggingen til web-grensesnittet til å godkjenne deg. Du må la webgrensesnittet være åpent for å unngå tilgangsfeil ved åpning av mobilappgrensesnittet.  

7. Lukk arbeidsområdet for å vise hjemmesiden for mobilappgrensesnittet i webleseren. Du kan deretter åpne innholdsbiblioteket for å opprette eller redigere læringsforløpskontroller. Du finner mer informasjon i [Innholdsbibliotek](#ContentLibrary)  


<a name="ContentLibrary"></a>   
## <a name="content-library"></a>Innholdsbibliotek  
 Innholdsbiblioteket viser alt innhold som er opprettet og tilgjengelig for organisasjonen, i tillegg til kommandoer for å opprette, behandle og samhandle med kontroller. Når du skal opprette eller redigere læringsforløpskontroller, kobler du først til klientgrensesnittet som du vil opprette kontroller for, og åpne deretter innholdsbiblioteket.  

**Hvis du vil åpne innholdsbiblioteket fra standardgrensesnitt til webklienten, gjør du ett av følgende:**  

-   På en sidestolpe velger du knappen **Innholdsbibliotek**.  

     ![Ikonet for Innholdsbiblioteket som vises på et læringsforløp](media/lp-sidebar-cl-icon.png "Ikonet for Innholdsbiblioteket som vises på et læringsforløp")  

-   Velg flisen **opplæring** i områdekartet, og velg deretter **Innholdsbibliotek**.  

     ![Innholdsbibliotek-ikonet på områdekartet til Dynamics 365 for Customer Engagement](media/lp-sitemap-content-library.png "Innholdsbibliotek-ikonet på områdekartet til Dynamics 365 for Customer Engagement")  

**Åpne innholdsbiblioteket fra simulatoren for mobilappgrensesnitt:**  

1.  Velg ellipsen i en sirkel (...) nederst til høyre på skjermen.  

    ![Ellipser-knappen for å vise Læringsforløp-ikoner](media/lp-cl-ellipses.png "Ellipser-knappen for å vise Læringsforløp-ikoner")  

2.  Velg **Innholdsbibliotek for læringsforløp**.  

    ![Læringsforløp-knapper som vises i grensesnittet for mobilapp](media/lp-mobile-lp-button.png "Læringsforløp-knapper som vises i grensesnittet for mobilapp")  



> [!NOTE]
>  Hvis du ikke ser alle disse kolonnene i innholdsbiblioteket, kan det være fordi leserens Vis zoom er satt til mer enn 100 %. Hvis du vil se alle kolonnene, kan du sette zoom-innstillingen til 100 % eller lavere.  

 Innholdsbiblioteket inneholder kolonnene som er beskrevet i følgende tabell:  

|Kolonne|Beskrivelse|  
|------------|-----------------|  
|**Navn**|Navnet du brukte da du opprettet den veiledede oppgaven eller sidestolpen. Et rødt låsesymbol ved siden av navnet indikerer at innholdet er sjekket ut. Du kan holde markøren over ikonet for å se hvilken bruker som har innholdet sjekket ut.<br /><br /> ![Rød hengelås-ikon angir at innhold er sjekket ut.](media/lp-cl-checked-out.png "Rød hengelås-ikon angir at innhold er sjekket ut.")<br /><br /> En rød stjerne ved siden av navnet angir nylig innsjekket innhold.<br /><br /> ![Rød stjerne som angir nylig innsjekket innhold](media/lp-cl-new-check-in.png "Rød stjerne som angir nylig innsjekket innhold")|  
|**Tittel**|Tittelen du angav da du la til innhold i den veiledede oppgaven eller sidestolpen. Titler for sidestolper og veiledede oppgaver vises på sidestolper når de er lagt til som koblinger, eller når de er returnert som søkeresultater.|  
|**Type**|Et symbol som angir typen innhold: Sidestolpe eller veiledet oppgave|  
|**Skjemafaktor**|Symboler som representerer formfaktoren som ble valgt for dette innholdet da det ble opprettet, enten **Skrivebord** eller **Nettbrett**.<br /><br /> Kolonnen **Formfaktor** vises ikke når du bruker innholdsbiblioteket mens du er koblet til simulatoren for mobilappgrensesnitt eller Interaktiv servicehub.|  
|**Merker**|Viser alle koder som brukes i dette innholdet. Du kan legge til koder i dialogboksen **Avanserte alternativer**. Bruk koder til å filtrere innhold som vises i biblioteket.|  
|**Programversjon**|Versjonen av programmet som kontrollen ble opprettet på.|  
|**Forfatter**|Navnet på personen som opprettet kontrollen.|  
|**Språk**|En numerisk verdi som representerer antall språk som kontrollen er lokalisert til.<br /><br /> Denne kolonnen|  
|**Status**|Viser **Publisert** hvis innholdet for øyeblikket er publisert. Ellers er statusen **Utkast**.|  
|**Aktivert**|Viser om innholdet er aktivert eller deaktivert.  Bare aktivert innhold vises for brukerne.|  
|**Sist publisert**|Den siste datoen som innholdet ble publisert på.|  

<a name="ContentTypes"></a>   
## <a name="learning-path-content-types-guided-tasks-and-sidebars"></a>Innholdstyper for læringsforløp: Veiledede oppgaver og sidestolper  
 Du kan opprette to typer innhold i læringsforløp: Veiledede oppgaver og sidestolper.  

<a name="GT"></a>   
### <a name="guided-tasks"></a>Veiledede oppgaver  
 En veiledet oppgave er vanligvis en serie med trinn, men det kan også være et enkelt trinn. En bruker kan starte en veiledet oppgave ved å velge en kobling på en sidestolpe, ved å navigere til en side eller ved å velge en kobling på en side som du har opprettet innhold for. I hvert trinn velger brukeren **Neste**-knappen eller fullfører en definert handling for å fortsette til neste trinn, eller for å fullføre den veiledede oppgaven.  

 Veiledede oppgaver er nyttige for å hjelpe dine brukere gjennom vanlige eller nye oppgaver. De kan også brukes for å sikre at oppgaver utføres konsekvent i organisasjonen, eller at dataene angis på en bestemt måte i tråd med organisasjonens prosesser eller arbeidsflyt. Du kan inkludere koblinger, videoer og annen informasjon i veiledede oppgaver for å hjelpe brukerne med å bli kjent med og lære mer om den delen av brukergrensesnittet som trinnet refererer til.  

<a name="Sidebar"></a>   
### <a name="sidebars"></a>Sidestolper  
 En sidestolpe vises når en bruker velger Hjelp-knappen, navigerer til en side, eller velger en kobling eller knapp på en side som du har opprettet innhold for. Du kan også opprette Hjem-sidestolper som vises når brukeren åpner siden eller skjermen, eller velger Hjem-ikonet på en sidestolpe.  

 ![Hjem-ikon på en sidestolpe](media/sidebar-home.png "Hjem-ikon på en sidestolpe")  

 Du kan også definere Feil-sidestolper som vises når det er et problem med å vise den tiltenkte sidestolpen. Du kan inkludere koblinger, videoer og annen informasjon i sidestolper for å hjelpe brukerne med å bli kjent med og lære mer om siden eller skjemaet som vises, eller handlinger de kan utføre på siden eller skjemaet.  

<a name="CreateGT"></a>   
## <a name="create-a-guided-task"></a>Opprette en veiledet oppgave  

 Det er to trinn for å opprette en veiledet oppgave:  

1.  Definer hvordan oppgaven utløses, og tilordne rollene som innholdet gjelder for.  

2.  Bruk flytredigering for å legge til trinn som brukerne ser når de går gjennom den veiledede oppgaven.  

### <a name="define-the-triggers-and-roles"></a>Definere utløsere og roller  

1. Gå til siden du vil opprette en veiledet oppgave for.  

2. Åpne Innholdsbibliotek. Se [Innholdsbibliotek](#ContentLibrary) for å lære hvordan du gjør dette.  

3. I innholdsbiblioteket velger du **Veiledet oppgave**.  

    ![Kobling for å opprette en ny veiledet oppgave i innholdsbiblioteket for læringsforløp](media/lp-content-library-gt.png "Kobling for å opprette en ny veiledet oppgave i innholdsbiblioteket for læringsforløp")  

4. Angi et navn, og velg andre innstillinger for den veiledede oppgaven. Bruk denne tabellen for referanse.  


   |              Innstilling               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Beskrivelse                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
   |------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |    **Deaktiver denne veiledede oppgaven**    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          Merk av for å deaktivere den veiledede oppgaven. Når deaktivert, vil den ikke vises for brukerne.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
   | **Angi som feil veiledet oppgave** |                                                                                                                                                                                                                                                                                                                                                                                                                       Merk av her hvis du vil vise denne veiledede oppgaven bare når det er en feil med andre veiledede oppgaver, for eksempel mangel på rettigheter eller et problem som forhindrer at andre veiledede oppgaver tilknyttet siden vises.                                                                                                                                                                                                                                                                                                                                                                                                                       |
   |              **Navn**              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        Navnet på den veiledede oppgaven som vises i innholdsbiblioteket.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   |             **Klient**             |                                                                                                                                                                               Klientverdien angis automatisk for plattformen der du lager innhold. **Advarsel!**  Hvis du redigerer en eksisterende kontroll når du er koblet til et annet grensesnitt enn den som kontrollen ble opprettet på, oppdateres klientinnstillingen til den gjeldende klienttypen. Dette fører til at kontrollen brytes slik at den ikke virker på klienten som du opprinnelig opprettet kontrollen for. <br /><br /> Hvis du oppretter kontroller for webgrensesnittet, vises **Webklient**.<br /><br /> Hvis du er koblet til simulatoren for mobilappgrensesnitt, vises **Mobilapper**.<br /><br /> Hvis du er koblet til den interaktive servicehuben, vises **Interaktiv servicehub**.                                                                                                                                                                               |
   |          **Formfaktor**           |                                                                                                                                                                       Formfaktoren som vises, avhenger av grensesnittet som du lager innhold for. Hvis du bruker webgrensesnittet for klienten, vises **Skrivebord** og **Nettbrett**. Når valgt for webklienten, refererer **Nettbrett** til weblesere som kjører på nettbrettenheter, ikke mobilappen.<br /><br /> Hvis du oppretter kontroller for mobilappgrensesnittet, vises **Nettbrett**. Dette refererer til enheter som kjører på [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-mobilappen, men støttes bare på nettbrett.<br /><br /> Hvis du bruker den interaktive servicehuben, vises **Skrivebord**. **Viktig!**  Læringsforløp støttes ikke i [!INCLUDE[pn_crm_shortest](../../includes/pn-dyn-365-phones.md)].                                                                                                                                                                        |
   |     **Veiledet oppgave åpnes når**     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                              Velg om du vil at den veiledede oppgaven skal vises når **siden lastes inn**, eller når en bruker **klikker en kobling** på en sidestolpe.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
   |        **Livssyklusfase**         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        Denne innstillingen er bare for internt bruk.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
   |   **Sikkerhetsrolle for Dynamics 365 for Customer Engagement-apper**   |                                                                                                                                                                                                                                                                                                                                                                                                  Velg sikkerhetsrollen(e) som du vil at den veiledede oppgaven skal vises for. Du kan velge så mange roller du vil. Hvis en bruker er tilordnet mer enn én rolle, vises den veiledede oppgaven bare for rollen med høyest prioritet, som beskrevet tidligere i dette emnet.                                                                                                                                                                                                                                                                                                                                                                                                   |
   |             **Status**             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                Viser statusen for veiledet oppgave. Statusen vil være **Utkast** før du publiserer den.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
   |        **Avanserte alternativer**        | Dette alternativet er tilgjengelig når du har lagret den veiledede oppgaven. Følgende innstillinger er tilgjengelige under **Avanserte alternativer**:<ul><li>**Feil ved veiledet oppgave**: Merk av for dette alternativet hvis du vil vise denne veiledende oppgaven bare når det er en feil med andre veiledende oppgaver.</li><li>**Støttede språk**: Velg språkene for denne veiledede oppgaven, og for import og eksport.</li><li>**Forfatter**: Endre forfatteren som er definert for denne veiledede oppgaven.</li><li>**Koder**: Legg til eller fjern koder som brukes i denne veiledede oppgaven. Bruk koder til å gjøre det enklere å søke etter innhold i innholdsbiblioteket, eller til å kategorisere innhold.</li></ul><br />Du kan også angi følgende under **Publiser informasjon**:<ul><li>**Programversjon**: Angi [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-versjonen som er knyttet til innholdet.</li><li>**Versjon**: Angi versjonen for innholdet du oppretter.</li><li>**Godkjenningsgruppe**: Angi godkjenningsgruppen for innholdet du oppretter.</li><li>**Publiseringsgrupper**: Velg publiseringsgruppen(e) for dette innholdet.</li></ul> |


5. Når du er ferdig, velger du **Lagre** for å bruke flytredigeringen,  

### <a name="add-steps-with-the-flow-editor"></a>Legge til trinn med flytredigering  

1. Legg til tittelen der *Tittel på veiledet oppgave* vises. Dette er tittelen som brukerne vil se.  

2. Velg om du bare vil vise faste ID-kontroller. Registrerte kontroller er angitt med grønt, og uregistrerte kontroller er angitt med blått når du drar flisen for å feste den til brukergrensesnittet. Hvis du fester et trinn til en kontroll som ikke har en fast ID, kan det påvirkes av en fremtidig oppdatering av [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]. Oppdateringer vil ikke påvirke faste ID-kontroller.  

3. Velg **Legg til nytt trinn**, og velg deretter typen trinn du vil bruke for det første trinnet i den veiledede oppgaven.  

   |Knapptype|Beskrivelse|  
   |-----------------|-----------------|  
   |**Trinn med Neste-knapp**|Dette trinnet har en Neste-knapp som kan brukes til å gå til neste trinn i flyten. Hvis dette er det siste trinnet i flyten, vises ikke Neste-knappen. Dra flisen for å feste trinnet der du vil at det skal vises i appen.|  
   |**Trinn med brukerhandling**|Dette trinnet har ikke en Neste-knapp. Brukeren blir bedt om å velge grensesnittelementet som trinnet er festet til. Hvis det oppstår en omadressering eller endring i grensesnittilstanden som et resultat av dette valget, pass på å feste det neste trinnet på den endrede grensesnittilstanden. Dra flisen for å feste trinnet der du vil at det skal vises i appen.<br /><br /> Fest denne typen trinn til en kontroll som kan velges i brukergrensesnittet, for eksempel en knapp eller kobling.|  
   |**Brukerhandling med Neste-knapp**|Dette trinnet har ikke en Neste-knapp. Å velge Neste-knappen har samme virkning som å velge grensesnittelementet som trinnet er festet til. Hvis det oppstår en omadressering eller endring i grensesnittilstanden som et resultat av dette valget, pass på å feste det neste trinnet på den endrede grensesnittilstanden. Dra flisen for å feste trinnet der du vil at det skal vises i appen.|  
   |**Læringstrinn**|Dette trinnet har en knapp som kan tilpasses, som avslutningshandling Dette trinnet kan bare være plassert på slutten av en veiledet oppgaveflyt. Du kan bruke det til å koble til en Læringsforløp-sidestolpe. Dra flisen for å feste trinnet der du vil at det skal vises i appen.|  

   > [!NOTE]
   >  Hvis du allerede har planlagt den veiledede oppgaven og vet hvilke trinn du vil legge til, kan du legge til alle nå. Hvert trinn som du legger til, vises i flytredigeringen i rekkefølgen den legges til. Du kan endre rekkefølgen på trinnene ved å dra dem opp eller ned i listen.  

4. Velg typen trinn som du vil legge til, og dra deretter flisen til i brukergrensesnittet for å feste den til en kontroll. Du må kanskje prøve noen ganger før du blir vant til å plassere trinnet der du vil.  

   > [!NOTE]
   >  Du kan holde flisen i opptil 15 sekunder. Hvis du ikke fester den innen 15 sekunder, blir flisen ufestet og musepekeren endres tilbake til vanlig markør.  

   ![Veiledet flytredigering](media/lp-gt-flow-editor.png "Veiledet flytredigering")  

5. Når du har plassert trinnet der du vil ha den, slipper du museknappen for å feste den til kontrollen. Trinnet vises på plasseringen du valgte. Hvis du vil flytte trinnet, bruker du **Dra meg**-knappen på panelet ved siden av trinnet.  

   ![Dra meg-ikon på en ledet veiledet oppgaveboble](media/lp-gt-bubble-drag-me.png "Dra meg-ikon på en ledet veiledet oppgaveboble")  

6. Legg til innhold i trinnet ved hjelp av kontrollene som vises ved siden av den. Følgende innstillinger er tilgjengelige:  

   - **Innholdstype**: Legg til tekst eller en video i trinnet. Velg **Rediger** for å se flere innstillinger. Du kan endre skriftstørrelse, farge og stil for teksten, og legge til et miniatyrbilde for video.  

   - **Plassering**: Angi plasseringen av trinnet på kontrollen du har festet det til. Valg inkluderer: Plasser automatisk (merket som standard), Øverst til venstre, Øverst til høyre, Nederst til venstre, Nederst til høyre, Til venstre øverst, Til venstre nederst, Til høyre øverst og Til høyre nederst.  

   - **Kopi**: Opprett en kopi av trinnet med identisk innhold festet til samme sted, og sett det inn i den veiledede oppgaveflyten rett etter det opprinnelige trinnet.  

7. Velg **Lagre** når du er ferdig med å plassere og legge til innhold i trinnet, og lukk deretter trinnet ved hjelp av Lukk-knappen i øvre høyre hjørne på trinnet, eller velg pilen i hjørnet øverst til venstre på skjermen for å gå tilbake til flytredigeringen.  

   > [!NOTE]
   >  Du kan alltid redigere trinnet senere, så ikke bekymre deg hvis du ved et uhell lukker det før det er akkurat slik du ønsker.  

8. Hvis du vil legge til eller redigere det neste trinnet i den veiledede oppgaven, velger du høyrepilen ![Vinkeltegn-ikon for å gå tilbake til flytredigering](media/lp-chevron.png "Vinkeltegn-ikon for å gå tilbake til flytredigering") øverst til venstre på skjermen for å vise flytredigeringen.  

9. Legg til ytterligere trinn du vil ta med i den veiledede oppgaven, og pass på å lagre hvert trinn når du er ferdig med å legge til innhold.  

    > [!NOTE]
    >  Hvis du flytter et trinn eller kopierer det ved hjelp av **Kopier**-knappen på verktøylinjen, vil ulagrede endringer i trinnet gå tapt. Husk å lagre endringene ofte.  

10. Når du er ferdig med å legge til trinn i veiledende oppgaven, velger du **Lagre**.  

11. Velg **Forhåndsvisning** for å teste den veiledede oppgaven og se hvordan den vil se ut for brukerne.  

    > [!NOTE]
    >  Hvis du vil publisere den veiledede oppgaven, må du forhåndsvise den først. Når du lukker et trinn eller bruker pilen i hjørnet øverst til venstre på skjermen i forhåndsvisningsmodus, ser du knappene **Sjekk inn** og **Publiser** i utformingen av læringsforløp.  

12. Hvis du er fornøyd med endringene, sjekker du dem inn og publiserer den veiledede oppgaven, eller publiserer den senere fra innholdsbiblioteket.  

<a name="CreateSidebar"></a>   
## <a name="create-a-sidebar"></a>Opprette en sidestolpe  

 Det er to trinn for å opprette en sidestolpe:  

1.  Angi egenskapene for Sidestolpe og tilordne rollene der de gjelder.  

2.  Legg til innhold i Sidestolpe (tekst, bilder, koblinger og knapper).  

### <a name="set-the-sidebar-properties-and-roles"></a>Angi egenskaper for sidestolpe og roller  

1. Gå til siden du vil opprette en sidestolpe for.  

2. Åpne Innholdsbibliotek. Se [Innholdsbibliotek](#ContentLibrary) for å lære hvordan du gjør dette.  

3. I innholdsbiblioteket velger du **Sidestolpe**.  

   ![Kobling for å opprette en ny sidestolpe i innholdsbiblioteket for læringsforløp](media/lp-content-library-sb.png "Kobling for å opprette en ny sidestolpe i innholdsbiblioteket for læringsforløp")  

4. Angi et navn og velg deretter andre innstillinger for sidestolpen. Bruk denne tabellen for referanse.  


   |             Innstilling             |                                                                                                                                                                                                                                                                                                                                                        Beskrivelse                                                                                                                                                                                                                                                                                                                                                        |
   |---------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           **Deaktiver**           |                                                                                                                                                                                                                                                                                                                                       Merk av her for å deaktivere sidestolpen.                                                                                                                                                                                                                                                                                                                                       |
   | **Angi som feil sidestolpe**  |                                                                                                                                                                                                                                         Merk av her hvis du vil vise denne sidestolpen bare når det er en feil med andre sidestolper, for eksempel mangel på rettigheter eller andre problemer som forhindrer at andre sidestolper tilknyttet siden vises.                                                                                                                                                                                                                                          |
   |   **Gjør dette til hjem-sidestolpe**    |                                                                                                                                                                                                                                                                         Hjem-sidestolpen vises når brukeren velger Hjem-knappen, eller hvis det er ikke er en sidestolpe på siden, og brukeren velger Hjelp. Hver side kan bare ha én Hjem-sidestolpe.                                                                                                                                                                                                                                                                         |
   |            **Navn**             |                                                                                                                                                                                                                                                                                                                                    Navnet som vises i innholdsbiblioteket.                                                                                                                                                                                                                                                                                                                                     |
   |           **Klient**            | Klientverdien angis automatisk for plattformen der du lager innhold. **Advarsel!**  Hvis du redigerer en eksisterende kontroll når du er koblet til et annet grensesnitt enn den som kontrollen ble opprettet på, oppdateres klientinnstillingen til den gjeldende klienttypen. Dette fører til at kontrollen brytes slik at den ikke virker på klienten som du opprinnelig opprettet kontrollen for. <br /><br /> Hvis du oppretter kontroller for webgrensesnittet, vises **Webklient**.<br /><br /> Hvis du er koblet til simulatoren for mobilappgrensesnitt, vises **Mobilapper**.<br /><br /> Hvis du er koblet til den interaktive servicehuben, vises **Interaktiv servicehub**. |
   |         **Formfaktor**         |                                                  Formfaktoren som vises, avhenger av grensesnittet som du lager innhold for. Hvis du bruker webgrensesnittet for klienten, vises **Skrivebord** og **Nettbrett**. Når valgt for webklienten, refererer **Nettbrett** til weblesere som kjører på nettbrettenheter, ikke mobilappen.<br /><br /> Hvis du oppretter kontroller for mobilappgrensesnittet, vises **Nettbrett**. Dette refererer til enheter som kjører på [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-mobilappen, men støttes bare på nettbrett.<br /><br /> Hvis du bruker den interaktive servicehuben, vises **Skrivebord**.                                                  |
   |     **Sidestolpe åpnes når**      |                                                                                                                                                                                                                                                                                               Velg om du vil at sidestolpen skal vises når siden lastes inn, eller når en bruker velger en kobling eller knapp på siden.                                                                                                                                                                                                                                                                                               |
   |       **Livssyklusfase**       |                                                                                                                                                                                                                                                                                                                                              Dette er bare for internt bruk.                                                                                                                                                                                                                                                                                                                                               |
   | **Sikkerhetsrolle for Dynamics 365 for Customer Engagement-apper** |                                                                                                                                                                                                                  Velg rollen eller rollene som du vil at sidestolpen skal vises for brukerne for. Du kan velge så mange roller du vil. Hvis en bruker er tilordnet mer enn én rolle, vises sidestolpen bare for rollen med høyest prioritet, som beskrevet tidligere i dette emnet.                                                                                                                                                                                                                   |
   |          **Mal**           |                                                                                                                                                                                                                                                                                       Velg malen du vil bruke for den nye sidestolpen, enten **Én kolonne** eller **To kolonner**. Standardmalen er en sidestolpe med én kolonne.                                                                                                                                                                                                                                                                                        |
   |           **Status**            |                                                                                                                                                                                                                                                                                                              Viser statusen for sidestolpen. Statusen vil være **Utkast** før du publiserer sidestolpen.                                                                                                                                                                                                                                                                                                              |
   |      **Avanserte alternativer**       |                                                                         Dette alternativet er ikke tilgjengelig før du lagrer sidestolpen. Følgende innstillinger under **Avanserte alternativer** er tilgjengelige:<ul><li>**Deaktiver topptekst i sidestolpe**</li><li>**Deaktiver tittel på sidestolpe**</li><li>**Deaktiver bunntekst i sidestolpe**</li><li>**Forfatter**: Endre forfatteren som er definert for sidestolpen.</li><li>**Koder**: Legg til eller fjern koder som brukes i sidestolpen. Bruk av koder kan gjøre det enklere å søke etter innhold i innholdsbiblioteket, eller å kategorisere innholdet.</li><li>**Støttede språk**: Velg språkene for denne sidestolpen, og for import og eksport.</li></ul>                                                                         |


5. Når du er ferdig, velger du **Lagre** for å begynne å legge til innhold i sidestolpen i utformingen.  

<a name="SidebarContent"></a>   

### <a name="add-content-to-your-sidebar"></a>Legge til innhold i sidestolpen  

1.  Når du lagrer sidestolpenavnet og -egenskapene i innholdsbiblioteket, åpnes utformingen.  

2.  Angi en tittel for sidestolpen.  

3.  Legg til innholdet som du vil vise for brukerne når sidestolpen vises.  

4.  Hvis du vil legge til en ny inndeling, velger du **Legg til inndeling**.  

5.  Hvis du vil fjerne en inndeling fra malen, merker du inndelingen du vil slette, og velger deretter **Slett**.  

6.  Når du er ferdig med å endre innholdet i sidestolpen, velger du **Lagre** for å lagre endringene, og lukker deretter sidestolpen ved å velge **Lukk** øverst i høyre hjørne for å gå tilbake til innholdsbiblioteket.  

7.  Velg **Administrer** øverst på siden, og velg deretter **Sjekk inn** for å lagre endringene og gjøre dem tilgjengelige for andre brukere som oppretter innhold.  

### <a name="add-links-to-your-sidebar"></a>Legge til koblinger i sidestolpen  
 Når du oppretter en sidestolpe, er det flere alternativer for å legge til koblinger i den. Du kan opprette en kobling til en annen veiledet oppgave eller sidestolpe i læringsforløp til en annen side i [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] eller til en webside. Du kan også søke etter hjelp- og opplæringsemner du kan koble til når du oppretter en sidestolpe. Når du har angitt egenskaper og roller for sidestolpe og er klar til å legge til innhold, kan du følge disse trinnene for å legge til koblinger i en del av sidestolpen du opprettet.  

1. I delen du vil legge koblinger til, velger du ikonet **Liste over koblinger**.  

   ![Liste over koblinger-ikonet som er valgt på en sidestolpe for læringsforløp](media/lp-sidebar-links.png "Liste over koblinger-ikonet som er valgt på en sidestolpe for læringsforløp")  

2. Legg til en inndelingstittel, og velg deretter **+ Legg til kobling**.  

   ![Legg til kobling-boks uthevet i en del av en sidestolpe for læringsforløp](media/lp-sidebar-addlink.png "Legg til kobling-boks uthevet i en del av en sidestolpe for læringsforløp")  

3. Velg typen kobling du vil legge til, og velg deretter **Neste**. Du kan velge mellom følgende alternativer:  

   - **Veiledet oppgave**: Oppretter en kobling til en eksisterende veiledet oppgave i læringsforløp. Dette kan være nyttig for å gi informasjon om en oppgave i sidestolpen, og deretter koble til en veiledet oppgave som leder en bruker gjennom oppgaven i [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-grensesnittet.  

   - **Sidestolpe**: Opprett en kobling til en eksisterende sidestolpe for læringsforløp. Du kan bruke en kobling til en sidestolpe for å  

   - **Side i app**  

   - **Nettside**  

<a name="Videos"></a>   
## <a name="use-videos-in-your-learning-path-controls"></a>Bruke videoer i læringsforløpskontroller  
 Bare videoer på YouTube støttes i læringsforløpskontroller. Hvis du planlegger å bruke videoer i læringsforløpskontroller, må du ha en YouTube-konto og en kanal å laste opp videoer til. Du kan ikke koble til videoer på en kanal som er satt til privat, men du kan koble til videoer hvis kanalen er satt til offentlig eller ikke oppført. Du kan også sette opp din egen kanal slik at flere personer kan administrere videoinnholdet for organisasjonen.  

 Når du legger til videoer i kontrollene, kan du bygge inn videoen i kontrollen. Hvis du vil at brukerne skal vise videoene i en ny kategori eller nettleservindu, kan du legge til en tekstdel i sidestolpen, og deretter legge til en kobling til videoen i tekstdelen.  

 Når du bygger inn videoer som vises i en sidestolpe eller veiledet oppgave, bruker du koblingen som du får fra YouTube. Læringsforløp oppdaterer automatisk koblingen for å bygge inn videoen og endrer størrelse slik at den passer i Sidestolpe- eller Veiledet oppgave-flisen. Brukeren kan velge **Full skjerm** for å vise videoen i fullskjermmodus. Hvis en bruker stopper avspillingen, eller når avspillingen er fullført, kan YouTube automatisk vise koblinger til andre videoer som brukeren kan være interessert i. Du kan forhindre at dette skjer ved å endre koblingen i kontrollen til å inkludere **?rel=0** på slutten.  

 Når du for eksempel har opprettet og lastet opp en video til kanalen, kopierer du URL-adressen for video levert av YouTube, som er **https://youtu.be/4TrYMB4pjyw**. Hvis du vil bygge inn denne videoen i en kontroll, kan du angi denne URL-adressen i feltet **Angi URL-adresse til video** for kontrollen.  

 Når du lagrer kontrollen, endrer Læringsforløp URL-adressen til **https://www.youtube.com/embed/4TrYMB4pjyw**. Hvis du vil slå av visningen av koblinger til andre videoer når videoen er midlertidig stanset eller fullført, redigerer du URL-adressen ved å tilføye **?rel=0** i slutten slik at URL-adressen ser omtrent slik ut: **https://www.youtube.com/embed/4TrYMB4pjyw?rel=0**.  

Mer informasjon om hvordan du bruker YouTube: [YouTube-hjelpesenter](https://go.microsoft.com/fwlink/?linkid=847120)  

<a name="PublishLP"></a>   
## <a name="publish-learning-path-content"></a>Publisere læringsforløpsinnhold  
 Brukerne vil bare se læringsforløpsinnhold du oppretter, når du har publisert det. Bare innhold som er sjekket inn, kan publiseres.  

1.  Åpne Innholdsbibliotek.  

2.  Merk av ved siden av hver veiledede oppgave og sidestolpe som du vil publisere. Kontroller at kontrollen du vil publisere, er sjekket inn.  

3.  Velg **Publiser** øverst på siden, og velg deretter **Publiser**.  

4.  På siden **Publiser kontroller** velger du publiseringsmiljøene du vil publisere innholdet til, og velger deretter **Publiser**.  

<a name="PublishingGroup"></a>   
### <a name="about-publishing-groups"></a>Publiseringsgrupper  
 Læringsforløpsinnhold publiseres til en publiseringsgruppe. Når du slår på læringsforløp for organisasjonen, opprettes en publiseringsgruppe med samme navn som organisasjonsnavnet. Du kan opprette flere publiseringsgrupper etter behov. Du kan legge til flere organisasjoner i en publiseringsgruppe, og en organisasjon kan være medlem av flere publiseringsgrupper slik at du kan tilpasse innhold og enkelt publisere det til ulike organisasjoner.  

<a name="CreatePG"></a>   
### <a name="create-a-publishing-group"></a>Opprette en publiseringsgruppe  

1.  Åpne Innholdsbibliotek.  

2.  Velg **Konfigurasjon** øverst på skjermen.  

3.  Velg **Publiseringskonfigurasjon**.  

4.  Velg **Ny side** på siden **Publiseringskonfigurasjon**.  

5.  Angi et navn og eventuelt en beskrivelse.  

6.  Velg organisasjonene du vil ta med i publiseringsgruppen. Du ser bare organisasjoner som du har tillatelser for.  

7.  Velg **Lagre** og deretter **OK**.  

<a name="ExportandImport"></a>   
## <a name="export-and-import-learning-path-content"></a>Eksportere og importere læringsforløpsinnhold  
 Du kan eksportere innhold som du oppretter, kanskje for å dele med en forfatter i en annen organisasjon, eller for å lage sikkerhetskopier. Eksportfunksjonen oppretter en komprimert ZIP-fil som inneholder .json-filene som brukes for innholdet i læringsforløp. Det vil være en mappe i ZIP-filen for hver valgte sidestolpe eller veiledet oppgave i læringsforløp.  

<a name="ExportProc"></a>   
### <a name="export-your-learning-path-content"></a>Eksportere læringsforløpsinnholdet  

1.  I innholdsbiblioteket merker du av ved siden av innholdet du vil eksportere.  

     Du kan eksportere innhold uten å sjekke det inn.  

2.  Velg **Administrer** øverst på siden, og velg deretter **Eksporter**.  

3.  Velg alternativet du vil bruke for å lagre den genererte ZIP-filen, og velg deretter filnavn og plassering.  

    > [!NOTE]
    >  Standardfilnavnet for ZIP-filen er det samme hver gang du eksporterer, så du bør bruke et unikt navn for å unngå å overskrive filer som har blitt eksportert tidligere.  

### <a name="import-your-learning-path-content"></a>Importer Læringsforløpinnhold.  

1.  I innholdsbiblioteket, velger du **Administrer** og deretter **Importer**.  

2.  Velg **Bla gjennom** for å velge den tidligere eksporterte filen du vil importere, eller dra filen til **Dra kontroller hit** -boksen i dialogboksen.  

    > [!CAUTION]
    >  Når du importerer en kontroll, vil den overskrive og erstatte alle versjoner av den samme kontrollen som allerede finnes i biblioteket, selv om den eksisterende kontrollen er nyere.  

3.  Kontroller at filnavnet som vises er filen du vil importere, og velg deretter **Importer**.  

4.  Velg **OK** i bekreftelsesdialogboksen.  

<a name="Localize"></a>   
## <a name="localize-learning-path-controls"></a>Lokaliser læringsforløpskontroller  
 Du kan lokalisere innholdet i kontrollene som du oppretter i Læringsforløpet slik at de vises til brukere i språket de har valgt i [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]. Hvis du vil lokalisere kontrollene, kan du ganske enkelt eksportere dem, lokalisere strengene som vises til brukere og deretter importere kontrollen som inneholder lokalisert innhold. Du kan importere kontrollen til samme organisasjon eller til en annen organisasjon. Du kan lokalisere den samme kontrollen til flere språk og deretter importere bestemte språk til bestemte organisasjoner som støtter brukere som har dette språket valgt. Støtte for lokalisering i Læringsforløp følger OASIS XML 2.0-standarden for XLIFF (XML Localisation Interchange File Format). Det finnes verktøy og opplæringsprogrammer fritt tilgjengelig for å arbeide med dette fellesformatet. Hvis du vil ha mer informasjon, kan du se [XLIFF versjon 2.0](http://docs.oasis-open.org/xliff/xliff-core/v2.0/os/xliff-core-v2.0-os.html)  

 Mer informasjon om språkinnstillinger for bruker i [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]: [Angi personlige alternativer](/dynamics365/customer-engagement/basics/set-personal-options)  

1.  Velg kontrollen du vil lokalisere i innholdsbiblioteket.  

2.  Velg **Lokaliser**, og velg deretter **Eksporter**.  

    ![Eksportknapp på menyen lokalisering av læringsforløp](media/lp-localize-export.png "Eksportknapp på menyen lokalisering av læringsforløp")  

3.  Velg alternativet du vil bruke for å lagre den genererte ZIP-filen, og velg deretter filnavn og plassering.  

    > [!NOTE]
    >  Standardfilnavnet for ZIP-filen er det samme hver gang du eksporterer, så du bør bruke et unikt navn for å unngå å overskrive filer som har blitt eksportert tidligere.  

4.  Når du har lokalisert innhold i innholdsbiblioteket, velger du **Lokaliser** og deretter **Importer**.  

5.  Velg **Bla gjennom** for å velge den tidligere eksporterte filen du vil importere, eller dra filen til **Dra kontroller hit** -boksen i dialogboksen.  

    > [!CAUTION]
    >  Når du importerer en kontroll, vil den overskrive og erstatte alle versjoner av den samme kontrollen som allerede finnes i biblioteket, selv om den eksisterende kontrollen er nyere.  

6.  Kontroller at filnavnet som vises er filen du vil importere, og velg deretter **Importer**.  

7.  Velg **OK** i bekreftelsesdialogboksen.  

8.  Publiser den lokalisert kontrollen til ønskede publiseringsmiljøer, slik at den lokaliserte kontrollen blir tilgjengelig for brukerne. Lokalisert innhold vises automatisk for brukere som har valgt det samme språket for brukergrensesnittet.  



## <a name="includepn_crm_shortestincludespn-crm-shortestmd-apps-data-center-mapping-to-includepn-azure-shortestincludespn-azure-shortestmd-regions"></a>[!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-appdatasentertilordning til [!INCLUDE[pn-azure-shortest](../../includes/pn-azure-shortest.md)]-områder
Følgende tabell viser regionene i [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-appdatasenteret og tilsvarende [!INCLUDE[pn-azure-shortest](../../includes/pn-azure-shortest.md)]-områder der læringsforløp vil være tilgjengelig fra.


| [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)]-datasenter | [!INCLUDE[pn-azure-shortest](../../includes/pn-azure-shortest.md)]-region |
|------------------------------------------------------------------------|------------------------------------------------------------------------|
|                          Asia/Stillehavskysten (APAC)                           |                               Øst-Asia                                |
|                              Canada (CAN)                              |                             Midt-Canada                             |
|       Europa, Midt-Østen, Afrika og Storbritannia (EMEA, GBR)       |                              Vest-Europa                               |
|                              India (IND)                               |                             Sentrale India                              |
|                              Japan (JPN)                               |                               Japan – øst                               |
|                          Nord-Amerika (NAM)                           |                                USA Øst                                 |
|                             Oseania (OCE)                              |                             Øst i Australia                             |
|                          Sør-Amerika (SAM)                           |                              Sør i Brasil                              |

## <a name="privacy-notice"></a>Personvernerklæring  
[!INCLUDE[cc_privacy_learning_path_authoring](../../includes/cc-privacy-learning-path-authoring.md)]

### <a name="see-also"></a>Se også  
 [På/av-bryter for læringsforløp (veiledningshjelp)](/dynamics365/customer-engagement/admin/on-off-switch-for-learning-path-guided-help)
