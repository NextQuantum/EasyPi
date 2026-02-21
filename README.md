<div align="center">

# EasyPi

**Raspberry Pi Security & Network Control Dashboard**  
**Binary releases only** (no source code in this repository)

[![Release](https://img.shields.io/github/v/release/NextQuantum/EasyPi?display_name=tag&style=for-the-badge)](https://github.com/NextQuantum/EasyPi/releases)
[![Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi%20(aarch64)-C51A4A?style=for-the-badge)](#install)
[![License](https://img.shields.io/badge/License-Proprietary-111827?style=for-the-badge)](LICENSE)

</div>

---

## What You Get

EasyPi gives you a web interface to manage network protection on Raspberry Pi:

- Dashboard with live system stats
- Guard Security / parental controls / bypass detection
- DNS controls and filtering
- VPN, remote access, network tools
- Backups and restore flows

---

## Screenshots

![Dashboard](screenshots/dashboard/dashboard-1.png)

| Security | Network Toolkit |
|---|---|
| ![Guard Security](screenshots/guard-security/5-parents-control.png) | ![Toolkit](screenshots/network-toolkit/1-toolkit.png) |

More screenshots: [docs/SCREENSHOTS.md](docs/SCREENSHOTS.md)

---

## Install

### 1. Download release files

Open [Releases](https://github.com/NextQuantum/EasyPi/releases) and download:

- `easypi-full-aarch64.tar.gz`
- `SHA256SUMS.txt`

### 2. Verify checksum (recommended)

Linux/macOS:

```bash
sha256sum easypi-full-aarch64.tar.gz
cat SHA256SUMS.txt
```

PowerShell:

```powershell
Get-FileHash .\easypi-full-aarch64.tar.gz -Algorithm SHA256
Get-Content .\SHA256SUMS.txt
```

### 3. Install on Raspberry Pi

```bash
sudo mkdir -p /opt/EasyPi
sudo tar -xzf easypi-full-aarch64.tar.gz -C /opt/EasyPi
sudo bash /opt/EasyPi/install.sh --binary
```

After install, open:

- `https://<RASPBERRY_PI_IP>/`

---

## First Login / Certificate Warning

For local IP HTTPS, browser may show `ERR_CERT_AUTHORITY_INVALID`.  
This is expected with self-signed local certificates.

You can continue manually (`Advanced` -> `Proceed`) on your own trusted LAN.

---

## Update to New Version

1. Download a newer release archive.
2. Extract over `/opt/EasyPi`.
3. Run installer again:

```bash
sudo bash /opt/EasyPi/install.sh --binary
```

---

## Troubleshooting

Check service status:

```bash
sudo systemctl --no-pager -l status easypi-backend easypi-netprotection nginx
```

Live logs:

```bash
sudo journalctl -u easypi-backend -f
sudo journalctl -u easypi-netprotection -f
```

---

## License

This project is distributed under a proprietary license.  
See [LICENSE](LICENSE).
