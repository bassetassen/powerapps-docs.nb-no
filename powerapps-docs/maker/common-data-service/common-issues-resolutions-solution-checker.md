---
title: Vanlige problemer og løsninger for Løsningskontroll | Microsoft Docs
description: ' En liste over vanlige problemer og løsninger i Løsningskontroll'
keywords: ''
ms.date: 02/11/2019
ms.service: powerapps
ms.custom:
  - ''
ms.topic: article
ms.assetid: caa4e3f2-9700-49b8-87ed-8a68e8878b02
author: jowells1
ms.author: jowells
manager: austinj
ms.reviewer: null
robots: 'noindex,nofollow'
search.audienceType:
  - developer
search.app:
  - PowerApps
  - D365CE
---
# <a name="common-issues-and-resolutions-for-solution-checker"></a>Vanlige problemer og løsninger for Løsningskontroll

Denne artikkelen inneholder en liste over enkelte vanlige problemer som kan oppstå når du bruker Løsningskontroll. Der det er nødvendig er løsninger tilgjengelig.

## <a name="youre-unable-to-use-solution-checker-to-run-analysis-or-download-results"></a>Løsningskontroll kan ikke brukes til å kjøre analyser eller laste ned resultater

Kort tid etter at du har sendt en løsningskontrollforespørsel om å kjøre en analyse eller laste ned resultater, blir ikke operasjonen fullført, og det vises en feilmelding, for eksempel følgende:

> *«Vi kan ikke kjøre kontrollen på **[Løsningsnavn]**-løsningen. Prøv på nytt.»*

Når det er mulig, prøver løsningskontrollen å returnere en bestemt feilmelding med en kobling til informasjon om mulig årsak og løsningstrinn. Velg **"Finn ut mer"** hvis du vil ha mer informasjon.

![Feilmeldingslinje](media/solution-checker-missing-roles-error.png)

Feil som oppstår under bakgrunnsbehandlingen av analysen, mislykkes med statusen **"Kunne ikke fullføres"** og returnerer en feilmelding i PowerApps-portalen i tillegg til å sende e-postvarsling til anmoderen. 

![Feilstatus](media/solution-checker-exception-status.png)

Ved å velge portalvarselet, kobles du til denne siden med vanlige problemer for videre feilsøking. Hvis noen av de vanligste problemene ikke løser problemet, returneres det også et referansenummer. Gi dette referansenummeret til Microsofts kundestøtte for videre undersøkelser.

![Varsel om svikt](media/solution-checker-failure-notification.png)

## <a name="solution-checker-fails-due-to-unsupported-version-of-powerapps-checker"></a>Løsningskontrollen mislykkes på grunn av PowerApps-kontrollerversjon som ikke støttes

Løsningskontroll er en funksjon som aktiveres av PowerApps-kontrollappen.  Hvis du har installert en PowerApps-kontrollappversjon før **1.0.0.47**, kan Løsningskontroll-kjøring mislykkes. Du må oppgradere PowerApps-kontrollerversjonen fra [!INCLUDE [pn-dyn-365-admin-center](../../includes/pn-dyn-365-admin-center.md)]. 

Men hvis du har en PowerApps-kontrollerversjon før **1.0.0.45** installert, bør du slette løsningen og installere den på nytt. På grunn av de siste skjemaendringene kan oppgradering av PowerApps-kontroller fra versjoner tidligere enn **1.0.0.45** mislykkes.

Hvis du vil beholde de siste resultatene fra Løsningskontroll, eksporterer du resultatene fra en tidligere kjøring eller eksporter alle Løsningskontroll-data ved hjelp av [Eksportere data til Excel](../../user/export-data-excel.md) for å eksportere data fra følgende enheter:

- Analysekomponent
- Analysejobb
- Analyseresultat
- Analyseresultatdetalj

### <a name="how-to-uninstall-powerapps-checker"></a>Slik avinstallerer du PowerApps-kontroll

For å avinstallere PowerApps-kontrollerløsningen:

1. Som systemansvarlig eller systemtilpasser kan du åpne PowerApps-portalen ved å gå til https://web.powerapps.com/environments.
2. Velg **Løsninger**.
3. Velg **PowerApps-kontroller**, og velg deretter på **Slett** på løsningsverktøytlinjen.

### <a name="how-to-install-powerapps-checker"></a>Slik installerer du PowerApps-kontroll

Slik installerer du PowerApps-kontroll i Common Data Service-miljøet ditt på nytt:

1. Som systemansvarlig eller systemtilpasser kan du åpne PowerApps-portalen ved å gå til https://web.powerapps.com/environments.
2. Velg **Løsninger**.
3. På løsningsverktøylinjen velger du **Løsningskontroll**, og velg deretter **Installer**.

## <a name="solution-checker-cant-access-organizations-in-administration-mode"></a>Løsningskontroll får ikke tilgang til organisasjoner i administrasjonsmodus

Organisasjoner som har blitt satt i [administrasjonsmodus](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/manage-sandbox-instances#administration-mode), begrenser tilgang til kun brukere med roller for systemadministrator og systemtilpasser. Ettersom programidentiteten til PowerApps-kontrollen ikke har noen av disse rollene tilordnet som standard, får den ikke tilgang til organisasjoner i denne modusen.

Hvis du skal kunne bruke løsningskontrollen i denne organisasjonen, må administrasjonsmodusen være deaktivert.

### <a name="how-to-disable-administration-mode"></a>Slik deaktiverer du administrasjonsmodus

Slik deaktiverer du administrasjonsmodus for en organisasjonsforekomst:

1. Åpne Dynamics 365 for Customer Engagement-appforekomstvelgeren: https://port.crm.dynamics.com/G/Instances/InstancePicker.aspx.
2. Velg organisasjonsforekomsten som har problemer med å kjøre Løsningskontroll.
3. Velg **ADMIN**.<br/>
![Forekomstadmin](media/solution-checker-instance-admin.png)

4. Tøm **Aktiver administrasjonsmodus** og velg deretter **Lagre**.<br/>
![Deaktiver administratormodus](media/solution-checker-instance-disable-admin-mode.png)

5. Kjør Løsningskontroll på nytt.

## <a name="solution-checker-fails-due-to-missing-security-roles"></a>Løsningskontroll mislykkes på grunn av manglende sikkerhetsroller

Programbrukeren for Løsningskontroll krever at to sikkerhetsroller er tilordnet for å gi de nødvendige rettighetene til å kommunisere med Common Data Service-organisasjonen. Hvis noen av disse rollene ikke er tilordnet brukeren **"PowerApps-kontroll"**, vil forsøk på å kjøre analyse, laste ned resultater og avbryte kjøringer mislykkes. Dette skjer oftest når kunder har automatisering som fjerner sikkerhetsroller fra uventede brukere. Følgende sikkerhetsroller inneholder minsteantallet nødvendige tillatelser:

- Eksporter tilpassinger
- Løsningskontroll

### <a name="how-to-assign-missing-security-roles"></a>Slik tilordner du manglende sikkerhetsroller

Slik tilordner du manglende sikkerhets roller til brukeren PowerApps-kontroll:

1. Åpne Common Data Service-organisasjonen og naviger til **Innstillinger** > **Sikkerhet** > **Brukere**.
2. Velg **"PowerApps-kontroll"**-brukeren fra listen over brukere.
3. Velg **BEHANDLE ROLLER** på kommandolinjen.
4. Velg avmerkingsboksene **"Eksporter tilpassinger"** og **Løsningskontroll**, og deretter **OK**.<br/>
![Nødvendige sikkerhetsroller](media/solution-checker-required-roles.png)

5. Kjør Løsningskontroll på nytt.

## <a name="solution-checker-fails-due-to-restricted-access-mode"></a>Løsningskontroll mislykkes på grunn av modus for begrenset tilgang

Programbrukeren for løsningskontrollen krever en tilgangsmodus av typen **"Ikke-interaktiv"** eller **"Lese og skrive"** for å kunne kommunisere med Common Data Service-organisasjonen. Hvis tilgangsmodusen endres til en annen verdi, for eksempel **"Administrativ"**, mislykkes forsøk på å kjøre analyse, laste ned resultatene og avbryte kjøringer.

Du kan løse dette problemet ved å oppdatere programbrukeren **PowerApps-kontroll** til tilgangsmodus "ikke-interaktiv".

### <a name="how-to-update-user-access-mode"></a>Slik oppdaterer du brukertilgangsmodus

Slik oppdaterer du tilgangsmodusen for brukeren PowerApps-kontroll:

1. Åpne Common Data Service-organisasjonen og naviger til **Innstillinger** > **Sikkerhet** > **Brukere**.
2. Velg brukeren **PowerApps-kontroll** fra listen over brukere, og dobbeltklikk for å åpne brukerskjemaet.
3. Bla til delen **"administrasjon"** > **"klientadgangslisensinformasjon (CAL)"**-inndelingen i skjemaet.
4. Velg **"ikke-interaktiv"** i rullegardinkontrollen for **tilgangsmodus**.<br/>
![Tilgangsmodus](media/solution-checker-access-mode.png)

5. Lagre og lukk brukerskjemaet.
6. Kjør Løsningskontroll på nytt.

## <a name="solution-checker-fails-due-to-disabled-first-party-application-in-aad"></a>Løsningskontroll mislykkes på grunn av deaktivert førstepartsprogram i AAD

Den førsteparts foretaksprogramidentiteten som brukes av Løsningskontroll (PowerApps-Advisor) bør ikke deaktiveres i Azure Active Directory (AAD). Hvis den er deaktivert, kan ikke identiteten godkjenne når den ber om bærertegn for Common Data Service og andre nødvendige ressursleverandører på vegne av brukeren som ber om det. 

Følg fremgangsmåten nedenfor for å kontrollere at programidentiteten ikke er deaktivert i AAD, og om nødvendig aktivere programmet.

### <a name="how-to-verify-andor-modify-application-enabled-status"></a>Slik kontrollerer du og/eller endrer programaktivert status

Slik kontrollerer og/eller endrer du den aktiverte statusen for PowerApps-Advisors foretaksprogramidentitet

1. Få tilgang til leieren din i [Azure Active Directory-portalen (AAD)](https://aad.portal.azure.com/).
2. Naviger til **Enterprise-programmer**.
3. Velg **alle programmer** og søk etter **"PowerApps-Advisor"**.<br/>
![Søk i PowerApps-Advisor-appen](media/solution-checker-search-advisor-app.png)

4. Velg **"PowerApps-Advisor"** for å vise detaljene for appen.
5. Velg **Egenskaper**.
6. Sjekk statusen for **Aktivert for pålogging av brukere**. Hvis **"Nei"**, er programmet deaktivert.<br/>
![Deaktivert Enterprise-app](media/solution-checker-disabled-app.png)

7. Velg alternativknappen for å gjøre om verdien til **"Ja"**. Dette aktiverer programmet.<br/>
![Aktiver PowerApps-Advisor-appen](media/solution-checker-enable-app.png)

8. Velg **Lagre**. Programmet er nå aktivert. Det kan hende du må vente noen minutter på at endringen skal gå gjennom.
9. Kjør Løsningskontroll på nytt.

> [!IMPORTANT]
> Du må ha administratorrettigheter i Azure Active Directory (AAD) for å kunne redigere Enterprise-programmer.

## <a name="solution-checker-fails-to-export-solutions-with-draft-business-process-flow-components"></a>Løsningskontroll kan ikke eksportere løsninger med komponentutkast for forretningsprosessflyt

Hvis en løsning inneholder en komponent for forretningsprosessflyt i utkasttilstand som aldri har vært aktivert tidligere, kan ikke Løsningskontroll eksportere løsningen for analyse. Denne feilen er ikke unik for løsningskontrollen, og forårsakes av forretningsprosessflyten som er avhengig av en reserveenhetskomponent som ikke blir opprettet før forretningsprosessflyten er aktivert for første gang. Dette problemet kan også oppstå hvis en forretningsprosessflyt er aktivert i Løsningsutforsker.

Les [KB-artikkel #4337537: Ugyldig eksport – forretningsprosessenhet mangler](https://support.microsoft.com/en-hk/help/4337537/invalid-export-business-process-entity-missing) hvis du vil ha informasjon om problemet og trinnene som må løses.

## <a name="solution-checker-fails-to-export-patched-solutions"></a>Løsningskontroll eksporterer ikke oppdaterte løsninger

Hvis en løsning har en [oppdatering](https://docs.microsoft.com/powerapps/developer/common-data-service/create-patches-simplify-solution-updates), mislykkes Løsningskontroll i å eksportere løsningen for analysen. Når en løsning har brukt en oppdatering, låses den opprinnelige løsningen, og den kan ikke endres eller eksporteres så lenge det finnes avhengige oppdateringer i organisasjonen som identifiserer løsningen som den overordnede løsningen.

Hvis du vil løse dette problemet, kan du klone løsningen, slik at alle oppdateringer som gjelder løsningen, rulles inn i den nyopprettede løsningen. Dette låser opp løsningen og gjør at løsningen kan eksporteres fra systemet.  Hvis du vil ha mer informasjon, kan du se [Klone en løsning](use-segmented-solutions-patches-simplify-updates.md#clone-a-solution).

## <a name="solution-checker-will-not-analyze-empty-solutions"></a>Løsningskontroll analyserer ikke tomme løsninger

Hvis Løsningskontroll eksporterer en løsning som ikke inneholder komponenter som skal analyseres, avsluttes den ytterligere behandlingen og kjøringen regnes som mislykket. Kontroller at den valgte løsningen som ble sendt til analyse i Løsningskontroll, inneholder minst én komponent.

## <a name="solution-checker-fails-to-export-large-solutions"></a>Løsningskontroll eksporterer ikke store løsninger

Det viktigste scenariet ved mislykket eksport av en stor løsning fra Common Data Service-miljøet innebærer et tidsavbruddunntak på eksportforespørselen. Dette skjer hvis forespørselen overskrider 20 minutter. Store løsninger, som standardløsningen, kan føre til at eksporten ikke kan utføres i dette tidsrommet, og kontrollen vil ikke fullføres. Hvis Løsningskontroll oppdager et tidsavbrudd under eksportering, prøver den tre ganger før den ikke lenger behandler jobben, slik at det kan ta over en time før du får et feilvarsel.

Løsningen er å lage mindre løsninger med færre komponenter som skal analyseres. Hvis den store filstørrelsen på løsningen er på grunn av mange komponenter i plugin-modulsamlingen, kan du se veiledning for å [optimalisere egendefinert samlingsutvikling](../../developer/common-data-service/best-practices/business-logic/optimize-assembly-development.md). 

> [!IMPORTANT]
> For å redusere falske positive svar, sikre at du legger til avhengige tilpassinger. Når du oppretter en løsning og legger til disse komponentene, inkluder følgende:
> - Når du legger til plugin-moduler, inkluder behandlingstrinn for SDK-melding for plugin-modulen.
> - Når du legger til i enhetsskjemaer, kan du inkludere JavaScript-webressurser som er knyttet til skjemahendelsene.  
> - Når du legger til JavaScript-webressurser, inkluder eventuelle avhengige JavaScript-webressurser.
> - Når du legger til HTML-webressurser, inkluder eventuelle avhengige skript som er definert i HTML-webressursen.
> - Når du legger til egendefinerte arbeidsflyter, kan du inkludere samlingen som brukes i arbeidsflyten.

## <a name="line-number-references-for-issues-in-html-resources-with-embedded-javascript-are-not-correct"></a>Linjenummerreferanser for problemer i HTML-ressursene med innebygd JavaScript er ikke riktig 

Når du skal behandles HTML-webressurser i Løsningskontroll, behandles HTML-webressursen separat fra JavaScript i HTML-webressursen. På grunn av dette vil linjenummeret inne i `<script>` i HTML-webressursen ikke bli riktig.

## <a name="web-unsupported-syntax-issue-for-web-resources"></a>Webstøttesyntaksproblem for webressurser

ECMAScript 6 (2015) eller senere versjoner støttes ikke for Løsningskontroll. Når Løsningskontroll analyserer JavaScript med ECMAScript 6 eller senere, rapporteres et internettstøttet syntaksproblem for nettressursen.  

## <a name="multiple-violations-reported-for-plug-ins-and-workflow-activities-based-on-call-scope"></a>Flere brudd rapportert for plugin-moduler og arbeidsflytaktiviteter basert på samtaleomfang

For plugin-moduler og regler for arbeidsflytaktivitet der problemet bare er relevant i den kallende konteksten, starter Løsningskontroll-verktøyet analysen på IPlugin-grensesnittimplementeringen og går gjennom et kalldiagram for å finne problemer i omfanget for den implementeringen.  I enkelte tilfeller kan mange samtalebaner ankomme til samme sted der problemet registreres.  Siden problemet er relevant for samtaleomfanget, kan verktøyet rapportere basert på dette omfanget for å gi en bedre oversikt over innvirkningen, i stedet for på forskjellige steder. Flere problemer kan derfor referere til et enkelt sted som må løses.

## <a name="see-also"></a>Se også
[Gode fremgangsmåter og veiledning for Common Data Service](../../developer/common-data-service/best-practices/index.md)<br/>
[Gode fremgangsmåter og veiledning for modelldrevne apper](../../developer/model-driven-apps/best-practices/index.md)<br/>
