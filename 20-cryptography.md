# Cryptography

## 📌 Introduction
Cryptography underpins confidentiality, integrity, authentication, and non-repudiation across
virtually every other module in this course — from securing web traffic (TLS) to password storage
and digital signatures.

---

## 🎯 Objectives
- Distinguish symmetric vs asymmetric encryption and when each is used.
- Understand hashing vs encryption and why they solve different problems.
- Understand PKI, digital signatures, and certificate authorities.
- Recognize common cryptographic attacks and how to defend against them.

---

## 🔐 Symmetric vs Asymmetric Cryptography
- **Symmetric** (e.g., **AES**, DES/3DES) – same key encrypts and decrypts; fast, but requires
  secure key distribution in advance.
- **Asymmetric** (e.g., **RSA**, ECC) – public/private key pair; solves the key-distribution
  problem since the public key can be shared openly.
- **Diffie-Hellman** – lets two parties derive a shared secret over an insecure channel without
  transmitting the secret itself.

---

## 🔏 Hashing
- Produces a fixed-size, one-way "fingerprint" of data — used for **integrity verification**, not
  confidentiality (not reversible like encryption).
- **MD5** – considered broken (collision vulnerabilities); avoid for security purposes.
- **SHA-256 / SHA-3** – current recommended hash families.
- **Salting** – adds unique random data per password before hashing, defeating precomputed
  rainbow-table attacks.
- **bcrypt / Argon2** – purpose-built, intentionally slow password-hashing algorithms.

---

## 🖋️ Digital Signatures & PKI
- **Digital Signature** – provides authentication, integrity, and non-repudiation using the
  signer's private key.
- **Certificate Authority (CA)** – issues digital certificates binding a public key to a verified
  identity.
- **PKI (Public Key Infrastructure)** – the overall system of certificates, CAs, and trust chains.

---

## ⚠️ Common Cryptographic Attacks
- **Rainbow table attack** – precomputed hash-to-plaintext lookup, defeated by salting.
- **Birthday attack** – exploits collision probability math to find hash collisions faster than
  brute force.
- **MITM on key exchange** – intercepting/substituting keys during protocols like Diffie-Hellman.
- **Downgrade attacks (e.g., POODLE)** – exploiting legacy SSL/early TLS weaknesses; mitigated by
  enforcing modern TLS (1.2/1.3).

---

## 🧵 Steganography
- Conceals the **existence** of a message within another file (e.g., an image), as opposed to
  encryption, which hides the content but not necessarily the fact that a message exists.

---

## 🧪 Hands-on Labs
- **Lab 1: Symmetric vs Asymmetric Identification** – classify a list of algorithms (AES, RSA, DES,
  ECC, Diffie-Hellman) by type.
- **Lab 2: Hash Comparison** – hash the same input with MD5 and SHA-256; compare collision
  resistance discussion points.
- **Lab 3: Password Salting Demo** – hash identical passwords with and without unique salts and
  compare the outputs.
- **Lab 4: TLS Inspection** – use a browser/tool to inspect a site's TLS certificate chain and
  protocol version.

---

## 🛡️ Best Practices
- Use AES for symmetric encryption; RSA/ECC for asymmetric needs.
- Use SHA-256/SHA-3 for integrity; bcrypt/Argon2 (salted) for password storage — never plaintext
  or reversible encryption for passwords.
- Enforce TLS 1.2/1.3 for all data in transit; disable legacy SSL/early TLS.
- Rotate keys/certificates on a defined schedule and before expiry.

---

## ⚠️ Disclaimer
This content is for **educational purposes only**.
