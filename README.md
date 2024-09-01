# Apache Fingerprinting
Implementing fingerprinting in the Apache web server

## Motivation
To demonstrate the effectiveness and improve adoption of timing and fingerprint analysis for detection of malicious web clients and proxies by implemented collection of relevant metadata in the Apache web server, especially addressing current challenges such as AitM proxies and residential proxies.

## Tasks
  - Expose TLS RTT in mod_ssl using recently added SSL_get_handshake_rtt function
    - Finished, this was merged into apache (target release unknown): https://github.com/apache/httpd/commit/79990b070f2e5374e1add982342b1fa71f5d189e
    - Patches and ubuntu packages here: 
  - Expose TLS Fingerprint data in mod_ssl (ex. data needed to generate ja3/ja4)
    - Repo here:
  - Expose TCP fingerprinting and RTT data from kernel via TCP_INFO
  - HTTP fingerprinting of browsers (header existance, order, capitalization, values, etc) possibly via modsecurity style rules or integration of yara rules
  - HTTP RTT via server-side scripts (probably could be an apache module, but likely will be server-side scripting)

## Related Work
  - gait: zeek extension by Sandia National Labs that implements similar fingerprinting. The goal is to expose similar metadata in the web server.
  - ja4: Widely adopted tool for fingerprinting. While we may differ in approach (focus on exposing metadata vs. creating a standardized format for sharing), there will be significant overlap in attributes collected.

## Participation
I would love to mentor a high school or undergrad student in parts of this project. This project involved understanding some really important concepts in network security. The developed technologies could be used as a testbed for research and the experience and the domain knowledge would help equip a student for research in the area of proxy detection.


