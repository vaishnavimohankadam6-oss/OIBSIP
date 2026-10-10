Task 1: Basic Network Scanning with Nmap

1. Objective

The objective of this task is to perform a basic network scan using Nmap, identify open and closed ports, detect running services, and document the results in a controlled local lab environment.

2. Lab Environment

Operating System: Kali Linux running in Oracle VirtualBox

Scanning Tool: Nmap 7.95

Target IP Address: 127.0.0.1

Target Description: Local loopback interface of the Kali Linux system

Test Service: Python HTTP server running on port 8000

Server Binding: 127.0.0.1:8000

All scanning activities were performed against my own local lab environment.

3. Introduction to Nmap

Nmap (Network Mapper) is an open-source network discovery and security auditing tool. It helps security professionals identify hosts, discover open ports, determine which services are running, and gather information about operating systems.

Network scanning is an important part of cybersecurity because open ports and exposed services can increase a system's attack surface. Security professionals use scan results to identify unnecessary services and recommend appropriate security controls.

Nmap results provide useful information, but they do not automatically prove that a system is vulnerable.

4. Commands Performed

4.1 Check Nmap Version

nmap --version

Purpose: To verify that Nmap was installed and available in the Kali Linux terminal.

Result: Nmap version 7.95 was displayed.

4.2 Identify the Local IP Configuration

ip -br addr

Purpose: To inspect the system's network interfaces and IP addresses.

Result: The loopback interface displayed the IPv4 address 127.0.0.1.

4.3 Perform a Basic Network Scan

nmap 127.0.0.1

Purpose: To scan Nmap's default set of 1,000 commonly scanned TCP ports on the local system.

Observation: When the test HTTP server was not running, the scan reported the scanned ports as closed. After starting the local HTTP server, the scan detected port 8000/tcp as open.

This demonstrates that port states can change depending on whether a service is listening.

4.4 Start the Local HTTP Test Server

mkdir -p ~/nmap-lab
echo "Nmap practice lab" > ~/nmap-lab/index.html
cd ~/nmap-lab
python3 -m http.server 8000 --bind 127.0.0.1

Purpose: To create a simple local HTTP service for safe scanning practice.

The server listens only on the loopback address 127.0.0.1, making it accessible through the local system rather than intentionally exposing it to other network devices.

4.5 Detect the Service and Version

nmap -sV -p 8000 127.0.0.1

Purpose: The -sV option enables service/version detection, while -p 8000 specifies the port to scan.

Observed result:

Port: 8000/tcp

State: open

Service: http

Detected version information: SimpleHTTPServer 0.6 (Python 3.13.9)

This result indicates that an HTTP service was listening on port 8000 during the scan.

4.6 Attempt Operating System Detection

nmap -O 127.0.0.1

Purpose: The -O option enables operating system detection by analysing network responses.

Observed result: Nmap returned a possible Linux operating system fingerprint, with a broad kernel range.

Because the target was the local loopback address, this fingerprint should not be treated as definitive operating system identification. Operating system detection can be uncertain and may require additional network evidence.

4.7 Save Scan Results to a File

nmap 127.0.0.1 > ~/nmap-lab/nmap_scan_results.txt
nmap -sV -p 8000 127.0.0.1 >> ~/nmap-lab/nmap_scan_results.txt
nmap -O 127.0.0.1 >> ~/nmap-lab/nmap_scan_results.txt

Purpose: To save the output of the basic scan, service detection, and operating system detection into one text file.

> creates or overwrites a file with command output.

>> appends additional output to the existing file.

cat ~/nmap-lab/nmap_scan_results.txt displays the saved results.

The collected results were uploaded to this repository as nmap_scan_results.txt.

5. Understanding the Results

Finding

Meaning

127.0.0.1

The local loopback address; traffic is directed to the same system.

8000/tcp

TCP port 8000 was scanned.

open

A service was listening and accepting connections on that port.

http

Nmap identified the service as HTTP.

SimpleHTTPServer 0.6

Service/version information detected by Nmap.

closed

The target responded, but no service was listening on that port at the time of scanning.

6. Security Analysis

An open port is not automatically a vulnerability. Its risk depends on the service, its configuration, exposure, and the sensitivity of the system.

In this lab, the HTTP server was intentionally started to demonstrate how Nmap identifies a listening service.

Potential security considerations include:

Unnecessary services should be stopped to reduce the attack surface.

Services should listen only on the network interfaces they actually need.

HTTP does not provide transport encryption by itself, so sensitive information should not be transmitted over unencrypted HTTP.

Service/version information can help defenders identify outdated or misconfigured software.

Operating system fingerprints should be treated as estimates rather than guaranteed identification.

For this exercise, the HTTP server was bound to 127.0.0.1, and the scan was restricted to the local system.

7. Screenshots and Evidence

The following screenshots are included in this project folder:

01-nmap-version-and-ip.png — Nmap version and local IP configuration.

02-basic-scan.png — Basic scan of the local target.

03-os-detection.png — Attempted operating system detection.

04-test-server-running.png — Local Python HTTP server running on port 8000.

05-service-version-scan.png — Service and version detection.

06-saved-scan-results.png — Scan results displayed from the saved text file.

8. Ethical Considerations

Network scanning must be performed only on systems that I own or have explicit permission to test. This exercise was restricted to a local lab environment.

The results must not be used to make unsupported claims about vulnerabilities. Further testing and verification would be necessary before reporting a confirmed security issue.

9. Conclusion

This task provided practical experience with Nmap and basic network reconnaissance. I verified the tool installation, inspected the local IP configuration, performed a basic port scan, detected an HTTP service, attempted operating system detection, and saved the scan results.

The exercise demonstrated how service availability affects port states and why scan results must be interpreted in context.

10. References

Nmap Official Documentation: https://nmap.org/book/man.html

Nmap Service and Version Detection: https://nmap.org/book/man-version-detection.html

Nmap Operating System Detection: https://nmap.org/book/man-os-detection.html
