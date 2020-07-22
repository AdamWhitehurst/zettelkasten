---

id: 202007220657
tags: [ #datascience #analytics #statistics #todo ]

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
	tags: [
		'zettelkasten',
	],
	dailyJournalEntry: true,
};

```

## See Also