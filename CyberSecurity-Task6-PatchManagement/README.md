# Task 6 – Research Report on Patch Management

## 1. Objective

The objective of this report is to understand patch management, explore the importance of security updates, examine real-world incidents caused by exploited vulnerabilities, and develop a practical patch management process for organizations.

## 2. Introduction

Patch management is the process of identifying, acquiring, testing, deploying, and verifying software updates across computers, servers, applications, and network devices.

Software vendors release patches to fix security vulnerabilities, correct software defects, improve stability, and maintain compatibility. Security patches are particularly important because attackers may exploit known vulnerabilities in systems that have not been updated.

Effective patch management reduces the attack surface, helps protect sensitive information, and supports business continuity.

## 3. What Is a CVE?

CVE stands for **Common Vulnerabilities and Exposures**. It is a publicly accessible catalogue of identified cybersecurity vulnerabilities. A CVE identifier provides a consistent reference for discussing a particular vulnerability.

For example, **CVE-2017-0144** identifies a vulnerability associated with Microsoft's SMBv1 implementation that was exploited by the WannaCry ransomware outbreak.

A CVE identifier does not automatically mean a vulnerability is critical or exploitable in every environment. Security teams should evaluate the severity, affected products, available patches, exposure, and likelihood of exploitation before prioritizing remediation.

CVEs can be researched through the official CVE website and the National Vulnerability Database (NVD).

## 4. Real-World Case Studies

### 4.1 WannaCry Ransomware Attack (2017)

**Overview:**

WannaCry was a ransomware outbreak that spread rapidly in May 2017. It encrypted files on affected Windows systems and demanded ransom payments. The malware also propagated between vulnerable systems by exploiting an SMBv1 vulnerability.

**Vulnerability:**

The outbreak exploited a vulnerability addressed by Microsoft's security update MS17-010. The related vulnerability identifier CVE-2017-0144 is associated with the EternalBlue exploit.

**What went wrong?**

Systems that had not installed the relevant security updates remained exposed. Unsupported or outdated systems also created additional security challenges.

**Consequences:**

- Files and systems became unavailable because of encryption.
- Organizations experienced operational disruption.
- Hospitals, businesses, and other institutions faced recovery costs.
- The incident demonstrated how quickly a known vulnerability can be exploited at scale.

**Lessons learned:**

Organizations should prioritize critical security patches, retire unsupported operating systems, maintain reliable backups, and segment networks to reduce the spread of malware.

### 4.2 Equifax Data Breach (2017)

**Overview:**

In 2017, Equifax disclosed a major data breach involving sensitive personal information. The breach exposed information relating to approximately 147 million people.

**Vulnerability:**

The incident involved an unpatched vulnerability in Apache Struts, identified as CVE-2017-5638. A security update had been released before the breach was disclosed.

**What went wrong?**

The vulnerability was not remediated in the affected environment before attackers exploited it. The incident highlighted weaknesses in vulnerability identification, patch deployment, and verification processes.

**Consequences:**

- Sensitive personal information was exposed.
- The organization faced investigations, legal consequences, and financial costs.
- Public trust was damaged.
- The incident demonstrated the risks of inadequate vulnerability management.

**Lessons learned:**

Organizations should maintain an accurate inventory of applications, monitor security advisories, prioritize actively exploitable vulnerabilities, track remediation deadlines, and independently verify that patches have been applied.

## 5. Consequences of Poor Patch Management

1. **Security breaches:** Attackers may exploit known vulnerabilities to gain unauthorized access.
2. **Data loss and exposure:** Vulnerabilities can enable unauthorized access to personal, financial, or business information.
3. **Ransomware infections:** Unpatched systems can become entry points for ransomware and other malware.
4. **Operational downtime:** Security incidents may interrupt services and business operations.
5. **Financial and legal consequences:** Organizations may incur recovery expenses, regulatory penalties, lawsuits, or compensation costs.
6. **Reputational damage:** Customers and partners may lose confidence in an organization.
7. **Compliance failures:** Failure to maintain systems securely may violate organizational policies or applicable regulatory requirements.

## 6. Patch Management Lifecycle

### Step 1: Discovery

Identify all systems, operating systems, applications, firmware, and network devices managed by the organization.

Maintain an accurate asset inventory that includes software versions, system owners, and business importance.

### Step 2: Assessment

Review vendor advisories, CVE records, vulnerability scanner results, and available threat intelligence.

Evaluate severity, exploit availability, internet exposure, business impact, and whether the affected software is actually present.

### Step 3: Prioritization

Rank vulnerabilities according to risk rather than relying only on severity scores.

Prioritize actively exploited vulnerabilities, internet-facing systems, critical business assets, and vulnerabilities with readily available exploitation techniques.

### Step 4: Testing

Test patches in a controlled environment before widespread deployment whenever feasible.

Check application compatibility, system stability, performance, and interactions with other software. For urgent critical vulnerabilities, use an accelerated process with appropriate safeguards.

### Step 5: Deployment

Deploy approved patches using a controlled rollout process. Begin with a suitable pilot group where practical, then expand deployment according to risk and operational requirements.

Schedule maintenance windows, communicate expected downtime, and maintain a rollback or recovery plan.

### Step 6: Verification

Confirm that patches were installed successfully. Use patch-management reports, version checks, system logs, and vulnerability scans where appropriate.

Investigate failed installations and systems that remain vulnerable.

### Step 7: Documentation and Review

Record the affected assets, vulnerability identifiers, patch versions, deployment dates, test results, exceptions, and verification evidence.

Review patch compliance regularly and improve the process using lessons learned from failures and incidents.

**Lifecycle summary:**

Discovery → Assessment → Prioritization → Testing → Deployment → Verification → Documentation and Review

## 7. Seven-Step Patch Management Checklist

- [ ] Maintain an up-to-date inventory of hardware, operating systems, and applications.
- [ ] Monitor vendor security advisories and vulnerability databases.
- [ ] Assess vulnerability severity, active exploitation, system exposure, and business impact.
- [ ] Prioritize patches according to risk and define remediation deadlines.
- [ ] Test patches and prepare recovery or rollback procedures.
- [ ] Deploy patches using a documented, controlled process.
- [ ] Verify installation, rescan where appropriate, and document outstanding vulnerabilities or approved exceptions.

## 8. Common Challenges and Solutions

| Challenge                    | Explanation                                                        | Recommended solution                                                                                    |
| ---------------------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------- |
| Legacy systems               | Older systems may be unsupported or incompatible with new patches. | Upgrade or replace unsupported systems; use compensating controls while planning remediation.           |
| Downtime concerns            | Updates may interrupt important services.                          | Schedule maintenance windows, use phased deployment, and prepare recovery plans.                        |
| Large asset inventory        | Organizations may struggle to track all devices and software.      | Use centralized asset inventory and patch-management tools.                                             |
| Compatibility problems       | Patches can interfere with applications or configurations.         | Test in staging environments and deploy gradually when feasible.                                        |
| Limited resources            | Teams may not have enough time to update every system immediately. | Automate routine patching and prioritize high-risk vulnerabilities.                                     |
| Failed installations         | Updates may fail or leave systems partially patched.               | Monitor deployment results, investigate failures, and verify remediation independently.                 |
| Unknown or unmanaged devices | Systems outside normal management may remain vulnerable.           | Discover devices regularly, assign ownership, and establish clear onboarding and offboarding processes. |

## 9. Best Practices

- Establish a documented patch management policy with defined responsibilities and deadlines.
- Use risk-based prioritization and accelerate remediation for vulnerabilities under active exploitation.
- Automate patch discovery, deployment, and reporting where appropriate.
- Maintain secure, tested backups and recovery procedures.
- Restrict administrative privileges and segment networks to reduce the impact of compromise.
- Monitor patch compliance and report unresolved high-risk vulnerabilities to responsible stakeholders.
- Define a formal process for documenting exceptions and applying compensating controls.
- Keep unsupported software out of production wherever possible.

## 10. Conclusion

Patch management is an essential component of cybersecurity because it reduces the risk posed by known software vulnerabilities. The WannaCry outbreak and Equifax breach demonstrate the serious consequences that can result when vulnerable systems are not adequately protected.

An effective process involves asset discovery, vulnerability assessment, risk-based prioritization, testing, deployment, verification, and documentation. By combining these activities with automation, reliable backups, clear responsibilities, and continuous monitoring, organizations can strengthen their security posture and reduce the likelihood and impact of cyberattacks.

## 11. References

1. National Vulnerability Database (NVD), CVE-2017-0144: [https://nvd.nist.gov/vuln/detail/CVE-2017-0144](https://nvd.nist.gov/vuln/detail/CVE-2017-0144)
2. Microsoft Security Bulletin MS17-010: [https://learn.microsoft.com/en-us/security-updates/securitybulletins/2017/ms17-010](https://learn.microsoft.com/en-us/security-updates/securitybulletins/2017/ms17-010)
3. National Vulnerability Database (NVD), CVE-2017-5638: [https://nvd.nist.gov/vuln/detail/CVE-2017-5638](https://nvd.nist.gov/vuln/detail/CVE-2017-5638)
4. U.S. Government Accountability Office (GAO), Equifax Data Breach: [https://www.gao.gov/products/gao-19-29](https://www.gao.gov/products/gao-19-29)
5. Cybersecurity and Infrastructure Security Agency (CISA): [https://www.cisa.gov/](https://www.cisa.gov/)

**Report completed for:** Oasis Infobyte Cybersecurity Internship
**Task:** Task 6 – Research Report on Patch Management
