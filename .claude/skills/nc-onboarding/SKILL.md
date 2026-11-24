---
name: nc-onboarding
description: Walk Sarah or Lisa through onboarding a Nearby Calls client (intake, GHL sub-account, A2P texting registration, Google, review requests) and keep the client's file up to date. Use when someone says "start onboarding", "new client", names a client, or asks where a client is at.
---

# Nearby Calls onboarding

You are helping a non-technical teammate (Sarah or Lisa) onboard a Nearby Calls client. Read `CLAUDE.md` first for the rules. The step-by-step lives in `playbook/onboarding.md`, `playbook/a2p-10dlc.md`, and `playbook/reviews.md`.

## 1. Find or create the client
- Ask: "Which client?" if they didn't say.
- Look in `clients/` for a matching file. If there is one, read it and say in two or three sentences where things stand and what's next.
- If not, copy `clients/_template.md` to `clients/<business-name-in-lowercase-with-dashes>.md`, fill in what you know, and say "I started a file for them."
- If the GHL key works, look up the client's sub-account (`GET /locations/search?companyId=...` with the agency's company ID; ask the first time and save it to `CLAUDE.md`). Record the location ID in the file. If the call fails, carry on with clicks.

## 2. Work one step at a time
- Pick the next unchecked step in the client file. Say what it is, why it matters in one sentence, and give the exact clicks.
- When the step needs info from the client, write the message for them to send, ready to copy. Ask for everything still missing in one message.
- When a step reaches the client (a message, a review request, a Google change), show it and wait for a clear "yes" before anyone sends it.
- Ask them to tell you when the step is done (or paste a screenshot). Then tick it in the file.
- If something doesn't match the playbook (a menu moved, an error), help them through it, then fix the playbook.

## 3. Sensitive info
- Never write an EIN, SSN, password, code, or ID document into any file or repeat one back in chat. If someone pastes one, tell them you won't save it and they should type it straight into GHL.

## 4. End of every session
- Update the client file: ticks, **Waiting on**, and a dated **Log** line with who did what.
- Add any lesson to the right playbook file.
- Save (commit and push to `main` with a plain message, e.g. `Irwin Benefits: review link set`). Pull first if the push is rejected; never force push.
- Tell them: what's done, what's waiting and on whom, and the next step. Keep it short.

## Status questions
"Where are we with X?" or "What's waiting?": read the client files and answer in plain sentences. For "all clients", list each client with status and what it's waiting on.
