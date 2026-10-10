# Task 4: Research Report on Common Network Security Threats

## 1. Objective

The objective of this report is to study common network security threats, understand how they operate, examine their potential impact, and identify practical mitigation strategies. The report covers Denial of Service (DoS) and Distributed Denial of Service (DDoS), Man-in-the-Middle (MITM), IP spoofing, and DNS poisoning or spoofing.

## 2. Introduction

Computer networks allow devices and applications to exchange information. However, weaknesses in network protocols, configurations, and security controls can be exploited to disrupt services, intercept communications, impersonate systems, or redirect users to malicious destinations.

Understanding these threats helps security analysts assess risks, monitor network activity, and recommend preventive and corrective controls.

## 3. Denial of Service (DoS) and Distributed Denial of Service (DDoS)

### 3.1 Definition

A Denial of Service (DoS) attack attempts to make a computer, network, or online service unavailable to legitimate users by exhausting resources or disrupting normal operation.

A Distributed Denial of Service (DDoS) attack uses traffic or requests from multiple systems or sources to overwhelm a target. Attackers may use compromised devices, botnets, or reflection and amplification techniques.

### 3.2 How the attack works

A DoS attack may generate excessive requests from one source or exploit a weakness in a service. A DDoS attack distributes the traffic across many sources, making filtering and attribution more difficult.

Common categories include:

- **Volumetric attacks:** Consume available network bandwidth with large amounts of traffic.
- **Protocol attacks:** Exhaust resources in network devices or protocol-handling systems.
- **Application-layer attacks:** Overload services by generating excessive requests to applications such as web servers.

### 3.3 Real-world example

In February 2018, GitHub experienced a large DDoS attack involving memcached amplification. Cloudflare reported that the attack reached approximately 1.35 terabits per second. Amplification attacks abuse exposed services to generate responses much larger than the original requests.

This incident demonstrates how misconfigured or exposed infrastructure can contribute to large-scale service disruption.

### 3.4 Impact

- Websites and applications may become unavailable.
- Businesses may lose revenue and customer trust.
- Employees may be unable to access essential systems.
- Incident response and mitigation can increase operational costs.
- Repeated attacks can affect service reliability and reputation.

### 3.5 Mitigation strategies

1. Use DDoS protection services and network traffic filtering.
2. Apply rate limiting and suitable connection limits.
3. Monitor traffic patterns and establish alerts for abnormal spikes.
4. Configure firewalls, routers, and load balancers appropriately.
5. Disable unnecessary UDP services and prevent open resolvers from being abused.
6. Coordinate with hosting providers and internet service providers during major attacks.
7. Maintain an incident response plan and test recovery procedures.

## 4. Man-in-the-Middle (MITM) Attack

### 4.1 Definition

A Man-in-the-Middle attack occurs when an attacker positions themselves between two communicating parties to intercept or modify information exchanged between them.

The attacker may attempt to impersonate a legitimate endpoint, observe communications, or alter data while each party believes it is communicating with the intended recipient.

### 4.2 How the attack works

A possible scenario is an attacker operating a deceptive Wi-Fi access point. A user connects to it believing it is legitimate. If the attacker can successfully intercept or manipulate unprotected communications, sensitive information may be exposed.

Other MITM opportunities can arise from compromised routers, weak authentication, certificate-validation failures, or improperly configured networks.

### 4.3 Real-world example

A documented class of MITM vulnerabilities involves applications that fail to validate server certificates correctly. NIST's Mobile Threat Catalogue explains that weak server authentication can allow an attacker to impersonate a backend server and access or modify transmitted information.

This demonstrates why encrypted connections alone are not sufficient if applications do not correctly authenticate the server.

### 4.4 Impact

- Exposure of credentials and sensitive information.
- Theft or misuse of session tokens.
- Modification of data in transit.
- Redirection to fraudulent websites.
- Loss of confidentiality and integrity.
- Financial and reputational damage.

### 4.5 Mitigation strategies

1. Use HTTPS with valid TLS certificates.
2. Never ignore browser certificate warnings without investigation.
3. Ensure applications correctly validate server certificates.
4. Avoid transmitting sensitive information over untrusted or unencrypted connections.
5. Use strong authentication and multi-factor authentication.
6. Secure Wi-Fi networks and avoid connecting to suspicious access points.
7. Monitor for suspicious certificates, network changes, and unexpected redirects.

## 5. IP Spoofing

### 5.1 Definition

IP spoofing occurs when an attacker forges the source IP address in an IP packet. The receiving system sees a source address that may not represent the actual sender.

IP spoofing can be used to obscure the origin of traffic, impersonate another address in certain circumstances, or support reflection and amplification attacks.

### 5.2 How the attack works

An IP packet contains a source address and a destination address. In spoofing, the attacker modifies the source address to a forged value.

For example, an attacker may send requests to a third-party service with the victim's address forged as the source. The service may then send its responses to the victim instead of the real requester. When many responses are generated, this can contribute to a reflection-based DDoS attack.

Spoofing is not the same as taking control of the device whose address is forged. The source address alone is not reliable proof of the sender's identity.

### 5.3 Real-world example

In the 2018 memcached amplification attack against GitHub, spoofed source addresses helped attackers direct amplified responses toward the victim. Cloudflare's technical analysis explains how source-address spoofing enables reflection and amplification techniques.

This example illustrates how IP spoofing can be used as one component of a larger availability attack.

### 5.4 Impact

- Difficulty identifying the true origin of malicious traffic.
- Abuse of third-party servers in reflection attacks.
- Network congestion and service disruption.
- Misleading logs and inaccurate attribution.
- Potential abuse of systems that rely only on source IP addresses for trust.

### 5.5 Mitigation strategies

1. Implement ingress and egress filtering at network boundaries.
2. Apply source-address validation based on the network's legitimate address ranges.
3. Follow source-address filtering recommendations such as BCP 38.
4. Use stateful firewalls where appropriate.
5. Avoid treating an IP address alone as sufficient authentication.
6. Monitor unusual traffic patterns and investigate spoofed or impossible source addresses.
7. Coordinate with network providers to filter spoofed traffic closer to its origin.

## 6. DNS Poisoning and DNS Spoofing

### 6.1 Definition

The Domain Name System (DNS) translates human-readable domain names into information such as IP addresses needed to locate network services.

DNS poisoning commonly refers to corrupting DNS cache data so that a domain resolves to an incorrect address. DNS spoofing is a broader term that can describe forged DNS responses or other deceptive DNS behavior.

These terms are related, but they are not always interchangeable: poisoning generally emphasizes corrupting stored DNS information, while spoofing emphasizes falsifying DNS responses or data.

### 6.2 How the attack works

When a user visits a domain, a DNS resolver helps determine the address associated with that name.

If an attacker successfully poisons a resolver's cache or causes a client to accept a forged DNS response, the domain may resolve to an attacker-controlled or otherwise incorrect address. The user may then reach a fraudulent destination while believing it is legitimate.

A successful attack depends on the attacker's opportunity and the DNS implementation or configuration involved; it is not guaranteed merely because a user performs a DNS lookup.

### 6.3 Real-world example

The Kaminsky DNS vulnerability disclosed in 2008 highlighted weaknesses in DNS cache-poisoning defenses. The issue demonstrated that attackers could exploit weaknesses in resolver behavior to attempt to inject fraudulent DNS records.

The incident led to widespread attention to DNS resolver security and accelerated deployment of protective measures such as stronger source-port randomization and DNS software updates.

### 6.4 Impact

- Users may be redirected to fraudulent websites.
- Credentials or other sensitive information may be exposed.
- Users may download malicious files from deceptive destinations.
- Trust in legitimate websites and services can be undermined.
- Organizations may experience service disruption and reputational damage.

### 6.5 Mitigation strategies

1. Keep DNS resolver software updated.
2. Use secure resolver configurations and restrict unauthorized access.
3. Apply DNS Security Extensions (DNSSEC) validation where supported.
4. Monitor DNS records and investigate unexpected changes.
5. Use trusted DNS resolvers and protect the administrative accounts that manage DNS.
6. Use HTTPS and validate certificates to provide an additional layer of protection against redirection.
7. Investigate suspicious DNS responses and clear affected caches when appropriate.

DNSSEC can help validate the authenticity and integrity of DNS data, but it does not encrypt DNS queries or prevent every form of redirection or compromise.

## 7. Comparison of Common Network Security Threats

| Threat | Main objective | Typical method | Potential impact | Key mitigation |
|---|---|---|---|---|
| DoS/DDoS | Disrupt service availability | Exhaust bandwidth, protocol resources, or application capacity | Service outage and financial loss | DDoS protection, filtering, rate limiting |
| MITM | Intercept or modify communications | Position between communicating endpoints | Data theft, session compromise, altered data | TLS, certificate validation, strong authentication |
| IP spoofing | Forge source IP information | Modify packet source addresses | Reflection attacks, misleading attribution | Ingress/egress filtering, source validation |
| DNS poisoning/spoofing | Redirect name resolution | Inject false DNS data or responses | Redirection, phishing, service disruption | DNSSEC validation, secure resolvers, monitoring |

## 8. General Security Recommendations

Organizations should use a layered security approach rather than relying on one control.

Recommended practices include:

- Maintain updated network devices, operating systems, and services.
- Use firewalls and access-control rules to restrict unnecessary exposure.
- Monitor network traffic, DNS activity, and service availability.
- Apply strong authentication and least-privilege access.
- Encrypt sensitive communications and validate endpoint identities.
- Review DNS configurations and protect domain-management accounts.
- Maintain incident response, backup, and recovery procedures.
- Provide security awareness training to help users recognize suspicious network behavior.

## 9. Conclusion

DoS/DDoS, MITM, IP spoofing, and DNS poisoning or spoofing threaten different aspects of network security. DoS/DDoS primarily affect availability, MITM attacks threaten confidentiality and integrity, IP spoofing can support impersonation and reflection attacks, and DNS poisoning can redirect users to incorrect destinations.

Effective protection requires secure configurations, traffic filtering, encryption, authentication, monitoring, timely updates, and incident response planning. Security teams should understand the limitations of each control and use multiple defensive layers.

## 10. References

1. National Institute of Standards and Technology (NIST), *Man-in-the-Middle Attack Glossary*: https://csrc.nist.gov/glossary/term/man_in_the_middle_attack
2. Cloudflare, *What Is IP Spoofing?*: https://www.cloudflare.com/learning/ddos/glossary/ip-spoofing/
3. Cloudflare, *The Real Cause of Large DDoS: IP Spoofing*: https://blog.cloudflare.com/the-root-cause-of-large-ddos-ip-spoofing/
4. Cybersecurity and Infrastructure Security Agency (CISA), *UDP-Based Amplification Attacks*: https://www.cisa.gov/ncas/alerts/ta14-017a
5. NIST, *Mobile Threat Catalogue — Man-in-the-Middle Attack on Server Authentication*: https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-1.html

**Note:** This report is intended for educational purposes and defensive security awareness.
