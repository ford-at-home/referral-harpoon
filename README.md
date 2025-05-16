# Referral Harpoon

Referral Harpoon is a Python-based, AI-powered LinkedIn recruiting assistant designed for engineers who want to fish for top talent from their own network — and cash in on referral bonuses while they're at it.

With a single prompt, Referral Harpoon:

- Scrapes your LinkedIn connections (via data export or session cookie)
- Uses AI to filter top candidates that match your search
- Auto-writes a friendly, personalized email or DM
- Sends it on your behalf (via Gmail, SendGrid, or LinkedIn messaging API)

> “Hey, I saw your background and thought you might be a great fit for a role we’re hiring for…”

Run it weekly. Set it and forget it. Land hires, earn bonuses.

---

## Features

- AI-powered candidate filtering based on your prompt
- Automated scraping of LinkedIn connection data
- Email & LinkedIn DM message generation (via GPT-4 or Claude)
- Support for monthly, bi-weekly, or manual cadences
- Pluggable sending options (Gmail, SendGrid, or LinkedIn API)

## Usage

1. Clone the repo.
2. Export your LinkedIn connections or use session cookie for scraping.
3. Run the app with your desired candidate prompt.
4. Review and approve messages (optional).
5. Fire away!

```bash
python run.py "Looking for senior data engineers with startup experience"
```

## Demo

Coming soon.

## Legal

This is a proof-of-concept. Use responsibly and in accordance with LinkedIn's terms of service.
