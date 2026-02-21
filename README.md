<div align="center">

# EasyPi

**Binary releases for Raspberry Pi**

No source code is published in this repository.

</div>

---

## UI Preview

![Dashboard](screenshots/dashboard/dashboard-1.png)

More screenshots: [docs/SCREENSHOTS.md](docs/SCREENSHOTS.md)

---

## Install (Raspberry Pi aarch64)

1. Open [Releases](../../releases) and download:
- `easypi-full-aarch64.tar.gz`
- `SHA256SUMS.txt`

2. Verify checksum:

```bash
sha256sum easypi-full-aarch64.tar.gz
cat SHA256SUMS.txt
```

3. Install:

```bash
sudo mkdir -p /opt/EasyPi
sudo tar -xzf easypi-full-aarch64.tar.gz -C /opt/EasyPi
sudo bash /opt/EasyPi/install.sh --binary
```

---

## Notes

- First open uses HTTPS with a self-signed certificate.
- Browser warning `ERR_CERT_AUTHORITY_INVALID` is expected for local IP access.
- This does **not** mean the installer archive is unsafe.

---

## License

Proprietary license: see [LICENSE](LICENSE).
