## My Obsidian Notes 

```dataviewjs
const pages = dv.pages("")
    .where(p => !p.file.folder.includes("Images") && !p.file.name.includes("README"))
    .sort(p => p.file.folder + "/" + p.file.name);

dv.header(2, "🗂️ Notes Index");

dv.table(
    ["📁 Folder Path", "📄 Note"],
    pages.map(p => [
        p.file.folder.replace(/\//g, " › "),
        `[${p.file.name}](${p.file.path})`
    ])
);
```

