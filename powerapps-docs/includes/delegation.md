## <a name="delegation"></a>Delegering
Når det er mulig, vil PowerApps delegere filtrerings- og sorteringoperasjoner til datakilden og siden gjennom resultatene ved behov. Når du for eksempel starter en app som viser en **[Galleri](../maker/canvas-apps/controls/control-gallery.md)**-kontroll fylt med data, blir bare det første settet med oppføringer overført til enheten til å begynne med. Når brukeren ruller, hentes flere data fra datakilden. Resultatet er raskere oppstartstid for appen og tilgang til et svært store datasett.

Det er imidlertid ikke alltid mulig å delegere. Datakilder varierer avhengig av hvilke funksjoner og operatorer de støtter med delegering. Hvis fullstendig delegering av en formel ikke er mulig, vil redigeringsmiljøet vise en advarsel for delen som ikke kan delegeres. Vurder å endre formelen når det er mulig, for å unngå funksjoner og operatorer som ikke kan delegeres.  [Delegeringslisten](../maker/canvas-apps/delegation-list.md) inneholder informasjon om hvilke datakilder og som kan delegeres.

Hvis det ikke er mulig å delegere, vil PowerApps bare hente et lite sett med oppføringer for å arbeide lokalt. Filtrerings- og sorteringsfunksjoner fungerer på et mindre sett med oppføringer. Det som er tilgjengelig i **[Galleri](../maker/canvas-apps/controls/control-gallery.md)** er kanskje ikke den fullstendige historikken, og dette kan være forvirrende for brukere. 

Hvis du vil ha mer informasjon, kan du se [delegeringsoversikten](../maker/canvas-apps/delegation-overview.md).

