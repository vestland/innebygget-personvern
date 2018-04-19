# Håndbok for innebygget personvern

Denne håndboken er ikke ment å være en fullstendig beskrivelse av prosessen rundt innebygget personvern, men skal være et hjelpemiddel til å finne den informasjonen man har behov for. Det bør gjøres en gjennomgang for hver løsning på hvilke deler av håndboken som er mest hensiktsmessig å fokusere på.

### Formål

Formålet med innebygget personvern er at man skal være proaktiv i forhold til beskyttelse av brukerne. Man skal på forhånd ha tenkt gjennom hvilke opplysninger som er nødvendige å samle inn, hvordan disse skal behandles og hvor lenge det er nødvendig å oppbevare dem. Løsningen skal lages på en slik måte at brukerne er fullt klar over hva opplysningene skal brukes til, og designet bør være utformet slik at ikke brukeren ledes til å oppgi flere opplysninger enn det som er nødvendig for å oppnå formålet med løsningen.

### Målgruppe

Målgruppen for håndboken er alle som er involvert prosessen med anskaffelse av et nytt system og eventuelle utviklere/testere.

### Nyttige lenker

* [Datatilsynets samleside for nye løsninger](https://www.datatilsynet.no/regelverk-og-skjema/lage-nye-losninger/)
* [Datatilsynets syv steg til innebygget personvern](https://www.datatilsynet.no/regelverk-og-skjema/lage-nye-losninger/innebygd-personvern/) med [sjekkliste](https://www.datatilsynet.no/globalassets/global/skjema-maler/sjekkliste-for-innebygd-personvern.pdf)
* [Datatilsynets veileder til utvikling med innebygget personvern](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/)

### Detaljer
[Krav](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7732)
* Det er viktig å tenke på hva slags type personopplysninger man skal samle inn, og nødvendigheten av disse.
* Behandlingen av personopplysningene må ha et rettslig grunnlag.
* Det bør gjennomføres en vurdering av eventuelle personvernkonsekvenser. Se ["Hvordan vurdere personvernkonsekvenser"](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/hvordan-vurdere-personvernkonsekvenser-pia/)

[Design](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7733)
* Tilgangen til systemet skal være begrenset. Systemet gir bare brukerne tilgang til den informasjonen some er nødvendig for å utføre den enkeltes oppgave.
* Det skal være tilgangsautentisering. Se [passordpolicy](https://www.qmplus.com/qmplus/ShowFile/3879/0/0/0/0/Passordpolicy.pdf?Company=hfk) i kvalitetsportalen.
* Sørge for at løsningen er utformet på en slik måte at man henter inn så lite personopplysninger som mulig for å oppnå formålet. Dette innebærer blant annet minst mulig bruk av fritekstfelt.
* Personopplysninger skal ikke kommuniseres, behandles eller lagres i klartekst. Det kan for eksempel brukes pseudonymisering, kryptering og aggregering av personopplysninger.
* Det skal være på plass et system for samtykke og tilbaketrekking av samtykke ved innsamling av personopplysninger.
* Den registrerte skal ha mulighet til å kontrollere personopplysningene. Det innebærer blant annet å be om innsyn, oppdatere og slette egne opplysninger. Dette kan være en manuell eller en automatisk prosess.
  * Det skal være på plass rutiner for sletting/arkivering når personopplysningene ikke lenger er relevant for formålet eller den registrerte ber om det.
  * Det skal være på plass rutiner for forespørsler om innsyn.
  * Det må gjøres en vurdering på hvordan løsningen, og systemer som avhenger av løsningen, blir påvirket dersom deler av datagrunnlaget blir fjernet. Løsningen må implementeres på en slik måte at fjerning av data ikke bryter med funksjonaliteten.

[Koding](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7734)
* Opprette og vedlikeholde en liste over godkjente verktøy for bruk under utviklingen. Man bør til enhver tid bruke siste __offisielle__ versjon av verktøyene. Denne listen vil ofte være forskjellig fra prosjekt til prosjekt.
* Utføre regelmessig statisk kodeanalyse og kodegjennomgang. Eksempel på verktøy man kan bruke:
  * https://github.com/coreos/clair
  * https://www.owasp.org/index.php/OWASP_Dependency_Check

[Test](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7735)
* Utarbeide regime for automatisk kjøring av testsett.
* Det bør utføres dynamisk testing, fuzz testing og penetrasjonstesting for å verifisere at personvernkrav og sikkerhetskrav er implementert. Eksempler på verktøy/ressurser man kan bruke:
  * https://www.owasp.org/index.php/OWASP_Testing_Project
  * https://www.owasp.org/index.php/OWASP_Zed_Attack_Proxy_Project
  * https://www.owasp.org/index.php/OWASP_Testing_Guide_Appendix_C:_Fuzz_Vectors

[Produksjonssetting](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7736)
* Utarbeid en plan for hendelseshåndtering med definerte ressurser og et kontaktpunkt. Her bør man ha en oversikt over de ulike rutinene for sletting/arkivering og forespørsler om innsyn.
* Sikkerhetsgjennomgang.
* Sikkerhets- og personvernombud skal verifisere at alle definerte personvern- og sikkerhetskrav er implementert og fungerer etter hensikten.

[Forvaltning](https://www.datatilsynet.no/regelverk-og-skjema/veiledere/programvareutvikling-med-innebygd-personvern/?id=7737)
* Følge planen for hendelseshåndtering.
* Regelmessig oppdatering og testing.

### Krav fra fylkeskommunen
* Vi forventer strukturerte metadata for alle dataflyter som inneholder GDPR klassifiseringen av data/prosess/behandling.

### Forbedringer det jobbes med
* Et eget lagringssted for personopplysninger. Da kan man bruke interne IDer for oppslag. Dette vil kunne føre til økt grad av pseudonymisering, og vil forbedre prosessen med behandlingen av personopplysninger. 
