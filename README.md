# Teaching Dial

Your teaching week as six dials, Monday to Saturday, with a live "Next up" countdown in India time. It is one HTML page with no server and no sign-in.

Open it: https://paulebe525.github.io/teaching-dial/

## Put it on your phone

1. Open the link in Chrome (Android) or Safari (iPhone).
2. Chrome: menu, then **Add to Home screen**. Safari: Share, then **Add to Home Screen**.

## Read timetable photos

1. Get at least one API key. You can save up to three:
   - **Gemini** (free tier): https://aistudio.google.com/apikey
   - **OpenAI / ChatGPT** (paid, billed by OpenAI per photo): https://platform.openai.com/api-keys
   - **Claude** (paid, billed by Anthropic per photo): https://platform.claude.com/settings/keys
2. In Teaching Dial, tap **Settings**, paste each key and tap **Save key**. Check **My name** and the other ways your name is written.
3. Tap **Add timetable** and pick or take one or more photos (printed or handwritten).
4. Check the classes it found, fix anything read wrong, and tap **Save to my week**.

The app matches your name itself. A full name or surname counts. A bare first name such as "Paul" counts only when no other person on that sheet has that name, so "Newton Paul Singh" is ignored.

### Fallback when a service is busy

Settings has a **Reading order** list (default: Gemini, then OpenAI, then Claude; use the arrows to change it). For each photo the app tries the services in that order and skips any without a key.

- If a service is busy, over its limit, or does not answer within 45 seconds (HTTP 429, 500, 502, 503, 504, 529, "overloaded", "RESOURCE_EXHAUSTED", timeout, no connection), the app moves on to the next one.
- If a service rejects its key (401/403 or "API key not valid"), the app says so and tells you to check that key in Settings, then still tries the next service.
- The check screen shows which service read each photo, for example "Read by Claude, Gemini was busy."
- If every service fails, the app shows one message naming what went wrong with each.

## Privacy

- The API keys and your saved week stay in this browser on this phone (localStorage). They are not sent to GitHub or to any server run for this app.
- Each photo is shrunk on the phone and sent only to the service reading it, with that service's own key. On Gemini's free tier, Google may use what you send to improve its products. See each company's terms.
- In Settings, **Remove key** deletes a key and **Reset to sample** deletes the saved week.

## Editing

- The sample week is the `WEEK_DATA` array in `index.html`.
- Model names are in `CONFIG` in `index.html`: `geminiModel` (`gemini-3.8-flash`), `openaiModel` (`gpt-6.1-terra`, Responses API), `claudeModel` (`claude-sonnet-5-5`, Messages API).
