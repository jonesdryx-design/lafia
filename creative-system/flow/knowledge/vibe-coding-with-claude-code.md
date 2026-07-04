# Vibe Coding with Claude Code — Day 4 Workshop (Building Apps)
**Source:** AI Creative Strategist / Genesis workshop, Day 4 · Max Bernstein (host/build), Mario Castelli (co-host) · **Added:** 2026-07-04

---

## THE CORE IDEA

Building/execution is becoming a commodity — anyone can generate an app now (Lovable, Bolt, Base44, Codex Apps, Claude Code). The competitive edge has moved to:

1. **Ideas** — what to build and why anyone would pay
2. **How you build** — what personal/client IP you embed
3. **Quality of output, consistently** — not the architecture flex (the "127-step N8N workflow" problem: people show off the pipeline, never the output across 10 runs). Consistent quality output is what almost nobody shows.

**If a 10-year-old could generate the same app in a prompt, what's your competitive advantage?** → knowing what to build, and why anyone would pay.

**Skill transfers.** Time spent learning to talk to AI (any tool — Poe, ChatGPT, whatever) is not wasted when you switch tools. "If you learn how AI works, you can transfer it from one thing to another. Principles carry over." — Mario, on going from Poe to Claude Code and building full video pipelines within a day or two.

---

## THE 3 PILLARS OF PRODUCT VALUE

1. **Validated idea** — not just a good idea, but researched/evidence-backed (Reddit threads, Discord servers, scraped reviews). AI research tools let you validate far further before you spend time building.
2. **Great design** — becoming table stakes. Loading states so nothing feels frozen, hover descriptions, progress/momentum cues, "magic moments," mobile-first (right-click → Inspect before shipping, always).
3. **AI architecture / prompting** — the internal engineering that makes output good *every single time*, not just once for a demo.

### The Idea-Finding Frameworks (from the "Atomic Insight Engine" skill mentioned)
- **Jobs to be Done** — what job is this app actually doing for the user
- **The Mom Test** (Rob Fitzpatrick) — don't ask "is this a good idea," find real customer language about whether they'd actually pay
- **Positioning** (April Dunford's *Obviously Awesome*) — a solid, simple positioning framework
- **4 starting paths** the ideation skill walks you through:
  - **Explorer** — "I know I want to build, but not what" → asks you questions
  - **Sniper** — "I know who, not what" → you have a client/customer in mind, ideation from there
  - **Client** — "I have clients currently, building something for them"
  - **Scratcher** — "I'm solving my own itch" (where most of Max's own ideas come from)

---

## THE 7 BEATS (workflow shape)
Frame → Shape → Plan → Build core → Make real → Verify → Ship. Becomes intuitive with reps; not a rigid checklist.

---

## THE BUILD LOOP (what actually happens, step by step)

This is the repeatable pattern used for every app in the session (a Facebook-ads warm-up dashboard, then the full Client Showcase app):

1. **Create a folder** — "Please create a folder on my desktop and call it [X]. This is where we will work for this session." Location doesn't matter much for learning; separate folders per app/client is the general rule (see Repo Hygiene below).
2. **Give it the build prompt.** Either:
   - A **ready-built prompt** copied straight from the course prompt library, or
   - Run the **meta-prompt** first ("turn your idea into a ready-build prompt") to generate a custom one from your own idea.
3. **Attach source data** if the app needs it (e.g. an Excel export) — literally drag the file in and say "use this for the test data, keep building the app."
4. **Approve the plan** it proposes before it writes code (most flows pause and ask).
5. **Iterate visually** — click through the running local app, use the annotation/element-select tool to point at something and say "make these purple," or just describe changes in plain English.
6. **Add a one-click launcher** — "Can you add a launcher inside the folder so I can launch this on a single click?" (creates a double-clickable file, e.g. a `.command` on Mac, that starts the local server and opens the browser for you).
7. **Troubleshoot by showing, not explaining** — screenshot the error/terminal output, drag it into chat, describe exactly what you did and what happened ("I double-clicked the launcher and nothing opened in my browser"). You don't need to understand the fix — brute-force iteration is the actual skill.
8. **Polish with a design skill** — "Can you run Impeccable to make this look nicer and more premium?" (see Tool Stack).
9. **Manage context with a handoff** — once a session gets large (session shown at 34% of window / 300K+ tokens), say **"handoff."** It writes a handoff file summarizing state so a fresh session can pick up cleanly (works from any folder — it'll find the file).
10. **Deploy when ready** — "don't deploy until it hurts." Stay local as long as possible; deploying (Vercel) repeatedly eats your free tier fast, and there's no reason to pay that cost until you're ready to share with a client/the world.

### Talking-to-AI ground rules (repeated all session)
- **Spelling doesn't matter.** Don't waste time auto-correcting typos before sending.
- **If it looks frozen** (tokens/counter not moving for a long stretch), hit stop and say "you froze, keep going."
- **If it can't find a folder/file**, just say "create the folder again" / restate the obvious — it's not precious, just tell it what to do.
- **Default answer to its clarifying questions**: "just say yes" unless you have a real opinion — you can always change it later, since you own 100% of the code.
- **You can always go backwards.** Nothing is permanent; if a direction is wrong, just tell it to change it.

---

## TROUBLESHOOTING / QUALITY-CONTROL PATTERNS

- **Screenshot + describe > explain.** "A lot of this stuff is... taking the screenshots and giving it to Claude and say fix this for me." (credited to Luke's earlier workshop)
- **Cross-model QA.** Run Claude Code and Codex against the *same local files* at the same time. Ask one model for a QA/audit prompt, paste the output into the other:
  > "Can you give me a prompt to run quality control or a QA audit inside of Codex? I will copy and paste the prompt inside of Codex — make sure it has all the path names it needs for this project to do it."
  Then paste Codex's findings back into Claude Code. "AI judging other AI" — very useful because both work off your local files, so they stay in sync without extra setup.
- **Clone/match a reference design.** Take a screenshot of the site/design you're chasing, tell Claude/Codex: "This is the original we are working towards — make design changes so it gets closer to this."
- **Design taste = a swipe file.** Browse `land-book.com`, `mobbin.com` (M-O-B-B-I-N), 21st.dev for components — screenshot anything you like into an "inspiration" folder before you start building, same as an old-school copy swipe file. "Steal like an artist."

---

## KEY PROMPTS (near-verbatim, reusable)

**Start a new build:**
> "Please create a folder on my desktop and call it [Project Name]. This is where we will work for this session."

**Install a design polish skill from a GitHub link (or any tool site):**
> "Install these skills globally and run this to make it look nicer and more premium: [github link]"

**Add a one-click launcher:**
> "Can you add a launcher inside the folder so I can launch this on a single click?"

**Extract a brand/design system from any live site (the "design.md" pattern):**
> "Can you create a design.md from this site?"
`design.md` = a brand-style file (fonts, colors, spacing, tone) readable by AI, same concept as `CLAUDE.md` but for design. Originated with Claude, then Gemini adopted the same convention so any LLM can read it. Once you have one, hand it to any tool (Claude, Codex) to build something visually consistent with an existing brand/site.

**Before installing any new tool/API/model — read the docs first (avoids errors down the line):**
> "I am thinking of installing [tool]. Before we do, can you please read all the documentation?"
> or: "Go pull all the documentation for [X] using the Exa MCP / Context7, so we can learn about it and save it so we know how to use it and install it properly."

**Prompt to build a "new model just dropped" onboarding skill:**
> "Can you help me create a prompt so that when a new model comes out, any user can give it to their Claude Code setup along with the model documentation, and it will tell them how to best use that model, the pros and cons of their current setup, and anything else a normal person may have missed from the model release?"

**Add a real UI component from a component library (21st.dev pattern):**
> Grab the `npx`/component install command from the library, give it to Claude: "Yes please install this component wherever you think fits best... and make sure it fits our current style, design, etc."

---

## TOOL STACK (what each piece is for)

| Tool | Role | Notes |
|---|---|---|
| **Claude Code** (terminal or desktop app) | The build agent | Terminal is faster and has fewer restrictions than the desktop app ("almost like it pulled over some co-work safety boxes"); desktop app is friendlier for beginners. Same underlying tool either way — `claude` in any terminal opens the identical experience. |
| **Convex** (convex.dev) | Backend database | Free tier is generous; auth is one CLI command, no juggling anon/public/private keys (unlike early Supabase). Local-first while building, flip to cloud deployment when you're ready to go live with Vercel. |
| **GitHub** | Version control / backup / distribution | "Nerdy Google Drive." Set one up on Day 1. One repo per project (don't dump everything in one, or you're handing people everything). Public = anyone can see it; private = link-only. Rollback = undo bad changes without losing history. |
| **Vercel** (or Netlify) | Deploy / hosting | **Not a database.** Hosts your live site/app. Repeated deploys eat your free-tier allotment fast (~100 deploys/month on some plans) — don't deploy until you actually need to share. |
| **21st.dev/community/components** | UI component swipe file | Browse by category (video players, galleries, hover cards, etc.), copy the install command, hand it to Claude with "make sure it fits our current style." |
| **Impeccable** (`impeccable.style`, `github.com/pbakaus/impeccable`) | Design "finishing polish" skill/plugin/CLI | The reliable install path when `/plugin` fails (it failed for many people live): literally paste the GitHub URL or the site URL into Claude Code and say "install this skill" / "install the skills from this GitHub." Install **globally** if you'll reuse it across projects. Scans for common "AI-generated look" patterns (fonts, layout defaults) and pushes toward a more premium/considered result — header hierarchy, real hero sections, spacing, etc. |
| **awesome-design-md** (`github.com/VoltAgent/awesome-design-md`) | Design vocabulary / design.md generator | "Missing vocabulary" problem — teaches the AI hierarchy, contrast, restraint so AI front-ends stop looking identical. Referenced as the "Awesome design" skill. |
| **Hallmark** (`github.com/nutlope/hallmark`) | Alternative design-polish skill | Mentioned in chat as a comparable option to Impeccable — untested by the group but worth trying. |
| **Exa** (`exa.ai`) / **Context7** | Documentation/research MCP connectors | Use before installing any new, data-heavy, or infrastructure-y tool: "go pull the documentation for X so we know how to use and install it properly." Context7 specifically indexes up-to-date code docs. Add via Claude.ai → Customize → Connectors → Browse connectors. |
| **Clerk** | Auth-as-a-service | Cited repeatedly as very agent-friendly — easy to wire up with Claude Code for login/signup (incl. social sign-in), free tier to start. |
| **Codex (OpenAI)** | Second build/QA agent | Reads/writes the same local files as Claude Code — no sync issues running both on one project. Workshop pattern: plan architecture in Codex, hand design work to Claude, cross-QA between the two. Anecdotally more generous with tokens per dollar than Claude Code; a common combo is a $20 Claude plan + $20 ChatGPT plan, leaning on Codex for heavier build lifting. |
| **DIA browser** | Alt to Chrome | Nice built-in sidebar/AI features, imports Chrome extensions, has its own skills; heavier on memory. |
| **NotebookLM** | Research digestion | Good for quickly turning a pile of source material (e.g. a video transcript) into a mind map. |
| **GoFullPage** (Chrome extension) | Full-page screenshots | Used to capture an entire long page (e.g. a long-form sales letter) in one image for design-cloning workflows. |

### On the "new model just dropped" situation (Fable 5 / Mythos, as of this workshop)
- Claude Fable 5 = the public GA release that sits above Opus (Mythos-class); launched the day of this call.
- Roughly **2x the price of Opus** — expensive to run casually.
- **Retains data longer / breaks "zero data retention"** — avoid for anything privacy-sensitive.
- Not yet available as a selectable Claude Code model in the desktop app at time of workshop — chat-only.
- Rolls back to Opus behavior if pushed toward disallowed territory.
- **Takeaway pattern, not model-specific:** whenever a new model drops, don't guess — feed Claude Code the model's actual release documentation (via Exa/Context7 or a direct doc link) and ask it to summarize the pros/cons and how to adapt your current setup, rather than relying on secondhand takes.
- General model guidance from the hosts (subject to going stale fast): Opus 4.8 was a bigger jump than 4.7 for building; Sonnet 4.5 preferred for copywriting (less "overthinking"); Sonnet 4.6 handled repetitive "copy this, paste that" setup tasks well.

---

## REPO / FILE HYGIENE

- Create a new GitHub repo per project — don't reuse one repo across unrelated builds, or you leak everything to whoever gets the link.
- Public vs private is purely about whether you want the world to see it.
- Add a `.gitignore` for large media (video/image-heavy folders) so GitHub doesn't choke — fine for a handful of images, not for a media library.
- Working folder can live wherever — inside an existing workspace or standalone; don't get hung up on this while learning.
- For images/assets: easiest path is literally drop them in a folder and say "use the images from here" with the path name, rather than uploading one at a time.

---

## OPERATING MODEL (how the hosts actually work day to day)

- **Delegate and walk away.** Kick off a build, then live your life / go in the pool / go to sleep — check back later. "I'll have Claude Code doing shit while I'm not sitting around waiting for the results. I'll just go live life." (Mario)
- **Parallelize.** Multiple terminal tabs / multiple Claude Code + Codex windows running different projects at once. New idea shows up mid-build? Open a new tab, start that one too, keep both cooking.
- **Overnight is prime time.** Both hosts do their best building 11pm–5am — no Slack, no email, no interruptions.
- **Output funnels to Google Drive.** Tell Claude Code to format final outputs (docs, reports) and drop them straight into a mapped `G://` Google Drive folder — "yell at Claude Code until shit shows up in my Google Drive."
- **Build vs. buy rule:** buy it if an existing product is close enough to what you want; build it once the gap between what's available and what you actually want gets big enough. Mario's specific trigger: if you're repeatedly telling AI to fix the same recurring thing, **that becomes a tool**; if you're repeatedly frustrated with someone else's product not doing what you need, **build your own**.
- **Selling software is a different beast than building for yourself.** Personal-use tools tolerate quirks; anything you commercialize/distribute needs to be kept simple at first, because support load ("the fire hose") scales with users. Ignore YouTube hype claiming it's trivial to build-and-sell overnight.
- **Idea sourcing habit:** scroll anything (Substack, YouTube transcripts, articles), pull the transcript/text, extract an idea, and — critically — **extrapolate rather than copy the idea literally**. Any piece of content can seed a product idea this way.
- **The mentally-taxing part goes away, so total hours worked can go up without it feeling like more work** — because the AI is doing the effortful part.

---

## TWO WORKED EXAMPLES FROM THE SESSION

### 1. Facebook Ads Test Dashboard (warm-up build)
Local-only web app, no backend. Steps: create folder → paste the "warm-up / blank folder / live calculator" starter prompt → attach a Facebook-ads export (Excel) → approve plan → app runs on `localhost` → iterate visually (annotation tool, "make these purple," dark mode) → add a one-click launcher → polish with Impeccable. Purpose: prove the basic loop works before adding backend complexity.

### 2. Client Showcase App (the main build)
A branded portfolio/approval site for presenting creative work (ad concepts, videos, images) to a client instead of a Google Drive link — client can view, leave comments, and approve directly on the site. Stack: **Convex** (data + auth), **GitHub** (backup/version), **Vercel** (deploy), **21st.dev** (a hover-play video card component), **Impeccable** (final polish), a **design.md** cloned from a reference site for brand consistency. Extension idea floated: an admin panel to manage multiple client-branded showcases from one place — described as "just Component Mining again, like websites on Day 3."

---

## RESOURCE LINKS (compiled from workshop + live chat)

- Impeccable — https://impeccable.style/ · https://github.com/pbakaus/impeccable
- Convex — https://www.convex.dev/ (pricing/limits: https://www.convex.dev/pricing)
- 21st.dev components — https://21st.dev/community/components
- Awesome design.md — https://github.com/VoltAgent/awesome-design-md
- Hallmark (alt design skill) — https://github.com/nutlope/hallmark
- Exa (docs/research MCP) — https://exa.ai/
- Neon (Postgres alt, reportedly no idle-pause limit on free tier, unlike some Convex/Supabase free tiers) — https://neon.com/
- Claude Fable 5 / Mythos announcement — https://www.anthropic.com/news/claude-fable-5-mythos-5
- Course day page (prompts/downloads) — https://theaicreativestrategist.com/day-4
- Land-book (design inspiration) — land-book.com
- Mobbin (design inspiration) — mobbin.com

---

## LIVE FAQ (condensed from chat)

- **"What does `npx`/`npm` mean?"** — Signal that something is installable/pluggable. You don't need to know the internals; when you see it, hand it to Claude Code and it knows what to do with it.
- **"What does 'repo' mean?"** — A repository — your project hosted on GitHub so it can be downloaded/shared/versioned.
- **"`/plugin` doesn't work for me."** — Common live failure. Fallback that reliably worked: paste the tool's GitHub URL (or website URL) directly into Claude Code and say "install this skill" / "install the skills from this GitHub."
- **"Convex vs. Vercel — what's the difference?"** — Convex is the database ("a sophisticated Google Sheets on steroids" — stores users, leads, app data per user). Vercel is hosting/deploy — it makes your app live at a URL but is not itself a database (unless you've separately wired in something like Neon through it).
- **"Do you have to worry about Convex projects pausing on the free tier like Supabase?"** — Reportedly different/less restrictive limits than Supabase's idle-pause; check Convex's own pricing/resources page for current limits before relying on it.
- **Terminal vs. desktop app** — Terminal is quicker and has fewer built-in restrictions, but Mario's rule: "Only go in the terminal if you already know what you're doing and want to go faster... Earn the terminal." If you hit an install error in Terminal, copy the exact error back into Claude Code (desktop or web) and ask what to run — it'll hand you the exact command to paste back into Terminal.
- **"Can I use both Codex and Claude Code on the same project?"** — Yes, and it's a normal workflow for the hosts (build in one, design/QA in the other) since both read/write the same local files without conflict.
