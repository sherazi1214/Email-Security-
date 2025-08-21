# Email-Security

**English:**
Email Security means applying technologies, protocols, and practices to protect emails from spam, phishing, spoofing, malware, and unauthorized access.

**Urdu:**
Email ek common attack vector hai, is liye uski protection bohot zaroori hai.

## Server-side Email Configuration

**English:**
On the server side, admins configure email servers (e.g., Microsoft Exchange, Postfix, Gmail servers) for:

**Authentication**: Ensure only valid users send/receive.

Anti-spam / Anti-virus filters.

TLS encryption for mail transfer.

Security records (SPF, DKIM, DMARC).

Logging & monitoring.

**Urdu:**
Server side settings ensure karte hain ke fake emails na bheje jayein aur communication secure ho.

## SPF (Sender Policy Framework)

**English:**
SPF is a DNS TXT record that specifies which mail servers are allowed to send emails on behalf of your domain.

**Example:**

v=spf1 include:_spf.google.com ~all


This means only Google’s servers can send emails for this domain.

**Urdu:**
SPF ka kaam hai ke kon kon server allowed hai domain se email bhejne ka.

## SPF Record

**English:**

Added in DNS Zone File.

**Format: v=spf1 [mechanisms] [qualifiers].**

Example:

+ Pass → allow.

- Fail → block.

~ SoftFail → usually mark as spam.

? Neutral.

**Urdu:**
SPF record ek rule book hoti hai jo DNS me likhi hoti hai.

## DKIM (DomainKeys Identified Mail)

**English:**

DKIM adds a digital signature to outgoing emails.

Receiving server verifies the signature using a public key stored in DNS.

Ensures message integrity (not altered in transit) and authenticity (sent from domain owner).

**Urdu:**
DKIM ek seal of authenticity lagata hai email par jo verify hota hai DNS key se.

## DMARC (Domain-based Message Authentication, Reporting, and Conformance)

**English:**

DMARC works on top of SPF and DKIM.

Defines a policy for what to do if an email fails SPF/DKIM.

Example policy in DNS TXT:

v=DMARC1; p=reject; rua=mailto:dmarc-reports@domain.com; sp=none; aspf=s


p=reject → block emails that fail SPF/DKIM.

Provides reports (RUA, RUF) about email authentication.

**Urdu:**
DMARC batata hai ke agar SPF/DKIM fail ho jaye to email ko reject ya spam me dalna hai.

## Encryption in Email

**English:**
Encryption ensures confidentiality of emails.

Transport Layer Encryption (TLS):

Encrypts the channel between mail servers (STARTTLS).

Prevents eavesdropping but doesn’t encrypt email content end-to-end.

End-to-End Encryption (PGP / S/MIME):

Content is encrypted with recipient’s public key.

Only recipient with private key can read it.

Provides confidentiality, integrity, and authenticity.

## Urdu:
Encryption ka kaam hai ke sirf intended recipient email read kar sake, koi aur intercept kare to unreadable hoga.

## Summary

**SPF** = defines allowed mail servers.

**DKIM** = digital signature for authenticity.

**DMARC** = policy + reporting on SPF/DKIM failures.

**Encryption** = protect email in transit & at rest.
