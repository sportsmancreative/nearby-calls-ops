# Review requests

Goal: after every job, the client's customer gets a friendly text or email with a link to leave a Google review. Never promise a client a number of reviews or a rating.

Source: HighLevel help center (checked Nov 24, 2026).

## 1. Connect Google
- In the client's sub-account: **Settings > Integrations > Google**, sign in with the Google account that manages their Business Profile, and pick the right location.
- New sub-accounts may show a **guided review setup** on the Reputation page. Use it if it's there; it walks through the same steps below and disappears once done.

## 2. Review link
- **Reputation > Settings > Review Link**. Choose Google (or paste the client's Google review link as a **Custom Link**).
- Test: open the link in a private browser window. It should open the "write a review" box for the right business.

## 3. Email requests (can start right away)
- **Reputation > Settings > Email Requests**. Turn on **Enable Email Review Requests**.
- When to send: 1 hour after the request is triggered is a good start. Repeat every 2 days, maximum 2 retries; it stops once they click.
- Pick the sender email. Create a template (or import one), drag in the **Review Link** element, then **Set Email Templates** for Live and Retry, and **Save**.

## 4. Text requests (only after A2P is approved)
- **Reputation > Settings > SMS Requests**. Turn on **Enable SMS Review Requests**.
- Same timing settings. Pick the client's A2P Verified number as sender.
- Template must include `{{reputation.review_link}}` and opt-out wording. Assign Live and Retry templates and **Save**.

Default text (edit for the client):
> Hi {{contact.first_name}}, thanks for choosing {Business}! If you have a minute, a quick Google review helps us a lot: {{reputation.review_link}} Reply STOP to opt out.

## 5. How requests get sent
Pick one with the client and write it in their file:
- **By hand**: Reputation > Requests > send to one person or a list. Good to start.
- **From a contact**: open the contact, click **Send Review Request**.
- **Automatic**: a Workflow with the **Send Review Request** action, triggered by a tag (for example `job complete`), a pipeline stage, or an app integration. **(to confirm: does our snapshot already have this workflow?)**

## 6. Test before go-live
Send a request to a team member's email and phone. Check the link, the wording, and the business name. Then tell the client it's live.

## Lessons learned
(Add a dated line each time we learn something.)
