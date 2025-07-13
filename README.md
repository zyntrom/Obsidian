## My Obsidian Notes 



```dataview
table file.name as "📄 Note", file.folder as "📁 Folder", file.ctime as "🕒 Created"
from "Kalvium Class Note"
where !contains(file.folder, "Images") and file.name != "README"
sort file.folder asc, file.name asc