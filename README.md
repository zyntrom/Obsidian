## My Obsidian Notes 

```dataviewjs
// Get only valid pages (with file property and folder)
const pages = dv.pages("")
  .where(p => p.file && p.file.folder && !p.file.folder.includes("Images") && !p.file.name.includes("README"));

// Helper: extract last 2 folders for display
function getFolder(path) {
  const parts = path.split("/");
  return parts.slice(-2).join(" › ");
}

// Extract Section number from title for proper numeric sorting
function extractSectionNumber(name) {
  const match = name.match(/Section (\d+)/);
  return match ? parseInt(match[1]) : Infinity;
}

// Sort by folder, then by section number if available
const sortedPages = pages.sort((a, b) => {
  const folderCompare = a.file.folder.localeCompare(b.file.folder);
  if (folderCompare !== 0) return folderCompare;
  return extractSectionNumber(a.file.name) - extractSectionNumber(b.file.name);
});

// Header
dv.header(2, "📚 Note Index (Grouped by Folder)");

// Display table
dv.table(
  ["📁 Folder", "📝 Note"],
  sortedPages.map(p => [
    getFolder(p.file.folder),
    `[${p.file.name.replace(/^Section \d+\s*/, "")}](${p.file.path})`
  ])
);

```



