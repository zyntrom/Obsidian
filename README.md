## My Obsidian Notes 

```dataviewjs
// Get pages excluding Images & README, and ensure they have folders
const pages = dv.pages("")
  .where(p => p.file && p.file.folder && 
              !p.file.folder.includes("Images") && 
              !p.file.name.includes("README"));

// Helper: extract last two folders (like `Critical Thinking › Module 1`)
function getFolder(path) {
  const parts = path.split("/");
  return parts.slice(-2).join(" › ");
}

// Helper: extract Section number from file name for sorting
function extractSectionNumber(name) {
  const match = name.match(/Section (\d+)/i);
  return match ? parseInt(match[1]) : Infinity;
}

// Sort first by folder, then by section number
const sortedPages = pages.array().sort((a, b) => {
  const folderCompare = getFolder(a.file.folder).localeCompare(getFolder(b.file.folder));
  if (folderCompare !== 0) return folderCompare;
  return extractSectionNumber(a.file.name) - extractSectionNumber(b.file.name);
});

// Header
dv.header(2, "📚 Note Index (Grouped by Folder)");

// Build and render table
dv.table(
  ["📁 Folder", "📝 Note"],
  sortedPages.map(p => [
    getFolder(p.file.folder),
    `[[${p.file.path}|${p.file.name}]]`
  ])
);

```



