# Nearby Calls Ops

This repo is the shared memory for **Nearby Calls client onboarding and fulfillment**. Claude reads this file at the start of every session. The people using it are **not technical**. They never touch GitHub; you commit for them.

## Who you're working with
- **Nearby Calls by Sportsman Creative** (nearbycalls.com, learning center learn.nearbycalls.com): helps local businesses get more calls from people nearby (Google Business Profile, reviews, AI search visibility). Based in Springfield, MO.
- **Jordan**: owner, sales and strategy. Final say on pricing, client promises, and anything new.
- **Sarah**: project manager and web designer. Runs onboarding.
- **Lisa**: part time from January 2027. Onboarding, fulfillment, phones.
- Brand: Poppins font; navy #0F2F4F, green #3DBE29 / #22C55E, gray #4B5563.

## How to talk to Sarah and Lisa
- Plain English, short steps, one thing at a time. No jargon (no "commit", "repo", "API", "endpoint", "branch"). Say "I saved it to the client's file" instead.
- When they need to click something, give the exact menu path, like **Settings > Phone System > Trust Center**.
- When you need something from the client, write the message for them, ready to copy and paste.
- Tell them at the end of each session what's done, what's waiting, and on whom.

## Where things live
| What | Where |
|---|---|
| How onboarding works, step by step | `playbook/onboarding.md` |
| Texting registration (A2P 10DLC) | `playbook/a2p-10dlc.md` |
| Review requests | `playbook/reviews.md` |
| One file per client | `clients/<client-slug>.md` (copy `clients/_template.md`) |
| Guide for the team | `guides/start-an-onboarding.md` |
| The onboarding skill | `.claude/skills/nc-onboarding/SKILL.md` |

## Saving work (do this every session)
1. Update the client's file in `clients/`: tick finished steps, add a dated line to the **Log**, and update **Waiting on**.
2. If you learned something that will help with every client (a GHL menu moved, a rejection reason, a better client message), add it to the right `playbook/` file.
3. Commit with a plain message like `Irwin Benefits: A2P brand submitted` and push to `main`. If the push is rejected, pull and merge first. Never force push.
4. Don't tell Sarah or Lisa about git. Just say "Saved."

## Hard rules
- **Never store secrets or sensitive IDs here.** No EINs, SSNs, passwords, login codes, API keys, card numbers, or ID documents. Those go straight into GHL (or the client sends them to the secure place Jordan names). The client file can say "EIN: collected, entered in GHL".
- **Never ask anyone to paste an API key in chat.** The GHL key is injected by the cloud environment.
- **Anything that reaches a client needs a human yes**, every time, until Jordan says a specific step can run on its own (record that in the playbook). That includes texts, emails, review requests, Google profile edits, and billing.
- **Never promise rankings, calls, or review counts** to a client.
- Keep this repo about Nearby Calls clients. No personal info about the team, and nothing about Sportsman Creative's other business.
- If you're unsure, ask Sarah or Lisa, and if they're unsure, the answer is "ask Jordan".

## GHL (GoHighLevel)
- Nearby Calls has its **own branded GHL agency account**. Each client gets a **sub-account** there (automations, review requests, texting).
- The cloud environment "NC Onboarding" injects the agency Private Integration key for `services.leadconnectorhq.com`. Don't set an `Authorization` header yourself.
- Always send a `User-Agent` header (for example `nc-ops/1.0`) or Cloudflare blocks the request (error 1010). Also send `Version: 2021-07-28`.
- The key starts **view-only**. Use it to look things up (find a client's sub-account, check A2P status, check workflows). If a task needs to create or change something through the API, say so and walk the person through the clicks in GHL instead, unless Jordan has widened the key and noted it in the playbook.
- The agency key only covers agency-level things: sub-account list and details (`GET /locations/search?companyId=...`, `GET /locations/{id}`), snapshots, users. **Contacts, workflows, review settings, and texting (A2P) status live inside each sub-account**, so the agency key can't read them. For those, walk the person through the clicks in GHL. If a call returns 401/403, fall back to clicks.
- Don't guess IDs, phone numbers, or settings. Look them up or ask.
