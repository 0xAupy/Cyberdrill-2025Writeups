# 📡 Transmission

### Category: Forensics

**Tool Used:** `Wireshark`

---

## 🛠️ Steps to Solve

1. Opened the `.pcap` file using **Wireshark**.

2. Applied the following display filter to isolate relevant packets:

```bash
frame.len == 60 && icmp
```

3. Inspected the ICMP packets—each one contained a portion of the flag in the payload.

4. Assembled the fragments to reconstruct the full flag.

## 🎯 Flag

**fl4g{Hum4n_15_7h3_w34k357_l1nk_1n_Cyb3r53cur17y}**
