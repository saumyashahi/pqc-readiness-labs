# PQC Readiness Labs – Developer-Focused Training

## Overview

Post-quantum cryptography (PQC) introduces a major shift in long-standing cryptographic assumptions used across web and application security. While much of the discussion around PQC is academic or protocol-focused, developers and security engineers are often left without clear, practical guidance on **what actually breaks**, **what does not**, and **how to migrate safely**.

This repository provides a small, hands-on set of **developer-focused training labs** that explore post-quantum readiness through the lens of real-world web and application security scenarios.

The goal is not to design cryptographic algorithms, but to help practitioners understand **cryptographic failure modes**, migration pitfalls, and secure design decisions in a post-quantum context.

---

## Target Audience

- Web and application developers
- Security engineers and AppSec teams
- Students learning secure software design
- OWASP contributors and trainers

No prior background in quantum computing or cryptographic mathematics is required.

---

## What This Project Is (and Is Not)

### This project **is**:
- Focused on **practical security impact**, not theory
- Aligned with **OWASP Top 10 – Cryptographic Failures**
- Designed around **realistic developer scenarios**
- Structured as **training-style, hands-on labs**

### This project **is not**:
- A cryptographic research project
- An implementation of PQC algorithms
- A replacement for formal cryptographic standards or guidance

---

## Lab Structure

Each lab follows a consistent structure:

- Scenario (real-world application context)
- Common developer assumptions
- What breaks (from a post-quantum perspective)
- Security impact
- Recommended migration approaches
- OWASP relevance and secure design considerations

This format is intended to make the labs easy to review, reuse, and adapt into existing OWASP training ecosystems.

---

## Current Scope (v0.1)

The initial version intentionally keeps scope narrow:

### Labs
1. **What Breaks**  
   Understanding how quantum attacks affect common public-key assumptions (e.g., RSA, ECDSA) used in web applications.

2. **What Survives (For Now)**  
   Clarifying which cryptographic primitives are not immediately impacted and common misconceptions around “quick fixes”.

3. **Migration Mistakes**  
   Exploring common errors made when attempting post-quantum migrations, including naïve replacements and hybrid crypto pitfalls.

---

## OWASP Alignment

This work aligns closely with:
- **OWASP Top 10 – Cryptographic Failures**
- Secure Design principles
- Developer education and awareness initiatives

The labs are intentionally framed to be compatible with OWASP training-style projects and learning resources.

---

## Project Status

This project is in an early exploratory phase (v0.1).  
Feedback, review, and guidance from the OWASP community are very welcome before expanding scope or formalizing further.

---

## Contributing & Feedback

At this stage, contributions are focused on:
- Reviewing lab clarity and accuracy
- Improving developer-focused explanations
- Ensuring alignment with OWASP principles and formats

Please feel free to open issues or provide feedback through OWASP community channels.

---

## License

This project is intended to follow OWASP’s open and collaborative principles.  
A standard OWASP-compatible license will be added as the project matures.
