# 🤖 Robot Talks

### Category: Steganography

**Tools Used:** `zsteg`, `file` command

---

## 🛠️ Steps to Solve

1. Downloaded the two PNG image files: `supply.png` and `dupply.png`.

2. Verified file types using the `file` command:

```bash
┌──(aupy㉿kali)-[~/Downloads]
└─$ file supply.png
supply.png: PNG image data, 500 x 500, 8-bit/color RGB, non-interlaced

┌──(aupy㉿kali)-[~/Downloads]
└─$ file dupply.png
dupply.png: PNG image data, 500 x 500, 8-bit/color RGB, non-interlaced
```

3. Ran zsteg on both images to check for hidden data in LSB planes and other channels:

```bash
┌──(aupy㉿kali)-[~/Downloads]
└─$ zsteg supply.png
imagedata           .. text: "dddJJJZZZ"
b2,rgb,lsb,xy       .. file: MPEG ADTS, layer II, v2,  56 kbps, Monaural
b3,rgb,msb,xy       .. file: very old 16-bit-int big-endian archive
b4,rgb,lsb,xy       .. file: MPEG ADTS, layer III, v2,  24 kbps, 22.05 kHz, Monaural
b4,rgb,msb,xy       .. text: "w'\"w'\"wWU"

┌──(aupy㉿kali)-[~/Downloads]
└─$ zsteg dupply.png
imagedata           .. text: "GGFXXXppq"
b1,b,lsb,xy         .. text: "WTISD{robots_talk_in_noise}"
b3,r,lsb,xy         .. text: "\t-A(\r(:WR"
b3,b,lsb,xy         .. text: "-A(\r(:WR"
b4,rgb,lsb,xy       .. file: MPEG ADTS, layer III,  v2.5,  24 kbps, 11.025 kHz, Monaural
```

Found the flag hidden inside the blue channel, bit plane 1, LSB of dupply.png.

---

## 🎯 Flag

**WTISD{robots_talk_in_noise}**

---
