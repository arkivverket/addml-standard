# Beskrivelse av ADDML

## Hva beskrives i ADDML 8.3. (Hovedstruktur)

ADDML består av 3 hoveddeler. En del som beskriver tilhørende informasjon (kataloginformasjon), dvs. informasjon om dataene i datasettet - *reference*. En del som er selve beskrivelsen av flate filer i detalj - *flatFiles*. En del som gir mulighet for å knytte opp andre filer enn flate filer til beskrivelsen - *dataObjects*.

![Hoveddelene i ADDML](/standard/figurer/figur_1.svg)

Figur - Hoveddelene i ADDML

I *reference* vil det kunne registreres bevaringsverdige metadata på kontekstuell og innholdsmessig nivå. I *flatFiles* vil man kunne registrere en detaljert beskrivelse av strukturen i datafilene dersom de enten er i fast format eller i tegnseparert format. Alle filer som ikke er i fast format eller tegnseparert format vil bli beskrevet i *dataObjects*. Dog vil det her ikke være mulig å gi en detaljert beskrivelse.

I en addml-fil vil disse toppnivåene se ut som følger:

```xml
<addml name="addmlnavn">
 <dataset name="datasettnavn">
 <reference name="refnavn">
 …..
 </reference>
 <flatFiles>
 …..
 </flatFiles>
 <dataObjects>
 …..
 </dataObjects>
 </dataset>
</addml>
```

Merk at samtlige hoveddeler ikke er obligatoriske i seg selv, slik at en tom addml-fil er tillatt.

Man kunne endret standarden ved å kreve minst en av hoveddelene, men en tom addml-fil er ansett som unaturlig. Tidligere var *reference* obligatorisk, men dette er en av endringene fra 8.2 til 8.3.

## Tilhørende informasjon – bevaringsverdige metadata.

* Figur - Oversikt over elementene i *reference*.

Med tilhørende informasjon menes informasjon om datasettet. Dette kan være opplysninger om hvem som har laget datasettet, hva slags type system det er hentet fra, bakgrunn for dataene i datasettet, osv. Dette er IKKE beskrivende informasjon av selve datasettet.

I ADDML er all slik informasjon samlet i *reference*. *reference* har to underelementer. Disse beskriver følgende:
* kontekstuell informasjon - *context*
* innholdsrelatert informasjon - *content*

Grupperingene har ingen faste felter, men det kan defineres egne felter som kan eller skal medfølge et datasett. Se eget avsnitt om generiske elementer.

Et eksempel på *reference* med underliggende elementer kan da se ut som følger:

```xml
<reference>
  <context>
    <additionalElements>
      <additionalElement name="agents">
        <additionalElements>
          <additionalElement name="agent">
            <additionalElements>
              <additionalElement name="recordCreator">
                <value>Riksarkivet</value>
              </additionalElement>
            </additionalElements>
          </additionalElement>
        </additionalElements>
      </additionalElement>
    </additionalElements>
  </context>
  <content>
    <additionalElements>
      <additionalElement name="archivalPeriod">
        <additionalElements>
          <additionalElement name="startDate">
            <value>20040401</value>
          </additionalElement>
          <additionalElement name="endDate">
            <value>20100331</value>
          </additionalElement>
          <additionalElement name="period">
            <additionalElements>
              <additionalElement name="inngåendeSkille">
                <value>Skarpt</value>
              </additionalElement>
              <additionalElement name="utgåendeSkille">
                <value>Mykt</value>
              </additionalElement>
            </additionalElements>
          </additionalElement>
        </additionalElements>
      </additionalElement>
    </additionalElements>
  </content>
</reference>
```

## Strukturen for å beskrive flate filer

* Figur - Oversikt over elementene i *dataset* (forenklet form)

Struktur delen i ADDML er en struktur for å beskrive filer som er av typen flate filer. Med flate filer menes at filen enten er med fast format (tabellform) – hvor alle felt starter i samme posisjon – eller tegnseparert format – hvor feltene er adskilt med et nærmere angitt tegn som skille mellom feltene (csv-filer er f.eks. på denne formen).

Figur 3 viser modellen i en forenklet versjon. Strukturen har et *flatFile* som øverste nivå. En *flatFile* vil inneholde *flatFileDefinition* , som igjen vil inneholde en eller flere *recordDefinition*. Og deretter vil så *recordDefinition* inneholde en eller flere *fieldDefinition*.

I en vanlig relasjonell database vil det normalt ikke være behov for post-nivået. Hvilket betyr at fil-nivået og post-nivået har smeltet sammen til ett og samme nivå – en tabell i en slik database. I andre sammenhenger kan imidlertid en fil inneholde mange forskjellige typer av poster som man ønsker å splitte opp til hver sin tabell. Koblingen mot en database vil derfor være mot post-nivået og ikke mot fil-nivået. Av denne grunnen er derfor også alle informasjoner om nøkler lagt på post-nivået.

Den komplette modellen inneholder tre hoveddeler. Dessuten består hvert nivå av et multiplums-nivå og et detalj-nivå, med unntak av *flatFiles*. De tre delene inneholder gjennomgående informasjoner om den fysiske representasjonen av nivået, den definisjonsmessige og en overordnet typedefinisjon. Det er imidlertid i dag ikke funnet behov for den fysiske representasjonen på annet enn fil-nivå. Skulle et slikt behov melde seg senere vil det være behov for en revisjon av standarden.

* Figur - Oversikt over elementene i *flatFiles* (komplett form).

Dette betyr at strukturen er blitt mer kompleks enn i tidligere versjoner, men samtidig mer fleksibel og generell for bruk.

De øverste nivåene i flatFiles vil da kunne se ut for eksempel som dette:

```xml
<flatFiles>
  <flatFile name="filnavn" definitionReference="fildef1">
  </flatFile>
  <flatFileDefinitions>
    <flatFileDefinition name="fildef1" typeReference="typefildef1">
      <recordDefinitions>
        <recordDefinition name="postdef1" typeReference="typepostdef1">
          ...
          <fieldDefinitions>
            <fieldDefinition name="fodselnr" typeReference="typefeltdef1">
              ...
            </fieldDefinition>
          </fieldDefinitions>
        </recordDefinition>
      </recordDefinitions>
    </flatFileDefinition>
  </flatFileDefinitions>
  <structureTypes>
    <flatFileTypes>
      <flatFileType name="typefildef1">
        ...
      </flatFileType>
    </flatFileTypes>
    <recordTypes>
      <recordType name="typepostdef1"/>
    </recordTypes>
    <fieldTypes>
      <fieldType name="typefeltdef1">
        ...
      </fieldType>
    </fieldTypes>
  </structureTypes>
</flatFiles>
```

## Andre filer enn flate filer

Som nevnt over inneholder strukturen kun definering av flate filer med fast eller tegnseparert format. Andre filtyper kan ikke beskrives i detalj vha. ADDML 8.3-elementer. Dog er det mulig å knytte andre typer filer og eller informasjonsobjekter opp mot datasettet som defineres i en ADDML-fil. Dette gjøres ved å definere disse filene/informasjonsobjektene som logiske objekter ved å bruke elementene *dataObjects* og *dataObject*. På et logisk objekt kan det så knyttes opp en del egenskaper for å forklare hva slags filer/informasjonsobjekter dette er. (Filene kan være datafiler i xml-format, dtd eller xml-skjema, dokumentfiler, bildefiler, lydfiler, videofiler, osv.)

* Figur - Oversikt over elementene i *dataObjects*.

Følgende kan være et eksempel på bruken av *dataObjects*:

```xml
<dataObjects>
  <dataObject name="Rapporter">
    <dataObjects>
      <dataObject name="rapportfil">
        ...
      </dataObject>
    </dataObjects>
  </dataObject>
</dataObjects>
```

## Generiske elementer

I de forskjellige beskrivelsene over har det dukket opp flere steder elementer som danner en loop. Det gjelder både for *additionalElements* – *additionalElement* og *dataObjects* – *dataObject*. I disse tilfellene er det snakk om en generisk struktur hvor den som benytter standarden selv kan bygge opp en hierarkisk struktur med de nevnte elementene.

## Egenskaper

For mange elementer er det i tillegg muligheten til å legge på egenskaper i form av attributtet *properties*. Også egenskaper har som tilleggselementer en generisk struktur ved *properties* – *property*.

Herunder vises et eksempel på bruk av egenskaper:

```xml

```

## Prosesser

Standarden gir i tillegg brukerne muligheten til å definere egne operasjoner som skal utføres på informasjonen. Dette gjøres ved bruk av elementet *processes* som kan inneholde et sett av elementene *process*, som definerer den enkelte operasjonen. Eksemplel på operasjoner som kan tenkes er kontroller (f.eks. kontrollere sjekksum, koder).

Kontroll av koder for elementet yrke i posttypen postdef1 i filen fildef1 kan f.eks. se slik ut:

```xml
<flatFileProcesses flatFileReference="fildef1">
  <recordProcesses definitionReference="postdef1">
    <fieldProcesses definitionReference="yrke">
      <processes>
        <process name="Control_Codes"/>
      </processes>
    </fieldProcesses>
  </recordProcesses>
</flatFileProcesses>
```

Når det gjelder generiske elementer, egenskaper og prosesser er det helt opp til brukerne av standarden å definere sine egne behov. Standarden gir bare muligheten i form av å definere disse som generiske elementer / attributter.
