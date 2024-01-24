# Innledning

Dette dokumentet beskriver det norske arkivverkets standard for teknisk metadata -
Archival Data Description Markup Language (ADDML) versjon 8.3 og den profilen
arkivverket benytter av standarden, navngitt 8.3.1.

Dokumentet fungerer som et suplement til den generelle beskrivelsen. Der hvor profilen angir
et sterkere krav enn standarden generelt, vil dette bli angitt etter samme prinsipper som i den
generelle beskrivelsen.

## Forutsetninger

Dette dokumentet forklarer hvordan ADDML skal benyttes ved innlevering av materiale til Arkivverket. Denne beskrivelsen vil også kunne være veiledende ved innlevering av materiale til kommunale arkiver.

For å kunne forstå innholdet anbefales det å lese dokumentet om ADDML generelt først for å få et grunnlag for hva ADDML er og hvordan den er bygget opp.

## Den norske pakkemodellen

Gjennom DIAS-prosjektet som var et samarbeid mellom Arkivverket og kommunale arkiver, ble det vedtatt en modell for arkivpakker (AIP). Denne modellen er siden av Arkivverket blitt benyttet til også å definere en modell for en innleveringspakke (SIP). De to modellene er dermed noenlunde like i grunnstruktur.

Selve innholdet og dets metadata pakkes inn i en tar-fil. I tillegg overføres også en fil som kalles infofilen som inneholder informasjon om tar-filen og informasjon knyttet til overføringen til depotet.

I selve pakken benyttes standardene dias-mets som er en profil av den internasjonale standarden mets og inneholder en oversikt over alle filer som inngår i pakken. Også infofilen er en profil av mets. I pakken følger dessuten dias-premis som er en profil av den internasjonale standarden og inneholder informasjon om hendelser og rettigheter til innholdet. Dessuten kan det forekomme filer som følger standardene ead og eac-cpf som inneholder arkiv- og aktørbeskrivelse. (Disse er valgfrie for en SIP.) Og endelig kommer den tekniske strukturbeskrivelsen i filen arkivuttrekk.xml som skal følge ADDML For ADDML må derfor hvert depot også definere sin profil av standarden og dette dokumentet beskriver en slik profil som da benyttes for overføring og i Arkivverket.

* Figur - Innholdet i en pakke.

## Hvordan benytte ADDML

ADDML benyttes for å beskrive datasett som avleveres eller deponeres i Arkivverket. Etter dagens regelverk er ADDML kun påkrevd for avlevering/deponering av uttrekk fra fagsystem (ikke Noark system) og for uttrekk som førlger Noark. Det har imidlertid vært planer om at filen arkivuttrekk.xml skal medfølge for alle typer avleveringer/deponeringer til Arkivverket. Med endring av arkivloven kan det dog være at kravene blir helt annerledes.

I ADDML kan man legge inn prosesser som fungerer som instruksjoner for et testverktøy. I dagens versjon av Arkade (5.0) er det valgfritt om programmet bruker disse eller om de skal forholde seg til brukergrensesnittet. Alle prosessene er beskrevet i et eget kapittel i dette dokumentet, slik at det fortsatt kan være mulig å benytte seg av instruksjoner i ADDML-filen. 

## Språkforvirring!?
I dette dokumentet forekommer det både engelske og norske begreper. Det er imidlertid ikke så tilfeldig som det kan virke.

ADDML standarden er laget i engelsk språkdrakt for at det skal være mulig også for andre å kunne benytte standarden. Dette betyr at alle tagger som hører til ADDML er engelske termer. Dette inkluderer også tagger definert for norske formål, for å holde det konsistent. Derimot vil verdiene være på norsk, med unntak for gitte kodesett – de som blir ansett som en del av standarden.

## Endringer i dokumentet

Fra versjon 1.0 til 1.1:
• Korrigert skrivefeil