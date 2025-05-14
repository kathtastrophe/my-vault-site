# Hello
Welcome to my vault, where I'm exploring some big topics to help me to make sense of the world and my place within it.
![[bear and duck surfing 1.jpg|250]]
```dataviewjs
// 1) grab every note in the vault
// 2) keep only those in Permanent/ or _Home/
// 3) filter to notes with >5 outgoing links
// 4) sort descending by outgoing‑link count
const pages = dv
  .pages("") 
  .filter(p => (
    // include both top‑level folders (and their subfolders)
    p.file.path.startsWith("Permanent/") ||
    p.file.path.startsWith("_Home/")
  ) && p.file.outlinks.length >= 5)
  .sort(p => p.file.outlinks.length, "desc");

// Render exactly two columns: clickable filename and outgoing‑link count
dv.table(
  ["File", "Outgoing Links"],
  pages.map(p => [
    dv.fileLink(p.file.path),
    p.file.outlinks.length
  ])
);

```





---
## See also

---
## References

---
## Tags

---

[^1]: 
