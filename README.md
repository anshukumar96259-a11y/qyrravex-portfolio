# Qyrravex / Anshu portfolio

A custom-coded, mobile-first personal portfolio with a neon-blue cinematic theme and a branded AI chat assistant.

## What's included
- Responsive portfolio: hero, about, project showcase, skills, assistant, contact.
- CSS motion, orbital hero art, scroll reveals, reduced-motion support.
- Qyrravex chat UI.
- Cloudflare Pages Function at `functions/api/chat.js`. It calls Gemini server-side; the API key is not shipped to the browser.
- No framework or build step required for the static front end.

## Honest status
The portfolio UI is functional immediately. The assistant will only generate AI replies after deployment to a host that runs Pages Functions and after `GEMINI_API_KEY` is configured as a server-side secret. A front-end-only static page cannot safely hold an API key. Qyrravex is a brand/assistant layer over a hosted model, not a foundation model trained from scratch.

## Free-first publishing from Android
1. Download and unzip this project.
2. In your browser, create a GitHub repository and upload the project files, keeping the `functions/api/chat.js` path exactly as shown.
3. In Cloudflare, create a Pages project connected to that repository. Use the repository root as the project root; leave build command empty and output directory as `.` for this plain static site with a Pages Function.
4. In the Cloudflare Pages project, open Settings → Variables and Secrets and add `GEMINI_API_KEY` as a secret. Create the key in Google AI Studio. Never paste the key into `index.html`, `app.js`, GitHub, or a public chat.
5. Redeploy the Pages project. Open the provided `pages.dev` URL and test Qyrravex.

Cloudflare and model-provider free limits/terms can change. Google's Gemini API free tier is limited and may have data-use terms; review them before sending private information. Do not send passwords, sensitive personal data, or private customer information to the assistant.

## Personalize before sharing
- Replace `hello@example.com` in `index.html` with the email address you want public.
- Edit the project descriptions to match what you have actually published.
- You may change the name Qyrravex in `index.html`, `app.js`, and `functions/api/chat.js`.
- If the brand becomes commercial, perform a formal trademark and domain check first. A search-engine query is not legal clearance.

## Local preview
Open `index.html` in a browser to preview the portfolio UI. Chat responses won't work in a local file preview because `/api/chat` needs a deployed Pages Function and secret.
