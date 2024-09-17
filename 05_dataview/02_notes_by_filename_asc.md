``` dataview
TABLE
	dateformat(file.mtime,"yyyy-MM-dd, HH:mm") AS "更新日時"
FROM "02_notes"
SORT file.name ASC
```
