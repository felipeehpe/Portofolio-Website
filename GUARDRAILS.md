# AI COLLABORATION GUARDRAILS
### Felipe + Claude — Portfolio Website

---

## How We Work

```
You describe the change (plain English)
        ↓
Claude edits index.html
        ↓
Claude pushes to GitHub
        ↓
Netlify auto-deploys (~1 min)
        ↓
You check the live site
        ↓
Approve or request changes
```

---

## Rules for Requesting Edits

### DO
- Be specific: "Change the hero name font size to 80px on mobile"
- One change at a time (or group related ones clearly)
- Paste media URLs directly — Claude will embed them
- Say what you DON'T want ("keep the animations, just change the color")
- Check the live site after every deploy before requesting the next change

### DON'T
- Ask for vague changes: "make it look better"
- Request multiple unrelated changes in one message
- Skip reviewing the live site after a push
- Let Claude rewrite the entire file unless you explicitly ask

---

## What Claude Will Always Do
- Edit only what was asked — nothing more
- Show what changed before pushing
- Push to GitHub so Netlify auto-deploys
- Preserve all animations, UX flow, and design system
- Ask before making any structural changes

## What Claude Will Never Do (Without Permission)
- Add new external libraries or frameworks
- Change the single-file structure
- Push breaking changes without warning
- Delete sections or cards
- Change the card-to-section UX flow

---

## Media Updates
| Want to update | What you do | What Claude does |
|---|---|---|
| Photo in card | Upload to Imgur/Drive → paste link | Replaces the `src` in HTML |
| Video in card | Upload to YouTube → paste URL | Updates the iframe embed |
| Profile photo | Same as above | Replaces the About card image |

---

## Best Practices (2025 AI + Web)

1. **Plan before prompting** — know what you want before asking
2. **Small steps** — one change at a time = fewer mistakes
3. **Always review** — check the live site, don't assume it worked
4. **You decide** — Claude suggests, you approve
5. **Context matters** — the more specific your request, the better the output
6. **Keep the CLAUDE.md updated** — if the design changes, update the rules

---

## If Something Breaks
1. Tell Claude: "the site broke after the last change"
2. Claude will revert the last commit
3. We diagnose before trying again

---

## Session Start Checklist
- [ ] Open terminal in `Portofolio-Website` folder
- [ ] Run `claude` to start Claude Code
- [ ] Check live site is working before making changes
- [ ] Tell Claude what you want to change
