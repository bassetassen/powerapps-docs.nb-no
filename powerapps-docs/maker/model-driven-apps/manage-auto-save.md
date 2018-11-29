---
title: Deaktivere automatisk lagring i en modelldrevet app med PowerApps | MicrosoftDocs
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
author: Mattp123
ms.assetid: 2e7f75dd-7a3f-4716-b995-b626929c0501
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="disable-auto-save-in-a-model-driven-app"></a>Deaktivere automatisk lagring i en modelldrevet app

Automatisk lagring hjelper appbrukere fokusere på arbeidet uten å måtte behandle lagring av data i skjemaet. De fleste vil sette pris på ikke å være nødt til å lagre dataene eksplisitt hver gang de oppdaterer en oppføring, men enkelte organisasjoner kan ha tilpassinger som er utformet til å forvente en eksplisitt lagring. For slike organisasjoner finnes det alternativer for å styre hvordan automatisk lagring brukes.  
  
<a name="BKMK_HowAutoSaveWorks"></a>   

## <a name="how-auto-save-works"></a>Hvordan automatisk lagring fungerer  
 Som standard har alle hovedskjemaer for [Oppdaterte enheter og klassiske enheter](create-design-forms.md#updated-versus-classic-entities) automatisk lagring aktivert. Etter at en post er opprettet (og lagret første gang), vil endringer som gjøres i et skjema, lagres automatisk tretti sekunder etter at endringen er gjort. Hvis ingen endringer i gjøres skjemaet, forekommer ikke automatisk lagring mens skjemaet er åpent. Når det er gjort en endring begynner perioden på 30 sekunder før automatisk lagring på nytt. Hvis noen er i ferd med å redigere et felt, blir ikke dette inkludert i en automatisk lagring. Hvis noen andre oppdaterer den samme oppføringen mens du redigerer den, hentes disse endringene og vises i skjemaet når automatisk lagring forekommer.  
  
 Med automatisk lagring aktivert vises lagreknappen bare ved den første lagringen av oppføringen. Når oppføringen er opprettet, vises ikke lagreknappen på kommandolinjen, men du kan se en ![Automatisk lagring-knapp](media/auto-save-icon.png "Automatisk lagring-knapp") knapp nede til høyre som viser om det finnes ulagrede endringer. Denne kontrollen vises også hvis automatisk lagring er deaktivert.  
  
 Du kan velge denne knappen for å lagre oppføringen og oppdatere data i skjemaet umiddelbart. Når automatisk lagring er aktivert, lagres oppføringen når du navigerer bort fra en oppføring eller lukker et separat vindu som viser en oppføring. Det er ikke nødvendig med knappen **Lagre og Lukk** som vises i skjemaer for enheter som ikke er oppdatert.  
  
<a name="BKMK_AutoSave"></a>   
## <a name="should-you-disable-auto-save"></a>Bør du deaktivere automatisk lagring?  
 Hvis du har plugin-moduler, arbeidsflyter eller skjemaskript som kjøres når en oppføring blir lagret, vil de kjøres hver gang automatisk lagring inntreffer. Dette kan føre til uønsket atferd hvis disse tilleggene ikke ble utformet for å virke med automatisk lagring. Enten automatisk lagring er aktivert eller ikke, bør plugin-moduler, arbeidsflyter og skjemaskript være utformet for å søke etter bestemte endringer, og de bør ikke kjøre tilfeldig for hver lagringshendelse.  
  
 Hvis du har konfigurert sporing av endringer for en enhet, behandles hver lagring som en separat oppdatering. Hvis noen blir værende på et skjema med ulagrede endringer i over 30 sekunder, ser du en tilleggsoppføring bare hvis vedkommende legger til flere data etter den automatiske lagringen er utført. Hvis du har rapporter som avhenger av sporing av endringer i data, og som behandler hver lagring som en enkeltstående "handling" i en oppføring, kan du se en økning i frekvensen av handlinger. Hvis du bruker denne fremgangsmåten, bør du vurdere om det som den enkelte brukeren gjør, forårsaker upålitelig måling med eller uten automatisk lagring aktivert.  
  
<a name="BKMK_DisableAutoSaveOrg"></a>   
## <a name="disable-auto-save-for-the-organization"></a>Deaktivere automatisk lagring for organisasjonen  
 Hvis du finner ut at automatisk lagring vil forårsake problemer med tillegg du bruker, kan du deaktivere det for organisasjonen. Det finnes ingen innstilling for å deaktivere automatisk lagring for enkeltenheter eller -skjemaer.  
  
1. Gå til **[Innstillinger](advanced-navigation.md#settings)** > **Administrasjon**.  
  
2.  Velg **Systeminnstillinger**.  
  
3.  For alternativet **Aktiver automatisk lagring på alle skjemaer** velger du **Nei**.  
  
<a name="BKMK_DisalbleAutoSaveForm"></a>   
## <a name="disable-auto-save-for-a-form"></a>Deaktivere automatisk lagring for et skjema  
 Hvis du vil deaktivere automatisk lagring for bestemte enhetsskjemaer, kan du legge til kode for `OnSave`-hendelsen i en enhet.  
  
> [!NOTE]
>  Automatisk lagring deaktiveres for skjemaet, men dataene vil fortsatt bli lagret når du velger ![knappen Automatisk lagring](media/auto-save-icon.png "knappen Automatisk lagring") knappen nede til høyre. Hvis du forsøker å navigere bort fra et skjema eller lukke et skjema der dataene er endret, blir de bedt om å lagre endringene før de kan navigere bort fra eller lukke skjemaet.  
  
1.  Logg på [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).  

2.  Utvid **Data**, velg **Enheter**, velg enheten du vil bruke, og velg deretter **Skjemaer**-kategorien.  
  
3.  Åpne skjemaet du vil redigere.  
  
4.  Opprette en JavaScript-webressurs og legge den til på skjemaet:  
  
    1.  I **Skjema**-gruppen i skjemaredigeringsprogrammet velger du **Skjemaegenskaper**.  
  
    2.  I kategorien **Hendelser** under **Skjemabiblioteker** velger du **Legg til**.  
  
    3.  Velg **Ny** i dialogboksen **Oppslagsoppføring**.  
  
    4.  Angi følgende informasjon i webressursskjemaet:  
  
        |||  
        |-|-|  
        |**Navn**|preventAutoSave|  
        |**Visningsnavn**|Forhindre automatisk lagring|  
        |**Type**|Skript (JScript)|  
  
    5.  Ved siden av **Type**-feltet velger du **Tekstredigering**.  
  
    6.  I **Kilde**-feltet limer du inn følgende kode:  
  
        ```javascript  
        function preventAutoSave(econtext) {  
            var eventArgs = econtext.getEventArgs();  
            if (eventArgs.getSaveMode() == 70 || eventArgs.getSaveMode() == 2) {  
                eventArgs.preventDefault();  
            }  
        }  
  
        ```  
  
    7.  Velg **OK** for å lukke tekstredigeringsprogrammet.  
  
    8.  Velg **Lagre** for å lagre webressursen, og lukk deretter webressursvinduet.  
  
    9. I dialogboksen **Oppslagsoppføring** velges den nye webressursen du opprettet. Velg **Legg til** for å lukke dialogboksen.  
  
5.  Konfigurere OnSave-hendelsen:  
  
    1.  I vinduet **Skjemaegenskaper** i delen **Hendelsesbehandlinger** setter du **Hendelse** til **OnSave**.  
  
    2.  Velg **Legg til**.  
  
    3.  I vinduet **Egenskaper for behandling** setter du **Bibliotek** til webressursen du la til i forrige trinn.  
  
    4.  Skriv inn "`preventAutoSave`" i **Funksjon**-feltet. Dette skiller mellom store og små bokstaver. Ikke ta med anførselstegnene.  
  
    5.  Forsikre deg om at det er merket av for **Aktivert**.  
  
    6.  Merk av for **Send utføringskontekst som første parameter**.  
  
        > [!IMPORTANT]
        >  Hvis du ikke gjør dette, vil ikke skriptet fungere.  
  
         Dialogboksen **Egenskaper for behandling** skal se slik ut. Tilpassingsprefikset "ny_" kan variere avhengig av tilpassingsprefikset som er angitt for standardutgiveren for din organisasjon.  
  
 ![OnSave-hendelsesbehandling for å forhindre automatisk lagring i Dynamics 365](media/prevent-auto-save-script.png "OnSave-hendelsesbehandling for å forhindre automatisk lagring i Dynamics 365")  
  
    7.  Velg **OK** for å lukke dialogboksen **Egenskaper for behandling**.  
  
    8.  Hvis det finnes andre hendelsesbehandlinger for den `OnSave`-hendelsen, kan du bruke de grønne pilene til å flytte denne til toppen.  
  
6. Velg **OK** for å lukke dialogboksen **Skjemaegenskaper**.  
  
7. Velg **Lagre og lukk** for å lukke skjemaet.  
  
8. Velg **Publiser alle tilpassinger** i løsningsutforskeren.  
  
 Når du har brukt dette skriptet i `OnSave`-hendelsen, og en bruker redigerer en oppføring ved hjelp av dette skjemaet, vises meldingen **ulagrede endringer** nederst til høyre i skjemaet, akkurat som om automatisk lagring ikke er deaktivert. Men denne meldingen vil ikke forsvinne før en bruker velger ![knappen Automatisk lagring](media/auto-save-icon.png "knappen Automatisk lagring") knappen ved siden av.  
  
## <a name="next-steps"></a>Neste trinn  
 [Opprette og utforme skjemaer](create-design-forms.md)      

 
