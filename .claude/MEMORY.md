# Project memory / open follow-ups

Notes that don't belong in `CLAUDE.md` (architecture) or `PONYTAIL.md` (style) —
pending items worth remembering across sessions.

## Open

- **Leads API `email`/`message` fields unconfirmed** (added 2026-10-03). The
  homepage contact form (`index.html` `#contact-form`, `initContactForm` in
  `js/script.js`) POSTs to `https://app.greenriseenergy.com/api/leads` — the
  same backend `campaign/index.html` uses. That page's own payload only proves
  these fields exist: `name`, `phone_no`, `bill_amount`, `city`, `source`,
  `utm_source`, `utm_medium`, `utm_campaign`, `visitor_id`,
  `cf-turnstile-response`. The homepage form also sends `email` and `message`
  under those literal names — fields the campaign page never collects, so
  there's no confirmed evidence those are the names this backend expects.
  Decision at the time: send them anyway and learn the real schema from the
  API's actual response rather than block on it. Marked with a `TODO:` comment
  in `js/script.js` right above the payload.

  **Next step:** once a real submission has been made, check what
  `/api/leads` returned. If it names `email`/`message` as unexpected/rejected
  fields (or there's other evidence they're silently dropped), fix the field
  names in the payload and remove the TODO. If confirmed correct, just remove
  the TODO comment.
