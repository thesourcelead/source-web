# Source · Home (web)

One static page: sign in with a Source account and see every box in the home, who is on each pad, time left, and where your own phone is. Organizers can unlock a session (End) or use Emergency release. The server enforces who can unlock (`006_unlock_organizers.sql`); the page just hides the buttons from everyone else.

- Address: https://source.swellsecondary.com (GitHub Pages, repo `thesourcelead/source-web`)
- Data: Supabase project `zkqszazgqajnswgjomce`, read through Row Level Security with the public key. No secrets in this repo.
- Live: Realtime private channels `device:<id>` (status, command results, presence) and `household:<id>` (session started/ended/extended), plus a 20 s refresh as a fallback.

## Publish an update
Run `./push_web_to_github.sh` from the project folder. GitHub Pages redeploys in about a minute.

## One-time setup
1. GitHub: create an empty **public** repo `thesourcelead/source-web`.
2. Run `./push_web_to_github.sh`.
3. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`. Custom domain: `source.swellsecondary.com`. Tick "Enforce HTTPS" once it's offered.
4. Squarespace → Domains → swellsecondary.com → DNS → add record: Type `CNAME`, Host `source`, Data `thesourcelead.github.io`.
