# Elementene i ADDML 8.3

I det etterfølgende er hvert enkelt element i ADDML beskrevet.

Hvert element har en figur som viser hvilke andre elementer det har en relasjon til, både som overliggende element og eventuelle underliggende element.

I tabellform er det gitt grunnleggende informasjon om elementet. Og deretter i en ny tabell alle attributter som elementet har. Også underliggende element er vist i en tabellform.

Til slutt er det vist et enkelt eksempel med bruk av elementet. For noen element er det vist til eksempler under andre element.

## additionalElement {#additionalElement}

Elementet additionalElement utgjør et egetdefinert element. Standarden selv definerer ingen tilleggselementer, men lar det være opp til brukerne å definere sine egne. Sammen med additionalElements danner additionalElement muligheten for å kunne bygge sin egen generiske struktur.

![Struktur](https://raw.githubusercontent.com/arkivverket/addml-standard/master/standard/figurer/elementer/additionalElement.svg)

| Elementnavn | Forekomster | Beskrivelse |
| -------- | ------- | ------- |
| additionalElement  | 1    | Identifiserer et enkelt tilleggselement. Et tilleggselement defineres av brukeren.

| Attributter | Forekomster | Beskrivelse |
| -------- | ------- | ------- |
| name  | 1    | Alle tilleggselement må ha et navn. Navnet identifiserer tilleggselementet og vil være utgangspunktet for eventuelle operasjoner som skal utføres på elementet eller gjenfinning av elementet for annet bruk.
| dataType  | 0-1    | Siden tilleggselementet kan ha et underelement med en verdi, kan man identifisere datatypen til denne verdien.
| format  | 0-1    | Siden tilleggselementet kan ha et underelement med en verdi, kan man identifisere formatet til denne verdien. Hvilke formater som skal aksepteres må brukeren selv definere.

| Underliggende elementer | Forekomster |
| -------- | ------- |
| [value](#value)  | 0-1 |
| [properties](#properties)  | 0-1 |
| [additionalElements](#additionalElements)  | 0-1 |
| [processes](#processes)  | 0-1 |

### Eksempel

```xml
<additionalElement name="period">
    <additionalElements>
        <additionalElement name="startDate" dataType="date" format="YYYYMMDD">
            <value>20000101</value>
        </additionalElement>
        <additionalElement name="endDate" dataType="date" format="YYYYMMDD">
            <value>20101231</value>
        </additionalElement>
    </additionalElements>
</additionalElement>
```

I eksempelet er det definert et tilleggselement period, som består av to underliggende tilleggselementer – startDate og endDate. Disse to elementene har hver sin verdi som er en dato på formen YYYYMMDD, altså 4-sifret år, 2-sifret måned og 2-sifret dag.

Dette kan også illustreres slik:

![Eksempel](https://raw.githubusercontent.com/arkivverket/addml-standard/master/standard/figurer/elementer/additionalElement_1.svg)

Hvor den tomme rammen markerer et omslag rundt en gruppe av elementer og altså tilsvarer nivået additionalElements.

## additionalElements {#additionalElements}

Elementet additionalElements er et samlenivå for gruppering av tilleggselementer.

![Struktur](https://raw.githubusercontent.com/arkivverket/addml-standard/master/standard/figurer/elementer/additionalElements.svg)

| Elementnavn | Forekomster | Beskrivelse |
| -------- | ------- | ------- |
| additionalElements | 0-1 | Dette elementet benyttes for å samle tilleggselementer i grupper. Og derigjennom å kunne danne strukturer av tilleggselementer.

Ingen attributter.

| Underliggende elementer | Forekomster |
| -------- | ------- |
| [description](#description) | 0-1 |
| [additionalElement](#additionalElement) | 0-n |
| [processes](#processes) | 0-1 |

For eksempel se [additionalElement](#additionalElement).
