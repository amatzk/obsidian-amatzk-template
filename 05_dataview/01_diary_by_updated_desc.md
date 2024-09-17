``` dataview
TABLE
	dateformat(file.ctime,"yyyy-MM-dd, HH:mm") AS "作成日時",
	dateformat(file.mtime,"yyyy-MM-dd, HH:mm") AS "更新日時"
FROM "01_diary"
SORT file.mtime DESC
```
