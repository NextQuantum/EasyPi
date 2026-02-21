<div align="center">

<img src="assets/logo.svg" width="120" alt="EasyPi Logo" />

# EasyPi

**The all-in-one web dashboard for your Raspberry Pi.**  
Monitor, secure, and control everything — no SSH required.

<br/>

[![License](https://img.shields.io/badge/License-Proprietary-FF6B35.svg?style=for-the-badge)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.9+-3776AB.svg?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![React](https://img.shields.io/badge/React-18+-61DAFB.svg?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-latest-009688.svg?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5+-3178C6.svg?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Raspberry Pi](https://img.shields.io/badge/Raspberry_Pi-3%2F4%2F5-C51A4A.svg?style=for-the-badge&logo=raspberrypi&logoColor=white)](https://www.raspberrypi.com/)

<br/>

[🇬🇧 English](#-english) · [🇷🇺 Русский](#-русский) · [🇩🇪 Deutsch](#-deutsch)

</div>

---

## 📸 UI Preview

| | |
|:-:|:-:|
| ![Dashboard](assets/screenshots/dashboard/dashboard-1.png) | ![Dashboard](assets/screenshots/dashboard/dashboard-2.png) |

More screenshots: [`docs/SCREENSHOTS.md`](docs/SCREENSHOTS.md)

---

# 🇬🇧 English

## � At a Glance

| 🖥️ Live Dashboard | 🔐 Security Suite | 📵 Parental Control |
|:-:|:-:|:-:|
| Real-time CPU, RAM, temperature | 2FA · PiGuard Scanner · Firewall | Block 40+ streaming apps & all bypass attempts |

| 🤖 AI Assistant | 🌐 VPN Management | 💾 Backup |
|:-:|:-:|:-:|
| Claude AI for diagnostics & setup | WireGuard + Tailscale with QR codes | Scheduled backups with one-click restore |

---

## ✨ Features

### 🖥️ Dashboard & Real-Time Monitoring

- Live metrics: **CPU · RAM · Temperature · Disk**
- **Network activity** (RX/TX traffic graphs)
- System services status at a glance
- Beautiful **historical charts** for all metrics

---

### 🚀 One-Click Service Management

- Install **Pi-hole, WireGuard, Jellyfin, Home Assistant** and 15+ more — in one click
- **Curated bundles**: Media Server · Smart Home · Monitoring
- **Service catalog** with detailed descriptions and state tracking

---

### 🔐 Enterprise-Grade Security

| Feature | Details |
|---|---|
| 2FA | TOTP-based two-factor authentication |
| Session auth | Secure `httpOnly` + `SameSite` cookies + JWT (7-day lifetime) |
| Session management | Per-device tracking & one-click revocation |
| PiGuard Scanner | Automated vulnerability detection |
| Firewall | UFW / iptables management |
| SSL/TLS | Full certificate support |
| CSRF protection | All state-mutating operations protected |
| Rate limiting | API brute-force protection |

**🧭 Full Gateway Mode** — ensures the Pi stays the network gateway:
- Auto-fix gateway routing loops (self-route recovery)
- Persistent IP forwarding across reboots
- NAT survives proxy restarts

---

### 📵 Parental Control & Streaming Blocker

> **DNS-based protection** — each device shows `DNS active / stale / not seen` status so you can verify protection at a glance.

**40+ blocked services:** YouTube · Netflix · TikTok · Instagram · Facebook · WhatsApp · Telegram · Discord · Twitch · Spotify · Amazon Prime · Disney+ · HBO Max · Hulu · Reddit · Twitter · Roblox · Fortnite · Steam · Epic Games · and more.

**Multi-layer blocking engine:**

| Layer | What it blocks |
|---|---|
| DNS | All known domains + CDN endpoints |
| ASN/IP | Hardcoded IPs (e.g. AS2906 for Netflix) |
| DoH/DoT kill | Encrypted DNS bypass prevention |
| Ports (iptables) | OpenVPN · IPSec · Tor · PPTP · Shadowsocks · SOCKS |

**Bypass Protection (auto-enabled):** 170+ VPN / DoH / Tor / Proxy domains + 19 ports

| Provider type | Count |
|---|---|
| VPN providers blocked | 40+ (NordVPN, ExpressVPN, ProtonVPN, Surfshark…) |
| DNS-over-HTTPS providers | 25+ (1.1.1.1, dns.google, cloudflare-dns.com…) |
| Proxy services | 25+ (hide.me, kproxy.com, croxyproxy.com…) |
| Tor exit points | torproject.org · bridges · *.onion |

**Fail-Closed Quarantine** *(optional)* — if a bypass is detected, EasyPi cuts **all internet** for that device until the admin clicks **Restore Internet**. Most effective with **Full Gateway Mode**.

> 📌 WireGuard / Tailscale ports (51820, 51821) are intentionally **not blocked** — EasyPi compatibility.

---

### 🌐 VPN & Remote Access

- **WireGuard VPN** with QR code generation for mobile clients
- **Tailscale Admin API**: auto DNS config, device management, route approval
- **PiCloud**: connect your Pi to cloud infrastructure
- Remote access configuration wizard

---

### 🤖 AI Assistant (Claude)

- Chat-based assistant powered by **Claude AI**
- Installs and configures services on demand
- Diagnoses problems from system logs
- Suggests shell commands with explanations
- Context-aware, system-specific recommendations

---

### 💾 Backup & Restore

- Scheduled automatic backups
- Full system snapshots (configs + databases)
- **One-click restore**
- Configuration versioning

---

### 📁 File Manager & 🔐 Encryption

- Web-based file browser and editor with **syntax highlighting**
- Upload / download files from any browser
- **PiCloud AES-256-GCM encryption** — client-side, password never leaves your browser
  - PBKDF2 with 100,000 iterations (brute-force hardened)
  - Unique Salt + IV per file
  - Magic bytes `EPEC` for easy identification

---

### 💻 Web Terminal

- **WebSSH Terminal** — full shell access in the browser
- Session recording & playback
- Multiple concurrent sessions

---

### 📹 Security Cameras

- RTSP camera integration
- Live view in browser
- Recording management

---

### 🔔 Notifications

- **Push notifications** in browser
- **Email notifications** (SMTP)
- Customizable preferences with quiet-hours support

---

### 📱 PWA & 🔧 Network Tools

- **PWA** — install as a mobile app, works partially offline
- **Port scanner** with range support
- **LAN device discovery**
- **Network speed test**
- **Network topology map**
- **Live traffic monitor**
- **Dark / Light theme**, fully responsive design

---

## 🏗️ Architecture

```
╔══════════════════════════════════════════════════════════╗
║          Frontend  ·  React 18 + TypeScript              ║
║     Vite · Tailwind CSS · Zustand · TanStack Query       ║
║         Recharts · xterm.js · vis-network                ║
╚══════════════════════════╤═══════════════════════════════╝
                           │  WebSocket + REST API
╔══════════════════════════╧═══════════════════════════════╗
║       Backend  ·  FastAPI + Uvicorn (Python 3.9+)        ║
║    SQLAlchemy · Alembic · Pydantic v2 · psutil           ║
║         paramiko (SSH) · go2rtc (WebRTC)                 ║
╚══════════════════════════╤═══════════════════════════════╝
                           │
╔══════════════════════════╧═══════════════════════════════╗
║    SQLite / PostgreSQL · System Services · Raspberry Pi  ║
╚══════════════════════════════════════════════════════════╝
```

### 🛠️ Tech Stack

| Layer | Technologies |
|---|---|
| **Frontend** | React 18 · TypeScript · Vite · Tailwind CSS · Zustand · TanStack Query · Recharts · xterm.js |
| **Backend** | FastAPI · Python 3.9+ · SQLAlchemy · Alembic · WebSockets · psutil |
| **System** | SQLite · UFW/iptables · WireGuard · Tailscale · go2rtc |

---

## 🚀 Quick Start

### Binary Release (Recommended)

1. Download the latest `easypi-full-aarch64.tar.gz` from [GitHub Releases](https://github.com/NextQuantum/EasyPi/releases).
2. Verify checksum against [`distribution/releases/SHA256SUMS.txt`](distribution/releases/SHA256SUMS.txt).
3. Install on Raspberry Pi:

```bash
sudo mkdir -p /opt/EasyPi
sudo tar -xzf easypi-full-aarch64.tar.gz -C /opt/EasyPi
sudo bash /opt/EasyPi/install.sh --binary
```

### Requirements

| Requirement | Minimum | Recommended |
|---|---|---|
| Hardware | Raspberry Pi 3 | **Pi 4 · 4 GB RAM** |
| OS | Raspberry Pi OS Bullseye | Latest Raspberry Pi OS |
| Storage | 16 GB SD card | **32 GB SD card** |
| Network | Internet connection | Wired Ethernet |

### Installation from Source

```bash
git clone https://github.com/NextQuantum/EasyPi.git
cd EasyPi
chmod +x install.sh
./install.sh
```

### First Access

```
https://your-pi-address/
  — or —
https://easypi.local/
```

> If the browser shows `Your connection is not private` / `net::ERR_CERT_AUTHORITY_INVALID` on the local EasyPi IP — this is expected with a self-signed certificate. On a trusted home network, click **Proceed to site (unsafe)**.

> **No default credentials.** On first launch EasyPi shows a setup screen to create your admin account and displays a **recovery token** — save it securely.

---

# 🇷🇺 Русский

<div align="center">

**EasyPi** — полноценная веб-панель управления Raspberry Pi.  
Мониторинг, безопасность и контроль — без SSH и командной строки.

</div>

---

## ✨ Возможности

### 🖥️ Dashboard и мониторинг

- Живые метрики: **CPU · RAM · Температура · Диск**
- **Сетевая активность** (графики RX/TX)
- Статус системных сервисов
- **История метрик** в виде графиков

---

### 🚀 Управление сервисами

- **Pi-hole, WireGuard, Jellyfin, Home Assistant** и 15+ других — в один клик
- **Готовые наборы**: Media Server · Smart Home · Monitoring
- **Каталог сервисов** с описаниями

---

### 🔐 Безопасность

| Функция | Описание |
|---|---|
| 2FA | TOTP двухфакторная аутентификация |
| Сессии | Secure `httpOnly` + `SameSite` cookies + JWT (7 дней) |
| Управление сессиями | Отслеживание устройств и мгновенный отзыв |
| PiGuard Scanner | Автоматическое обнаружение уязвимостей |
| Firewall | Управление UFW / iptables |
| SSL/TLS | Полная поддержка сертификатов |
| CSRF защита | Все изменяющие состояние операции |
| Rate limiting | Защита API от брутфорса |

**🧭 Full Gateway Mode:**
- Авто-исправление loop-маршрутов
- Постоянный IP Forwarding после перезагрузки
- NAT не пропадает при перезапуске прокси

---

### 📵 Родительский контроль

> Статус `DNS active / stale / not seen` для каждого устройства.

**40+ заблокированных сервисов:** YouTube · Netflix · TikTok · Instagram · Facebook · WhatsApp · Telegram · Discord · Twitch · Spotify · Amazon Prime · Disney+ · HBO Max · Hulu · Reddit · Twitter · Roblox · Fortnite · Steam · Epic Games · и другие.

| Уровень | Что блокирует |
|---|---|
| DNS | Все известные домены + CDN |
| ASN/IP | Захардкоженные IP (напр. AS2906 для Netflix) |
| DoH/DoT | Зашифрованный DNS |
| Порты | OpenVPN · IPSec · Tor · PPTP · Shadowsocks · SOCKS |

**Защита от обхода:** 170+ доменов + 19 портов

| Тип | Количество |
|---|---|
| VPN-провайдеры | 40+ |
| DoH провайдеры | 25+ |
| Прокси-сервисы | 25+ |
| Tor | torproject.org · bridges · *.onion |

**Fail-Closed карантин** — при обнаружении обхода блокирует **весь интернет** до нажатия **Restore Internet**.

> 📌 Порты WireGuard / Tailscale (51820, 51821) **не блокируются**.

---

### 🌐 VPN и удалённый доступ

- **WireGuard VPN** с QR-кодами для мобильных
- **Tailscale Admin API**: авто-настройка DNS, управление устройствами
- **PiCloud**: подключение к облачной инфраструктуре

---

### 🤖 AI Ассистент

- **Claude AI** — диагностика, настройка, команды
- Контекстно-зависимые рекомендации

---

### 💾 Резервное копирование

- Автоматические бэкапы по расписанию
- Полные снимки системы
- **Восстановление одним кликом**

---

### 📁 Файловый менеджер и 🔐 шифрование

- Просмотр и редактирование файлов в браузере
- **AES-256-GCM** (PiCloud) — шифрование на стороне клиента
- PBKDF2 с 100 000 итераций, уникальные Salt + IV

---

### 💻 Терминал · 📹 Камеры · 📱 PWA · 🔧 Сеть

- **WebSSH Терминал** — запись и воспроизведение сессий
- **RTSP видеонаблюдение** — живой просмотр
- **PWA** — установка как мобильное приложение
- **Сетевые инструменты**: сканер портов, обнаружение устройств, спидтест, карта топологии

---

## 🚀 Быстрый старт

### Бинарный релиз (рекомендуется)

1. Скачай `easypi-full-aarch64.tar.gz` из [GitHub Releases](https://github.com/NextQuantum/EasyPi/releases).
2. Проверь контрольную сумму: [`distribution/releases/SHA256SUMS.txt`](distribution/releases/SHA256SUMS.txt).
3. Установи:

```bash
sudo mkdir -p /opt/EasyPi
sudo tar -xzf easypi-full-aarch64.tar.gz -C /opt/EasyPi
sudo bash /opt/EasyPi/install.sh --binary
```

### Требования

| Требование | Минимум | Рекомендуется |
|---|---|---|
| Железо | Raspberry Pi 3 | **Pi 4 · 4 ГБ ОЗУ** |
| ОС | Raspberry Pi OS Bullseye | Последняя версия |
| Хранилище | SD карта 16 ГБ | **SD карта 32 ГБ** |
| Сеть | Интернет-подключение | Проводной Ethernet |

### Установка из исходников

```bash
git clone https://github.com/NextQuantum/EasyPi.git
cd EasyPi
chmod +x install.sh
./install.sh
```

### Первый вход

```
https://адрес-вашего-pi/
  — или —
https://easypi.local/
```

> Если браузер показывает `Подключение не защищено` — нормально для самоподписанного сертификата. Нажми **«Перейти на сайт (небезопасно)»**.

> **Логина и пароля по умолчанию нет.** При первом запуске создашь admin-аккаунт и получишь **recovery token** — сохрани.

---

# 🇩🇪 Deutsch

<div align="center">

**EasyPi** — das All-in-One-Dashboard für Ihren Raspberry Pi.  
Überwachung, Sicherheit und Kontrolle — ganz ohne SSH.

</div>

---

## ✨ Funktionen

### 🖥️ Dashboard & Echtzeit-Monitoring

- Live-Metriken: **CPU · RAM · Temperatur · Festplatte**
- **Netzwerkaktivität** (RX/TX-Graphen)
- Dienste-Status auf einen Blick
- **Historische Diagramme** für alle Metriken

---

### 🚀 Dienstverwaltung mit einem Klick

- **Pi-hole, WireGuard, Jellyfin, Home Assistant** und 15+ weitere — in einem Klick
- **Fertige Stacks**: Media Server · Smart Home · Monitoring
- **Dienstkatalog** mit ausführlichen Beschreibungen

---

### 🔐 Enterprise-Sicherheit

| Funktion | Details |
|---|---|
| 2FA | TOTP-basierte Zwei-Faktor-Authentifizierung |
| Sessions | Secure `httpOnly` + `SameSite` Cookies + JWT (7 Tage) |
| Sitzungsverwaltung | Geräteverfolgung & sofortiger Widerruf |
| PiGuard Scanner | Automatische Schwachstellenerkennung |
| Firewall | UFW / iptables-Verwaltung |
| SSL/TLS | Vollständige Zertifikatunterstützung |
| CSRF-Schutz | Alle zustandsändernden Operationen |
| Rate Limiting | API-Brute-Force-Schutz |

**🧭 Full Gateway Mode:**
- Auto-Fix für Gateway-Routing-Schleifen
- Persistentes IP-Forwarding nach Neustarts
- NAT bleibt aktiv bei Proxy-Neustarts

---

### 📵 Kindersicherung & Streaming-Blocker

> Pro Gerät wird `DNS active / stale / not seen` angezeigt.

**40+ gesperrte Dienste:** YouTube · Netflix · TikTok · Instagram · Facebook · WhatsApp · Telegram · Discord · Twitch · Spotify · Amazon Prime · Disney+ · HBO Max · Hulu · Reddit · Twitter · Roblox · Fortnite · Steam · Epic Games · und mehr.

| Ebene | Was blockiert wird |
|---|---|
| DNS | Alle bekannten Domains + CDN-Endpunkte |
| ASN/IP | Hardcodierte IPs (z.B. AS2906 für Netflix) |
| DoH/DoT | Verschlüsselte DNS-Umgehung |
| Ports | OpenVPN · IPSec · Tor · PPTP · Shadowsocks · SOCKS |

**Umgehungsschutz:** 170+ Domains + 19 Ports

**Fail-Closed Quarantäne** — bei erkannter Umgehung sperrt EasyPi das **gesamte Internet** bis **Restore Internet** geklickt wird.

> 📌 WireGuard / Tailscale-Ports (51820, 51821) werden **nicht blockiert**.

---

### 🌐 VPN & Fernzugriff

- **WireGuard VPN** mit QR-Code-Generierung
- **Tailscale Admin API**: automatische DNS-Konfiguration
- **PiCloud**: Raspberry Pi mit Cloud verbinden

---

### 🤖 KI-Assistent · 💾 Backup · 📁 Dateien · 💻 Terminal

- **Claude AI** — Diagnose, Befehle, Servicekonfiguration
- **Backup & Restore** — geplante Sicherungen, Ein-Klick-Wiederherstellung
- **Dateimanager** mit Code-Editor und AES-256-GCM Verschlüsselung
- **WebSSH-Terminal** — vollständiger Shell-Zugriff im Browser
- **RTSP-Kameras** — Live-Ansicht + Aufnahmeverwaltung
- **PWA** — Als mobile App installierbar
- **Netzwerk-Tools**: Port-Scanner, Speedtest, Topologie-Map

---

## 🚀 Schnellstart

### Binary Release (Empfohlen)

1. `easypi-full-aarch64.tar.gz` von [GitHub Releases](https://github.com/NextQuantum/EasyPi/releases) herunterladen.
2. Prüfsumme verifizieren: [`distribution/releases/SHA256SUMS.txt`](distribution/releases/SHA256SUMS.txt).
3. Installieren:

```bash
sudo mkdir -p /opt/EasyPi
sudo tar -xzf easypi-full-aarch64.tar.gz -C /opt/EasyPi
sudo bash /opt/EasyPi/install.sh --binary
```

### Anforderungen

| Anforderung | Minimum | Empfohlen |
|---|---|---|
| Hardware | Raspberry Pi 3 | **Pi 4 · 4 GB RAM** |
| Betriebssystem | Raspberry Pi OS Bullseye | Aktuelle Raspberry Pi OS |
| Speicher | 16 GB SD-Karte | **32 GB SD-Karte** |
| Netzwerk | Internetverbindung | Kabelgebundenes Ethernet |

### Installation aus Quellcode

```bash
git clone https://github.com/NextQuantum/EasyPi.git
cd EasyPi
chmod +x install.sh
./install.sh
```

### Erster Zugriff

```
https://ihre-pi-adresse/
  — oder —
https://easypi.local/
```

> Wenn der Browser `Verbindung ist nicht privat` zeigt — normal bei einem selbstsignierten Zertifikat. Im vertrauenswürdigen Heimnetz **„Weiter zur Website (unsicher)"** wählen.

> **Keine Standard-Anmeldedaten.** Beim ersten Start Admin-Konto erstellen und **Recovery-Token** sichern.

---

<div align="center">

## 📜 License · Лицензия · Lizenz

Distributed under a **proprietary license** — see [LICENSE](LICENSE) and [EULA.txt](EULA.txt).

---

## 🤝 Contributing

| How to help | Action |
|---|---|
| 🐛 Found a bug? | [Open an Issue](https://github.com/NextQuantum/EasyPi/issues) |
| 💡 Have an idea? | Describe your feature request |
| 🔧 Want to code? | Submit a Pull Request |
| 📖 Improve docs? | Updates are always welcome |
| ⭐ Like EasyPi? | Star the repo — it helps! |

---

<sub>Made with ❤️ for the Raspberry Pi community</sub>

[⬆ Back to top](#easypi)

</div>

