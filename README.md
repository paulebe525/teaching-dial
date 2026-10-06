# Teaching Dial

Your teaching week as six dials, Monday to Saturday, with a live "Next up" countdown in India time. It is one HTML page with no server and no sign-in.

Open it: https://paulebe525.github.io/teaching-dial/

## Put it on your phone

1. Open the link in Chrome (Android) or Safari (iPhone).
2. Chrome: menu, then **Add to Home screen**. Safari: Share, then **Add to Home Screen**.

## Read timetable photos

1. Get a free Gemini API key at https://aistudio.google.com/apikey. Sign in with a Google account, choose **Create API key**, and copy it.
2. In Teaching Dial, tap **Settings**, paste the key and tap **Save key**. Check **My name** and the other ways your name is written.
3. Tap **Add timetable** and pick or take one or more photos (printed or handwritten).
4. Check the classes it found, fix anything read wrong, and tap **Save to my week**.

The app matches your name itself. A full name or surname counts. A bare first name such as "Paul" counts only when no other person on that sheet has that name, so "Newton Paul Singh" is ignored.

## Privacy

- The API key and your saved week stay in this browser on this phone (localStorage). They are not sent to GitHub or to any server run for this app.
- Each photo is shrunk on the phone and sent only to Google's Gemini API to be read. On Gemini's free tier, Google may use what you send to improve its products. See Google's terms.
- In Settings, **Remove key** deletes the key and **Reset to sample** deletes the saved week.

## Editing

- The sample week is the `WEEK_DATA` array in `index.html`.
- The Gemini model name is `CONFIG.geminiModel` (currently `gemini-3.8-flash`).
