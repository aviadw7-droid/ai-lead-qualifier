# AI Lead Qualifier — Make.com + OpenAI

An automation that qualifies incoming business leads using AI — saving manual review time and ensuring faster responses to the right people.

---

## The Problem

Freelancers receive inquiries of varying quality. Manually reading and responding to every submission wastes hours and slows down response time to serious leads.

## The Solution

This automation analyzes every new inquiry the moment it arrives, scores it 1–10 using GPT-4o-mini, tags it as **hot / warm / cold**, and sends a personalized email response automatically — all without human intervention.

---

## How It Works

```
Google Form → Google Sheets → Make.com → OpenAI (GPT-4o-mini) → Parse JSON → Google Sheets (log) → Router → Gmail
```

1. A potential client fills out a Google Form with their name, email, and inquiry
2. Make.com detects the new row in Google Sheets
3. The inquiry is sent to OpenAI with a structured prompt
4. GPT-4o-mini returns a JSON object with a score, tag, and reason
5. The result is logged back into Google Sheets
6. A router sends a different personalized email based on the tag

---

## AI Prompt

```
You are a business lead qualifier. Analyze the following inquiry and return ONLY a JSON object, no extra text.

Name: [name]
Inquiry: [inquiry]

Return this exact format:
{
  "score": 7,
  "tag": "hot",
  "reason": "one sentence explaining the score"
}

Tags must be one of: hot, warm, cold.
Score must be between 1 and 10.
```

---

## Results

Tested across 6 different inquiry types with accurate classification across all cases.

- Hot leads received a priority follow-up email within seconds
- Warm leads received a nurturing response requesting more details
- Cold leads received a polite informational response

---

## Tech Stack

- **Make.com** — automation and workflow orchestration
- **OpenAI GPT-4o-mini** — lead scoring and classification
- **Google Forms** — lead intake
- **Google Sheets** — data logging
- **Gmail** — automated email responses

---

## What This Saves

- Manual review time per inquiry: ~5 minutes
- With 20 inquiries per week: **~1.5 hours saved weekly**
- Response time to hot leads: from hours → seconds

---

## Author

Aviad Weiss — AI Automation Specialist
[LinkedIn](https://www.linkedin.com/in/aviad-weiss)
