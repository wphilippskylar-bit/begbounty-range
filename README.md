# Bug Bounty Range

A game-style, **iPhone-first** learning app for the most common, highest-value web vulnerability classes — built as an installable offline PWA. Learn to **spot** each bug, read **how the original researcher found it**, then **prove the exploit to the console** on a safe, fully simulated in-browser range.

Live site: enable **GitHub Pages** (Settings → Pages → Deploy from branch → `main` / root). Then open the URL on your iPhone and **Add to Home Screen**.

## What's inside

Nine tracks, ranked by difficulty — pick any, they unlock independently:

| # | Track | Difficulty | You learn to… |
|---|-------|-----------|----------------|
| 1 | **IDOR** | ★ start here | Change an ID and read data that isn't yours |
| 2 | **Open Redirect** | ★ | Bend a redirect off-site, then beat the filter |
| 3 | **XSS** | ★★ | Make the page run your script (reflected + attribute break-out) |
| 4 | **SQL Injection** | ★★ | Bypass login and UNION data out |
| 5 | **CSRF** | ★★ | Forge a request the victim's browser sends |
| 6 | **SSRF** | ★★★ | Make the server fetch cloud metadata (Capital One pattern) |
| 7 | **Auth & JWT** | ★★★ | Forge an `alg:none` token; abuse predictable reset tokens |
| 8 | **Business Logic** | ★★★ | Tamper price/quantity; double-spend a race |
| 9 | **🏁 Live Range** | graduation | Chain bugs into account takeover + a weighted final exam |

Each step has: a **reading** (what it is, the real historical bug, how to hunt it), **flashcards** (spaced repetition), **practice** questions with instant explanations, a **range lab** where you capture a flag by proving the exploit, and a **gate test** you must score **over 90%** on to unlock the next step.

## Universal features

- **Device picker** on first launch — Phone mode trims effects for a smooth iPhone experience; Laptop mode spreads the console and labs side-by-side. Switch anytime under **Save**.
- **90% locked path** — every step is gated; you can't advance until you prove mastery.
- **Checkpoint phrases** — each passed gate gives a phrase. Type it into **Save → Restore** on any device to jump right back to where you were. There's also a full backup export/import.
- **Tools** — an Encoder/Decoder (URL, Base64, HTML entities) and an endless *identify-the-bug* drill.

## Safety & ethics

Everything here is a **simulation running entirely in your browser** — no real network requests, and no attacker code is executed (XSS previews render in a scripts-disabled sandboxed iframe; a parser decides success). The content repeatedly reinforces the one rule of real research: **only test systems you own or are explicitly authorized to test, and stay in scope.** It points you to legal practice grounds (PortSwigger Web Security Academy, Hack The Box, TryHackMe, OWASP Juice Shop) and to authorized programs (HackerOne, Bugcrowd, Intigriti).

## Build

```bash
pip install pillow
python3 build.py      # outputs dist/ and begbounty.zip
```

The build inlines all CSS + JS into a single offline `index.html` and generates icons, the manifest, and a cache-first service worker. Commit the contents of `dist/` to the repo root for GitHub Pages.
