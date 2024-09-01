# Apache Fingerprinting
Implementing fingerprinting in the Apache web server

## Motivation
To demonstrate the effectiveness and improve adoption of timing and fingerprint analysis for detection of malicious web clients and proxies by implementing collection of relevant metadata in the Apache web server. This capability is designed to counter current challenges such as AitM proxies, residential proxies, and compromised SOHO routers/IOT devices.

## Tasks
  - Expose TLS RTT in mod_ssl using recently added SSL_get_handshake_rtt function
    - Finished, this was merged into apache (target release unknown): https://github.com/apache/httpd/commit/79990b070f2e5374e1add982342b1fa71f5d189e
    - Patches and ubuntu packages here: 
  - Expose TLS Fingerprint data in mod_ssl (ex. data needed to generate ja3/ja4)
    - Repo here: https://github.com/csmutz/apache_tls_fingerprint
  - Expose TCP fingerprinting and RTT data from kernel via TCP_INFO
    - Rules or databased to block connections from known SOHO router/IOT devices?
  - HTTP fingerprinting of browsers (header existance, order, capitalization, values, etc)
    - Start with module that implements simple header order, capitalizaiton digest
    - Possible database or ML model, possibly via modsecurity style rules or integration of yara rules, of various browsers and modifications indicative of proxy types
  - HTTP RTT via server-side scripts (probably could be an apache module, but likely will be server-side scripting)

## Related Work
  - gait: zeek extension by Sandia National Labs that implements similar fingerprinting. The goal is to expose similar metadata in the web server. https://github.com/sandialabs/gait/
  - ja4: Widely adopted tool for fingerprinting. While we may differ in approach (focus on exposing metadata vs. creating a standardized format for sharing), there will be significant overlap in attributes collected. https://github.com/FoxIO-LLC/ja4

## Participation
I would love to mentor a high school or undergrad student in parts of this project. This project involved understanding some really important concepts in network security. The developed technologies could be used as a testbed for research and the experience and the domain knowledge would help equip a student for research in the area of proxy detection.


