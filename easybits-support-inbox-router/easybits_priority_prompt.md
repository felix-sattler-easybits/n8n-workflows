# 🚦 Priority Prompt

Paste this into the description of the `priority` field in your easybits pipeline.

Rate this email's priority based on **sentiment, urgency signals, and business impact**. Return ONLY the lowercase priority label — nothing else.

The email may be in **English or German**. Apply the same standards to both languages.

## Levels

- urgent
- normal
- low

## How to Identify Each Level

### urgent
The sender is angry, threatening to churn, reporting that something is broken in production, blocked from working, or explicitly says this is time-sensitive. Also: payment failures, account access issues, security concerns, or a prospect ready to buy now.

### normal
Standard requests, questions, or reports with no strong sentiment either way. Most emails fall here. The sender wants a response in a reasonable timeframe but isn't blocked or upset.

### low
Casual inquiries, FYIs, newsletters, generic vendor pitches, job applications, or anything that can wait days without consequence. Polite tone, no time pressure, no business impact if delayed.

## Signals That Bump Priority UP

### English
- **Negative sentiment:** frustrated, angry, disappointed, fed up, unacceptable
- **Urgency:** "urgent", "ASAP", "immediately", "right now", "today", "by EOD"
- **Breakage:** "broken", "down", "not working", "can't access", "blocked", "stuck"
- **Business impact:** "losing money", "losing customers", "missing deadline"
- **Escalation:** "cancel", "refund", "switch providers", "speak to a manager", "this is the third time"

### German
- **Negative sentiment:** "verärgert", "enttäuscht", "frustriert", "inakzeptabel", "Frechheit", "Unverschämtheit"
- **Urgency:** "dringend", "sofort", "umgehend", "schnellstmöglich", "eilig", "bis heute", "bis Ende der Woche"
- **Breakage:** "funktioniert nicht", "geht nicht", "kaputt", "ausgefallen", "kein Zugriff", "blockiert", "hängt"
- **Business impact:** "verlieren Kunden", "verlieren Geld", "Frist", "Termin verpassen"
- **Escalation:** "kündigen", "Erstattung", "Anbieterwechsel", "Vorgesetzten sprechen", "zum dritten Mal"

## Signals That Keep Priority NORMAL or LOW

- Polite, neutral tone
- **English:** "whenever you have a chance", "no rush", "just wondering", "FYI"
- **German:** "bei Gelegenheit", "keine Eile", "nur eine kurze Frage", "zur Information", "wenn es passt"
- Open-ended questions with no deadline
- Generic outreach, curiosity inquiries, or vendor pitches

## Decision Rules

- German business correspondence is often more **formal** than English. A polite, formal German email ("Sehr geehrte Damen und Herren") is NOT a sign of low urgency by itself — read the actual content.
- A frustrated German email may be more **restrained in tone** than an equally frustrated English one. Weight the words and described situation, not just emotional intensity.
- Priority is **independent of category and independent of language**. An urgent German billing email and an urgent English billing email both score `urgent`.
- Never explain your reasoning. Return only the level.

## Output Format

Return exactly one of the following lowercase strings and nothing else:

`urgent` `normal` `low`
