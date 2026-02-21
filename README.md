# EasyPi (Binary Release)

This repository contains **binary releases only**.

## Install (Raspberry Pi aarch64)

1. Download `easypi-full-aarch64.tar.gz` from Releases.
2. Verify checksum from `SHA256SUMS.txt`.
3. Install:

```bash
sudo mkdir -p /opt/EasyPi
sudo tar -xzf easypi-full-aarch64.tar.gz -C /opt/EasyPi
sudo bash /opt/EasyPi/install.sh --binary
```
