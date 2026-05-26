# Realtor101 — Build Log & Prompt Notes

## Scenario 1: Lead Ingestion — COMPLETE

**Date completed:** 2026-05-26

### What was built
End-to-end lead ingestion pipeline triggered by form submission on the landing page:

1. **Form submission** — Contact form on the Meridian Realty demo site POSTs to a Make (Integromat) webhook.
2. **Supabase lead creation** — Make HTTP module inserts a new row into the `leads` table via the Supabase REST API.
3. **Gemini opening message** — Make invokes the Gemini API to generate Jordan's first outreach message using the Jordan system prompt.
4. **Messages table** — The generated message is stored in the `messages` table, associated with the lead record.

### Key lesson learned
**Make HTTP modules require "Data structure" body input method — not "Raw".**

When sending JSON to Supabase (or any API) via Make's HTTP module, use the **Data structure** body type so Make handles JSON serialization and escaping automatically. Using **Raw** causes double-escaping and malformed JSON payloads that fail silently or return 400 errors.

### Files involved
- `index.html` — form wired to Make webhook (`/api/submit` or direct webhook URL)
- `make/` — Make scenario blueprint (if exported)
- `prompts/jordan_v1.md` — Jordan system prompt used for opening message generation

---

## Upcoming: Scenario 2

TBD — likely SMS/email delivery of Jordan's opening message to the lead.
