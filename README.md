```markdown
<div align="center">

# ⚡ FearverkDPI

**High-Performance Native DPI Bypass & Real-Time TUI Network Engine for Windows**

[![Language](https://img.shields.io/badge/Language-C%2B%2B17-blue.svg?style=for-the-badge&logo=c%2B%2B)](https://en.wikipedia.org/wiki/C%2B%2B)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-0078D6.svg?style=for-the-badge&logo=windows)](https://microsoft.com)
[![Driver](https://img.shields.io/badge/Driver-WinDivert%202.2%2B-red.svg?style=for-the-badge)](https://reqcrypt.org/windivert.html)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)
[![Speed](https://img.shields.io/badge/Speed-100%25%20Direct%20Line-brightgreen.svg?style=for-the-badge)](#)

[English](#-english) • [Русский](#-русский)

</div>

---

## 🌐 English

### 📖 Overview
**FearverkDPI** is a native, low-latency DPI circumvention engine built in modern C++ with `WinDivert`. Unlike slow commercial VPNs, FearverkDPI does **not** route your traffic through foreign servers. It operates locally on raw packet streams to fragment TLS SNI records, drop QUIC/UDP streams, and inject fake TCP packets with short TTL directly in kernel space.

### ✨ Key Features
* 🚀 **Zero-Lag & Full Bandwidth:** 100% direct connection speed without third-party proxy bottlenecks.
* 🎬 **Instant 4K YouTube Playback:** Automatic UDP 443 (QUIC) drop to force browsers into resilient TCP mode.
* 🛡️ **Advanced TLS De-synchronization:** Real-time ClientHello SNI splitting and low-TTL fake packet injection.
* 🎮 **Full Gaming & Voice Support:** Fixes voice channels in Discord, connection drops in Roblox Studio (Team Create), and blocked web endpoints.
* 📊 **Terminal User Interface (TUI):** Built-in telemetry tracking latency, live packet mutations, and domain hit rates.

---

### 📂 Directory Structure

```text
FearverkDPI/
├── bin/
│   └── FearverkDPI.exe       # Precompiled core binary
├── libs/
│   ├── windivert.h           # Header files
│   ├── WinDivert.lib         # Import library
│   ├── WinDivert.dll         # User-mode library
│   └── WinDivert64.sys       # Signed kernel driver
├── src/
│   └── FearverkDPI.cpp       # Main C++ engine source
├── general.bat               # Auto Mode (Fastest node selection)
├── general_jp.bat            # Japan profile preset
├── general_us.bat            # USA profile preset
└── general_de.bat            # Germany/EU profile preset

```

---

### 🚀 Quick Start

1. Go to the [Releases](https://github.com/) section and download the latest `FearverkDPI.zip`.
2. Extract the archive into any folder.
3. Right-click **`general.bat`** and choose **Run as Administrator**.
4. Open your browser, Discord, or Roblox Studio — all restricted endpoints will load instantly.

---

### 🛠️ Building from Source

Ensure you have MinGW (GCC 10+) or Clang with C++17 support:

```bash
# Compile directly into the bin folder
g++ -std=c++17 -O3 src/FearverkDPI.cpp -o bin/FearverkDPI.exe -Ilibs -Llibs -lWinDivert -lws2_32 -liphlpapi

```

---

### ⚙️ Command-Line Arguments

| Flag | Description | Default |
| --- | --- | --- |
| `-c, --country <CODE>` | Target gateway preset (`AUTO`, `JP`, `US`, `DE`, `NL`, `KR`) | `AUTO` |
| `--no-quic` | Disable automatic QUIC (UDP 443) packet dropping | `Enabled` |
| `--no-fake` | Disable fake TLS packet injection | `Enabled` |
| `--ttl <VAL>` | Configure custom Time-To-Live for fake packets | `3` |

---

## 🇷🇺 Русский

### 📖 О проекте

**FearverkDPI** — это высокоскоростной инструмент для обхода DPI-блокировок провайдеров, написанный на C++ с использованием драйвера `WinDivert`.

В отличие от классических VPN, программа **не перенаправляет ваш трафик на сторонние серверы**. Она работает локально на уровне ядра Windows: перехватывает исходящие пакеты, на лету разрезает поле `SNI` (доменное имя), сбрасывает протокол QUIC и выполняет инъекцию фейковых TLS-пакетов.

### ✨ Главные преимущества

* 🚀 **Максимальная скорость провайдера:** Нулевой пинг в играх и 100% скорости вашего тарифа без чужих медленных VPN-серверов.
* 🎬 **YouTube в 4K без задержек:** Мгновенный сброс UDP 443 (QUIC) заставляет браузер переключиться на оптимизированный TCP.
* 🛡️ **Продвинутая десинхронизация TCP/TLS:** Нарезка заголовков `ClientHello` прямо посреди имени домена и генерация Fake-пакетов с заниженным TTL.
* 🎮 **Работает везде:** Полная поддержка Discord (включая войс-каналы), Roblox Studio (Team Create) и заблокированных сайтов.
* 📊 **Интерактивный TUI-интерфейс:** Отображение пинга, счетчика искаженных пакетов, пойманных доменов и времени сессии в реальном времени.

---

### 🚀 Быстрый запуск

1. Скачайте архив в разделе [Releases](https://github.com/).
2. Распакуйте архив в удобное место.
3. Запустите **`general.bat`** (или профиль нужной страны) **от имени Администратора**.
4. Готово! YouTube, Discord и Roblox снова работают на полной скорости.

---

### 📜 Профили запуска (.bat)

| Скрипт | Назначение |
| --- | --- |
| `general.bat` | **Автоматический режим**: выбор узла с наименьшей задержкой |
| `general_jp.bat` | Профиль с ориентацией на шлюзы Азии и Японии |
| `general_us.bat` | Профиль с ориентацией на серверы США (Cloudflare) |
| `general_de.bat` | Профиль для европейских шлюзов (Франкфурт / Амстердам) |

---

### 🛠️ Сборка проекта

Для компиляции через MinGW / GCC выполните команду в корне проекта:

```bash
g++ -std=c++17 -O3 src/FearverkDPI.cpp -o bin/FearverkDPI.exe -Ilibs -Llibs -lWinDivert -lws2_32 -liphlpapi

```

---

### ⚠️ Важное примечание (Disclaimer)

Программа требует прав Администратора исключительно для взаимодействия с системным драйвером ядра `WinDivert`. Исходный код полностью открыт, не содержит сторонней телеметрии и не сохраняет пользовательские данные.

---

**Made with ⚡ for gamers, developers, and open web enthusiasts.**
