# Innledning

Dette dokumentet beskriver det norske arkivverkets standard for teknisk metadata - Archival Data Description Markup Language (ADDML) versjon 8.3.

Dokumentet består av følgende tre hoveddeler
* en innledende del med overordnede opplysninger
* en del som beskriver selve ADDML og de muligheter som ligger i standarden
* en del som beskriver Arkivverkets bruk av standarden.

ADDML er en standard for å beskrive samlinger av datafiler. En slik samling kalles et datasett og en fil som inneholder beskrivelsen av datasettet, kalles en datasettbeskrivelse.

## Mål

ADDML er en standard for å beskrive samlinger av datafiler som er organisert som flate filer. (En flat fil i denne sammenheng betyr at filen er i ren tekst og internt organisert enten ved fast 
posisjonering eller ved tegnseparasjon.)

En slik samling av filer kalles et datasett.

En fil som inneholder beskrivelsen av datasettet kalles en datasettbeskrivelse.

## Historie

ADDML har hatt tidligere versjoner, men kun et par av disse har vært i reell bruk. Nemlig versjon 7.2 og 7.3. Disse ble benyttet ved utviklingen av Arkadukt 1.0 og Arkade 1.0. Tidligere versjoner av ADDML ble utviklet samtidig med utviklingen av programvaren og ble følgelig aldri tatt i bruk.
Når programmene var av en slik karakter at de kunne testes ut var standarden ADDML allerede oppe i 7.2. Denne ble benyttet en stund, men fortsatt ble det avdekket mangler, slik at det etter en stund ble laget en ny versjon som fikk nummeret 7.3. Denne versjonen ble så benyttet i en del år på begynnelsen av 2000-tallet.

Ved utviklingen av ny versjon av programvaren Arkadukt og Arkade ble det også tatt beslutninger om å forenkle ADDML-standarden. Dette ble så gjort i et par runder og medførte så omfattende endringer at versjonsnummeret ble endret til 8. De første versjonene (8.0 og 8.1) ble igjen bare mellomversjoner inntil man kom frem til en stabil versjon med 8.2. En ny versjon (8.3) vil kom ved utgangen av 2014. Denne versjonen inneholder kun mindre justeringer sett i forhold til 8.2.

Med versjon 8.2 kom også et nytt regime for vedlikehold av standarden. Forut for denne versjonen ble det underskrevet en avtale mellom riksarkivarene i Norge og Sverige om en felles utvikling siden begge landenes riksarkiv benyttet standarden. Siden er også Finland kommet med i samarbeidet.

De første versjonene av standarden var beregnet på å beskrive strukturen for flate filer. I versjon 7.x ble det også lagt inn en mulighet for å beskrive xml-filer. I versjon 8.x er dette tatt ut igjen slik at struktur igjen kun fortsatt gjelder for flate filer. Å detalj-beskrive en xml-fil er det ikke sett noen hensikt med siden man normalt vil ha en slik beskrivelse i form av et xmlskjema (.xsd).

## Hvordan benytte ADDML

ADDML kan benyttes til mange formål. Den opprinnelige tanken bak ADDML var for å beskrive den tekniske strukturen til datasett som avleveres eller deponeres til et depot. I dag er standarden utvidet i forhold til sitt opprinnelige formål.

Den tekniske strukturen er fortsatt med slik at man kan beskrive strukturen for flate filer når disse skal overføres fra et system til et annet.

I versjon 8.x er det også mulig å beskrive andre typer filer, dog uten å gå i detalj. Det er mer lagt vekt på å kunne beskrive typen av filer, sammenhengen disse imellom, osv.

Både delen reference og delen dataObjects er generisk slik at man kan bygge ut etter eget behov. Dessuten er det også lagt inn muligheten for egenskaper som også kan benyttes på samme måte.

Når man tar i bruk ADDML er det derfor viktig at man selv setter begrensninger. Man må selv definere hvordan man benytter de generiske delene av standarden. Dette anbefales man å gjøre ved å lage en egen profil som beskriver ens egen bruk av standarden.