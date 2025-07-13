## My Obsidian Notes 

```dataviewjs
const pages = dv.pages("")
    .where(p => !p.file.folder.includes("Images") && !p.file.name.includes("README"))
    .sort(p => p.file.folder + "/" + p.file.name);

let folders = {};

for (let page of pages) {
    const parts = page.file.folder.split("/");
    const filename = page.file.name;
    let current = folders;

    for (let part of parts) {
        if (!(part in current)) current[part] = {};
        current = current[part];
    }

    if (!("__notes__" in current)) current["__notes__"] = [];
    current["__notes__"].push(page);
}

function renderTree(obj, indent = 0) {
    let output = "";
    const pad = "&nbsp;".repeat(indent * 4);
    
    for (let key in obj) {
        if (key === "__notes__") {
            for (let note of obj["__notes__"]) {
                output += `${pad}- 📄 [[${note.file.path}]]<br>`;
            }
        } else {
            output += `${pad}📁 **${key}**<br>`;
            output += renderTree(obj[key], indent + 1);
        }
    }
    return output;
}

dv.paragraph(renderTree(folders));
```
