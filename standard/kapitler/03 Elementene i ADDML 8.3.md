# Elementene i ADDML 8.3.

I det etterfølgende er hvert enkelt element i ADDML beskrevet.

Hvert element har en figur som viser hvilke andre elementer det har en relasjon til, både som overliggende element og eventuelle underliggende element.

I tabellform er det gitt grunnleggende informasjon om elementet. Og deretter i en ny tabell alle attributter som elementet har. Også underliggende element er vist i en tabellform.

Til slutt er det vist et enkelt eksempel med bruk av elementet. For noen element er det vist til eksempler under andre element.

## additionalElement

Elementet additionalElement utgjør et egetdefinert element. Standarden selv definerer ingen tilleggselementer, men lar det være opp til brukerne å definere sine egne. Sammen med additionalElements danner additionalElement muligheten for å kunne bygge sin egen generiske struktur.

![Struktur](https://www.plantuml.com/plantuml/png/FSqn3i9G2CRntLFe0IoxKnSFWWLRKg0D3-hrVOs94ycF_FEDBJ6oJ2ytyKcBk4AlI-RU7W2pv5AlOTeCC5Ov3ewL4v38zDvB9mo2m0yOjkI0lxrbhkZ0oiP-ldeaAPkZFdysxEVio4xzVW40?cache=no)

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
| value  | 0-1 |
| properties  | 0-1 |
| additionalElements  | 0-1 |
| processes  | 0-1 |

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

![Eksempel](https://www.plantuml.com/plantuml/png/FSqn3i9W28RXtLFe0InnTUhYEGmMR4c1DXJgzVqR4oUIXxpv-YqnianF5_51YxX2prFckjq1HicfNjsm663CikySCoSWaUcrbKuO184VCDoI0_xsbh6Y0IiRUtiTaQGiZlhusVFMhSTmpqxjVW40?cache=no)

Hvor den tomme rammen markerer et omslag rundt en gruppe av elementer og altså tilsvarer nivået additionalElements.
