# voice-assistent-in-website-for-a-real-estate-agency
Real estate agency landing page with an embedded AI voice assistant that speaks Telugu — collects leads and books site visits.
Nivasa Realty — Voice-Powered Real Estate Landing Page

A real estate agency landing page with an embedded Vapi voice AI assistant that speaks fluent Telugu. Visitors can call Meera, the AI assistant, straight from the browser — she collects their name, phone number, property requirements, and books a site visit, no forms required.

Built for a real estate agency in Vijayawada, Andhra Pradesh, but easy to re-skin for any city, agency name, or property list.


Features


One-click voice call — no app download, no phone dialing. Click, talk, done.
Telugu-speaking assistant — Meera converses naturally in Telugu (with common English words mixed in, the way people actually speak), not a robotic word-for-word translation.
Structured lead capture — every call collects name, mobile number, property type, location, budget, BHK/specs, and preferred site visit time.
Multiple call entry points — nav bar button, hero "stamp" CTA, voice-assistant section button, and a floating call button — all wired to a single shared call session.
Live call status — UI updates in real time as the call connects, as Meera speaks, and as she listens.
Sample property listings — placeholder cards for flats, an independent house, and an open plot, ready to be swapped for real inventory.
Fully responsive — works down to mobile screens.
No build step — a single static index.html file. Open it directly or host it anywhere.



Tech Stack

LayerChoiceMarkup/StylingPlain HTML5 + CSS (no framework)Voice AIVapi — Web SDK via @VapiAI/html-script-tagTranscriptionAzure STT (Telugu, India)LLMOpenAI GPT-4.1Text-to-speechElevenLabsFontsFraunces, IBM Plex Sans, IBM Plex Mono (Google Fonts)


Setup

1. Clone this repo

bashgit clone https://github.com/<your-username>/nivasa-realty.git
cd nivasa-realty

2. Create your Vapi assistant


Go to dashboard.vapi.ai and log in.
Create (or open) your assistant — configure the transcriber, model, voice, and system prompt (see Assistant → System Prompt in the dashboard).
Copy the Assistant ID from the top of the assistant page.
Go to your profile icon → Vapi API Keys → copy your Public API Key (safe to expose client-side).


3. Add your keys

Open index.html, find this block near the bottom of the file, and fill in your values:

javascriptconst VAPI_PUBLIC_KEY = "YOUR_VAPI_PUBLIC_KEY";
const VAPI_ASSISTANT_ID = "YOUR_VAPI_ASSISTANT_ID";

4. Open it

Just open index.html in a browser, or serve it with any static host (GitHub Pages, Netlify, Vercel, Hostinger, etc.). No build tools, no dependencies to install.


Customizing


Branding — update the agency name, tagline, and contact details in the <header> and <footer> sections.
Listings — each property is a .prop-card block in the #properties section; duplicate and edit as needed.
Colors — all colors are CSS variables at the top of the <style> block (--ink, --paper, --brass, --stamp, --blueprint).
Assistant behavior — the actual conversation logic (what Meera says and asks) lives in the Vapi dashboard under your assistant's System Prompt, not in this codebase.



Notes


Microphone permission is required for the voice call to work — most browsers will prompt the visitor automatically.
The Vapi public key is safe to expose in client-side code; it cannot be used to access your account or private data.
This is a demo/marketing front end. Lead data collected during calls is handled by your Vapi assistant configuration (e.g. forwarded to a webhook, n8n workflow, or Google Sheet) — it is not stored by this webpage itself.



License

Free to use and modify for your own agency or client projects.
