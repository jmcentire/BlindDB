# The Blind Database — Interactive Demo

An interactive demonstration of client-side encryption architecture from [*The Ephemeral Internet: Privacy Architecture for a Surveillance-Free Web*](https://github.com/jmcentire) by Jeremy McEntire.

## What This Shows

The demo walks through two architectures side by side:

**Today** — Enter credentials. Watch twelve wire exchanges (password, MFA, CAPTCHA, cookies, privacy policy). See the server's plaintext database. Watch a SQL injection dump everything: names, emails, phone numbers, browsing history. The MFA protected the session. Nobody came through the session.

**Tomorrow** — Same credentials. Two wire exchanges (a hash, a response). The server stores encrypted blobs at opaque addresses. The same SQL injection dumps hex garbage. No names, no emails, no messages, no browsing history.

## Run It

Open `index.html` in a browser. No server, no dependencies, no build step.

Or visit the live demo: [https://jmcentire.github.io/BlindDB/](https://jmcentire.github.io/BlindDB/)

## Technical Details

- Real SHA-256 via Web Crypto API
- XOR encryption for demonstration (production systems use AES-256-GCM or ChaCha20-Poly1305)
- All computation happens in the browser; the "server" is a JavaScript object
- Pre-seeded with 50 random records to simulate a multi-user database

## From the Book

This demo illustrates concepts from Chapters 3 and 5 of *The Ephemeral Internet*:

- **Anonymous Identity** (Ch. 3) — Hash construction producing site-specific tokens, unlinkable across sites
- **Blind Database** (Ch. 5) — Client-side encryption where the server is a pure key-value store with no knowledge of what keys mean or what values contain

ISBN 979-8-9940343-8-5 | Cage & Mirror Publishing, 2026
