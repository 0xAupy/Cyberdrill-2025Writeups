# 📝 I Love Documents

### Category: Forensics

**Concepts Used:** File Structure Analysis, File Extraction

---

## 🛠️ Steps to Solve

Downloaded the given .docx file.

Renamed the file extension from .docx to .zip.

.docx files are essentially zipped archives containing various XML and media files.

Extracted the contents of the zip file.

```bash

┌──(aupy㉿kali)-[~/Downloads]
└─$ cd espionage\ \(copy\ 1\)

┌──(aupy㉿kali)-[~/Downloads/espionage (copy 1)]
└─$ ls
'[Content_Types].xml'   customXml   docProps   _rels   word

┌──(aupy㉿kali)-[~/Downloads/espionage (copy 1)]
└─$ cd word

┌──(aupy㉿kali)-[~/Downloads/espionage (copy 1)/word]
└─$ ls
document.xml   numbering.xml  stylesWithEffects.xml  webSettings.xml
fontTable.xml  _rels          styles.xml
media          settings.xml   theme

┌──(aupy㉿kali)-[~/Downloads/espionage (copy 1)/word]
└─$ cd media

┌──(aupy㉿kali)-[~/Downloads/espionage (copy 1)/word/media]
└─$ ls
flag.png
```

Found a file named flag.png inside the word/media directory.

Opened the image file.

---

## 🎯 Flag

**WTISD{Frederick-Forsyth}**

---
