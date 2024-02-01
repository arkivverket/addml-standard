# Elementene i ADDML 8.3

I det etterfølgende er hvert enkelt element i ADDML beskrevet.

Hvert element har en figur som viser hvilke andre elementer det har en relasjon til, både som overliggende element og eventuelle underliggende element.

I tabellform er det gitt grunnleggende informasjon om elementet. Og deretter i en ny tabell alle attributter som elementet har. Også underliggende element er vist i en tabellform.

Til slutt er det vist et enkelt eksempel med bruk av elementet. For noen element er det vist til eksempler under andre element.

## addml  <a id="addml"/>

På toppnivået er det kun ett element - addml.

![Hierarki for addml](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/addml.svg)

| Elementnavn | Beskrivelse |
| :-- | :-- |
| addml | addml er toppnivået i strukturen. Dette elementet skal eksistere en og kun en gang i henhold til reglene for XML. |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 0-1 | name angir navnet til denne addml-filen. Det er ingen krav til navnsetting i utgangspunktet. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [dataset](#dataset) | 1-n |

Ingen overordnede elementer.


## dataset  <a id="dataset"/>

Hovednivået dataset som tilsvarer et datasett har også bare ett enkelt element. Til gjengjeld kan dette forekomme flere ganger.

![Hierarki for dataset](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/dataset.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [addml](#addml) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| dataset | dataset er hovednivået i beskrivelsen. I Arkivverket tilsvarer dette et arkivuttrekk. Imidlertid kan en og samme beskrivelse også inneholde flere dataset. Dette for at det skal være mulig å samle beskrivelser når de skal benyttes sammen, for eksempel i en brukssituasjon. |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 0-1 | name angir navnet til det spesifikke datasettet. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [reference](#reference) | 0-1 |
| [flatFiles](#flatFiles) | 0-1 |
| [dataObjects](#dataObjects) | 0-1 |

### Eksempel

Ved flere datasett i samme addml-fil er det anbefalt å bruke attributten name for hvert datasett for å holde de adskilt.

## reference  <a id="reference"/>

![Hierarki for reference](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/reference.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [dataset](#dataset) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| reference |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 0-1 | name angir navnet til det spesifikke referanseobjektet. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [context](#context) | 0-1 |
| [content](#content) | 0-1 |


## context  <a id="context"/>

![Hierarki for context](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/context.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [reference](#reference) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| context | context inneholder informasjon av kontekstuell art om avleveringen. Hva slags informasjon som skal være med under context må brukeren selv definere ved hjelp av additionalElement. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [additionalElements](#additionalElements) | 0-1 |
| [processes](#processes) | 0-1 |

Ingen attributter.

### Eksempel

```xml
<reference>
	<context>
		<additionalElements>
			<additionalElement name="arkivskaper" datatype="string">
				<value>Kulturdepartementet</value>
			</additionalElement>
		</additionalElements>
	</context>
<reference>
```

## content  <a id="content"/>

![Hierarki for content](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/content.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [reference](#reference) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| content | content inneholder informasjon av innholdsmessig art om avleveringen. Hva slags informasjon som skal være med under content må brukeren selv definere ved hjelp av additionalElement. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [additionalElements](#additionalElements) | 0-1 |
| [processes](#processes) | 0-1 |

Ingen attributter.

### Eksempel

```xml
<reference>
	<content>
		<additionalElements>
			<additionalElement name="period">
				<additionalElements>
					<!= Inngående og utgående skille =>
				</additionalElements>
			</additionalElement>
		</additionalElements>
	</content>
<reference>
```

## flatFiles  <a id="flatFiles"/>

![Hierarki for flatFiles](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFiles.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [dataset](#dataset) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFiles |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [flatFile](#flatFile) | 1-n |
| [flatFileDefinitions](#flatFileDefinitions) | 1 |
| [structureTypes](#structureTypes) | 1 |
| [queries](#queries) | 0-1 |
| [processes](#processes) | 0-1 |
| [flatFileProcesses](#flatFileProcesses) | 0-n |

Ingen attributter.


## flatFile  <a id="flatFile"/>

![Hierarki for flatFile](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFile.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFiles](#flatFiles) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFile |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |
| definitionReference | 1 | Referanse til flatFileDefinition, en referanse som kan være mange til en. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [properties](#properties) | 0-1 |


## flatFileDefinitions  <a id="flatFileDefinitions"/>

![Hierarki for flatFileDefinitions](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFileDefinitions.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFiles](#flatFiles) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFileDefinitions |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [flatFileDefinition](#flatFileDefinition) | 1-n |

Ingen attributter.


## flatFileDefinition  <a id="flatFileDefinition"/>

![Hierarki for flatFileDefinition](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFileDefinition.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileDefinitions](#flatFileDefinitions) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFileDefinition |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |
| typeReference | 0-1 | Referanse til flatFileType, en referanse som kan være mange til en. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [properties](#properties) | 0-1 |
| [external](#external) | 0-1 |
| [recordDefinitionFieldIdentifier](#recordDefinitionFieldIdentifier) | 0-1 |
| [recordDefinitions](#recordDefinitions) | 1 |


## external  <a id="external"/>

I noen tilfeller er det behov for å knytte et datauttrekk til et annet. Det er da definert to elementer i ADDML som er tenkt å benyttes til dette formålet. Elementene er external som angir at den filen som her defineres ikke er med i selve datauttrekket, og incomplete som angir at definisjonen ikke er komplett. Tanken er at man for eksterne filer bare definerer de elementene som er nødvendig for å opprette referanser mellom filen som defineres utenfra og de interne filene.
Et eksempel på en slik kobling kan være at man i uttrekket definerer postkatalogen som en ekstern fil. Dette fordi den benyttes av flere systemer samtidig. Samtidig er det også opprettet referanser (nøkler) fra interne elementer med postnr til denne eksterne postkatalogen.

![Hierarki for external](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/external.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileDefinition](#flatFileDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| external | Dette elementet benyttes når det er referanser til filer som ikke er med i uttrekket. Elementet er da et flagg som benyttes for å angi at filen ikke er med.  |

Ingen attributter, underordnede elemente eller underordnede elementer.

### Eksempel

```xml
<recordDefinition name=”post2”>
	<incomplete>
	<fixedLength>244</fixedLength>
	<fieldDefinition name=”postnr”>
		<startPos>1</startPos>
		<endPos>4</endpos>
	</fieldDefinition>
</recordDefinition>
```

I eksemplet er det definert en ufullstendig post (post2) med et
felt – postnr.

## recordDefinitionFieldIdentifier  <a id="recordDefinitionFieldIdentifier"/>

![Hierarki for recordDefinitionFieldIdentifier](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordDefinitionFieldIdentifier.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileDefinition](#flatFileDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordDefinitionFieldIdentifier |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## recordDefinitions  <a id="recordDefinitions"/>

![Hierarki for recordDefinitions](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordDefinitions.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileDefinition](#flatFileDefinition) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordDefinitions |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 1-n |

Ingen attributter.


## recordDefinition  <a id="recordDefinition"/>

![Hierarki for recordDefinition](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordDefinition.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinitions](#recordDefinitions) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordDefinition |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |
| typeReference | 0-1 | Referanse til recordType. Kun påkrevd om ledende nuller eller etterfølgende og ledende blanke tegn er fjernet. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [properties](#properties) | 0-1 |
| [recordDefinitionFieldValue](#recordDefinitionFieldValue) | 0-1 |
| [incomplete](#incomplete) | 0-1 |
| [fixedLength](#fixedLength) | 0-1 |
| [repeatingGroups](#repeatingGroups) | 0-1 |
| [keys](#keys) | 0-1 |
| [fieldDefinitions](#fieldDefinitions) | 1 |
| [headerLevel](#headerLevel) | 0-1 |


## recordDefinitionFieldValue  <a id="recordDefinitionFieldValue"/>

![Hierarki for recordDefinitionFieldValue](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordDefinitionFieldValue.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordDefinitionFieldValue |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## incomplete  <a id="incomplete"/>

![Hierarki for incomplete](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/incomplete.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| incomplete |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## fixedLength  <a id="fixedLength"/>

![Hierarki for fixedLength](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fixedLength.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 0-1 |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fixedLength |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## repeatingGroups  <a id="repeatingGroups"/>

![Hierarki for repeatingGroups](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/repeatingGroups.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| repeatingGroups |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [repeatingGroup](#repeatingGroup) | 1-n |

Ingen attributter.


## repeatingGroup  <a id="repeatingGroup"/>

![Hierarki for repeatingGroup](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/repeatingGroup.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [repeatingGroups](#repeatingGroups) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| repeatingGroup |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 0-1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [repeatingGroupOccurrenceField](#repeatingGroupOccurrenceField) | 1 |
| [fixedOccurrences](#fixedOccurrences) | 1 |
| [fieldDefinitionReferences](#fieldDefinitionReferences) | 1 |


## repeatingGroupOccurrenceField  <a id="repeatingGroupOccurrenceField"/>

![Hierarki for repeatingGroupOccurrenceField](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/repeatingGroupOccurrenceField.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [repeatingGroup](#repeatingGroup) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| repeatingGroupOccurrenceField |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| definitionReference | 1 | Referanse til fieldDefinition. |

Ingen underordnede elementer.


## fixedOccurrences  <a id="fixedOccurrences"/>

![Hierarki for fixedOccurrences](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fixedOccurrences.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [repeatingGroup](#repeatingGroup) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fixedOccurrences |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## keys  <a id="keys"/>

![Hierarki for keys](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/keys.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| keys |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [key](#key) | 1-n |

Ingen attributter.


## key  <a id="key"/>

![Hierarki for key](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/key.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [keys](#keys) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| key |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 0-1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [primaryKey](#primaryKey) | 1 |
| [alternateKey](#alternateKey) | 1 |
| [foreignKey](#foreignKey) | 1 |
| [fieldDefinitionReferences](#fieldDefinitionReferences) | 1 |


## primaryKey  <a id="primaryKey"/>

![Hierarki for primaryKey](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/primaryKey.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [key](#key) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| primaryKey |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## alternateKey  <a id="alternateKey"/>

![Hierarki for alternateKey](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/alternateKey.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [key](#key) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| alternateKey | Dette elementet benyttes for å angi alternative nøkler. I praksis vil dette gi muligheten for å angi indekser. Selve elementet er kun et flagg. |

Ingen attributter, underordnede elemente eller underordnede elementer.

### Eksempel

```xml
<key name="indeks1">
	<alternateKey/>
	<fieldDefinitionReferences>
		<!= elementene som inngår i nøkkel =>
	</fieldDefinitionReferences>
</key>
```

I eksemplet er det definert en nøkkel indeks1 som en alternative nøkkel (evt en indeks) og hvor de elementene som inngår er definert under fieldDefinitionReferences.

## foreignKey  <a id="foreignKey"/>

![Hierarki for foreignKey](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/foreignKey.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [key](#key) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| foreignKey |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [flatFileDefinitionReference](#flatFileDefinitionReference) | 1 |
| [relationType](#relationType) | 1 |

Ingen attributter.


## relationType  <a id="relationType"/>

![Hierarki for relationType](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/relationType.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [foreignKey](#foreignKey) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| relationType |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## fieldDefinitions  <a id="fieldDefinitions"/>

![Hierarki for fieldDefinitions](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldDefinitions.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldDefinitions |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 1-n |

Ingen attributter.


## fieldDefinition  <a id="fieldDefinition"/>

I ADDML er det tre parallelle informasjonstyper, den øverste er den generelle typen, hvor basis informasjon om felter defineres. Deretter kommer definisjonen av det enkelt felt, hvor man for mer eksplisitt informasjon om et felt og til slutt det fysiske delen som dog bare er på filnivå. Elementet som forklares her er på definisjonslaget.

![Hierarki for fieldDefinition](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldDefinition.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinitions](#fieldDefinitions) | 1-n |
| [fieldParts](#fieldParts) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldDefinition | Dette elementet er en beholder for informasjon om ett enkelt felt for filer som er i fast format, dvs. fast posisjonering eller tegnseparert. |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |
| typeReference | 1 | Referanse til fieldType. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [properties](#properties) | 0-1 |
| [startPos](#startPos) | 0-1 |
| [endPos](#endPos) | 0-1 |
| [fixedLength](#fixedLength) | 0-1 |
| [minLength](#minLength) | 0-1 |
| [maxLength](#maxLength) | 0-1 |
| [unique](#unique) | 0-1 |
| [notNull](#notNull) | 0-1 |
| [fieldParts](#fieldParts) | 0-1 |
| [codes](#codes) | 0-1 |

### Eksempel

```xml
<fieldDefinition name=”kjønn” typeReference=”flagg”>
	<startPos>1</startPos>
	<endPos>1</endPos>
	<codes>
		<code codeValue=”M” explan=”Mann”>
		<code codeValue=”K” explan=”Kvinne”>
		<code codeValue=”U” explan=”Ukjent”>
		<code codeValue=” ” explan=”Ikke oppgitt”>
	</codes>
   </fieldDefinition>
   <fieldDefinition name=”fødselsnr” typeReference=”fnr”>
	<startPos>1</startPos>
	<fixedLength>11</fixedLength>
	<notNull/>
	<unique/>
</fieldDefinition>
```

Over er vist et par eksempler med felter kjønn og fødselsnr.

## startPos  <a id="startPos"/>

![Hierarki for startPos](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/startPos.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| startPos |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## endPos  <a id="endPos"/>

![Hierarki for endPos](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/endPos.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| endPos | Dette elementet inneholder sluttposisjonen for et felt når det er snakk om et uttrekk med en flat fil med fast posisjonering. |

Ingen attributter, underordnede elemente eller underordnede elementer.

For eksempel se fieldDefinition.

## minLength  <a id="minLength"/>

![Hierarki for minLength](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/minLength.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| minLength |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## maxLength  <a id="maxLength"/>

![Hierarki for maxLength](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/maxLength.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| maxLength |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## unique  <a id="unique"/>

![Hierarki for unique](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/unique.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| unique |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## notNull  <a id="notNull"/>

![Hierarki for notNull](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/notNull.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| notNull |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## fieldParts  <a id="fieldParts"/>

![Hierarki for fieldParts](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldParts.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldParts |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 0-1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 1-n |


## codes  <a id="codes"/>

![Hierarki for codes](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/codes.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinition](#fieldDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| codes | Dette elementet er en gruppering av de gyldige kodene for et felt i datasettet. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [code](#code) | 1-n |

Ingen attributter.


For eksempel se *code*.

## code  <a id="code"/>

For et enkelt felt i et datasett kan man definere gyldige kodeverdier. Dette anbefales kun å gjøre dersom det er et begrenset antall, selv om standarden selv ikke setter noen begrensninger på antallet. Men dersom det er mange kodeverdier, anbefales heller at disse følger med datasettet som en egen fil.

![Hierarki for code](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/code.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [codes](#codes) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| code | Elementet code benyttes til å angi kodeverdier for et enkelt felt i et datasett. |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| codeValue | 1 | Den faktiske gyldige kodeverdien |
| explan | 0-1 | En forklaring på hva kodeverdien skal bety. Kan være spesielt nyttig når verdien av koden er kort og kryptisk. |

Ingen underordnede elementer.

### Eksempel

```xml
<fieldDefinition name="kjønn">
	<codes>
		<code codeValue="M" explan="Mann">
		<code codeValue="K" explan="Kvinne">
		<code codeValue="U" explan="Ukjent">
		<code codeValue=" " explan="Ikke oppgitt">
	</codes>
</fieldDefinition>
```

Legg merke til at i eksemplet er blank verdi en gyldig kodeverdi som ikke oppgitt, og at denne er en annen verdi enn ukjent.

## structureTypes  <a id="structureTypes"/>

![Hierarki for structureTypes](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/structureTypes.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFiles](#flatFiles) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| structureTypes |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [flatFileTypes](#flatFileTypes) | 1 |
| [recordTypes](#recordTypes) | 0-1 |
| [fieldTypes](#fieldTypes) | 1 |

Ingen attributter.


## flatFileTypes  <a id="flatFileTypes"/>

![Hierarki for flatFileTypes](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFileTypes.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [structureTypes](#structureTypes) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFileTypes |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [flatFileType](#flatFileType) | 1-n |

Ingen attributter.


## flatFileType  <a id="flatFileType"/>

![Hierarki for flatFileType](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFileType.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileTypes](#flatFileTypes) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFileType |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [charset](#charset) | 1 |
| [charDefinitions](#charDefinitions) | 0-1 |
| [fixedFileFormat](#fixedFileFormat) | 1 |
| [delimFileFormat](#delimFileFormat) | 1 |


## charset  <a id="charset"/>

![Hierarki for charset](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/charset.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileType](#flatFileType) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| charset | Dette elementet benyttes til å angi tegnsettet som benyttes i datasettet. Brukeren må selv definere hvordan de forskjellige tegnsettene skal angis. |

Ingen attributter, underordnede elemente eller underordnede elementer.

### Eksempel

```xml
<flatFileType name="fil1">
	<charset>ISO-8859-1</charset>
</flatFileType>
```

I eksemplet er f.eks tegnsettet angitt til å være ISO-8859-1.

## charDefinitions  <a id="charDefinitions"/>

![Hierarki for charDefinitions](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/charDefinitions.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileType](#flatFileType) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| charDefinitions | Dette elementet er et gruppenivå som inneholder de enkelte tegnene som har avvikende verdi. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [charDefinition](#charDefinition) | 1-n |

Ingen attributter.


				For eksempel se *charDefinition*.
							

## charDefinition  <a id="charDefinition"/>

charDefinition er ment å kunne benyttes ved spesialtegn som ikke følger vanlig standard. I de fleste tilfeller vil det være nok å bare angi tegnsett. Men dersom et datasett har avvikende tegn kan man benytte denne muligheten til å redefinere de få tegnene som avviker.

![Hierarki for charDefinition](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/charDefinition.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [charDefinitions](#charDefinitions) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| charDefinition | Elementet benyttes for angivelse av endring av en verdi for ett enkelt tegn som avviker fra tegnsettet som er oppgitt. |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| fromChar | 1 | Angivelse av verdien slik den er definert i tegnsettet. Hva slags type verdi som skal benyttes er det opp til brukeren å bestemme. |
| toChar | 1 | Angivelse av verdien slik den er i datasettet og som altså avviker fra tegnsettet. Hva slags type verdi som skal benyttes er det opp til brukeren å bestemme. |

Ingen underordnede elementer.

### Eksempel

```xml
<flatFileType name="fil1">
	<charset>EBCDIC</charset>
	<charDefinitions>
		<charDefinition fromChar="E6" toChar="5B">
		<charDefiniton fromChar="F8" toChar="7C">
		<charDefinition fromChar="E5" toChar="5D">
	</charDefinitions>
	….
</flatFileType>
```

I eksempelet er vist en mulig endring av verdien av de norske bokstavene æ, ø og å (små verdier) fra deres standard versjon i EBCDIC til en spesiell variant som har vært i bruk i Norge. Nemlig liten æ inn på plassen for [, liten ø inn på plassen for | og liten å inn på plassen for ].

I eksemplet er verdiene av tegnene oppgitt med hexadesimal verdi
			

## fixedFileFormat  <a id="fixedFileFormat"/>

![Hierarki for fixedFileFormat](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fixedFileFormat.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileType](#flatFileType) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fixedFileFormat |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [recordSeparator](#recordSeparator) | 0-1 |

Ingen attributter.


## delimFileFormat  <a id="delimFileFormat"/>

![Hierarki for delimFileFormat](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/delimFileFormat.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileType](#flatFileType) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| delimFileFormat | Dette elementet benyttes for flate filer for å angi at feltene i filene er atskilt med et tegn og ikke har faste posisjoner. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [recordSeparator](#recordSeparator) | 1 |
| [fieldSeparatingChar](#fieldSeparatingChar) | 1 |
| [quotingChar](#quotingChar) | 0-1 |

Ingen attributter.

### Eksempel

```xml
<flatFileType name=”fil1”>
	<delimFileFormat/>
</flatFileType>
```
	
I eksemplet er fil1 oppgitt å være en fil inneholdende felter som er separert ved et skilletegn, og dermed ikke har noen fast posisjon.

## fieldSeparatingChar  <a id="fieldSeparatingChar"/>

![Hierarki for fieldSeparatingChar](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldSeparatingChar.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [delimFileFormat](#delimFileFormat) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldSeparatingChar |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## quotingChar  <a id="quotingChar"/>

![Hierarki for quotingChar](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/quotingChar.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [delimFileFormat](#delimFileFormat) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| quotingChar |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## recordTypes  <a id="recordTypes"/>

![Hierarki for recordTypes](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordTypes.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [structureTypes](#structureTypes) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordTypes |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [recordType](#recordType) | 1-n |

Ingen attributter.


## recordType  <a id="recordType"/>

![Hierarki for recordType](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordType.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordTypes](#recordTypes) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordType |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [trimmed](#trimmed) | 0-1 |


## trimmed  <a id="trimmed"/>

![Hierarki for trimmed](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/trimmed.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordType](#recordType) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| trimmed |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## fieldTypes  <a id="fieldTypes"/>

![Hierarki for fieldTypes](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldTypes.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [structureTypes](#structureTypes) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldTypes |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [fieldType](#fieldType) | 1-n |

Ingen attributter.


## fieldType  <a id="fieldType"/>

![Hierarki for fieldType](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldType.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldTypes](#fieldTypes) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldType |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [dataType](#dataType) | 1 |
| [fieldFormat](#fieldFormat) | 0-1 |
| [alignment](#alignment) | 0-1 |
| [padChar](#padChar) | 0-1 |
| [packType](#packType) | 0-1 |
| [nullValues](#nullValues) | 0-1 |


## dataType  <a id="dataType"/>

![Hierarki for dataType](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/dataType.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldType](#fieldType) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| dataType | Hvilken datatype et felt er. Brukeren må selv definere gyldige datatyper og hvordan de skal betegnes. |

Ingen attributter, underordnede elemente eller underordnede elementer.

### Eksempel

```xml
<fieldType name="heltall">
	<dataType>integer</dataType>
</fieldType>
```

I eksemplet er det definert en felttype som heter heltall. Denne er da definert som datatypen
integer (integer for heltall).

## fieldFormat  <a id="fieldFormat"/>

![Hierarki for fieldFormat](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldFormat.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldType](#fieldType) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldFormat |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## alignment  <a id="alignment"/>

![Hierarki for alignment](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/alignment.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldType](#fieldType) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| alignment | alignment benyttes for å angi hvorvidt innholdet i et felt er venstrejustert, høyrejustert eller midtstilt. Brukeren selv må definere de faktiske verdiene for alignment. |

Ingen attributter, underordnede elemente eller underordnede elementer.


## padChar  <a id="padChar"/>

![Hierarki for padChar](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/padChar.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldType](#fieldType) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| padChar |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## packType  <a id="packType"/>

![Hierarki for packType](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/packType.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldType](#fieldType) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| packType |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## nullValues  <a id="nullValues"/>

![Hierarki for nullValues](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/nullValues.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldType](#fieldType) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| nullValues |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [nullValue](#nullValue) | 1-n |

Ingen attributter.


## nullValue  <a id="nullValue"/>

![Hierarki for nullValue](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/nullValue.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [nullValues](#nullValues) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| nullValue |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## queries  <a id="queries"/>

![Hierarki for queries](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/queries.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFiles](#flatFiles) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| queries |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [query](#query) | 1-n |

Ingen attributter.


## query  <a id="query"/>

![Hierarki for query](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/query.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [queries](#queries) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| query |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 0-1 | name angir navnet til det spesifikke objekt. Det er ingen krav til navnsetting i utgangspunktet, men navnene for samme type objekt må være unike innen en addml-fil. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [statement](#statement) | 1 |


## statement  <a id="statement"/>

![Hierarki for statement](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/statement.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [query](#query) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| statement |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## flatFileProcesses  <a id="flatFileProcesses"/>

![Hierarki for flatFileProcesses](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFileProcesses.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFiles](#flatFiles) | 0-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFileProcesses |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| flatFileReference | 1 |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [processes](#processes) | 0-1 |
| [recordProcesses](#recordProcesses) | 0-n |


## recordProcesses  <a id="recordProcesses"/>

![Hierarki for recordProcesses](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordProcesses.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileProcesses](#flatFileProcesses) | 0-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordProcesses |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| definitionReference | 1 |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [processes](#processes) | 0-1 |
| [fieldProcesses](#fieldProcesses) | 0-n |


## fieldProcesses  <a id="fieldProcesses"/>

![Hierarki for fieldProcesses](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldProcesses.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordProcesses](#recordProcesses) | 0-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldProcesses |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| definitionReference | 1 |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [processes](#processes) | 1 |


## processes  <a id="processes"/>

![Hierarki for processes](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/processes.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [context](#context) | 0-1 |
| [content](#content) | 0-1 |
| [flatFiles](#flatFiles) | 0-1 |
| [flatFileProcesses](#flatFileProcesses) | 0-1 |
| [recordProcesses](#recordProcesses) | 0-1 |
| [fieldProcesses](#fieldProcesses) | 1 |
| [dataObjects](#dataObjects) | 0-1 |
| [dataObject](#dataObject) | 0-1 |
| [additionalElements](#additionalElements) | 0-1 |
| [additionalElement](#additionalElement) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| processes |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [process](#process) | 1-n |

Ingen attributter.


## process  <a id="process"/>

![Hierarki for process](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/process.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [processes](#processes) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| process |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Navn på prosess som skal utføres. Dette er noe som brukerne og leverandørene av applikasjonene som benyttes må være enige om. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [parameters](#parameters) | 0-1 |


## parameters  <a id="parameters"/>

![Hierarki for parameters](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/parameters.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [process](#process) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| parameters |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [parameter](#parameter) | 1-n |

Ingen attributter.


## parameter  <a id="parameter"/>

![Hierarki for parameter](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/parameter.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [parameters](#parameters) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| parameter |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Navn på parameter som tilhører prosessen som skal utføres. Dette er noe som brukerne og leverandørene av applikasjonene som benyttes må være enige om. |
| value | 0-1 |  |

Ingen underordnede elementer.


## flatFileDefinitionReference  <a id="flatFileDefinitionReference"/>

![Hierarki for flatFileDefinitionReference](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/flatFileDefinitionReference.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [foreignKey](#foreignKey) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| flatFileDefinitionReference |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Referanse til en flatFile. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [recordDefinitionReferences](#recordDefinitionReferences) | 0-1 |


## recordDefinitionReferences  <a id="recordDefinitionReferences"/>

![Hierarki for recordDefinitionReferences](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordDefinitionReferences.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFileDefinitionReference](#flatFileDefinitionReference) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordDefinitionReferences |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [recordDefinitionReference](#recordDefinitionReference) | 1-n |

Ingen attributter.


## recordDefinitionReference  <a id="recordDefinitionReference"/>

![Hierarki for recordDefinitionReference](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordDefinitionReference.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinitionReferences](#recordDefinitionReferences) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordDefinitionReference |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Referanse til en recordDefinition |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [fieldDefinitionReferences](#fieldDefinitionReferences) | 0-1 |


## fieldDefinitionReferences  <a id="fieldDefinitionReferences"/>

![Hierarki for fieldDefinitionReferences](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldDefinitionReferences.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [repeatingGroup](#repeatingGroup) | 1 |
| [key](#key) | 1 |
| [recordDefinitionReference](#recordDefinitionReference) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldDefinitionReferences | Dette elementet er en samling av feltreferanser. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [fieldDefinitionReference](#fieldDefinitionReference) | 1-n |

Ingen attributter.


```xml

```

For eksempel se [fieldDefinitionReference](#fieldDefinitionReference).

## fieldDefinitionReference  <a id="fieldDefinitionReference"/>

![Hierarki for fieldDefinitionReference](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/fieldDefinitionReference.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fieldDefinitionReferences](#fieldDefinitionReferences) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| fieldDefinitionReference | Referanse til et felt |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Referanse til et fieldDefinition-felt |

Ingen underordnede elementer.

### Eksempel

```xml
 <key>
	<foreignKey>
		<flatFileDefinitionReference name=”fil2”>
			<recordDefinitionReferences>
				<recordDefinitionReference name=”post2”>
					<fieldDefinitionReferences>
						<fieldDefinitionReference name=”postnr”/>
					</fieldDefinitionReferences>
				</recordDefinitionReference>
			</recordDefinitionReferences>
		</flatFileDefinitionReference>
		<relationType>n:1</relationType>
	</foreignKey>
	<fieldDefinitionReferences>
		<fieldDefinitionReference name=”postnr”>
	</fieldDefinitionReferences>
 </key>
```

text

## dataObjects  <a id="dataObjects"/>

De første versjonene av ADDML ble konstruert for å håndtere flate filer. Etter hvert er det også blitt behov for å håndtere andre typer filer, ikke minst xml-filer. Av den grunn ble det innført en ny hoveddel med dataobjekter. Denne delen er generisk, hvor brukeren selv må definere strukturer og informasjonselementer som skal være med.

![Hierarki for dataObjects](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/dataObjects.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [dataset](#dataset) | 0-1 |
| [dataObject](#dataObject) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| dataObjects | Dette er elementer hvor man kan lage en egen hierarkisk struktur for filer som ikke er flate filer. Man må selv bygge opp strukturen på det viset en selv føler blir best mulig. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [dataObject](#dataObject) | 1-n |
| [processes](#processes) | 0-1 |

Ingen attributter.


For eksempel se *dataObject*.

## dataObject  <a id="dataObject"/>

De første versjonene av ADDML ble konstruert for å håndtere flate filer. Etter hvert er detogså blitt behov for å håndtere andre typer filer, ikke minst xml-filer. Av den grunn ble det innført en ny hoveddel med dataobjekter. Denne delen er generisk, hvor brukeren selv må definere strukturer og informasjonselementer som skal være med.

![Hierarki for dataObject](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/dataObject.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [dataObjects](#dataObjects) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| dataObject | Dette er elementer hvor man kan lage en egen hierarkisk struktur for filer som ikke er flate filer. Man må selv bygge opp strukturen på det viset en selv føler blir best mulig. |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Navnet på dataobjektet som defineres.  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [properties](#properties) | 0-1 |
| [dataObjects](#dataObjects) | 0-1 |
| [processes](#processes) | 0-1 |

### Eksempel

```xml
<dataObjects>
	<dataObject name="Noark 5-arkivuttrekk">
		<properties>
			<property name="info">
				<properties>
					<property name="type">
						<value>Noark 5</value>
						<properties>
							<property name="version">
								<value>5.0</value>
							</property>
						</properties>
					</property>
				</properties>
			</property>
		</properties>
		<dataObjects>
			<dataObject name="arkivstruktur">
				<properties>
					<property name="file">
						<!= Filegenskaper =>
					</property>
					<property name="schema">
						<value>main</value>
						<!= Hovedskjema =>
					</property>
					<property name="schema">
						<!= Andre skjema =>
					</property>
					<property name="info">
						<!= Informasjon =>
					</property>
				</properties>
			</dataObject>
		</dataObjects>
	</dataObject>
</dataObjects>
```

Eksempelet er hentet fra Noark 5. I datasettet er det definert et arkivuttrekk-nivå, med egenskaper som beskriver type og versjon arkivuttrekk som dataobjektet inneholder. Dette objektet inneholder ett under-dataobjekt, arkivstruktur, som er fil-nivå. Den inneholder filegenskaper, skjema-referanser og mer-informasjon.

## additionalElements  <a id="additionalElements"/>

Elementet additionalElements er et samlenivå for gruppering av tilleggselementer.

![Hierarki for additionalElements](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/additionalElements.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [context](#context) | 0-1 |
| [content](#content) | 0-1 |
| [additionalElement](#additionalElement) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| additionalElements | Dette elementet benyttes for å samle tilleggselementer i grupper. Og derigjennom å kunne danne strukturer av tilleggselementer. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [description](#description) | 0-1 |
| [additionalElement](#additionalElement) | 1-n |
| [processes](#processes) | 0-1 |

Ingen attributter.


## additionalElement  <a id="additionalElement"/>

Elementet additionalElement utgjør et egetdefinert element. Standarden selv definerer ingen tilleggselementer, men lar det være opp til brukerne å definere sine egne. Sammen med additionalElements danner additionalElement muligheten for å kunne bygge sin egen generiske struktur.

![Hierarki for additionalElement](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/additionalElement.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [additionalElements](#additionalElements) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| additionalElement | Identifiserer et enkelt tilleggselement. Et tilleggselement defineres av brukeren. |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Alle tilleggselement må ha et navn. Navnet identifiserer tilleggselementet og vil være utgangspunktet for eventuelle operasjoner som skal utføres på elementet eller gjenfinning av elementet for annet bruk. |
| dataType | 0-1 | Siden tilleggselementet kan ha et underelement med en verdi, kan man identifisere datatypen til denne verdien. |
| format | 0-1 | Siden tilleggselementet kan ha et underelement med en verdi, kan man identifisere formatet til denne verdien. Hvilke formater som skal aksepteres må brukeren selv definere. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [value](#value) | 0-1 |
| [properties](#properties) | 0-1 |
| [additionalElements](#additionalElements) | 0-1 |
| [processes](#processes) | 0-1 |


## description  <a id="description"/>

Elementet beskrivelse benyttes flere steder i strukturen.

![Hierarki for description](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/description.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [dataset](#dataset) | 0-1 |
| [context](#context) | 0-1 |
| [content](#content) | 0-1 |
| [flatFileDefinition](#flatFileDefinition) | 0-1 |
| [recordDefinition](#recordDefinition) | 0-1 |
| [fieldDefinition](#fieldDefinition) | 0-1 |
| [flatFileType](#flatFileType) | 0-1 |
| [recordType](#recordType) | 0-1 |
| [fieldType](#fieldType) | 0-1 |
| [query](#query) | 0-1 |
| [dataObjects](#dataObjects) | 0-1 |
| [dataObject](#dataObject) | 0-1 |
| [additionalElements](#additionalElements) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| description | Dette elementet inneholder en tekstlig beskrivelse knyttet til elementet det ligger under. |

Ingen attributter, underordnede elemente eller underordnede elementer.

### Eksempel

```xml
<dataset>
	<description>
	Dette datasettet inneholder et arkivuttrekk fra system x fra arkivskaper y.
	</description>
</dataset>
```

text

## properties  <a id="properties"/>

![Hierarki for properties](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/properties.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [flatFile](#flatFile) | 0-1 |
| [flatFileDefinition](#flatFileDefinition) | 0-1 |
| [recordDefinition](#recordDefinition) | 0-1 |
| [fieldDefinition](#fieldDefinition) | 0-1 |
| [dataObject](#dataObject) | 0-1 |
| [additionalElement](#additionalElement) | 0-1 |
| [property](#property) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| properties |  |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [property](#property) | 1-n |

Ingen attributter.


## property  <a id="property"/>

![Hierarki for property](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/property.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [properties](#properties) | 1-n |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| property |  |

| Attributt | Forekomst | Beskrivelse |
| :-- | :-- | :-- |
| name | 1 | Alle egenskaper må ha et navn. Navnet identifiserer egenskapen og vil være utgangspunktet for eventuelle operasjoner som skal utføres på egenskapen eller gjenfinning av egenskapen for annet bruk. |
| dataType | 0-1 | Siden egenskapen kan ha et underelement med en verdi, kan man identifisere datatypen til denne verdien. |
| format | 0-1 | Siden egenskapen kan ha et underelement med en verdi, kan man identifisere formatet til denne verdien. Hvilke formater som skal aksepteres må brukeren selv definere. |

| Underliggende elementer | Forekomster |
| :-- |  :-- |
| [value](#value) | 0-1 |
| [properties](#properties) | 0-1 |


## headerLevel  <a id="headerLevel"/>

![Hierarki for headerLevel](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/headerLevel.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [recordDefinition](#recordDefinition) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| headerLevel |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## recordSeparator  <a id="recordSeparator"/>

![Hierarki for recordSeparator](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/recordSeparator.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [fixedFileFormat](#fixedFileFormat) | 0-1 |
| [delimFileFormat](#delimFileFormat) | 1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| recordSeparator |  |

Ingen attributter, underordnede elemente eller underordnede elementer.


## value  <a id="value"/>

![Hierarki for value](https://raw.githubusercontent.com/arkivverket/addml-standard/master/profiler/arkivverket/figurer/elementer/value.svg)

| Overordnede elementer | Forekomster av element |
| :-- |  :-- |
| [additionalElement](#additionalElement) | 0-1 |
| [property](#property) | 0-1 |

| Elementnavn | Beskrivelse |
| :-- | :-- |
| value |  |

Ingen attributter, underordnede elemente eller underordnede elementer.
