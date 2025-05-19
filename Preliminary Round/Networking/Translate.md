# 🌐 Translate

### Category: Forensics

**Tools Used:** Wireshark, OpenSSL

---

## 🛠️ Steps to Solve

1. **Opened the `.pcap` file** in **Wireshark**.

2. Applied `Follow TCP Stream` on the relevant packets.

3. Inside the stream, a conversation was found:

```txt
Hi, This is Salt, your team mate for the web project.
did you ping to Boss?
It happens for the beginners.
You have used the default password. Don't do it.
you know it's very secret.
Did you get the file from Boss?
He might forgot it.
I will let him remember about it.
use Artcrypt25isH3r3 there.
```

➡️ Password Found: Artcrypt25isH3r3

## 🔐 Decryption Phase

At the bottom of the stream, found this blob (AES-encrypted):

```bash
Salted__..Y,Os.3.........z.......#u.D...[.)dM......3..<.q<.+.4..p
```

Clicked on "Show as" → Raw, then saved the output as: **encrypted.bin**
Decrypted it using OpenSSL AES-256-CBC:

```bash
openssl enc -aes-256-cbc -d -in encrypted.bin -out decrypted.txt -pass pass:Artcrypt25isH3r3
```

Opened the decrypted.txt file:

## 🎯 Flag

**F1@g{4r7_15_7h3_34rl1357_f0rm_0f_3ncryp710n}**
