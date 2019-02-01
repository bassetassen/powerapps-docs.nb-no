---
title: Bygge inn en lerretapp i et modelldrevet skjema | MicrosoftDocs
ms.custom: ''
ms.date: 12/10/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 00e62904-2ce9-4730-a113-02b1fedbf22e
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="embed-a-canvas-app-on-a-model-driven-form"></a>Bygge inn en lerretapp i et modelldrevet skjema

Lerretapper gjør det mulig for oppretterne å enkelt utvikle og opprette egendefinerte oppsett ved hjelp WYSIWYG-lerretapputforming med kort kode. Lerrettapper gjør det også mulig for utviklere koble og vise data fra over 200 datakilder i sine skjemaer.

> [!NOTE]
> Denne funksjonen er en forhåndsvisningsfunksjon. <br />
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

Med innebygde lerretapper kan utviklere tilføre styrken fra lerretapper til de modelldrevne skjemaene. Ved hjelp av innebygde lerretapper kan du enkelt opprette omfattende visuelle områder i et skjema og vise data fra en rekke kilder ved siden av dataene fra Common Data Service.

   > [!div class="mx-imgBorder"] 
   > ![](media/embed-canvas-app-in-form.png "Innebygd lerretapp i et modelldrevet appskjema")

Lerretapper er innebygd i modelldrevne skjemaer på samme måte som andre egendefinerte kontroller er lagt til. En innebygd lerretapp inneholder omfattende dataintegreringsfunksjoner som tilfører kontekstavhengige data fra den innebygde lerretappen.

Fremgangsmåten for å bygge inn en lerretapp i det modelldrevne skjemaet varierer avhengig av datakonteksten som du vil at det vertsmodelldrevne skjemaet skal tilføre den innebygde lerretappen.
-   Sende gjeldende oppføring som datakontekst. Mer informasjon: [Sende gjeldende oppføring som datakontekst med en innebygd lerretapp](pass-current-embedded-canvas-app.md)
-   Send en liste over oppføringer relatert til den gjeldende oppføringen, som datakontekst. Mer informasjon: [Sende en liste over relaterte oppføringer som datakontekst med en innebygd lerretapp](pass-related-embedded-canvas-app.md) 

<!-- After you have added an embedded canvas app to your model-driven form, learn how to share your embedded canvas app with other users (LINK TO ARTICLE #4).  -->

<!-- For things to keep in mind when working with embedded canvas apps and to help troubleshoot any issues you might encounter, see (LINK TO ARTICLE #5). -->

## <a name="see-also"></a>Se også
[Hva er lerretapper i PowerApps?](../canvas-apps/getting-started.md) <br />
[Legge til og konfigurere en lerretappkontroll i PowerApps](../canvas-apps/add-configure-controls.md) <br />
[Oversikt over lerretappkoblinger for PowerApps](../canvas-apps/connections-list.md) 
