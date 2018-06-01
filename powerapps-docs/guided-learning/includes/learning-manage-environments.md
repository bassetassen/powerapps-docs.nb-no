Hvis du har fulgt kurset så langt, har du brukt en del tid på å arbeide i web.powerapps.com. Enten du visste det eller ei, så har du arbeidet i et bestemt *miljø* hele tiden. Et miljø er ganske enkelt en gruppering av apper og andre ressurser (du får mer informasjon om dette straks). Se øverst til høyre på skjermen i web.powerapps.com, og du ser en rullegardinmeny som viser ditt nåværende miljø.

![Miljøvelger](./media/learning-manage-environments/environment-picker.png)

Hvis du er fersk med PowerApps, har du kanskje bare standardmiljøet ved dette tidspunktet. Klikk eller trykk på menyen for å se om det finnes andre tilgjengelige miljøer.

## <a name="why-use-environments"></a>Hvorfor bruke miljøer?
Et miljø er en beholder for apper og andre ressurser, for eksempel datatilkoblinger og flyter fra Microsoft Flow. Det er en måte å gruppere ting på, basert på forretningsbehov. Det finnes flere grunner til å opprette flere miljøer enn standardmiljøet:

* **Å dele inn apputvikling etter avdeling**: i en stor organisasjon kan det være at hver avdeling arbeider i forskjellige miljøer.
* **Å støtte for programlivssyklus (ALM)**: du kan ha separate miljøer for apper under utvikling og apper som du allerede har fullført og delt.
* **Å administrere datatilgang**: hvert miljø kan ha sin egen Common Data Service for Apps-database, og andre datatilkoblinger er spesifikke for miljøet (det vil si at de ikke er delt på tvers av miljøer).

Én ting å huske på er at miljøer bare er aktuelt for apputviklere og PowerApps-administratorer. Når du deler en app med en bruker, kjører brukeren bare appen så lenge han eller hun har de riktige tillatelsene. De trenger ikke å bekymre seg om hvilket miljø den kom fra.

## <a name="create-an-environment"></a>Å opprette et miljø
I dette kurset har vi så langt fokusert på apputviklere, men miljøer opprettes og vedlikeholdes av administratorer. Hvis du ikke er administrator, kan denne informasjonen fremdeles være nyttig når du snakker med administratoren om å konfigurere miljøer. I PowerApps-administrasjonssenteret klikker eller trykker du på **Miljøer**, og deretter på **Nytt miljø**. Skriv inn et navn for miljøet på **Nytt miljø**-skjermen, velg et navn for området, og velg om du vil opprette en Common Data Service for Apps-database for miljøet. Klikk eller trykk deretter på **Opprett et miljø**.

![Å opprette et miljø](./media/learning-manage-environments/create-environment.png)

Det var alt, du har nå et nytt miljø å arbeide i. Hvis du går tilbake til web.powerapps.com, ser du det i rullegardinmenyen Miljøer.

## <a name="manage-access-to-an-environment"></a>Administrere tilgang til et miljø
Du har tilgang til et miljø hvis du er:

* En **miljøadministrator**: du har alle tillatelser i miljøet.
* En **miljøoppretter**: du kan se alle apper, opprette apper og arbeide med Common Data Service for Apps (andre tillatelser gjelder).

Som administrator kan du gi tilgang til et miljø fra **Miljøer**-fanen. Først klikker eller trykker du på et miljø. Hvis du vil legge til noen (en **miljøoppretter** i dette eksemplet), klikker eller trykker du på **miljøroller** og deretter på **miljøoppretter**. Derfra kan du legge til brukere eller grupper i rollen og klikke på **Lagre**.

![Administrere miljøtilgang](./media/learning-manage-environments/environment-access.png)

Nå har du en bedre forståelse av fordelene med miljøer og hvordan du oppretter og gir tilgang til dem. Selv om du ikke er i en administratorrolle, er det nyttig å vite hvordan dette fungerer. 

Dette bringer oss til slutten av delen om å behandle apper, og dessuten til slutten av dette veiledende opplæringskurset. Vi håper du er fornøyd og har lært mye – gi oss beskjed hvis du har tilbakemeldinger, og sjekk innom senere igjen, vi har nemlig planer om å legge til innhold over tid. For mer dyptgående innhold akkurat nå, kan du sjekke ut [PowerApps-dokumentasjon](https://docs.microsoft.com/powerapps/). 

