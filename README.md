## My Obsidian Notes 



```dataview
table file.name as "Note Title", file.ctime as "Created"
from ""
where file.name != "README" and !file.name.endsWith(".png") and !file.name.endsWith(".jpg")
sort file.name asc
```


