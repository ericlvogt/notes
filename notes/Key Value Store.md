Type of [[Database]] that only has a key column and value. Intentionally simple for fast lookups

```dataview 
	table without id file.inlinks where file.name = this.file.name
```