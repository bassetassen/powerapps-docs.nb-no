I dette emnet ser vi nærmere på den genererte appen ved å gå gjennom skjermbildene og kontrollene som definerer appens virkemåte. Vi går ikke gjennom alle detaljene, men å se mer om hvordan denne appen fungerer vil hjelpe deg når du skal bygge dine egne apper. I et senere emne skal vi se på formlene som fungerer med skjermbilder og kontroller.

## <a name="understanding-controls-in-powerapps"></a>Forstå kontroller i PowerApps
En kontroll er ganske enkelt et UI-element som har tilknyttede virkemåter. Mange kontroller i PowerApps er de samme som kontrollene du har brukt i andre apper: etiketter, bokser for innskriving av tekst, rullegardinlister, navigasjonselementer og så videre. PowerApps har imidlertid mer spesialiserte kontroller, som for eksempel **Gallerier** (som viser sammendragsdata) og **Skjemaer** (som viser detaljdata og gjør det mulig å opprette og redigere elementer). Her finner du også noen virkelig kule kontroller, som for eksempel **Bilde**, **Kamera** og **Strekkode**. Hvis du vil se hva som er tilgjengelig, kan du klikke eller trykke på **Sett inn** på båndet og klikke eller trykke på hvert av alternativene etter tur, fra**Tekst** til **Ikoner**.

![Kontroller-fanen på PowerApps Studio-båndet](./media/learning-spo-app-explore-controls/ribbon-controls.png)

## <a name="explore-the-browse-screen"></a>Utforske Bla gjennom-skjermbildet
Hvert av de tre appskjermbildene har en hovedkontroll og noen flere kontroller. Det første skjermbildet i appen er Bla gjennom-skjermbildet, kalt **BrowseScreen1** som standard. Hovedkontrollen på dette skjermbildet er et galleri med navnet **BrowseGallery1**. **BrowseGallery1** inneholder andre kontroller, som for eksempel **NextArrow1** (en ikon-kontroll – klikk eller trykk på den for å gå til Details-skjermbildet). Skjermbildet har også separate kontroller, deriblant **IconNewItem1** (en ikon-kontroll – klikk eller trykk på den for å opprette et element på Rediger/opprett-skjermbildet).

![Bla gjennom-skjermbildet med kontroller](./media/learning-spo-app-explore-controls/browse-screen.png)

PowerApps har flere ulike typer gallerier, slik at du kan bruke det som passer best til kravene til oppsettet i appen din. Du vil se flere måter å kontrollere oppsett på senere i denne delen.

![Alternativer for PowerApps-gallerier](./media/learning-spo-app-explore-controls/galleries.png)

## <a name="explore-the-details-screen"></a>Utforske Detaljer-skjermbildet
Det neste skjermbildet er Detaljer-skjermbildet, kalt **DetailsScreen1** som standard. Hovedkontrollen på dette skjermbildet er et visningsskjema kalt **DetailForm1**. **DetailForm1** inneholder andre kontroller, deriblant **DataCard1** (en kortkontroll, som i dette tilfellet viser gulvkategorien). Skjermbildet har også separate kontroller, deriblant **IconEdit1** (en ikon-kontroll – klikk eller trykk på den for å redigere det nåværende elementet på Rediger/opprett-skjermbildet).

![Detaljer-skjermbildet med kontroller](./media/learning-spo-app-explore-controls/details-screen.png)

Det finnes mange alternativer for gallerier, men for skjemaer er det enklere – det er enten et redigeringsskjema eller et visningsskjema.

![Alternativer for PowerApps-skjemaer](./media/learning-spo-app-explore-controls/forms.png)

## <a name="explore-the-editcreate-screen"></a>Utforske Rediger/opprett-skjermbildet
Det tredje skjermbildet i appen er Rediger/opprett-skjermbildet, kalt **EditScreen1** som standard. Hovedkontrollen på dette skjermbildet er et visningsskjema kalt **EditForm1**. **EditForm1** inneholder andre kontroller, deriblant **DataCard8** (en kortkontroll, som i dette tilfellet lar deg redigere gulvkategorien). Skjermbildet har også separate kontroller, deriblant **IconAccept1** (en ikon-kontroll – klikk eller trykk på den for å lagre endringene du har gjort på Rediger/opprett-skjermbildet).

![Rediger-skjermbildet med kontroller](./media/learning-spo-app-explore-controls/edit-screen.png)

Nå som du har en følelse av hvordan appen er bygget opp av skjermbilder og kontroller, skal vi i neste emne se på hvordan du tilpasser appen.

