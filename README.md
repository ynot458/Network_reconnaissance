🔎 Simple Python Port Scanner

A lightweight TCP port scanner written in Python.
This tool scans all 65,535 TCP ports on a target host, identifies common services, and performs basic banner grabbing for open ports.

⚠️ For educational and authorized testing purposes only.

📌 Features

Scans TCP ports 1–65535

Detects open ports

Maps common ports to service names

Performs basic banner grabbing

Smart probing for HTTP services

Fast scanning with low timeout (0.2 seconds)

Graceful keyboard interrupt handling

🛠 How It Works

The scanner:

Iterates through all TCP ports (1–65535)

Uses socket.connect_ex() to check if the port is open

Identifies the service using a predefined port dictionary

Attempts to grab a banner from the service

Prints formatted results for open ports

Example output:

[OPEN] Port 22     | Service: SSH             | Banner: SSH-2.0-OpenSSH_8.2
[OPEN] Port 80     | Service: HTTP            | Banner: HTTP/1.1 200 OK

🚀 Installation & Usage
1️⃣ Clone the repository
git clone https://github.com/yourusername/simple-port-scanner.git
cd simple-port-scanner

2️⃣ Run the scanner
python3 scanner.py


By default, it scans:

127.0.0.1


To change the target, edit this line in the script:

TARGET = "127.0.0.1"


Replace it with your desired IP address.

📂 Code Overview
Service Mapping

The scanner includes common service mappings:

Port	Service
21	FTP
22	SSH
25	SMTP
80	HTTP
443	HTTPS
3306	MySQL
6379	Redis

It also includes demo ports for testing environments.

Banner Grabbing

Sends HTTP GET requests for web services

Sends newline probes for other services

Captures first line of the response

Handles decoding errors gracefully

⚙️ Configuration

You can modify:

Timeout value:

socket.setdefaulttimeout(0.2)


Service dictionary:

SERVICE_PORTS = {...}


Target IP address:

TARGET = "127.0.0.1"
