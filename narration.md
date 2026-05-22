# Cursor: The Agentic Way - Per-Slide Narration

A 10-slide YouTube script, paced beginner -> advanced.

Each slide has three beats so you can edit cleanly:

- **On-screen (5 sec)** - the hook said while the slide appears.
- **Main beat (60-90 sec)** - the actual teaching.
- **Transition (5-10 sec)** - bridge to the next slide.

Total runtime: ~14-15 minutes. Trim "On-screen" lines if you want a tighter ~10 min cut.

---

## Slide 1 - Cursor: The Agentic Way (Title)

**On-screen (5 sec):**
> "Welcome. In the next 10 slides we're going from your first Tab keystroke in Cursor to running background agents in the cloud."

**Main beat (60 sec):**
> "Cursor is the most-talked-about AI code editor of the last two years - and most tutorials only cover the surface. They show you Chat, maybe Agent mode, and call it a day. They miss the killer features: Tab autocomplete, Cmd-K inline edit, the @ symbol for context, custom rules, MCP servers, background agents. Today we fix that. The deck is structured beginner to advanced. Slides 2 and 3 are day-one stuff. Slides 4 through 6 are intermediate. Slides 7, 8, 9 are where power users live. And slide 10 is a single cheat sheet you can screenshot and keep open. Let's go."

**Transition (5 sec):**
> "First: what even is Cursor?"

---

## Slide 2 - What is Cursor?

**On-screen (5 sec):**
> "Short version: Cursor is VS Code with AI as a first-class citizen, not a plug-in."

**Main beat (75 sec):**
> "It's a fork of VS Code by a company called Anysphere. Same keybindings, same extensions, same themes - your dot-vscode config just works. The import wizard on first launch pulls everything over in about 30 seconds. The two things that make it different from a Copilot plug-in. One: Cursor indexes your entire repository so the AI actually sees the codebase, not just the file you're staring at. Two: you can swap models per message - Claude Sonnet for daily work, Claude Opus for hard refactors, GPT-4o for speed, Gemini for huge contexts. Privacy Mode is one toggle in settings and means your code never leaves your machine for training. Free Hobby tier is generous - perfect to try. Pro is twenty dollars a month and unlocks the frontier models with unlimited fast requests. Business is forty per seat with SSO and admin controls."

**Transition (8 sec):**
> "Install in 60 seconds. Now let's look at how you actually use it."

---

## Slide 3 - The 4 Ways to Talk to Cursor (the most important slide)

**On-screen (5 sec):**
> "This is the slide most tutorials skip. Cursor has four interaction modes, in order of how much work you delegate."

**Main beat (90 sec):**
> "Mode one: Tab autocomplete. Just press Tab. Cursor predicts your next edit - one line, multiple lines, even across files. The killer detail: it doesn't just complete the cursor position, it suggests cursor jumps. You start typing in one file, Tab proposes a related change in another file. This alone is worth the subscription. Mode two: Ctrl-K, inline edit. Select some code, press Ctrl-K, describe the change in plain English, get a diff right there. Best for renames, refactors, format conversions - anything where you know exactly the chunk that needs to change. Mode three: Ctrl-L, Chat. A sidebar conversation. Ask questions, get explanations, optionally apply edits. Best for understanding code and quick how-do-I queries. Mode four: Ctrl-I, Agent. The autonomous one. You give a goal, it reads files, edits them, runs tests, loops until done. The rule: start at the smallest level that works. Use Tab for a line, Cmd-K for a block, Chat for a question, Agent for a feature. Beginners jump to Agent for everything - and pay for it in speed and money."

**Transition (8 sec):**
> "All four get smarter with one tiny character: the @ symbol."

---

## Slide 4 - The @ Symbol

**On-screen (5 sec):**
> "If you remember nothing else from this video, remember: every prompt should start with an @-reference."

**Main beat (90 sec):**
> "The AI is only as smart as the context you give it. Without an @-reference, Cursor guesses from your currently open files. With one, it knows exactly what you mean. Eight reference types matter. @file - a single file by path. @folder - a whole directory. @code - a specific function or class. @docs - lets you reference indexed library documentation: React, Next.js, Stripe, hundreds of libraries; no more pasting docs into chat. @web - a live web search; great for fresh API changes or library updates. @git - reference a diff or a commit; killer for code review. @codebase - retrieval across your entire repo using embeddings; this is what makes "find every place we call the old payments API" actually work. And @past-chat - reference an earlier conversation, so you don't have to re-explain context. The example at the bottom shows a real prompt: it references two specific files and the relevant library docs. Quality jumps the moment you start using @-references on every prompt. Make it a habit."

**Transition (8 sec):**
> "Okay - we know the modes and we know how to feed context. Time to unleash Agent mode."

---

## Slide 5 - Agent Mode in Depth

**On-screen (5 sec):**
> "Agent mode is the autonomous one. Open it with Ctrl-I. Here's what's happening under the hood."

**Main beat (90 sec):**
> "It's a loop: pick a tool, run it, read the output, pick the next tool. Four tools. Read - opens any file and quotes back exact lines, so it's always working from real code. Edit - produces a structured diff for every change; you accept or reject per chunk, not per file. Search - regex and glob across the whole repo. Shell - runs npm test, git, installs, anything. Two safety nets you should know. First: every edit is shown as a diff before it's applied; nothing happens silently. Second: every agent run creates a checkpoint - if it went sideways, you rewind to before it started in one click. There's an auto-run toggle in settings that whitelists 'safe' shell commands - things like npm test, ls, git status - so the loop doesn't pause on every command. Turn it on once you trust the model. The example prompt at the bottom is a real production-quality one: notice the @-reference, the specific behaviour spec, and the explicit 'add a test' at the end. That structure - context plus spec plus tests - is what separates a useful agent run from a useless one."

**Transition (8 sec):**
> "But sometimes you shouldn't let the agent edit yet. That's what Plan mode is for."

---

## Slide 6 - Plan Mode

**On-screen (5 sec):**
> "Plan mode is Agent mode with no edit permission - and that's exactly the point."

**Main beat (80 sec):**
> "Three modes in the chat panel: Ask (read-only chat), Plan (read + plan, no edit), and Agent (full edit). In Plan mode, the agent can read your code but can't change anything. It explores, asks you clarifying questions, then produces a written plan: which files it'll touch, what tests it'll add, what trade-offs it sees. You review the plan. If you like it, you confirm and Cursor flips itself into Agent mode and executes. If you don't, you edit the plan and re-run. The rule I follow: any change that touches more than two files - Plan first. Anything in auth, payments, billing, migrations, security - Plan first. Anything where you'd otherwise ask three clarifying questions - Plan first. Ten minutes of planning saves an hour of damage control. The first time you skip planning on a big refactor and watch the agent half-implement the wrong thing, you'll understand why this slide exists."

**Transition (8 sec):**
> "Modes and shortcuts get you 80% of the way. Now the power-user 20% - starting with rules."

---

## Slide 7 - Rules and AGENTS.md

**On-screen (5 sec):**
> "When you work on a real project, you'll get tired of writing the same instructions every prompt. Rules fix that."

**Main beat (85 sec):**
> "Drop a markdown file inside dot-cursor-slash-rules and Cursor reads it on every agent run. The .mdc extension is special - it lets you add YAML frontmatter. Two useful keys: 'globs' scopes the rule to certain file patterns - so your React rules only fire on TSX files. And 'description' lets the agent decide whether the rule applies. AGENTS.md is the newer cross-tool standard - it lives at the repo root, no dot-folder, and works in Cursor, Claude Code, Cody, and others. Use AGENTS.md for high-level project context that's not tool-specific. Use dot-cursor-slash-rules for Cursor-specific behaviour. SKILL.md is a third, recent addition - reusable multi-step workflows that the agent picks up automatically when the task description matches. The rule example at the bottom is the kind of thing every real project needs: package manager preference, test layout, doc requirements, secret-handling. Five lines of rules saves you thousands of repeated instructions."

**Transition (8 sec):**
> "Rules tell the agent how to behave. The next slide expands what the agent can do."

---

## Slide 8 - MCP, Hooks, Background Agents

**On-screen (5 sec):**
> "Three features that turn Cursor from a code editor into an actual agent platform."

**Main beat (90 sec):**
> "MCP - the Model Context Protocol - is an open spec originally from Anthropic that any AI tool can implement. Every MCP server exposes tools the agent can call. Jira-MCP lets the agent read and update tickets. Postgres-MCP lets it query your database. GitHub-MCP gives it full PR management. There are hundreds of MCP servers already published, and writing your own is about 50 lines of code. Hooks - a hooks.json file in dot-cursor - let you run shell scripts when certain agent events fire. Auto-format every accepted edit. Auto-run tests after every diff. Audit-log every change to a file. Background Agents are the showstopper: kick off a long task, it runs in the cloud on its own branch in a clean sandbox, and you get a PR when it's done. You can fire off 'refactor the test suite' before lunch and review the PR after. The power combo at the bottom - MCP-Jira picks up tickets, Background Agent implements, a Hook posts the PR link back to Jira - that's zero-context-switching engineering. That's the agentic way."

**Transition (8 sec):**
> "All the power in the world doesn't matter if the output is buggy. So let's talk discipline."

---

## Slide 9 - TDD with Agents

**On-screen (5 sec):**
> "The single biggest quality multiplier when working with agents: test-driven development."

**Main beat (85 sec):**
> "The cycle is Red, Green, Refactor. RED - you ask the agent to write failing tests first. This is the step everyone skips and it's the magic one. Those tests become a precise specification the AI has to satisfy. No more 'looks right but doesn't actually work.' GREEN - the agent writes the minimum code to make the tests pass. Because the tests exist, you instantly know when it's done - no guessing, no debating. REFACTOR - the agent cleans up the code, with the tests as a safety net. Any refactor that breaks behaviour turns a test red and you catch it immediately. The three prompts at the bottom are the real prompts I use - one at a time, not one big mega-prompt. Iterative prompts give the agent shorter feedback loops and dramatically better output. The mental model: tests are how you turn 'trust the AI' into 'trust the tests.' That is a much better deal."

**Transition (8 sec):**
> "Last slide. The single page that summarises everything."

---

## Slide 10 - The Cheat Sheet

**On-screen (5 sec):**
> "Pause the video. Screenshot this slide. This is the only one you need to remember."

**Main beat (75 sec):**
> "Left side - the shortcuts. Tab to accept autocomplete - your most-used key. Ctrl-K for inline edit. Ctrl-L for Chat. Ctrl-I for Agent. Ctrl-Shift-L to add the selected text to the chat. And all the @-references: @file, @codebase, @docs, @web, @git. Right side - the decision tree. Need code changed? No - use Chat. Yes - is the task big or unclear? Yes - start in Plan mode to scope it. No - jump straight to Agent. At the bottom, model selection: grunt work goes to Haiku or 4o-mini; daily driver is Sonnet or 4o; when it matters - billing, auth, security, final verification - use Opus or o-series. And three rules to remember if you forget everything else. One: tests first. Two: plan before big changes. Three: match the model to the stakes. That is the agentic way."

**Transition / outro (10 sec):**
> "Thanks for watching. Links to the rules templates, AGENTS.md examples, and the slide deck source are all in the description. Like and subscribe for more Cursor deep-dives. Happy shipping!"

---

## Total Estimated Runtime

| Slide | On-screen | Main | Transition | Subtotal |
|------:|----------:|-----:|-----------:|---------:|
| 1     | 5s        | 60s  | 5s         | 70s      |
| 2     | 5s        | 75s  | 8s         | 88s      |
| 3     | 5s        | 90s  | 8s         | 103s     |
| 4     | 5s        | 90s  | 8s         | 103s     |
| 5     | 5s        | 90s  | 8s         | 103s     |
| 6     | 5s        | 80s  | 8s         | 93s      |
| 7     | 5s        | 85s  | 8s         | 98s      |
| 8     | 5s        | 90s  | 8s         | 103s     |
| 9     | 5s        | 85s  | 8s         | 98s      |
| 10    | 5s        | 75s  | 10s        | 90s      |
|       |           |      | **Total**  | **~16 min** |

Tip: trim the "On-screen" intros if you want a sub-12-minute cut. YouTube retention peaks at 8-12 min.
