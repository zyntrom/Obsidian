## My Obsidian Notes 

```dataviewjs
const pages = dv.pages("")
  .where(p => !p.file.folder.includes("Images") && !p.file.name.includes("README"))
  .sort(p => p.file.folder + "/" + p.file.name);

// Function to get last 4 folder parts
function getFolder(path) {
  const parts = path.split("/");
  return parts.slice(-2).join(" › ");
}

dv.header(2, "📚 Note Index (Grouped by Folder)");

dv.table(
  ["📁 Folder", "📝 Note"],
  pages.map(p => [
    getFolder(p.file.folder),
    `[[${p.file.path}|${p.file.name}]]`
  ])
);
```



