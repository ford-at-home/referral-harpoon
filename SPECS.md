# Referral Harpoon – Technical Specifications

## System Overview

Referral Harpoon allows engineers to activate their network for recruiting via:
- AI-powered candidate discovery
- Automated outreach messaging
- Cadence-based job campaigns

---

## Components

### 1. Data Ingestion
- **Option A**: Manual upload of LinkedIn connections export (CSV)
- **Option B**: Scraping via Selenium using user session cookie
- **Option C**: LinkedIn API (if user has access)

### 2. AI Candidate Matching
- Uses OpenAI, Anthropic, or open-source LLMs
- Prompt: User provides role description
- Output: Top 5 candidate matches from LinkedIn data

### 3. Email/DM Generation
- Personalized with:
  - Candidate name
  - Shared history (e.g. same college, company)
  - Custom job pitch
- Generated via prompt chaining with LLM

### 4. Sending Engine
- **Email**: Gmail API, SendGrid, or SMTP
- **DM (if possible)**: LinkedIn Messaging API or browser automation fallback

### 5. Scheduler
- Cron-based repeat scheduling
- Option to log outreach, follow-ups

---

## Alternatives Considered

| Feature | Chosen | Alternatives |
|--------|--------|--------------|
| LLM | Claude / GPT-4 | Llama 3, Mistral |
| Email | Gmail API | SMTP, Outlook |
| Scraping | LinkedIn export / Selenium | PhantomBuster, LinkedIn API |
| Matching Logic | LLM semantic rank | Regex, manual tagging |

## Security & Privacy

- OAuth for email services
- .env for storing API keys
- All scraped data stored locally unless user enables remote sync

## Limitations

- LinkedIn TOS may prohibit scraping
- Messaging limits may apply
- Candidate matches are only as good as your network + the model
