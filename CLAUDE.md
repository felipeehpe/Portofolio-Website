# PORTFOLIO PROJECT — CLAUDE CONTEXT

## Owner
- Name: Felipe Ehrhardt
- Role: Content Creator
- Location: Gold Coast, Australia
- Stack: Single-file HTML + CSS + JS (no frameworks)

---

## Project File
- `index.html` — single file, self-contained
- Deploy: Netlify (auto-deploy on GitHub push)
- Repo: https://github.com/felipeehpe/Portofolio-Website
- Live URL: https://portfoliofelipeehpe.netlify.app

---

## Design System

### Colors
- Background: `#080808`
- Text: `#f0ece4`
- Muted text: `rgba(240,236,228,0.35)`
- Card About: `#1a1a1a` / accent `#c8c0b0`
- Card Work: `#0b1a2e` / accent `#3d8bff`
- Card Photography: `#1f0f00` / accent `#ff7a1a`
- Card Videography: `#150015` / accent `#c03cff`

### Typography
- Display: `Bebas Neue` (Google Fonts)
- Body: `DM Sans` (Google Fonts)
- Italic accent: `DM Serif Display` (Google Fonts)

### Style Rules
- Dark cinematic aesthetic (Apple-level quality)
- Smooth transitions: `cubic-bezier(0.16,1,0.3,1)`
- Hover animations: 200–300ms ease-out
- Grain overlay texture (SVG noise, opacity 0.045)
- NO hard page jumps — card transforms into section

---

## UX Flow
1. Hero: name fades in fullscreen (~2.8s)
2. Hero dissolves → persistent header + 4 cards appear
3. Cards idle-float with subtle perspective rotation
4. Click: card expands to full-screen section
5. Back button returns to card interface

---

## Cards (4 total)
| Key | Label | Color |
|-----|-------|-------|
| about | About Me | Gray/White |
| work | Work & Cases | Blue |
| photo | Photography | Orange |
| video | Videography | Purple |

---

## Media Hosting
| Type | Where |
|------|-------|
| Images | Google Drive (public link) or Imgur |
| Videos | YouTube (unlisted or public) — embed via iframe |

---

## Edit Rules (IMPORTANT)
- DO NOT change the overall single-file structure
- DO NOT add external JS libraries unless explicitly asked
- KEEP all animations CSS-based where possible
- PRESERVE the card-to-section expansion UX (no page jumps)
- When editing: show ONLY the changed snippet, never rewrite the full file unless asked
- Use str_replace style edits — show old block and new block only
- If multiple changes: list each one separately

---

## How to Request Edits
Tell Claude in plain English what you want. Be specific:
- "Change the About card background color to dark green"
- "Update the Work section heading to say 'Built for brands'"
- "Add my YouTube video [URL] to the video card"
- "Replace the photo carousel images with these links: [link1] [link2]"

Claude will edit `index.html`, push to GitHub, and Netlify auto-deploys in ~1 minute.

---

## Token Efficiency Rules (from claude-token-efficient)
Source: https://github.com/drona23/claude-token-efficient

- **Read before writing** — understand the file fully before making any edit
- **Targeted edits only** — modify only what is needed, never rewrite full files
- **Single read per file** — read each file once per session unless it changed
- **No preamble, no fluff** — responses go straight to the solution
- **No over-engineering** — simplest solution wins; no unnecessary abstractions
- **Validate before done** — check edits are correct before pushing
- **ASCII-compatible output** — avoid special characters that break parsers
- **CLAUDE.md saves tokens at scale** — persistent context avoids re-explaining every session

---

## MarkItDown (from microsoft/markitdown)
Source: https://github.com/microsoft/markitdown

Tool that converts files (PDF, Word, Excel, PowerPoint, images, HTML) to Markdown for LLM processing.

**Use case for this project:**
- Have a PDF portfolio, brief, or project doc? Run through MarkItDown, paste output to Claude, say "use this to update section X"

**Install:** `pip install 'markitdown[all]'`
**CLI:** `markitdown yourfile.pdf -o output.md`

---

## Content Update System

All site content lives in `CONTENT.md` (same folder as index.html).

### To update content:
1. Open `CONTENT.md` in VS Code
2. Replace any value after the colon with your real content
3. Save the file
4. Tell Claude: **"apply CONTENT.md to the site"**
5. Claude reads `CONTENT.md` → edits `index.html` → pushes → live in ~1 min

### What's in CONTENT.md:
| Section | Fields |
|---------|--------|
| Personal Info | Name, role, bio, photo URL, WhatsApp, phone, email |
| Hero | YouTube video ID |
| Video Section | Main reel ID + 6 projects (title, tag, YT ID, client, format, result, desc) |
| Photography | 10 projects (title, tag, client, format, result, desc, 3 images + thumb) |
| Work / Trusted By | Up to 8 brand names |
| Work / Testimonials | Up to 5 quotes (quote, author, role, company) |

### Image URLs:
- Google Drive: Share file → "Anyone with link" → use `https://drive.google.com/uc?id=FILE_ID`
- Imgur: Upload → right-click image → Copy image address
- Any direct `.jpg` / `.png` / `.webp` URL works
