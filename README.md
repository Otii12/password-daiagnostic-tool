
# Password Diagnostic Tool

A lightweight, client-side password strength checker with breach detection — built to demonstrate practical security concepts, not just pass/fail a password.

## What it does

- **Strength analysis** — checks length, character variety, and common weak patterns, then estimates entropy (the number of bits of randomness in the password).
- **Breach check** — checks the password against known data breaches using the [Have I Been Pwned](https://haveibeenpwned.com/API/v3#PwnedPasswords) API, without ever sending the actual password over the network.

## How the breach check stays private

This tool uses a technique called **k-anonymity**:

1. The password is hashed locally in the browser using SHA-1.
2. Only the **first 5 characters** of that hash are sent to the API.
3. The API returns every breached hash suffix that shares that prefix (usually thousands of them).
4. The browser checks locally whether the full hash appears in that list.

The server never sees the password, and never sees the full hash — only a fragment shared by thousands of other passwords.

## Tech stack

- Plain HTML, CSS, and JavaScript — no frameworks, no build step.
- `crypto.subtle` (built into the browser) for hashing.
- Have I Been Pwned Pwned Passwords API for breach lookups.

## Running it

No installation needed. Open `index.html` in any browser, or visit the live GitHub Pages link below.

**Live demo:** _(add your GitHub Pages link here once set up)_

## Why I built this

Built as a hands-on project to practice core security concepts — entropy, hashing, and privacy-preserving API design — while learning frontend development.

## Author

**[Your Name]** — IT professional, tech support & web development
[LinkedIn](#) · [Portfolio](#)
