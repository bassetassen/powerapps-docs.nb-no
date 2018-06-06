En av de viktigste fordelene med PowerApps er at du ikke trenger å skrive tradisjonell programkode, du trenger ikke å være utvikler for å opprette apper. Men du trenger fremdeles en måte å uttrykke logikken i en app på, og å kontrollere appens navigering, filtrering, sortering og andre funksjoner. Det er her formler kommer inn. Hvis du har brukt Excel-formler tidligere, burde metodene i PowerApps virke kjent. I dette emnet viser vi et par grunnleggende formler for tekstformatering, og så går vi gjennom tre av formlene som PowerApps inkluderer i den genererte appen. Du får en smakebit av hva formler kan gjøre. Deretter kan du kikke litt på andre formler i den genererte appen og skrive dine egne.

## <a name="understanding-formulas-and-properties"></a>Prinsipper ved formler og egenskaper
I det forrige emnet inkluderte vi prisfeltet i skjermgalleriet, men det ble vist som bare et tall uten valutasymbol. La oss si at vi vil legge til et dollarsymbol og samtidig endre tekstfargen avhengig av hvor mye varen koster (for eksempel rødt hvis det er mer enn USD 5, ellers grønt). Bildet nedenfor viser hva vi mener.

![Tekstformatering for farge og valuta](./media/learning-spo-app-explore-formulas/text-formatting.png)

Vi starter med valutaformateringen. Som standard henter PowerApps bare inn en prisverdi for hvert element, som er angitt som **Text**-*egenskapen* på etiketten som viser prisen.

![Standardformatering av pris](./media/learning-spo-app-explore-formulas/price-default.png)

Legg til dollarsymbolet ved å klikke eller trykke på etikett-kontrollen, og i formellinjen angir du **Text**-egenskapen for denne formelen.

![Valutaformatering av pris](./media/learning-spo-app-explore-formulas/price-formatted.png)

Formelen – `Text(Price, "[$-en-US]$ ##.00"` bruker **Text**-*funksjonen* til å spesifisere hvordan tallet skal formateres. Formelen er som en Excel-formel, men PowerApps-formler refererer til kontroller og andre appelementer i stedet for celler i et regneark. Hvis du klikker eller trykker på en kontroll, og så klikker eller trykker på rullegardinlisten for egenskaper, vil du se en liste over egenskaper som er relevante for kontrollen. Her er for eksempel en delvis liste over egenskaper av en etikett. Noen egenskaper gjelder for en rekke forskjellige kontroller, mens andre gjelder bare for en bestemt kontroll.

![Angi egenskaper](./media/learning-spo-app-explore-formulas/properties.png)

Du kan formatere farge basert på prisen ved å bruke en formel som denne for **Color**-egenskapen av etiketten: `If(Price > 5, Color.Red, Color.Green)`.

![Formatering av farge på pris](./media/learning-spo-app-explore-formulas/color-formatted.png)

## <a name="formulas-included-in-the-generated-app"></a>Formler inkludert i den genererte appen
Nå som du vet hvordan du kan bruke formler sammen med egenskaper, skal vi se på tre eksempler som PowerApps bruker i den genererte appen. Alle eksemplene er fra bla gjennom-skjermen og fungerer med OnSelect-egenskapen, som definerer hva som skjer når en bruker klikker eller trykker på en appkontroll.

* Den første formelen er knyttet til **IconNewItem1**-kontrollen: ![Nytt element-ikon](./media/learning-spo-app-explore-formulas/icon-add-item.png). Du klikker eller trykker på denne kontrollen for å gå fra bla gjennom-skjermen til rediger-/opprettskjermen og opprette et element. 
  
  * Formelen er `NewForm(EditForm1);Navigate(EditScreen1, ScreenTransition.None)`
  * Formelen *instansierer* et nytt redigeringsskjema og går deretter til rediger-/opprettskjermen, så du kan opprette et nytt element. En verdi på `ScreenTransition.None` betyr at det ikke er noen overgang mellom skjermene (som uttoning).
* Den andre formelen er tilknyttet **IconSortUpDown1**-kontrollen: ![Sorter galleri-ikon](./media/learning-spo-app-explore-formulas/icon-sort.png). Du klikker eller trykker på denne kontrollen for å sortere listen med elementer i bla gjennom-skjermgalleriet.
  
  * Formelen er `UpdateContext({SortDescending1: !SortDescending1})`
  * Formelen bruker `UpdateContext` til å oppdatere en *variabel* kalt `SortDescending1`. Verdien av variabelen skifter frem og tilbake når du klikker på kontrollen. Dette forteller galleriet på denne skjermen hvordan elementene skal sorteres (se videoen for mer informasjon). 
* Den tredje formelen er knyttet til **NextArrow1**-kontrollen: ![Gå til detaljpil-ikonet](./media/learning-spo-app-explore-formulas/icon-arrow.png). Du klikker eller trykker på denne kontrollen for å gå fra bla gjennom-skjermen til detaljskjermen.
  
  * Formelen er `Navigate(DetailScreen1, ScreenTransition.None)`
  * Formelen går til detaljskjermen, igjen uten overgang.

Det er mange flere formler i appen, så bruk litt tid på å klikke på kontroller og se hvilke formler som er angitt for de forskjellige egenskapene.

## <a name="wrapping-it-all-up"></a>Konklusjon
Dermed er vi ferdige med å utforske den genererte appen, hvor vi har tatt en titt bak kulissene på skjermene, kontrollene, egenskapene og formlene som gir appen sine funksjoner. Nå bør du altså ha en bedre forståelse av hvordan en generert app virker. Du kan ta med deg denne kunnskapen når du lager dine egne apper. 

Før vi går videre til neste inndeling, tar vi en tur innom SharePoint igjen og viser deg hvordan appen nå er integrert i listeopplevelsen. Som du ser, fungerer nå **FlooringApp** som en *visning* av listen, og du starter appen ved å klikke på **Åpne**. Dette er en enkel måte å administrere lister på, med en brukervennlig, tilpasset opplevelse.

![App som visning av SharePoint-liste](./media/learning-spo-app-explore-formulas/list-view.png)
