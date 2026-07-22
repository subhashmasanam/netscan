# NetScan — Python Network Scanner

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.7%2B-blue?logo=python&logoColor=white" alt="Python 3.7+">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey" alt="Cross Platform">
  <img src="https://img.shields.io/badge/License-MIT-green" alt="MIT License">
  <img src="https://img.shields.io/badge/Status-Active-brightgreen" alt="Active">
</p>

A lightweight, multi-threaded **network scanner** that discovers live hosts on your local network — no third-party dependencies, just Python's standard library.

Built as part of a hands-on cybersecurity learning journey.

---

## Features

- **Auto-detects your network** — no arguments needed, it finds your local IP and subnet automatically
- **Fast parallel scanning** — uses multi-threading (100 concurrent workers) to ping entire subnets in seconds
- **Cross-platform** — works on Windows, Linux, and macOS (auto-adjusts ping syntax per OS)
- **Flexible targeting** — scan by full CIDR, partial IP, or full IP; the tool fills in the rest
- **Clean, sorted output** — displays discovered hosts in numerical IP order
- **Graceful interrupt handling** — stop a scan anytime with `Ctrl+C` and still see partial results

---

## Tech Stack

| Component | Purpose |
|---|---|
| `socket` | IP/network operations & fallback IP detection |
| `ipaddress` | Network/CIDR parsing and host enumeration |
| `concurrent.futures` | Multi-threaded ping sweeps |
| `subprocess` | Running native `ping`/`ipconfig`/`ifconfig` commands |
| `re` | Parsing OS command output |
| `platform` | Detecting the host OS |

---

## Installation

No external dependencies required — just Python 3.7+.

```bash
git clone https://github.com/subhashmasanam/netscan.git
cd netscan
```

> Replace `netscan.py` below with your actual script filename if different.

---

## Usage

Run directly with Python:

```bash
python netscan.py [network]
```

### Examples

| Command | What it does |
|---|---|
| `python netscan.py` | Auto-detects and scans your current local network |
| `python netscan.py 192.168.1.0` | Scans `192.168.1.0/24` |
| `python netscan.py 192.168.1` | Scans `192.168.1.0/24` |
| `python netscan.py 192.168.1.0/24` | Scans the exact CIDR range provided |
| `python netscan.py -h` | Shows help and usage instructions |

### Sample Output

```
 _                         
| |                        
| '_ \ / _ \ __| / __|/ __/ _` | '_ \ 
| | | |  __/ |_  \__ \ (_| (_| | | | |
|_| |_|\___|\__| |___/\___\__,_|_| |_|

welcome to NetScan, a network scanner brought to you by subhash

Scanning network: 192.168.1.0/24

Online hosts:
192.168.1.1
192.168.1.5
192.168.1.12
192.168.1.20
```

---

## Disclaimer

This tool is intended for use on **networks you own or have explicit permission to scan** (e.g., your home lab or authorized test environments). Unauthorized scanning of networks you don't own may be illegal in your jurisdiction.

---

## Author

**Subhash Masanam**
Email: subhashmasanam@gmail.com
[LinkedIn](https://www.linkedin.com/in/subhash-masanam-72a78b280/) · [GitHub](https://github.com/subhashmasanam)

---

## License

This project is licensed under the MIT License — feel free to use and modify it for learning purposes.
