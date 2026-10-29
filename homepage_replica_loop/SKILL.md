# Personal homepage replica and iteration loop

## When to use

- The user wants a personal homepage that looks like a reference site, or wants to iterate on an existing single file homepage from phone feedback such as text, screenshots or screen recordings.

- Use this skill when the deliverable is one self contained HTML file with inline CSS and JavaScript and no build step.

## Replication boundary

- Replicate layout, structure, visual style, motion and effects from the reference.

- Never copy the reference text, branding, personal names, images or code. Rewrite every word in the user's own voice and rebuild every effect from scratch.

- Keep the user's identity facts at the level they already publish. Never add a school name, legal name or contact detail the user did not approve for that page.

## Study the reference first

- Open the reference in the browser and record its visual system before writing code: background and panel colors, text colors, accent color, border treatment, corner radius, type scale, label style, container width, section spacing, header behavior and footer treatment.

- Treat screenshot estimates as estimates. Never claim pixel exact measurements from a screenshot.

- Ask the user whether to change the current homepage or build a new site when that choice is unclear, and confirm before replacing a live page.

## Build in one file

- Keep everything in one HTML file: markup, style and script inline, system font stacks, no external assets, so the file runs anywhere on its own.

- Build the page in sections that match the reference structure, then layer motion: scroll progress, hero canvas, morph states, tickers, typewriter, magnetic buttons, click bursts, count up stats, back to top, and a hidden mascot terminal when the user asks for one.

- Respect reduced motion. Pause ambient animation, freeze time driven states and keep the page fully readable when the user prefers reduced motion.

- Keep interactive controls wired to live variables, never to a second copy of the drawing code, so sliders and toggles change the visible canvas immediately.

## Check before you deploy

- Extract the inline script and run `node --check` on it. Fix syntax errors before deploying anything.

- Confirm every new element id appears exactly once and every removed section leaves no dangling reference in scripts, palettes or navigation.

- Never deploy a page that references a section, anchor or element id that no longer exists.

## Deploy both copies and verify live

- Deploy the Pages copy and the GitHub Pages copy together on every change. Never leave the two copies out of sync.

- Deploy Pages with the project's direct upload script and deploy GitHub Pages with a file push to the site repo main branch. Wait for the GitHub Pages rebuild lag before verifying that copy.

- When uploading Pages assets directly, hash each file with SHA-256 truncated to 32 hex characters. A full 64 character hash deploys cleanly but serves errors on every page.

- Verify live with a fetch of each public URL and grep for the markers of the change. Report the change only after both copies show the markers.

- Give the user a fresh cache buster link on every delivery, because a phone browser cache or back forward cache can show a stale page and fake a missing feature.

## Iterate from phone feedback

- Treat a phone video or screenshot as the primary evidence. Diagnose the exact cause before editing, and name it in the reply.

- Common causes are a full screen overlay layer softening the canvas, a scroll fade dimming the hero, a canvas stretched to a panel size that distorts its aspect ratio, and desktop padding that eats a narrow screen.

- Fix aspect ratio by sizing the canvas backing store to its displayed size or by letting the browser scale it proportionally. Never stretch a fixed coordinate drawing into a panel of a different aspect ratio.

- Keep mobile side padding small so the layout fills a narrow screen, and keep desktop proportions untouched.

- After a fix, deploy both copies, verify the markers live, and send a new cache buster link. Ask the user to check the specific thing they complained about.

## Available connectors

- None. This skill uses the browser for visual study, the shell for syntax checks and deploys, and the GitHub connector for the site repo push.
