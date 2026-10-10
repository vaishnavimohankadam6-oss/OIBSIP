# Task 5 – Research Report on Social Engineering

## 1. Objective

The objective of this report is to understand common social engineering attacks, examine real-world incidents, identify their impacts, and recommend security measures to prevent them.

## 2. Introduction

Social engineering is a cybersecurity technique in which attackers manipulate people into revealing confidential information, transferring money, granting unauthorized access, or performing actions that compromise security.

Instead of exploiting only technical vulnerabilities, social engineering exploits human emotions and behaviour, such as trust, fear, urgency, curiosity, and the desire to help.

Common social engineering attacks include phishing, pretexting, baiting, and quid pro quo attacks.

## 3. Phishing

### 3.1 Definition

Phishing is an attack in which an attacker impersonates a trusted person or organization to trick a victim into revealing sensitive information, clicking a malicious link, downloading malware, or authorizing a fraudulent transaction.

### 3.2 Types of Phishing

- **Email phishing:** Fraudulent emails sent to many people, often impersonating banks, companies, or online services.
- **Spear phishing:** Targeted phishing messages designed for a specific individual or organization.
- **Whaling:** Targeted phishing aimed at senior executives or other high-value individuals.
- **Smishing:** Phishing conducted through SMS or text messages.
- **Vishing:** Voice-based phishing through phone calls.
- **Clone phishing:** A legitimate message is copied and modified to include a malicious link or attachment.

### 3.3 Real-World Case Study: Google and Facebook Business Email Scam

Between 2013 and 2015, a Lithuanian man used fraudulent emails and invoices impersonating a legitimate Asian hardware manufacturer to deceive employees at Google and Facebook. The companies transferred more than $100 million before the fraud was discovered. The case involved business email impersonation and fraudulent payment requests, demonstrating how attackers exploit trust in business communications.

**Security lessons:**
- Verify unexpected payment requests independently.
- Confirm changes to supplier bank details through a trusted channel.
- Require approval for large or unusual transfers.
- Train employees to recognize impersonation and suspicious requests.

### 3.4 Prevention Measures

1. **Email filtering:** Use spam filters and security gateways to identify suspicious messages.
2. **Multi-factor authentication (MFA):** Add another verification factor to reduce the impact of stolen passwords.
3. **URL and attachment verification:** Avoid opening unexpected links or files; verify the sender and destination before interacting.
4. **Security awareness training:** Teach employees to recognize urgency, impersonation, suspicious attachments, and requests for credentials or payments.

## 4. Pretexting

### 4.1 Definition

Pretexting is a social engineering attack in which an attacker invents a believable identity or situation to persuade a victim to disclose information or perform an action.

The attacker may pretend to be an IT support employee, bank representative, manager, vendor, or government official.

### 4.2 How Pretexting Works

1. The attacker researches the target or organization.
2. The attacker creates a convincing story or identity.
3. The attacker contacts the victim and establishes apparent trust.
4. The attacker requests confidential information, money, or access.
5. The attacker uses the information or access for unauthorized purposes.

### 4.3 Case Study: Ubiquiti Business Email Compromise

In 2015, Ubiquiti Networks disclosed that it had suffered a business email compromise involving employee impersonation and fraudulent requests. The company reported an estimated $46.7 million loss at the time. The incident illustrates how deceptive communications and apparently legitimate business requests can manipulate employees into transferring funds.

The incident is relevant to pretexting because the attacker relied on impersonation and a convincing business context. It also demonstrates the importance of verifying requests through independent channels.

### 4.4 Prevention Measures

1. **Verify identities:** Confirm requests for sensitive information or access through a known, trusted contact method.
2. **Apply least privilege:** Give employees and external parties only the access required for their roles.
3. **Use approval procedures:** Require independent verification and appropriate authorization for sensitive actions, account changes, and financial transfers.

## 5. Baiting

### 5.1 Definition

Baiting is a social engineering attack that uses something tempting or seemingly useful to persuade a victim to take an unsafe action. The bait may be a physical object, such as a USB drive, or a digital item, such as a free download.

### 5.2 Physical Baiting

In physical baiting, an attacker may leave a USB drive labelled "Salary Details," "Confidential," or "Exam Results" in a place where employees or students might find it. A curious person may connect the device to a computer, potentially exposing the system to malicious files or unauthorized activity.

### 5.3 Digital Baiting

Digital baiting may involve:
- Fake free software or premium downloads.
- Pirated applications containing malware.
- Attractive download links that install unwanted or malicious software.
- Fraudulent offers that require users to disclose credentials or personal information.

### 5.4 Case Study: Stuxnet and Infected USB Devices

Stuxnet was a sophisticated malware operation discovered in 2010 that targeted industrial control systems. Investigations linked its spread to removable media among other possible infection routes. The incident demonstrates why removable devices and systems with limited network connectivity can still create security risks.

**Important distinction:** Stuxnet is an example of malware propagation involving removable media, not proof that every USB-based infection is a baiting attack. Baiting specifically involves tempting or manipulating a victim into using the item.

### 5.5 Prevention Measures

1. **Control removable media:** Do not connect unknown USB devices. Establish policies for approved removable storage and scan permitted devices.
2. **Use trusted software sources:** Download applications only from official or verified sources, and avoid suspicious free offers.
3. **Apply endpoint protection:** Keep operating systems and security tools updated, use endpoint detection where available, and restrict execution of untrusted files.

## 6. Bonus Topic: Quid Pro Quo Attacks

### 6.1 Definition

A quid pro quo attack is a social engineering technique in which an attacker offers a service, benefit, or reward in exchange for information or access.

The term means "something for something."

### 6.2 Example

An attacker calls an employee pretending to be technical support. The attacker offers to fix a computer problem but asks the employee to reveal a password or install a remote-access tool. The employee may comply because the offer appears helpful.

### 6.3 Prevention

- Use official IT support channels.
- Never disclose passwords or authentication codes to someone claiming to provide assistance.
- Verify software installations and remote-access requests with authorized IT staff.

## 7. Comparison of Social Engineering Attacks

| Attack type | Main technique | Example | Key defence |
|---|---|---|---|
| Phishing | Deceptive messages or websites | Fake bank email | Email filtering and MFA |
| Pretexting | Invented identity or story | Fake IT support request | Independent identity verification |
| Baiting | Tempting item or offer | Unknown USB drive | Removable-media controls |
| Quid pro quo | Benefit offered in exchange for access or information | Fake technical support | Approved support procedures |

## 8. Five-Point Security Awareness Checklist

1. **Think before clicking:** Check unexpected links, attachments, and download offers.
2. **Verify identities:** Independently confirm requests for confidential information, access, or payments.
3. **Protect credentials:** Never share passwords or MFA codes with callers, email senders, or unknown websites.
4. **Report suspicious activity:** Inform the organization's security or IT team about suspected social engineering.
5. **Follow security policies:** Use approved software, removable media, authentication, and payment procedures.

## 9. Conclusion

Social engineering remains a significant cybersecurity threat because it exploits human trust and decision-making. Phishing uses deceptive communications, pretexting relies on invented identities or situations, baiting uses tempting objects or offers, and quid pro quo attacks promise a benefit in exchange for information or access.

Organizations can reduce these risks through employee awareness, multi-factor authentication, independent verification, least-privilege access, secure software practices, and clear reporting procedures. Technical controls are important, but informed users and reliable verification processes are also essential to an effective security strategy.

## 10. References

1. Federal Bureau of Investigation (FBI) – Business Email Compromise: https://www.fbi.gov/how-we-can-help-you/scams-and-safety/common-frauds-and-scams/business-email-compromise
2. U.S. Department of Justice – Ubiquiti Networks Business Email Compromise Case: https://www.justice.gov/opa/pr/lithuanian-man-sentenced-5-years-prison-defrauding-google-and-facebook-100-million
3. Cybersecurity and Infrastructure Security Agency (CISA) – Avoiding Social Engineering and Phishing Attacks: https://www.cisa.gov/news-events/news/avoiding-social-engineering-and-phishing-attacks
4. Microsoft Security – What Is Social Engineering?: https://www.microsoft.com/en-us/security/business/security-101/what-is-social-engineering
5. Cybersecurity and Infrastructure Security Agency (CISA) – Removable Media Security: https://www.cisa.gov/

**Report completed for:** Oasis Infobyte Cybersecurity Internship  
**Task:** Task 5 – Research Report on Social Engineering
