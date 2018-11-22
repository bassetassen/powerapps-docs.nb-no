## <a name="mapping-functions-for-dynamics-365-customer-engagement-plan"></a>Kartfunksjoner for Dynamics 365 Customer Engagement Plan 
 Field Service og Project Service Automation har nøkkelfunksjoner som er avhengige av posisjonen. Posisjonen til for eksempel forretningsforbindelser for service (som angir hvor service eller oppgaver finner sted) eller start- eller sluttposisjonen for ressurser (dem som utfører service eller oppgaver).  Det er nødvendig å bruke en karttjeneste (i dette tilfellet Bing-kart) hvis systemet skal kunne vise dem på et kart, eller beregne avstanden mellom punkter.  
  
 Nedenfor vises arbeidsflyten til og fra tjenesten Bing-kart:  
  
|Fra Dynamics 365|Bing-kart returnerer|Obs!|  
|-----------------------|-----------------------|----------|  
|Adresse (forretningsforbindelse eller ressurs)|Breddegrad og lengdegrad for adressen (posisjon)|Dette kalles geokoding for en adresse.|  
|Sett med posisjoner (breddegrad/lengdegrad)|Avstand mellom posisjoner|Dette kan brukes for å finne optimale ruter for ressurser eller til å beregne reisetid.|  
|Sett med posisjoner (breddegrad/lengdegrad)|Kartvisning med posisjonene som stifter på kartet|Dette brukes til å vise forretningsforbindelsene og ressursene i en kartvisning.|  
  
> [!NOTE]
>  Bortsett fra dataene som angis ovenfor, sendes det ikke andre data til tjenesten Bing-kart.
