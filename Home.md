---
cssclasses:
  - dashboard
---



## Vault Info

- Recent file updates:
`$=dv.list(dv.pages('').sort(f=>f.file.mtime.ts,"desc").limit(3).file.link)`

- Stats:
	-  File Count: `$=dv.pages().length`