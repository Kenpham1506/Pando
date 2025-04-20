# 🌱 PANDO Protocol

**Peer Audited Network of Decentralized Organisms**

PANDO is a decentralized protocol for managing asset ownership, trust, and verification—without central authorities. Inspired by Pando the tree, it promotes long-term resilience through transparency, peer auditing, and cryptographic trust.

---

## 📘 Overview

PANDO enables independent servers to mint and manage cryptographically signed assets, with all actions verified through a trust-based, peer-audited system.

---

## 🔹 Entities

- **Server (Node):** Hosts that mint, store, and validate assets.
- **Client:** Users who own and transfer assets.
- **Asset:** A signed digital object with verifiable metadata, ownership, and history.

---

## 📦 Asset Format

```json
{
  "asset": {
    "id": "abc",
    "owner_email": "clientA@client.com",
    "origin_email": "serverA@server.net",
    "data": {
      "seed_str": "...",
      "image_float": 0.25,
      "border_float": 0.5
    }
  },
  "origin_signature": "Signed by origin server",
  "owner_signature": "Signed by current owner"
}
```
## ⚙️ Core Mechanics

### Minting

- Only origin servers can mint.
- Minting is rate-limited based on uptime and peer validation.
- Events are logged, hashed, signed, and peer-audited.

### Transfer

- Only the current owner can transfer assets.
- Requires recipient public key and owner signature.
- Transfers are added to immutable logs.

### Git-Style Log

- Each server maintains a signed, append-only log.
- Peers periodically validate and sign each other’s logs.

---

## 🔀 Peer Auditing & Uptime

- Servers conduct regular verification sessions.
- Verified uptime unlocks minting rights.
- Logs are cross-signed by peer servers to ensure integrity.

---

## 🌟 Reputation System

- Servers earn reputation through:
  - Consistent uptime
  - Honest audits
  - Valid minting history
- Reputation is inherited by assets at mint time.

---

## 🔐 Security

### 🔑 Trust Model

- RSA cryptography secures all signatures.
- Git-style logs prevent history rewriting.
- All events must be signed and auditable.

### 🛡️ Threat Mitigation

| Threat                  | Defense                                                                 |
|------------------------|-------------------------------------------------------------------------|
| Forged Minting         | Requires validated uptime and peer audits                               |
| History Rewriting      | Logs are immutable; peer signatures detect tampering                    |
| Fake Audit Signatures  | RSA verification ensures authenticity                                   |
| Sybil Attacks          | Reputation-weighted trust + exponential mint cost                       |
| Rogue Clients          | Clients can only request, not mint or alter metadata                    |
| Server Collusion       | Logs are public; clients and peers can detect and isolate collusion     |
| DoS / Spam             | Minting is rate-limited and cost-scaled                                 |
| Bad Nodes              | Non-cooperating peers can be blacklisted or ignored                     |

---

## 🌳 Philosophy

**PANDO** is not just software—it’s a living organism of decentralized trust. Like its namesake tree, every node is part of a greater whole, resilient through shared roots.

**Together, we grow stronger.**
