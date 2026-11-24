# Texting registration (A2P 10DLC)

US phone carriers require every business that texts customers from a regular local number to register. Without it, texts get blocked. In GHL it's two parts: the **Brand** (who the business is) and the **Campaign** (what texts they'll send and how people agree to get them). Then the number shows **A2P Verified**.

Source: HighLevel help center (checked Nov 24, 2026). Menu names change; if one doesn't match, tell Claude and we'll fix this page.

## Before you start: what to collect
| Item | Notes |
|---|---|
| Legal business name | Exactly as on IRS records (CP-575 or 147C letter). Small mismatches get rejected. |
| EIN | US EIN only (not DUNS). EINs less than about 15 days old can be rejected. **Never save it in our files.** |
| Business type and industry | e.g. LLC; industry "Insurance" or "Professional Services" |
| Address | Street address, no P.O. box. Must match IRS records. |
| Business email | Their own domain is best. Gmail works but can be slower. |
| Contact person | First/last name, job title, email, phone. Must be reachable and real. |
| Website | Live, shows business name and contact info, has a **Privacy Policy** and **Terms** page (see below). |
| What texts they'll send | Usually: review requests, appointment reminders, replies to customer questions. |
| How customers agree to texts | Website form checkbox, in person, on a paper form, etc. |

**Sole proprietor (no EIN)?** Different path: no "LLC" in the name, a real mobile phone (not a VoIP or GHL number) that gets a code by text, a Gmail/Yahoo-type email, and only one number. If the business has an EIN, always use the standard path.

## Website requirements (most rejections happen here)
The client's website needs:
1. A **Privacy Policy** page with this line (or close to it): *"No mobile information will be shared with third parties or affiliates for marketing or promotional purposes. Text messaging originator opt-in data and consent will not be shared with any third parties."*
2. A **Terms** page with an SMS section: program name, what messages they'll get, "Message frequency varies", "Message and data rates may apply", "Reply HELP for help, STOP to opt out", and a contact email or phone.
3. A form where people agree to texts (if that's the opt-in method), with an **unchecked** consent checkbox and the same disclosure text next to it. GHL can generate this as a chat widget (see Campaign step).

If the site is ours (Sportsman Creative built it), Sarah can add these. If not, Claude drafts the text for the client to add.

## Step 1: Brand
1. In the client's sub-account: **Settings > Phone System > Trust Center**. Under **A2P Messaging (SMS)**, click **Start Registration**.
   - Or from the agency view: **Settings > Phone Integration (or Phone System) > Trust Center (A2P) > Brands > Start registration**, then pick the sub-account.
2. Answer "Where is the business registered?" (USA) and "Does it have a Tax ID?" (Yes for an LLC).
3. Business details: legal name, type, industry, registration ID type (EIN), EIN, business email, region. Uploading the CP-575 letter fills these in.
4. Address, then contact person.
5. Verification: a code by email, or an identity check (Persona). The client may need to do this part; tell them it's coming.
6. Submit. Standard brands usually take a few business days.

## Step 2: Campaign (after the Brand is approved)
1. **Settings > Phone System > Trust Center > A2P Messaging (SMS) > Brand & Campaigns > Campaigns > Create Campaign**. Pick the brand.
2. Choose **Chat Widget Setup** (easiest; GHL gives you a widget to put on the website) or **Switch to manual setup** (if consent happens another way).
3. Use case: for review requests and customer service, **Mixed** or **Informational / Non-Marketing** usually fits. Ask Claude to help pick.
4. Manual setup fields: use case description, sample messages, opt-in method and description, opt-in message, Privacy Policy URL, Terms URL, and the checkboxes for links / phone numbers in messages (review requests contain a link, so tick **links**).
5. Click **Review Application**, fix anything it flags, then submit. Don't resubmit while it says **Pending**.
6. When approved, check **Settings > Phone System > Phone Numbers** shows **A2P Verified** on the client's number.

### Good sample messages (edit for the client)
- "Hi {first name}, thanks for choosing {Business}! Would you mind leaving us a quick Google review? {link} Reply STOP to opt out."
- "{Business}: Hi {first name}, this is a reminder about your appointment on {date}. Reply HELP for help or STOP to opt out."
- Each sample names the business and includes opt-out wording.

### Opt-in message
"{Business}: You're subscribed to texts about your service and review requests. Message frequency varies. Msg & data rates may apply. Reply HELP for help, STOP to opt out."

## Costs
Carrier fees (one-time brand and vetting fees, a small monthly campaign fee, plus per-text charges) are passed through by GHL at cost. The exact amounts show in the Trust Center before you submit. **(to confirm with Jordan: do we cover these or bill the client?)**

## If it's rejected
Open the campaign or brand, click **View required fixes**. Common reasons: name or EIN doesn't match IRS records, address mismatch, website missing Privacy/Terms or SMS wording, opt-in not shown, use case doesn't match sample messages. Fix everything, then resubmit. Resubmitting an eligible rejected campaign doesn't charge the vetting fee again. Write what happened in the client file and add the lesson here.

## Lessons learned
(Add a dated line each time we learn something.)
- 2026-11-24: Our A2P intake form (GHL form, "A2P Registration Information") lets clients type anything in the EIN box. Irwin typed his business name. Always check the EIN field looks like `12-3456789` before submitting. Fix to the form (to confirm with Jordan): make EIN a pattern-checked field, split "Business type" into LLC / Corporation / Sole proprietor / Partnership / Nonprofit, and add Website and "Legal name exactly as on your IRS EIN letter" hints.
- 2026-11-24: Check the website's business name against the legal name before submitting. The website and brand must match (or the site must say "DBA").
- 2026-11-24: A big bundled telemarketing consent checkbox isn't enough. Carriers want a separate, optional, unchecked texting checkbox with frequency, rates, HELP and STOP.
