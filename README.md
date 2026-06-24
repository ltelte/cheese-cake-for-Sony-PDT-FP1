CVE-2025-21479 - Qualcomm GPU Privilege Escalation Exploit

## 🚨 Critical Security Notice

This code is provided for authorized security research and educational purposes only. Use only on devices you own or have explicit permission to test.

---

## 📱 Tested Environment

| Component | Specification |
|-----------|---------------|
| **Device** | Sony Portable Data Transmitter (PDT-FP1) |
| **Firmware** | PDT-FP1_Customized_EU_UK_67.1.G.2.62 |
| **Android Version** | 14 |
| **Security Patch Level** | 2025-05-01 |
| **SoC** | Snapdragon 8 Gen 2 (SM8550 / kalama) |
| **GPU** | Adreno 740 v2 |

---

## 🔧 Usage

```bash
# Connect device via ADB
adb shell

# Execute exploit
/data/local/tmp/exploit-fw_67.1.G.2.62_EU
```

---

## 🛡️ Vulnerability Check

Verify vulnerable firmware pattern:

```bash
xxd /vendor/firmware/a740_sqe.fw | grep -i "0300 422a"
```

Pattern Comparison:

Status Assembly Mask Value
Vulnerable (v675) and $04, $12, 0x3 0x3
Patched (v676) and $04, $12, 0x7 0x7

ℹ️ Note: If the grep output shows 0300 422a, the firmware is vulnerable.

---

## 📚 References

- [Cheese - GPU Exploitation Framework](https://github.com/zhuowei/cheese)
- [CVE-2025-21479 Technical Analysis](https://xploitbengineer.github.io/CVE-2025-21479)
- [JD Dawn Security Lab Writeup](https://dawnslab.jd.com/android_gpu_attack_cve_2025_21479/#more)

---

## ⚠️ Important Notes

- **Exact device and firmware must match** for successful exploitation
- This exploit targets the Qualcomm Adreno GPU driver vulnerability
- The vulnerability allows for privilege escalation on affected devices
- **DO NOT use on production devices or unauthorized systems**

---

## 🏛️ License & Ethics

This repository is for security research purposes. By using this code, you agree to:

1. Use only on devices you own or have explicit authorization to test
2. Report vulnerabilities responsibly to vendors
3. Not use for malicious purposes or unauthorized access
4. Comply with all applicable laws and regulations

---

## 🔒 Disclaimer

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND. The authors and contributors are not responsible for any misuse or damage caused by this code.

---
