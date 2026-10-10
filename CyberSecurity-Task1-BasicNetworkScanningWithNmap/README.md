Task 1: Basic Network Scanning with Nmap

Objective

Perform a basic network scan, identify port states and services, and document the results using Nmap in a controlled local lab.

Environment

Operating system: Kali Linux running in Oracle VirtualBox

Tool: Nmap 7.95

Target: 127.0.0.1 (local loopback interface)

Test service: Python HTTP server bound to 127.0.0.1:8000

Commands Performed

1. Basic scan

nmap 127.0.0.1

Scanned Nmap's default set of 1,000 common TCP ports. During the initial scan, all 1,000 ports were closed. After the local HTTP server was started, port 8000 appeared open in the default scan.

2. Service and version detection

nmap -sV -p 8000 127.0.0.1

Nmap reported TCP port 8000 as open and identified the service as HTTP, reporting SimpleHTTPServer 0.6 (Python 3.13.9).

3. OS detection

nmap -O 127.0.0.1

Nmap reported a Linux OS fingerprint but could not confidently identify a specific OS from the loopback scan. This result is an estimate, not definitive OS identification.

Findings

TCP port 8000 was open while the local Python HTTP server was running.

Nmap identified an HTTP service on that port.

The other 999 ports in the default scan were reported closed during the later scan.

OS detection produced limited results on the loopback target.

Security Analysis

An open port indicates that a service is accepting connections. Open ports are not automatically vulnerabilities; their necessity, configuration, software version, and exposure must be assessed.

The test server was deliberately bound to 127.0.0.1 to restrict it to the local machine. The scan results demonstrate basic Nmap functionality and do not establish that the system is vulnerable.

Ethical Considerations

All scanning in this exercise was restricted to my own local lab. Network scanning should only be performed on systems for which explicit authorization has been obtained.

Limitations

The target was the local loopback interface, not a separate network host. OS identification and service findings should be interpreted within this limited test environment.
