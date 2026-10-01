# Rolo

**Rolo** (short for Rolodex) is an AI-powered personal relationship manager. Tell it about the people in your life out loud, and it turns what you say into contact profiles, notices when a relationship starts to drift, and suggests specific ways to reconnect: a text to send, a call to make, a hangout to plan.

Built by Alexander Baig and Gabriel Elezaj. This repository is a fork of [AlexanderB123-ai/ROLO](https://github.com/AlexanderB123-ai/ROLO), where the project was developed.

## What it does

- **Voice to profile.** Tap the mic and talk about someone, or several people at once. The browser transcribes your speech and Claude extracts a structured profile for each person: how you met, interests, work, birthday, open threads to follow up on, and how close you are.
- **Contacts by closeness.** The Contacts view groups people into rings by importance, fades out the ones you have not spoken to in a while, and shows who is drifting and whose birthday is coming up.
- **Drift detection.** Each relationship is graded by days since your last interaction: good up to 30 days, then mild, warning past 60 and critical past 90.
- **Suggestions.** A list of the people worth reaching out to now. For each person, Rolo proposes three tailored ideas (a quick text, a call, an in-person hangout), each with a draft message and the reasoning behind it.
- **Calendar.** A month view of your interactions, with an interaction streak and the month's birthdays.
- **Ask Rolo.** A chat for questions about your network and your social plans.

Rolo starts with 50 sample contacts so there is something to explore straight away. Everything is stored in your browser's local storage. There is no backend, and the sign-in screen is a demo: any credentials work.

## Tech

React 19, Vite, Tailwind CSS 4, Framer Motion, the Web Speech API, and the Anthropic Messages API (called directly from the browser).

## Run it locally

```bash
npm install
cp .env.example .env    # then set VITE_ANTHROPIC_API_KEY in .env
npm run dev
```

Voice input needs a browser that supports the Web Speech API, such as Chrome, Edge or Safari.

Without an API key the app still runs: voice capture and outreach suggestions fall back to built-in sample responses, and Ask Rolo shows an error instead of an answer.

Other scripts:

```bash
npm run build      # production build in dist/
npm run preview    # serve the production build
npm run lint
```

## Notes

- Rolo is a prototype. The API key is bundled into the browser build, so use a restricted or throwaway key, and do not deploy a build that contains a key you care about.
- The site is built for GitHub Pages under the `/ROLO/` base path (see `vite.config.js` and `.github/workflows/deploy.yml`). The original deployment is at https://alexanderb123-ai.github.io/ROLO/.
