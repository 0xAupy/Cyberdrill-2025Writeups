# 🖼️ Beautiful Raod

### Category: Steganography

**Tool Used:** `zsteg`

---

## 🔍 Challenge Summary

We were provided with a PNG file named `stego.png`. The goal was to extract any hidden data from the image.

---

## 🛠️ Steps to Solve

We used the `zsteg` tool, which is commonly used to extract hidden text and data from PNGs using various LSB and bit-plane techniques:

````bash
┌──(aupy㉿kali)-[~/Downloads]
└─$ zsteg stego.png
imagedata           .. file: mc68k executable (shared demand paged) not stripped
b1,rgb,lsb,xy       .. text: "79:#include <stdio.h>\n\nint main() {\n\n    printf(\"Th15_1s_RC!\");\n\n    return 0;\n\n}\nVrP"
b1,bgr,lsb,xy       .. file: OpenPGP Secret Key
b3,r,msb,xy         .. text: " .*,z\rJVk"
b3,g,lsb,xy         .. file: apollo a88k COFF executable not stripped - version 3078
b4,g,lsb,xy         .. text: "U-2d!=7v6"
b4,b,msb,xy         .. text: "b\"~bN  rIP"```
This gave us several interesting outputs, but one in particular stood out:

```bash
b1,rgb,lsb,xy       .. text: "79:#include <stdio.h>\\n\\nint main() {\\n\\n    printf(\\"Th15_1s_RC!\\");\\n\\n    return 0;\\n\\n}\\nVrP"
````

This snippet shows a simple C program where the printf() function reveals the flag directly.

## 🎯 Flag

**WTISD{Th15_1s_RC!}**
