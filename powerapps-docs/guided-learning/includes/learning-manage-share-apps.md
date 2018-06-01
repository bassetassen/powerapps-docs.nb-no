Det er flott å utvikle apper som er rettet mot bedriftens behov, men den virkelige magien ved PowerApps ligger i å dele disse appene med andre. Nå som du vet hvordan du bygger en app, vil du i dette emnet lære hvordan du deler den. Du kan dele en app med bestemte brukere eller grupper, eller du kan dele den med hele organisasjonen. Når du deler en app med noen, kan de kjøre den fra Dynamics 365 i en nettleser eller PowerApps Mobile for Windows, iOS eller Android. Hvis du gir noen bidragsytertillatelser, kan de også oppdatere appen.

## <a name="prepare-to-share-an-app"></a>Klargjøre for å dele en app
Du må lagre en app til skyen før du kan dele den med alle. Før du deler en app kan du gi den et hensiktsmessig navn og en beskrivelse, slik at brukerne vet hva appen handler om og enkelt kan velge den fra en liste. Klikk eller trykk på **Fil** i PowerApps Studio, og skriv deretter inn en beskrivelse.

![Appbeskrivelse](./media/learning-manage-share-apps/app-description.png)

Vær oppmerksom på at eventuelle endringer du gjør i en delt app, flyter gjennom til personene du har delt den med så snart du lagrer endringene. Dette kan være flott hvis du forbedrer appen, men det kan også påvirke andre hvis du fjerner eller gjør betydelige endringer på funksjoner.

## <a name="share-an-app"></a>Å dele en app
I web.powerapps.com, på en appflis, trykker du på de tre prikkene (. . .), og klikk deretter på **Del**.

![Å dele appen fra web.powerapps.com](./media/learning-manage-share-apps/share-app.png)

Herfra kan du dele en app, og du kan også styre versjonskontroller for apper, noe vi går gjennom i neste emne. Angi brukerne og gruppene du vil dele appen med, og hvilke roller hver av dem skal ha – **Bruker** eller **Bidragsyter**. Klikk eller trykk på **Lagre**.

![Alle brukere og grupper](./media/learning-manage-share-apps/select-users.png)

Hvis du velger å varsle brukerne via e-post, får alle du har delt appen med en e-postmelding med en kobling til Dynamics 365. App-bidragsytere mottar også en kobling til web.powerapps.com.  Hvis noen ikke følger koblingen til Dynamics 365, vil ikke appen vises for dem der. Den vil være i AppSource, men de må selv legge den til Dynamics 365.

![App i Dynamics 365](./media/learning-manage-share-apps/dynamics-365.png)

## <a name="permissions-and-licensing"></a>Tillatelser og lisensiering
Vi kommer ikke til å gå i detalj rundt tillatelser og lisensiering, men vi ønsker å dekke et par grunnleggende punkter om deling:

* Brukere og bidragsytere må ha tilgang til alle datatilkoblinger og gatewayer som en delt app bruker. Noen tillatelser leveres implisitt med appen, mens andre gis eksplisitt.
* Hvis appen bruker Common Data Service for app-enheter, trenger brukere og bidragsytere tilgang til Common Data Service for Apps-databasen. Bidragsytere trenger også en PowerApps «P2»-lisens hvis de arbeider direkte med enheter.

Det er enkelt å dele apper, og det er en flott måte å ta i bruk en app du synes er nyttig på, og gjøre den tilgjengelig for personer på tvers av organisasjonen. I neste emne forklarer vi hvordan du kontrollerer hvilken versjon av en app som skal være aktiv når du bruker og deler appen.

