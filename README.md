# Biblical Translation Guide

This repository catalogues a broad family of English Bible translations.  Each
translation is represented as a YAML file under the `translations/` directory.
The project captures more than publication dates: it records sample text
(John 3:16), the primary source texts consulted, the relationships to other
translations, and a five‑dimensional description of translation philosophy.

## Translation philosophy framework

Traditional labels like *formal* and *dynamic* are helpful but often hide the
trade‑offs translators make.  This guide uses five axes to describe how a
translation handles the delicate balance between fidelity and clarity:

| Axis | High | Low |
|-----|-----|-----|
| **word‑for‑word** | Stays close to individual words and their order | Freely departs from word‑level rendering |
| **sentence‑for‑sentence** | Preserves sentence structure and boundary | Merges or recasts sentences for readability |
| **passage‑for‑passage** | Follows the flow of longer units | Reorders or summarises passages |
| **idea‑for‑idea** | Conveys the thought even if wording changes | Prioritises literal wording over modern phrasing |
| **syntax‑for‑syntax** | Retains grammatical form (e.g. verb tenses, clauses) | Replaces structure with target‑language equivalents |

Values of `high`, `medium` and `low` (or occasionally `low`, `moderate`, `high` depending on the file) in the translation files indicate a
relative emphasis along each axis when compared to other translations.  For
example, the King James Version has **high** `word_for_word` and `syntax_for_syntax`
values but **low** `idea_for_idea` because it prioritises literal wording and
structure over modern idiom.

## Directory structure

```
biblical-translation-guide/
├── README.md                 # this file
├── translation.schema.yaml   # schema describing translation file format
└── translations/             # YAML files for each translation
    ├── kjv_1611.yaml
    ├── drb_1582-1610.yaml
    ├── …
    └── new_world_translation_1961.yaml
```

The filenames are slugified from the translation name and year.  They contain
the following top‑level keys:

- `translation`: The full name of the Bible version.
- `abbreviation`: A common abbreviation.
- `tradition`: Broad religious tradition (Protestant, Catholic, Jewish, etc.).
- `year`: Year or range of first publication.
- `example_verse`: An object with `reference` and `text` fields for John 3:16.
- `source_texts`: An object with `primary` and `secondary` lists of source texts.
- `translation_philosophy`: An object with five keys (`word_for_word`,
  `sentence_for_sentence`, `passage_for_passage`, `idea_for_idea`,
  `syntax_for_syntax`) whose values are `high`, `medium` or `low`.
 - `derivation`: An object noting `direct_sources` and `indirect_influences`
   describing how this translation relates to earlier versions.
- `historical_context`: An object describing who commissioned the translation
  and why.

## Contributing

If you wish to add another translation, create a new YAML file in
`translations/` following the schema and update the README accordingly.
