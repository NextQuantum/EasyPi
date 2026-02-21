<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=36&pause=1000&color=FF6B35&center=true&vCenter=true&width=600&lines=🥧+EasyPi;Raspberry+Pi+Web+Manager" alt="EasyPi" />

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

![EasyPi Dashboard](assets/screenshots/dashboard/dashboard-1.png)

More screenshots: [`docs/SCREENSHOTS.md`](docs/SCREENSHOTS.md)

---

# 🇬🇧 English

<div align="center">

## 📸 At a Glance

| 🖥️ Live Dashboard | 🔐 Security Suite | 📵 Parental Control |
|:-:|:-:|:-:|
| Real-time CPU, RAM, temperature | 2FA · PiGuard Scanner · Firewall | Block 40+ streaming apps, all bypass attempts |

| 🤖 AI Assistant | 🌐 VPN Management | 💾 Cloud Backup |
|:-:|:-:|:-:|
| Claude AI for diagnostics & setup | WireGuard + Tailscale with QR codes | Scheduled backups with one-click restore |

</div>

---

## ✨ Features

<details open>
<summary><b>🖥️ Dashboard & Real-Time Monitoring</b></summary>
<br/>

- Live metrics for **CPU · RAM · Temperature · Disk**
- **Network activity** (RX/TX traffic graphs)
- System services status at a glance
- Beautiful **historical charts** for all metrics

</details>

<details open>
<summary><b>🚀 One-Click Service Management</b></summary>
<br/>

- Install **Pi-hole, WireGuard, Jellyfin, Home Assistant** and 15+ more — in one click
- **Curated bundles**: Media Server · Smart Home · Monitoring
- **Service catalog** with detailed descriptions and state tracking

</details>

<details open>
<summary><b>🔐 Enterprise-Grade Security</b></summary>
<br/>

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

</details>

<details open>
<summary><b>📵 Parental Control & Streaming Blocker</b></summary>
<br/>

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

</details>

<details>
<summary><b>🌐 VPN & Remote Access</b></summary>
<br/>

- **WireGuard VPN** with QR code generation for mobile clients
- **Tailscale Admin API**: auto DNS config, device management, route approval
- **PiCloud**: connect your Pi to cloud infrastructure
- Remote access configuration wizard

</details>

<details>
<summary><b>🤖 AI Assistant (Claude)</b></summary>
<br/>

- Chat-based assistant powered by **Claude AI**
- Installs and configures services on demand
- Diagnoses problems from system logs
- Suggests shell commands with explanations
- Context-aware, system-specific recommendations

</details>

<details>
<summary><b>💾 Backup & Restore</b></summary>
<br/>

- Scheduled automatic backups
- Full system snapshots (configs + databases)
- **One-click restore**
- Configuration versioning

</details>

<details>
<summary><b>📁 File Manager & 🔐 Encryption</b></summary>
<br/>

- Web-based file browser and editor with **syntax highlighting**
- Upload / download files from any browser
- **PiCloud AES-256-GCM encryption** — client-side, password never leaves your browser
  - PBKDF2 with 100,000 iterations (brute-force hardened)
  - Unique Salt + IV per file
  - Magic bytes `EPEC` for easy identification

</details>

<details>
<summary><b>💻 Web Terminal, 📹 Cameras & more</b></summary>
<br/>

- **WebSSH Terminal** — full shell access in the browser, with session recording & playback
- **RTSP Security Camera** integration — live view + recording management
- **Push & Email notifications** (SMTP) with quiet-hours support
- **PWA** — install as a mobile app, works partially offline
- **Network Tools** — port scanner, LAN discovery, speed test, topology map, live traffic monitor
- **Dark / Light theme** with fully responsive design

</details>

---

## 🏗️ Architecture

```
╔══════════════════════════════════════════════════╗
║        Frontend  ·  React 18 + TypeScript        ║
║        Vite  ·  Tailwind CSS  ·  Zustand         ║
╚══════════════════════╤═══════════════════════════╝
                       │  WebSocket + REST API
╔══════════════════════╧═══════════════════════════╗
║       Backend  ·  FastAPI (Python 3.9+)          ║
║       SQLAlchemy  ·  Alembic  ·  psutil          ║
╚══════════════════════╤═══════════════════════════╝
                       │
╔══════════════════════╧═══════════════════════════╗
║     SQLite  ·  System Services  ·  Raspberry Pi  ║
╚══════════════════════════════════════════════════╝
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

1. Download the latest `easypi-full-aarch64.tar.gz` from GitHub Releases.
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

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/NextQuantum/EasyPi.git
cd EasyPi

# 2. Run the installer
chmod +x install.sh
./install.sh
```

### First Access

```
https://your-pi-address/
  — or —
https://easypi.local/
```

> If the browser shows `Your connection is not private` / `net::ERR_CERT_AUTHORITY_INVALID` on local EasyPi IP (for example, `192.168.89.226`), this is expected with a self-signed certificate. On a trusted home network, you can click **Proceed to site (unsafe)**.

> **No default credentials.** On first launch EasyPi shows a setup screen to create your admin account and displays a **recovery token** — save it securely.

---

# 🇷🇺 Русский

<div align="center">

**EasyPi** — полноценная веб-панель управления Raspberry Pi.  
Мониторинг, безопасность и контроль — без SSH и командной строки.

</div>

---

## ✨ Возможности

<details open>
<summary><b>🖥️ Dashboard и мониторинг в реальном времени</b></summary>
<br/>

- Живые метрики: **CPU · RAM · Температура · Диск**
- Мониторинг **сетевой активности** (графики RX/TX трафика)
- Статус системных сервисов с первого взгляда
- **История метрик** в виде красивых графиков

</details>

<details open>
<summary><b>🚀 Управление сервисами одним кликом</b></summary>
<br/>

- Установка **Pi-hole, WireGuard, Jellyfin, Home Assistant** и 15+ других — в один клик
- **Готовые наборы**: Media Server · Smart Home · Monitoring
- **Каталог сервисов** с подробными описаниями

</details>

<details open>
<summary><b>🔐 Безопасность корпоративного уровня</b></summary>
<br/>

| Функция | Описание |
|---|---|
| 2FA | Двухфакторная аутентификация на TOTP |
| Сессии | Secure `httpOnly` + `SameSite` cookies + JWT (7 дней) |
| Управление сессиями | Отслеживание устройств и мгновенный отзыв |
| PiGuard Scanner | Автоматическое обнаружение уязвимостей |
| Firewall | Управление UFW / iptables |
| SSL/TLS | Полная поддержка сертификатов |
| CSRF защита | Все изменяющие состояние операции защищены |
| Rate limiting | Защита API от брутфорса |

**🧭 Full Gateway Mode:**
- Авто-исправление loop-маршрутов (если шлюз — сам Pi)
- Постоянный IP Forwarding после перезагрузки
- NAT не пропадает при перезапуске прокси

</details>

<details open>
<summary><b>📵 Родительский контроль и блокировка стримингов</b></summary>
<br/>

> Для каждого устройства отображается статус `DNS active / stale / not seen` — сразу видно, защищено ли устройство.

**40+ заблокированных сервисов:** YouTube · Netflix · TikTok · Instagram · Facebook · WhatsApp · Telegram · Discord · Twitch · Spotify · Amazon Prime · Disney+ · HBO Max · Hulu · Reddit · Twitter · Roblox · Fortnite · Steam · Epic Games · и другие.

**Многоуровневая система блокировки:**

| Уровень | Что блокирует |
|---|---|
| DNS | Все известные домены + CDN |
| ASN/IP | Захардкоженные IP (напр. AS2906 для Netflix) |
| DoH/DoT | Предотвращение обхода через зашифрованный DNS |
| Порты (iptables) | OpenVPN · IPSec · Tor · PPTP · Shadowsocks · SOCKS |

**Защита от обхода (включается автоматически):** 170+ VPN / DoH / Tor / Proxy доменов + 19 портов

| Тип | Количество |
|---|---|
| Блокируемые VPN-провайдеры | 40+ (NordVPN, ExpressVPN, ProtonVPN, Surfshark…) |
| DNS-over-HTTPS провайдеры | 25+ (1.1.1.1, dns.google, cloudflare-dns.com…) |
| Прокси-сервисы | 25+ (hide.me, kproxy.com, croxyproxy.com…) |
| Tor | torproject.org · bridges · *.onion |

**Fail-Closed карантин** *(опционально)* — при обнаружении обхода EasyPi блокирует **весь интернет** для устройства до нажатия **Restore Internet** в UI. Максимальная эффективность в **Full Gateway Mode**.

> 📌 Порты WireGuard / Tailscale (51820, 51821) **не блокируются** — совместимость с EasyPi.

</details>

<details>
<summary><b>🌐 VPN и удалённый доступ</b></summary>
<br/>

- **WireGuard VPN** с генерацией QR-кодов для мобильных клиентов
- **Tailscale Admin API**: авто-настройка DNS, управление устройствами, одобрение маршрутов
- **PiCloud**: подключение Pi к облачной инфраструктуре
- Визард настройки удалённого доступа

</details>

<details>
<summary><b>🤖 AI Ассистент (Claude)</b></summary>
<br/>

- Чат-помощник на базе **Claude AI**
- Устанавливает и настраивает сервисы по запросу
- Диагностирует проблемы по логам системы
- Предлагает и объясняет команды
- Контекстно-зависимые рекомендации для вашей системы

</details>

<details>
<summary><b>💾 Резервное копирование</b></summary>
<br/>

- Автоматические бэкапы по расписанию
- Полные снимки системы (конфиги + базы данных)
- **Восстановление одним кликом**
- Версионирование конфигураций

</details>

<details>
<summary><b>📁 Файловый менеджер и 🔐 шифрование</b></summary>
<br/>

- Веб-браузер и редактор файлов с **подсветкой синтаксиса**
- Загрузка и скачивание файлов из любого браузера
- **Шифрование AES-256-GCM (PiCloud)** — на стороне клиента, пароль никогда не покидает браузер
  - PBKDF2 с 100 000 итераций (защита от брутфорса)
  - Уникальные Salt + IV для каждого файла
  - Magic bytes `EPEC` для идентификации

</details>

<details>
<summary><b>💻 Терминал, 📹 Камеры и другое</b></summary>
<br/>

- **WebSSH Терминал** — полный доступ к shell в браузере, запись и воспроизведение сессий
- **RTSP видеонаблюдение** — живой просмотр + управление записями
- **Push и Email уведомления** (SMTP) с поддержкой тихих часов
- **PWA** — установка как мобильное приложение, частичная работа офлайн
- **Сетевые инструменты** — сканер портов, обнаружение устройств, спидтест, карта топологии, мониторинг трафика
- **Тёмная / Светлая тема**, полностью адаптивный дизайн

</details>

---

## 🚀 Быстрый старт

### Требования

| Требование | Минимум | Рекомендуется |
|---|---|---|
| Железо | Raspberry Pi 3 | **Pi 4 · 4 ГБ ОЗУ** |
| ОС | Raspberry Pi OS Bullseye | Последняя Raspberry Pi OS |
| Хранилище | SD карта 16 ГБ | **SD карта 32 ГБ** |
| Сеть | Интернет-подключение | Проводной Ethernet |

### Установка

```bash
# 1. Склонируй репозиторий
git clone https://github.com/NextQuantum/EasyPi.git
cd EasyPi

# 2. Запусти установщик
chmod +x install.sh
./install.sh
```

### Первый вход

```
https://адрес-вашего-pi/
  — или —
https://easypi.local/
```

> Если браузер показывает `Подключение не защищено` / `net::ERR_CERT_AUTHORITY_INVALID` на локальном IP EasyPi (например, `192.168.89.226`) — это нормально для самоподписанного сертификата. В домашней сети можно нажать **«Перейти на сайт (небезопасно)»**.

> **Логина и пароля по умолчанию нет.** При первом запуске EasyPi покажет экран создания admin-аккаунта и **recovery token** — сохрани его в надёжном месте.

---

# 🇩🇪 Deutsch

<div align="center">

**EasyPi** — das All-in-One-Dashboard für Ihren Raspberry Pi.  
Überwachung, Sicherheit und Kontrolle — ganz ohne SSH oder Kommandozeile.

</div>

---

## ✨ Funktionen

<details open>
<summary><b>🖥️ Dashboard & Echtzeit-Monitoring</b></summary>
<br/>

- Live-Metriken: **CPU · RAM · Temperatur · Festplatte**
- **Netzwerkaktivität** (RX/TX-Graphen)
- Dienste-Status auf einen Blick
- **Historische Diagramme** für alle Metriken

</details>

<details open>
<summary><b>🚀 Dienstverwaltung mit einem Klick</b></summary>
<br/>

- **Pi-hole, WireGuard, Jellyfin, Home Assistant** und 15+ weitere Dienste — in einem Klick installieren
- **Fertige Stacks**: Media Server · Smart Home · Monitoring
- **Dienstkatalog** mit ausführlichen Beschreibungen

</details>

<details open>
<summary><b>🔐 Enterprise-Sicherheit</b></summary>
<br/>

| Funktion | Details |
|---|---|
| 2FA | TOTP-basierte Zwei-Faktor-Authentifizierung |
| Sessions | Secure `httpOnly` + `SameSite` Cookies + JWT (7 Tage) |
| Sitzungsverwaltung | Geräteverfolgung & sofortiger Widerruf |
| PiGuard Scanner | Automatische Schwachstellenerkennung |
| Firewall | UFW / iptables-Verwaltung |
| SSL/TLS | Vollständige Zertifikatunterstützung |
| CSRF-Schutz | Alle zustandsändernden Operationen geschützt |
| Rate Limiting | API-Brute-Force-Schutz |

**🧭 Full Gateway Mode:**
- Auto-Fix für Gateway-Routing-Schleifen
- Persistentes IP-Forwarding nach Neustarts
- NAT bleibt aktiv bei Proxy-Neustarts

</details>

<details open>
<summary><b>📵 Kindersicherung & Streaming-Blocker</b></summary>
<br/>

> Pro Gerät wird `DNS active / stale / not seen` angezeigt — sofortiger Überblick über den Schutzstatus.

**40+ gesperrte Dienste:** YouTube · Netflix · TikTok · Instagram · Facebook · WhatsApp · Telegram · Discord · Twitch · Spotify · Amazon Prime · Disney+ · HBO Max · Hulu · Reddit · Twitter · Roblox · Fortnite · Steam · Epic Games · und mehr.

**Mehrstufige Blockierungs-Engine:**

| Ebene | Was blockiert wird |
|---|---|
| DNS | Alle bekannten Domains + CDN-Endpunkte |
| ASN/IP | Hardcodierte IPs (z.B. AS2906 für Netflix) |
| DoH/DoT | Verschlüsselte DNS-Umgehung verhindern |
| Ports (iptables) | OpenVPN · IPSec · Tor · PPTP · Shadowsocks · SOCKS |

**Umgehungsschutz (automatisch aktiviert):** 170+ VPN / DoH / Tor / Proxy-Domains + 19 Ports

**Fail-Closed Quarantäne** *(optional)* — bei erkannter Umgehung sperrt EasyPi **das gesamte Internet** für das Gerät, bis der Admin **Restore Internet** klickt. Am effektivsten im **Full Gateway Mode**.

> 📌 WireGuard / Tailscale-Ports (51820, 51821) werden bewusst **nicht blockiert** — EasyPi-Kompatibilität.

</details>

<details>
<summary><b>Weitere Funktionen</b></summary>
<br/>

- **WireGuard VPN** mit QR-Code-Generierung für mobile Geräte
- **Tailscale Admin API**: automatische DNS-Konfiguration, Geräteverwaltung
- **KI-Assistent (Claude AI)** — Diagnose, Befehle, Servicekonfiguration
- **Backup & Restore** — geplante Sicherungen, Ein-Klick-Wiederherstellung
- **Dateimanager** mit Code-Editor und Syntaxhervorhebung
- **AES-256-GCM Dateiverschlüsselung** — clientseitig, Passwort verlässt nie den Browser
- **WebSSH-Terminal** — vollständiger Shell-Zugriff im Browser
- **RTSP-Kameras** — Live-Ansicht + Aufnahmeverwaltung
- **PWA** — Als mobile App installierbar
- **Netzwerk-Tools** — Port-Scanner, Geräteerkennung, Speedtest, Topologie-Map

</details>

---

## 🚀 Schnellstart

### Anforderungen

| Anforderung | Minimum | Empfohlen |
|---|---|---|
| Hardware | Raspberry Pi 3 | **Pi 4 · 4 GB RAM** |
| Betriebssystem | Raspberry Pi OS Bullseye | Aktuelle Raspberry Pi OS |
| Speicher | 16 GB SD-Karte | **32 GB SD-Karte** |
| Netzwerk | Internetverbindung | Kabelgebundenes Ethernet |

### Installation

```bash
# 1. Repository klonen
git clone https://github.com/NextQuantum/EasyPi.git
cd EasyPi

# 2. Installer ausführen
chmod +x install.sh
./install.sh
```

### Erster Zugriff

```
https://ihre-pi-adresse/
  — oder —
https://easypi.local/
```

> Wenn der Browser bei der lokalen EasyPi-IP (z. B. `192.168.89.226`) `Verbindung ist nicht privat` / `net::ERR_CERT_AUTHORITY_INVALID` zeigt, ist das bei einem selbstsignierten Zertifikat normal. Im vertrauenswürdigen Heimnetz kann man **„Weiter zur Website (unsicher)“** wählen.

> **Keine Standard-Anmeldedaten.** Beim ersten Start zeigt EasyPi den Setup-Bildschirm zur Admin-Kontoerstellung und einen **Recovery-Token** — diesen sicher aufbewahren.

---

<div align="center">

## 📜 License · Лицензия · Lizenz

Distributed under a **proprietary license** — see [LICENSE](LICENSE) and [EULA.txt](EULA.txt).

---

## 🤝 Contributing

We welcome every contribution! 🎉

| How to help | Action |
|---|---|
| 🐛 Found a bug? | [Open an Issue](https://github.com/NextQuantum/EasyPi/issues) |
| 💡 Have an idea? | Describe your feature request |
| 🔧 Want to code? | Submit a Pull Request |
| 📖 Improve docs? | Updates are always welcome |
| ⭐ Like EasyPi? | Star the repo — it helps! |

---

<sub>Made with ❤️ for the Raspberry Pi community</sub>

[⬆ Back to top](#-easypi)

</div>
