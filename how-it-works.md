---
title: How It Works
layout: default
---

# How School Failsafe Works

## 1) Setup (mobile-first)
1. **Create account** — email magic link or SMS one-time code.  
2. **Basics** — parent name, email, mobile, time zone.  
3. **Kids** — name, grade, school (for labeling).  
4. **Preferred calendar** — Google | Apple (iOS) | Outlook | `.ics`.  
5. **Private family address** — e.g., `family123@school.dolife-ai.com`.  
6. **Auto-forwarding** — add a rule in your email (Gmail/Outlook/iCloud/etc.) that forwards **school emails** to your private address.  
   - No teacher CC needed.  
   - No inbox OAuth access.  
7. **Delivery options** — SMS alerts (default), optional daily recap, optional email invite.  
8. **Payment** — Stripe Checkout + Customer Portal.  
9. **Send Test** — we confirm your SMS and calendar add-link.

> Tip: We provide provider-specific forwarding examples in the wizard.

---

## 2) What you’ll receive
- **One SMS per actionable item**: a concise summary, child/school tag, and a **one-tap “Add to Calendar”** link for your chosen provider.
- **Tasks vs events**  
  - If there’s a specific time → event with start/end.  
  - If it’s a due-date task with no time → we create an all-day item or a 0-minute item at **8:00 AM** on the due date (consistent, easy to spot).  
- **Daily recap (optional)**: a single email listing open actions & dates.

---

## 3) What we do under the hood (privacy-light)
We only process **what you forward** to your private address.

**Parsing & redaction pipeline**  
1. Partition the email into structured pieces (subject, paragraphs, lists, tables, quoted replies).  
2. Mark signatures/quoted replies so they don’t distract extraction.  
3. **Redact PII (names, emails, phones, addresses, etc.)** before any AI step.  
4. Extract a strict JSON action: `must_do`, `title`, `when`, `where`, `child`, `confidence`, `links`, `source_message_id`.

**Storage**  
- **Delete raw email after processing.**  
- Keep an **Action JSON** + a **short redacted snippet** for audit.  
- No raw bodies in logs.  
- Per-user row-level security.

---

## 4) Calendar “Add” link logic
- You choose a **Preferred calendar** once; we generate the best link per action.  
- **Google** → prefilled event on calendar.google.com  
- **Apple iOS** → direct `.ics` that opens Calendar  
- **Outlook** → outlook deeplink (consumer/365) with `.ics` fallback  
- **.ics generator** → stable UID (familyId:messageId), `SEQUENCE` bumps on updates, `STATUS:CANCELLED` on retracts; optional `VALARM`.

---

## 5) DoLife app integration (optional, no duplication)
- If you later install **DoLife**, it subscribes to action webhooks and surfaces items in **For Review**.  
- When you share an email into DoLife on iOS, the app **redacts on-device** and calls the same engine.  
- **Dedupe** uses `source_message_id` so you don’t get duplicates.

---

## 6) Troubleshooting
- **No SMS?** Confirm your phone number and that your carrier allows A2P texts; try “Send Test” again.  
- **Forwarding too broad?** Narrow your rule (e.g., from domain: your school district).  
- **Time zone off?** Check your profile time zone and phone settings.  
- **Calendar didn’t open?** Try the `.ics` fallback; verify you’re signed in to the right calendar account.  
- **Stop messages**: Reply **STOP** to unsubscribe SMS; reply **HELP** for help. You can re-enable SMS in your profile anytime.

Need help? Email **support@dolife-ai.com**.
