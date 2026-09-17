# KhOS 🛡️

**KhOS** is a custom, lightweight, Debian-based Linux distribution built specifically for CTF players, security enthusiasts, and reverse engineers. It comes pre-packaged with essential reversing tools, security utilities, and a clean, familiar Windows-style XFCE desktop optimized for virtual machines.

---

## ⚡ Key Highlights

- **Base**: Debian 12 (Bookworm)
- **Desktop Environment**: XFCE4 (Windows-style workflow with Whisker Menu)
- **Memory Footprint**: Sub-500 MB idle RAM usage
- **VM Ready**: Out-of-the-box auto-resizing, clipboard sharing, and display scaling via X11 integration
- **Pre-installed Tooling**:
  - **Browser**: Brave Browser (Prepped for proxy switching)
  - **Reverse Engineering**: Ghidra Suite, GDB, Pwntools, Binwalk
  - **Network & Pentest**: Nmap, Wireshark, Tshark, Netcat, Socat, Tcpdump
  - **Web & Password Cracking**: Nikto, SQLmap, Hydra, John the Ripper, Hashcat

---

## 📥 Download ISO

You can download the bootable hybrid ISO directly:

[![Download KhOS ISO](https://img.shields.io/badge/Download-KhOS%20v1.0%20(Google%20Drive)-4285F4?style=for-the-badge&logo=googledrive&logoColor=white)](https://drive.google.com/uc?export=download&id=1o6rlPdm1dNpkBkJsAnbMcFCrkSiPPJyE)

> **Direct Download Link:** [KhOS Hybrid ISO](https://drive.google.com/uc?export=download&id=1o6rlPdm1dNpkBkJsAnbMcFCrkSiPPJyE)

---

## 🛠️ Recommended VM Configuration (VirtualBox / VMware)

| Resource | Recommended | Minimum |
|---|---|---|
| **RAM** | 4 GB | 2 GB |
| **vCPU** | 2 - 4 Cores | 1 Core |
| **Storage** | 30 GB | 20 GB |
| **Graphics Controller** | VMSVGA (128 MB VRAM) | VMSVGA (64 MB) |
| **Features** | Bidirectional Clipboard & Drag'n'Drop | Standard |

---

## 🏗️ Building From Source

KhOS is built using Debian's native `live-build` framework. To recreate the image locally:

```bash
# 1. Install live-build dependencies
sudo apt update && sudo apt install -y live-build debootstrap squashfs-tools xorriso

# 2. Clone this repository
git clone https://github.com/z41hk/KhOS.git
cd KhOS

# 3. Initialize configuration
lb config \
  --distribution bookworm \
  --binary-images iso-hybrid \
  --archive-areas "main contrib non-free non-free-firmware" \
  --system live

# 4. Compile the ISO
sudo lb build
