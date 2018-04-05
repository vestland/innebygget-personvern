# Håndbok for innebygget personvern

Denne håndboken er ikke ment å være en fullstendig beskrivelse av prosessen rundt innebygget personvern, men skal være et hjelpemiddel til å finne den informasjonen man har behov for.

### Formål

Formålet med innebygget personvern er at man skal være proaktiv i forhold til beskyttelse av brukerne. Man skal på forhånd ha tenkt gjennom hvilke opplysninger som er nødvendige å samle inn, hvordan disse skal behandles og hvor lenge det er nødvendig å oppbevare dem. Løsningen skal lages på en slik måte at brukerne er fullt klar over hva opplysningene skal brukes til, og designet bør være utformet slik at ikke brukeren ledes til å oppgi flere opplysninger enn det som er nødvendig for å oppnå formålet med løsningen.

### Nyttige lenker

* [Datatilsynets samleside for nye løsninger](https://www.datatilsynet.no/regelverk-og-skjema/lage-nye-losninger/)
* [Datatilsynets syv steg til innebygget personvern](https://www.datatilsynet.no/regelverk-og-skjema/lage-nye-losninger/innebygd-personvern/) med [sjekkliste](https://www.datatilsynet.no/globalassets/global/skjema-maler/sjekkliste-for-innebygd-personvern.pdf)
* [Datatilsynets veileder til utvikling med innebygget personvern](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/)

### Detaljer
[Krav](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7732)
* Det er viktig å tenke på hva slags type personopplysninger man skal samle inn, og nødvendigheten av disse.
* Behandlingen av personopplysningene må ha et rettslig grunnlag.
* Det bør gjennomføres en vurdering av eventuelle personvernkonsekvenser. Se [Hvordan vurdere personvernkonsekvenser](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/hvordan-vurdere-personvernkonsekvenser-pia/)

[Design](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7733)
* Sørge for at løsningen er utformet på en slik måte at man henter inn så lite personopplysninger som mulig for å oppnå formålet.
* Det skal være på plass rutiner for sletting/arkivering når personopplysningene ikke lenger er relevant for formålet.
* Personopplysninger bør ikke kommuniseres, behandles eller lagres i klartekst. Det kan for eksempel brukes pseudonymisering, kryptering og aggregering av personopplysninger.
* Den registrerte bør bli tilstrekkelig informert om hvordan programvaren fungerer og hvordan personopplysninger behandles.
* Den registrerte skal ha mulighet til å kontrollere personopplysningene. Det innebærer blant annet å be om innsyn, oppdatere og slette egne opplysninger. Dette kan være en manuell eller en automatisk prosess.  

[Koding](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7734)
* Opprette og vedlikeholde en liste over godkjente verktøy for bruk under utviklingen. Man bør til enhver tid bruke siste versjon av verktøyene.
* Utføre regelmessig statisk kodeanalyse og kodegjennomgang.

[Test](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7735)
* Utarbeide regime for automatisk kjøring av testsett.
* Det bør utføres dynamisk testing, fuzz testing og penetrasjonstesting for å verifisere at personvernkrav og sikkerhetskrav er implementert.

[Produksjonssetting](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7736)
* Utarbeid en plan for hendelseshåndtering.
* Sikkerhetsgjennomgang.
* Sikkerhets- og personvernombud skal verifisere at alle definerte personvern- og sikkerhetskrav er implementert og fungerer etter hensikten.

[Forvaltning](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7737)
* Følge planen for hendelseshåndtering.
* Regelmessig oppdatering og testing.

### Krav fra fylkeskommunen
* Vi forventer strukturerte metadata for alle dataflyter som inneholder GDPR klassifiseringen av data/prosess/behandling.

### Forbedringer det jobbes med
* Et eget lagringssted for personopplysninger. Da kan man bruke interne IDer for oppslag. Dette vil kunne føre til økt grad av pseudonymisering, og vil forbedre prosessen med behandlingen av personopplysninger. 
