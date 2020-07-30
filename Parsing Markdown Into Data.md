---

id: 202007220657
tags: [ #datascience #programming #statistics #todo ]

---

# Parsing Markdown into Data

Take fields inside markdown files like

```
id: 202007220657
tags: [ #zettelkasten ]
daily_journal_entry: true

```

and turn it into a data representation like

```js
const note = {
  id: 202007220657,
  tags: ["zettelkasten"],
  dailyJournalEntry: true,
};
```

This process should be done with a markdown-to-json parser, as JSON easily maps to the data objects we want. Currently-known packages that do this are:
[[markdown-json]]

const imgOrText(readContent(Element or Node);

## Packages
[[markdown-js]]
[[markdown-it]]

## References
