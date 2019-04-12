---
title: Feilsøke Power Query | Microsoft Docs
description: Løs problemer ved hjelp av Power Query for å opprette en egendefinert enhet i Common Data Service.
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="troubleshoot-power-query"></a>Feilsøk Power Query
Når du bruker Power Query for Excel til å opprette en egendefinert enhet som inneholder data fra eksterne kilder, kan denne feilmeldingen vises:

>"Azure Active Directory-administratoren har angitt en policy som hindrer deg fra å bruke denne funksjonen. Kontakt administratoren, som kan gi tillatelser for denne funksjonen på dine vegne."

Feilen vises hvis Power Query ikke får tilgang til organisasjonens data i PowerApps eller Common Data Service. Dette problemet oppstår i to tilfeller:

* En Azure Active Directory (Azure AD)-leieradministrator har fratatt brukeren muligheten til å gi samtykke til apper som får tilgang til firmadata på deres vegne.
* Bruker en uadministrert Active Directory-leier. En uadministrert leier er en mappe uten en global administrator som ble opprettet for å fullføre et selvbetjent registreringstilbud. Hvis du vil løse dette scenarioet, må brukerne først konvertere til en administrert leier og deretter følge én av de to løsningene på dette problemet. Løsningene er beskrevet i neste del.

Azure Active Directory-administratoren må følge én av prosedyrene som vises senere i denne artikkelen, for å løse problemet.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>La brukere gi samtykke til apper som får tilgang til firmadata
Denne metoden er kanskje enklere enn neste, men den gjør det mulig med mer omfattende tillatelser.

1. I [Azure-portalen](https://portal.azure.com) åpner du **Azure Active Directory**-ruten, og velger deretter **Brukerinnstillinger**.
2. Ved siden av **Brukere kan samtykke til apper som får tilgang til firmadata på deres vegne** velger du **Ja**, og velger deretter **Lagre**.

## <a name="allow-power-query-to-access-company-data"></a>Tillat at Power Query får tilgang til firmadata
Alternativt kan leieradministratoren gi samtykke til Power Query uten å endre tillatelser for hele leieren.

1. Installer [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Kjør følgende PowerShell-kommandoer:
   * Login-AzureRmAccount (og logg på som leieradministratoren)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Fordelen med denne metoden (kontra løsningen for hele leieren) er at denne løsningen er svært målrettet. Den klargjør bare **Power Query**-tjenestens hovednavn, men gjør ingen andre tillatelsesendringer i leieren.

## <a name="update-personal-data"></a>Oppdatere personlige data

Brukere kan oppdatere mashups og annen informasjon (for eksempel spørringsnavn og mashup-metadata) gjennom redigeringsprogrammet for spørringen og gjennom dialogboksen **Alternativer** som er tilgjengelig fra redigeringsprogrammet for spørringen.

I PowerApps kan du åpne redigeringsprogrammet for spørring ved å gjøre følgende:
1. Gå til **Data**-ruten, utvid den, og velg deretter **Enheter**. 
2. Velg ellipsen (...), og velg deretter **Rediger spørringer**.
3. På båndet velger du **Alternativer**-knappen, og velger deretter **Eksporter diagnostikk**-knappen.


## <a name="delete-personal-data"></a>Slette personlige data

De fleste dataene blir slettet automatisk innen 30 dager. Brukere må fjerne deres mashups gjennom PowerApps ved data og metadata rundt mashups. Alle tilknyttede data og metadata slettes innen 30 dager.

Slik fjerner du mashups fra Power Apps:
1. Fjern Data Integrator-prosjektene, som kan fjernes fra kategorien namesake.
2. Velg ellipsen (…), og deretter velger du **Slett**-alternativet.

Hvis du har opprettet en mashup gjennom funksjonen "Nye enheter fra data (teknisk forhåndsvisning)", kan du fjerne den ved å gjøre følgende:
1. Velg ellipsen (...), og velg deretter **Rediger spørringer**.
2. Velg **Alternativer**-knappen på båndet.
3. Velg **Fjern alle spørringer**-knappen.  
    Når du har bekreftet at du vil slette spørringene, slettes de.

## <a name="export-personal-data"></a>Eksportere personlige data

Hvis brukere vil eksportere personlige data, kan de gjøre følgende:
1. Åpne redigeringsprogrammet for spørring.
2. Velg **Alternativer**-knappen på båndet.
3. Velg **Eksporter diagnostikk**-knappen.

I PowerApps kan du åpne redigeringsprogrammet for spørring ved å gjøre følgende:
1. Gå til **Data**-ruten, utvid den, og velg deretter **Enheter**.
2. Velg ellipsen (...), og velg deretter **Rediger spørringer**. 
3. På båndet velger du **Alternativer**-knappen, og velger deretter **Eksporter diagnostikk**-knappen.

Systemgenererte logger om brukerhandlinger i brukergrensesnittet er tilgjengelige i Azure-portalen.



