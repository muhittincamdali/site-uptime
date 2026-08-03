# site-uptime

External uptime monitor for **muhittincamdali.com** — runs entirely on GitHub Actions, independent of the server.

**Why:** on 2026-07-23 the site went down (Hetzner non-payment IP block) and stayed down for 3.5 days because all monitoring lived _on the server itself_. This monitor lives outside.

**How it works:** every ~5 minutes a workflow probes `/` and `/api/health/`. Two consecutive failures → an issue labeled `outage` is opened (GitHub e-mails the owner automatically). On recovery the issue gets a ✅ comment and is closed. While down, each run adds a "still down" comment.

Manual run: Actions → _Site Uptime Check_ → Run workflow.
