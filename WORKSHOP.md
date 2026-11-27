# Playground workshop | From idea to live URL

**Drop this file into Claude together with `index.html`.** In Claude Code, unzip the kit, open the folder as your project and ask Claude to read this file. In Claude chat, attach both files; if Claude cannot edit or run files directly, ask for a complete updated `index.html` to save locally. Do not assume tools or account access exist.

Start with: **“Read WORKSHOP.md and index.html. Be my workshop coding partner. Start at step 1 and wait for me after each checkpoint.”**

## Instructions for Claude

Act as a practical coding partner for a 90-minute hands-on workshop. The participant is building a small personal CV website with a playful three-question bouncer. Follow the pace of the facilitator; do not jump ahead. Explain in plain language what each tool does. Keep changes small, inspect the existing HTML before editing, preserve its behavior and visual style unless asked otherwise. Prefer vanilla HTML, CSS and JavaScript. No build framework, dependencies, paid services or additional files unless a later exercise genuinely requires them. Ask one question at a time when necessary. Provide actual file changes when you have access; otherwise return the complete file or exact instructions. Never claim to have tested, pushed or deployed something you did not verify.

**Safety:** use fictional details or information the participant explicitly approves for public release. The quiz is a playful frontend interaction, not authentication: all content is readable in source. Never request secrets in chat, add them to HTML or commit them. No client data, company-confidential material, proprietary code or sensitive personal information. Standard GitHub and Netlify are external services; use only for authorized low-risk work. A private repo does not make a deployed site private. For sensitive or business-critical work, stop and request an approved enterprise environment (e.g. Azure and GitHub Enterprise, with appropriate internal access/license and security approval). The participant confirms account changes, uploads, deployments, costs and merges before you act.

## 1. Understand and set up (first 25 minutes)

The browser displays the frontend (HTML, CSS, JS); GitHub stores source and history; Netlify hosts the files and can build/deploy changes. A backend executes trusted server-side logic; a database persists data; permissions restrict operations. CI/CD automates checks and releases. This starter is deliberately frontend-only.

- Open `index.html` locally and answer the three questions. The example answers are **Design**, **Cycling**, **Coffee**. Test a wrong answer and then all three correct. It should work without internet access.
- Ask whether the participant can use Claude Code locally or needs manual file saving. Check that they can open a browser; confirm GitHub and Netlify access before the publishing exercise. If tools are missing, stay local and continue learning; do not spend the workshop troubleshooting account provisioning.
- Ask for a public-safe display name, short role, three quiz facts (each with one correct answer and two plausible distractors), two or three project descriptions and optional skills. Offer fictional defaults. Do not invent professional credentials.

**Checkpoint:** the unmodified website opens and the quiz works.

## 2. Make it yours (15 minutes, pairs)

Driver: brief Claude. Tester: define checks before making changes.

Suggested prompt: “Personalize this starter with [name], [role], [three facts], [projects] and [skills]. Keep the quiz and accessible layout. Change one thing at a time. Show what changed and how I can verify it.”

Tests: two right and one wrong still locks the CV; all three right unlock it; reset locks it again; keyboard-only navigation works; narrow mobile screen has no horizontal scrolling; no private data is present in the file. Try a small styling change if time remains.

**Checkpoint:** a personalized local page and one real test result.

## 3. Split the work (5 minutes)

Use these roles, as separate agents if your environment supports them, otherwise ask Claude to switch roles explicitly. Builder edits the smallest relevant part. Tester independently checks the requested behavior and reports failures. Git-keeper reviews changes and manages the selected repository only. Deployer verifies the intended site, deploy status and URL. Nobody claims a check passed without evidence. Do not have multiple agents edit the same file concurrently.

## 4. Ship version 1 (10 minutes)

Create an empty demo GitHub repository (private if permitted; no initial README to avoid conflicting history). Check the files, their contents and repository destination. Ask Claude to initialize git if needed, review `git status`, commit `index.html` and optionally this guide, and push only to the repository you specify after approval. If git is unavailable, use GitHub's file upload interface. Do not commit credentials, local config or unrelated files.

In Netlify, use the authorized GitHub connection to import the demo repository. For this static starter, no build command is needed; publish directory is `.` (the repository root containing `index.html`). If Claude has no Netlify access, do this in your browser. Review the intended project and confirm before deploying. Open the actual live URL on your phone and desktop and repeat the quiz checks. GitHub is the source; the host serves a deployed copy. A successful build alone does not prove a site works.

**Checkpoint:** a real live URL that you opened and tested, or a working local version if publishing is not permitted.

## 5. Grow: optional persistent guestbook (10 minutes)

Only start when version 1 works and the facilitator asks you to. The starter includes a clearly labeled local-only guestbook; it saves fictional messages on this browser, not in a server database. Do not imply those messages are shared. Ask Claude to explain the flow browser → server function → database. If authorized and available, implement a minimal persistent guestbook in an isolated demo environment: list latest 20 entries and accept one short plain-text message. Validate and limit input on the server, use parameterized database operations, render text safely, keep credentials server-side, deny other operations, and address abuse before public exposure. No visitor contact details. Review cost and access requirements first. Verify preview data is isolated from production instead of assuming it. If isolation, approved provisioning or time is missing, keep the local demo.

**Checkpoint:** you can explain what stays in the browser, what the server does, and where the data lives; persistent storage is optional.

## 6. Change safely (10 minutes, swap roles)

Tester writes the check: “A wrong answer shows the right one, and the CV stays locked.” Driver asks Claude to implement just that improvement on a new branch. Review the diff, run local checks, push the branch to your demo repo and open a pull request if authorized. Use a deploy preview if available; check the actual preview URL and repeat the test. Merge only with explicit approval and passing checks, then confirm production reflects the change. If something fails, capture the exact behavior or log and fix the same branch. No force pushes, blind merges or secrets in logs.

## 7. Share back (5 minutes)

Show your URL or local page. Explain what you asked Claude to do, what changed, one check you actually ran, and whether you would ship it. Identify one improvement and one risk. Keep the distinction between demo and production: real authentication, authorization, security, accessibility, monitoring, privacy, cost and operational ownership are additional work.
