Here is your cleaned README formatted exactly as requested:

* ✅ Only emojis in headings
* ✅ All headings are H1 (`#`)
* ✅ Clean GitHub-compatible Markdown

---

# 🔎 Simple Python Port Scanner

A lightweight TCP port scanner written in Python.
This tool scans all 65,535 TCP ports on a target host, identifies common services, and performs basic banner grabbing.

For educational and authorized testing purposes only.

# ✨ Features

* Scans TCP ports 1–65535
* Detects open ports
* Maps common ports to service names
* Performs basic banner grabbing
* Smart probing for HTTP services
* Fast scanning with low timeout
* Handles Ctrl+C safely

# ⚙️ How It Works

The scanner:

* Loops through ports 1–65535
* Uses `socket.connect_ex()` to check if a port is open
* Matches the port to a known service
* Attempts to grab a banner
* Prints formatted results

Example output:

```
[OPEN] Port 22     | Service: SSH        | Banner: SSH-2.0-OpenSSH_8.2
[OPEN] Port 80     | Service: HTTP       | Banner: HTTP/1.1 200 OK
```

# 🚀 Installation

Clone the repository:

```
git clone https://github.com/yourusername/simple-port-scanner.git
cd simple-port-scanner
```

# ▶️ Usage

Run:

```
python3 scanner.py
```

By default, the script scans:

```
127.0.0.1
```

To change the target, modify this line in the script:

```python
TARGET = "127.0.0.1"
```

# 🛠 Configuration

You can modify:

Timeout:

```python
socket.setdefaulttimeout(0.2)
```

Service mapping dictionary:

```python
SERVICE_PORTS = {
    21: "FTP",
    22: "SSH",
    80: "HTTP",
    443: "HTTPS",
}
```
