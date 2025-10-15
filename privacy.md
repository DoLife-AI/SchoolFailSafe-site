---
layout: page
title: Privacy Policy
description: Privacy practices for School Failsafe by DoLife AI, LLC
---

# Privacy Policy

_Last updated: October 14, 2025_

**School Failsafe** is a privacy-light service operated by **DoLife AI, LLC** that turns forwarded school emails into concise text alerts and one-tap calendar links. This policy explains what we collect, why we collect it, and how we protect it.

## What We Collect

### Account & Profile
- **Contact info:** name, email, mobile phone, time zone
- **Preferences:** preferred calendar (Google, Apple/iOS, Outlook, or `.ics`)
- **Billing data:** limited information from our payment processor (Stripe), such as a customer ID and subscription status

### Service Data
- **Forwarded emails:** only emails you choose to forward to your private School Failsafe address.  
  - **Defaults:** we process the email, extract action details, and **delete raw email content after processing**.
  - **Retained:** a small, redacted “Action JSON” (what/when/who/links/confidence/source ids) and a short redacted snippet for audit and troubleshooting.
- **Delivery metadata:** message logs (e.g., SMS sent status, time, link type) without raw message bodies.

### Technical
- Basic device/browser info, IP address, and timestamps for security, fraud prevention, and troubleshooting.

## How We Use Your Information
- Provide and improve School Failsafe (account login, OTP, alerts, calendar links)
- Generate and deliver the “Action JSON” derived from forwarded emails
- Billing and subscription management (via Stripe)
- Security, abuse prevention, and legal compliance
- Customer support

We **do not** sell your personal information. We do not train models on your raw email content.

## Data Handling Defaults
- **Scope:** We only see the emails you forward to your private address. We do not connect to your inbox or read unrelated emails.
- **Redaction:** We run a redaction pipeline on structured text before any AI extraction step.
- **Deletion:** Raw email bodies are **deleted after processing** by default. We retain only the structured Action JSON and a short redacted snippet for audit.
- **Access controls:** Role-based access; encryption in transit (TLS) and at rest; least-privilege keys; no raw bodies in logs.
- **User control:** You may request **Delete Everything** at any time (see “Your Choices”).

## Your Choices & Rights
- **Access / Update:** You can update profile information in your account.
- **Opt-out of SMS:** Text **STOP** to stop messages; **HELP** for help.
- **Delete:** Request deletion of your data by emailing **[support@schoolfailsafe.com](mailto:support@schoolfailsafe.com)**. We will remove account data, Action JSON, and associated delivery logs unless retention is required by law (e.g., tax records for billing).
- **Export:** You may request a copy of your Action JSON.

## Sharing with Service Providers
We use trusted third parties to run the service:
- **Supabase** (authentication, database, edge functions)
- **Postmark** (email, including magic-link login)
- **Twilio** (SMS delivery, link shortening as applicable)
- **Stripe** (payments and Customer Portal)
- **Hosting/CDN** as needed for the website and wizard

These providers process data on our behalf under contracts that require confidentiality and appropriate security.

## Data Retention
- **Account & billing:** kept while your subscription is active and for a reasonable period afterward to meet legal/financial obligations.
- **Action JSON:** retained while you use the service or until you request deletion.
- **Raw email bodies:** deleted after processing (default), with short redacted snippets kept only for audit/troubleshooting.

## Security
We use encryption (in transit and at rest), RLS (row-level security) in our database, and least-privilege credentials. No system is 100% secure; if we discover a breach, we will notify affected users as required by law.

## Children’s Privacy
School Failsafe is designed for parents/guardians. We do not knowingly collect personal information directly from children under 13. If you believe a child has provided us information, contact **[support@schoolfailsafe.com](mailto:support@schoolfailsafe.com)**.

## International Users
Our service and data storage may be located in the United States. By using the service, you consent to processing in the U.S. If you are in a region with specific privacy rights (e.g., GDPR/UK GDPR/CCPA/CPRA), contact us to exercise applicable rights; we will honor valid requests to the extent required by law.

## Changes to This Policy
We may update this policy from time to time. We will post changes here and update the “Last updated” date above.

## Contact Us
**DoLife AI, LLC**  
Email: [support@schoolfailsafe.com](mailto:support@schoolfailsafe.com)  
Mailing address: _Add your business mailing address here._
