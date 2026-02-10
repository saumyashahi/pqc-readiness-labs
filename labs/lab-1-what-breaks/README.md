# Lab 1: What Breaks – TLS Authentication

## Objective

This lab demonstrates how post-quantum threats impact **TLS authentication mechanisms** commonly used in web applications, with a focus on public-key cryptographic assumptions rather than protocol internals.

By the end of this lab, learners should understand:
- Which parts of TLS rely on quantum-vulnerable primitives
- Why long-term trust assumptions break under quantum attacks
- What security risks this introduces for web applications
- What high-level mitigation strategies developers should consider today

---

## Scenario

A web application uses HTTPS with standard TLS configuration:

- Server authentication is performed using an **RSA or ECDSA certificate**
- Clients trust the server based on a public-key infrastructure (PKI)
- Certificates are assumed to be secure for their entire validity period

This setup is widely deployed across modern web applications and is generally considered secure today.

---

## Common Developer Assumptions

Developers and system owners often assume:

- “TLS is secure as long as we use HTTPS”
- “Large RSA keys or modern elliptic curves are future-proof”
- “If a certificate is valid today, it will remain trustworthy”
- “Quantum threats are too far away to worry about now”

These assumptions hold in a classical computing model — but not in a post-quantum context.

---

## What Breaks (Post-Quantum Perspective)

TLS authentication relies on **public-key cryptography** to establish server identity.

Quantum algorithms such as **Shor’s algorithm** can efficiently break:
- RSA
- Elliptic Curve Cryptography (ECC), including ECDSA and ECDH

This means:
- An attacker with a sufficiently powerful quantum computer could **forge server certificates**
- Previously recorded TLS handshakes could be **retrospectively compromised**
- Trust in long-lived certificates becomes unsafe

Importantly, this does **not** require breaking the TLS protocol itself — only the cryptographic assumptions underneath it.

---

## Security Impact

If TLS authentication is compromised:

- Clients can no longer reliably verify server identity
- Man-in-the-middle attacks become feasible
- Sensitive data (credentials, tokens, personal data) may be exposed
- Long-term confidentiality is at risk for recorded traffic (“harvest now, decrypt later”)

This directly affects web application security, even if application-layer code is unchanged.

---

## What Does *Not* Break Here

This lab focuses specifically on **authentication**.

- Symmetric encryption (e.g., AES) used in TLS record protection is not immediately broken
- Hash functions used for integrity remain largely unaffected in the near term

However, these protections are only meaningful **if authentication can be trusted**.

---

## Developer Guidance (High-Level)

Developers and security teams should begin considering:

- **Algorithm agility** in TLS configurations
- Awareness of **hybrid cryptographic approaches** (classical + post-quantum)
- Reducing reliance on long-lived cryptographic trust where possible
- Tracking post-quantum readiness of certificate authorities and TLS libraries

These steps do not require immediate migration, but they do require **design awareness today**.

---

## OWASP Relevance

This scenario aligns with:
- **OWASP Top 10 – Cryptographic Failures**
- Secure Design principles related to trust boundaries and long-term confidentiality
- Developer education around misuse and overreliance on cryptographic assumptions

Understanding *why* TLS authentication assumptions fail is critical to building resilient web applications.

---

## Key Takeaways

- TLS authentication depends on public-key crypto that is quantum-vulnerable
- The TLS protocol itself is not “broken,” but its trust model is impacted
- Developers must think beyond “HTTPS = secure”
- Post-quantum readiness is a **design concern**, not just a future upgrade task

---

## Next Steps

- Lab 2: What Survives (For Now)
- Lab 3: Common Migration Mistakes
