# Deployment Guide – Referral Harpoon

This guide walks you through deploying Referral Harpoon on AWS using EC2 and Lambda for automation.

## 1. Prerequisites

- AWS CLI installed
- Python 3.11+
- GitHub repo cloned
- Gmail or SendGrid account
- (Optional) Claude or OpenAI API key

## 2. Setup

### A. Environment Variables

Create a `.env` file:

```
OPENAI_API_KEY=your_key
SENDGRID_API_KEY=your_key
GMAIL_CLIENT_ID=...
LINKEDIN_SESSION_COOKIE=your_cookie
```

### B. Install dependencies

```bash
pip install -r requirements.txt
```

## 3. Deploy to EC2

Provision an EC2 instance (t3.micro or larger):

```bash
aws ec2 run-instances --image-id ami-0... --instance-type t3.micro ...
```

SSH into instance and clone repo, set up cron job to run:

```bash
crontab -e
# Example: run every 2 weeks
0 10 */14 * * /home/ubuntu/referral-harpoon/run.sh >> /var/log/referral.log
```

## 4. Deploy with Lambda (Optional)

You can turn the matching and messaging flow into a Lambda function that runs on schedule via CloudWatch Events.

Steps:

* Zip the code
* Upload to Lambda
* Attach necessary IAM roles
* Use EventBridge to trigger

## 5. Logs and Monitoring

* Output is logged to `referral.log`
* Use CloudWatch Logs if using Lambda

## 6. Safety Mechanisms

* Dry-run mode enabled by default
* Message preview screen in CLI
* Message cap per run (e.g., 5 messages per run)

---

## Recommended Stack

* AWS EC2 or Lambda
* Python 3.11
* OpenAI or Claude for AI
* SendGrid or Gmail for email
