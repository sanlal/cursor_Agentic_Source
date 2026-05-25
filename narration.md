# Cursor: The Agentic Way — Video Script

One flowing 14-minute script for the 10-slide deck. Written to be *spoken*, not read — so it sounds like a person teaching, not a manual being narrated.

---

## How to use this script

- **One slide = one block of speech.** No artificial "intro / main / outro" splits. Just talk through it; advance when the natural beat ends (look for the `▸ click` marker).
- **Read it out loud first.** If a sentence trips your tongue, change a word. Don't fight the page.
- **Pauses matter.** The `(...)` marks are full-stop pauses, ~0.5-1s. They give the viewer a moment to catch the visual.
- **Emphasis** — words in *italics* are the ones to lean into when you say them.
- **Total runtime:** ~13:45. Trims at the end if you need a sub-12 cut.

A note on voice: imagine you're sitting across from a friend who just installed Cursor and asked *"so what do I actually need to know?"*. That's the energy. No host voice. No "hey what's up YouTube". Just a smart friend who uses this thing every day.

---

## Slide 1 — Title  *(0:00 - 0:55)*

> *(Slide fades in. Don't start talking immediately — give it a beat.)*
>
> There's a thing I see senior engineers do in Cursor that beginners don't — and it has *almost nothing* to do with writing better prompts. (...) It's about knowing which of Cursor's four input modes to reach for, and when to *not* reach for the AI at all.
>
> Most tutorials you'll find online show you Chat. Some show you Agent. And that's it. (...) But that's like reviewing a Swiss Army knife by only opening the big blade. There are *seven other tools in there*, and they're the ones that turn Cursor from "a fancy autocomplete" into something that genuinely changes how you ship code.
>
> So that's what we're doing in the next fourteen minutes. We'll start on day one — like, you just installed it — and by the end you'll know how to run agents in the cloud while you're at lunch. (...) Beginner to power user, in one sitting.
>
> ▸ click

---

## Slide 2 — What is Cursor?  *(0:55 - 2:10)*

> Quick orientation, because I get asked this constantly. (...) Cursor is *not* a Copilot plug-in. It's a full code editor — a fork of VS Code, by a company called Anysphere. Which means if you've used VS Code, you already know roughly *ninety percent* of Cursor. Same keybindings, same extensions, same themes. (...) Your dot-vscode folder works. The first time you launch it, an import wizard pulls your settings across in about thirty seconds. Painless.
>
> The ten percent that's different is the part that actually matters. (...) Two things. (...) *One:* Cursor indexes your entire repository into a vector database. Not just the file you've got open — *the whole codebase*. Which means when you ask it a question, it can pull context from anywhere in the project. (...) *Two:* you choose the model per message. Claude Sonnet for daily work. Claude Opus when you're touching billing code and you can *not* afford a mistake. GPT-4o when you want it fast. Gemini when the file is enormous. You pick.
>
> Privacy mode is one toggle in settings — flip it and your code never leaves your machine for training. That single switch is why most enterprises now allow it. (...) Free tier is generous, by the way. You don't need to pay to play. Pro is twenty dollars a month, which is roughly the cost of one nice lunch, and it unlocks the frontier models.
>
> ▸ click

---

## Slide 3 — The 4 Ways to Talk to Cursor  *(2:10 - 3:45)*

> Okay. *This* is the slide. (...) If you watch nothing else in this video, watch this one.
>
> Cursor has *four* ways to give it instructions, and they're arranged from "tiny" to "huge" in how much work you delegate. (...) And the single biggest mistake new users make — honestly, the one that wastes the most credits and the most time — is jumping straight to the biggest one for *every* task.
>
> So, in order. (...) *Tab*. Just the Tab key. You start typing, Cursor predicts the next edit. One line, multiple lines, sometimes even across files — you'll be editing in one file and Tab will suggest the matching change in another. The first time it happens you'll laugh. (...) Then *Control-K*. Select a chunk of code, hit Control-K, type "make this async" or "extract this into a hook" in plain English, and you get a diff right there in the editor. (...) Then *Control-L* — the chat sidebar. For when you have a question, not an edit. "Why is this slow?" "What does this regex do?" (...) And finally *Control-I* — Agent mode. The autonomous one. You hand it a *goal*, and it goes and reads files, edits them, runs your tests, iterates until it's done.
>
> The rule that took me embarrassingly long to learn: (...) *start at the smallest tool that gets the job done*. Tab for a line. Control-K for a block. Chat for a question. Agent for a feature. (...) Beginners use Agent for "rename this variable" and then wonder why they ran out of credits in three days. Don't be that person.
>
> ▸ click

---

## Slide 4 — The @ symbol  *(3:45 - 5:15)*

> Now — *all four* of those modes get dramatically smarter the moment you start using the @ symbol.
>
> Here's the mental model. (...) The AI is only as smart as the *context* you feed it. Without an @-reference, Cursor is guessing — it looks at your currently open files and hopes for the best. With an @-reference, it *knows*. (...) And the gap between guessing and knowing? It's the entire difference between magic and mediocre.
>
> There are eight reference types and they each unlock something different. (...) `@file` for one specific file by path. `@folder` for an entire directory. `@code` to point at one function or one class — surgical. (...) `@docs` is huge. Cursor has hundreds of libraries indexed — React, Next.js, Stripe, Prisma, you name it. So instead of copy-pasting the docs into chat like a savage, you just type `@docs` and pick the library. (...) `@web` does a live web search, perfect for "what changed in this library last week". `@git` references a diff or a commit — *unbelievable* for code review. (...) `@codebase` does retrieval across your entire repo using embeddings. This is the one that makes "find every place we still call the old payments API" actually *work*. (...) And `@past-chat` lets you reference an earlier conversation so you don't have to re-explain context every time.
>
> Look at the example at the bottom of the slide. It references two specific files, *plus* the relevant library docs. (...) That's not a fancy prompt. That's just — a prompt that's been given enough context to succeed. Train yourself to start every prompt with an @-reference. It is the single highest-leverage habit you can build with this tool.
>
> ▸ click

---

## Slide 5 — Agent Mode in Depth  *(5:15 - 6:45)*

> Okay — modes, context, we've got the basics. Let's open the hood on the one everyone talks about. (...) *Agent mode.*
>
> What it actually does is run a loop. (...) Pick a tool, run it, read the output, decide what to do next, repeat — until it thinks it's done. (...) And it has four tools at its disposal. *Read* — it opens any file and quotes back the exact lines, so it's always working from real code, not hallucinated code. *Edit* — every change comes back as a diff, and you accept or reject *per chunk*. Not per file. Per chunk. So you can keep three good changes and throw away the one bad one. (...) *Search* — regex and glob across the whole repo. And *Shell* — it can actually run things. `npm test`, `git status`, installs — whatever your project needs.
>
> Two safety nets you absolutely need to know about. (...) *First*: nothing happens silently. Every edit shows up as a diff in front of you before it touches your files. (...) *Second*: every agent run creates a *checkpoint*. If five minutes in you realise the agent went sideways, one click rewinds everything — files, terminal, conversation — back to before it started. It's like a save state in a video game. Use it. Aggressively.
>
> There's also an *auto-run* toggle in settings that lets you whitelist "safe" shell commands — `npm test`, `ls`, `git status` — so the loop doesn't stop and ask permission every single time. Turn that on once you trust the model. It makes Agent mode flow.
>
> Look at that example prompt. (...) Notice three things. There's an @-reference. There's a specific behaviour spec — *what* the toggle should do, not just "add a toggle". And there's "add a test" at the end. (...) Context, plus spec, plus tests. *That* is what separates a useful agent run from a useless one.
>
> ▸ click

---

## Slide 6 — Plan Mode  *(6:45 - 8:00)*

> Now — here's the move that levelled up my output more than anything else in this whole video. (...) *Plan mode.*
>
> The chat panel in Cursor has a little dropdown most people never click. It has three options: Ask, Plan, and Agent. Ask is read-only chat — no edits, no actions. Agent is what we just saw — full autonomy. (...) Plan mode is the middle child, and it's the most underrated feature in the whole app.
>
> In Plan mode, the agent can *read* your code but it can't *edit* anything. So instead of charging in and making changes, it explores the codebase, asks you clarifying questions, and produces a written plan: *here are the files I'll touch, here's the order, here are the tests I'll add, here are the trade-offs I see*. (...) You read the plan. If you like it, you click confirm, and Cursor flips itself into Agent mode and executes. If you don't, you edit the plan in plain English and re-run.
>
> The rule I follow — and write this one down. (...) *Any change that touches more than two files: Plan first. Anything in auth, payments, billing, migrations, security: Plan first. Anything where you'd otherwise have to ask three clarifying questions: Plan first.*
>
> Ten minutes of planning saves an hour of damage control. (...) The first time you skip Plan on a big refactor and watch the agent confidently half-implement the wrong thing, you'll understand why this slide exists. Trust me on this.
>
> ▸ click

---

## Slide 7 — Rules and AGENTS.md  *(8:00 - 9:25)*

> Alright, that covers the *built-in* modes. Now we move into the part of Cursor most tutorials don't even mention — the stuff that turns a fresh repo into an *agent-ready* repo.
>
> Starts with rules. (...) If you've used Cursor for more than a week on a real project, you've probably found yourself typing the same instructions over and over. "Use pnpm, not npm." "Tests live next to source files." "We use Vitest, not Jest." (...) Rules fix that.
>
> You drop a markdown file inside a folder called dot-cursor-slash-rules, and Cursor reads it on *every single agent invocation*. No repeating yourself. The `.mdc` extension is special — it lets you add YAML frontmatter at the top. Two keys really matter: `globs:`, which scopes a rule to certain file patterns — so your React rules only fire on `.tsx` files — and `description:`, which lets the agent decide whether the rule applies to the current task.
>
> Then there's `AGENTS.md`. (...) This is the newer, cross-tool standard. It lives at the root of the repo, no dot-folder, and it works in Cursor, Claude Code, Cody — basically any modern AI tool. Use `AGENTS.md` for the project-level stuff that's not Cursor-specific: what the project is, how it's structured, the conventions. Use `.cursor/rules` for Cursor-specific behaviour. (...) And there's a third thing called `SKILL.md` — think of it as a reusable playbook that the agent picks up automatically when the task matches.
>
> Look at the example at the bottom. (...) Four lines. Package manager preference. Test layout. Doc requirements. Secret handling. (...) Four lines of rules can save you *thousands* of repeated instructions over the life of a project. The ROI is absurd.
>
> ▸ click

---

## Slide 8 — MCP, Hooks, Background Agents  *(9:25 - 11:00)*

> Okay now we're in power-user territory. *Three* features that, frankly, turn Cursor from a code editor into an actual *agent platform*.
>
> *MCP* — the Model Context Protocol. It's an open spec that came out of Anthropic, and any AI tool can implement it. Every MCP server exposes new *tools* that the agent can call. So — install the Jira MCP server, and now your agent can read tickets, update statuses, leave comments. Install the Postgres MCP server, and the agent can query your database directly. GitHub MCP gives it full pull-request management. (...) There are *hundreds* of MCP servers already published, and writing your own is genuinely about fifty lines of code. This is a big deal.
>
> *Hooks*. A file called `hooks.json` in your dot-cursor folder. It lets you run shell scripts when certain agent events fire. (...) Auto-format every accepted edit. Auto-run your tests after every diff. Audit-log every single change the agent makes to a file you specify. Hooks are the difference between "I trust the agent" and "I have receipts".
>
> And the showstopper — *Background Agents*. (...) You kick off a long task and instead of it running on your machine, it runs *in the cloud*. On its own branch. In a clean sandbox. And when it's done — you get a pull request. (...) Which means you can fire off "refactor the entire test suite to use Vitest" before lunch, walk away, and come back to a PR waiting for review.
>
> Now look at the combo at the bottom. (...) MCP-Jira picks up the ticket. Background Agent implements it on a branch. A Hook posts the PR link back to the Jira ticket when it's done. (...) That right there — that is zero-context-switching engineering. That is *the agentic way*.
>
> ▸ click

---

## Slide 9 — TDD with Agents  *(11:00 - 12:20)*

> All that power doesn't matter if the agent ships buggy code. So let's talk about the single biggest quality multiplier I know of. (...) *Test-driven development with an agent.*
>
> Same cycle as classic TDD. Red, green, refactor. (...) But the trick — the part that's specifically magic when the AI is in the loop — is the first step.
>
> *Red*. You ask the agent to write *failing tests first*. Just the tests. Don't let it touch the implementation yet. (...) This is the step *every* beginner skips, and it's the one that does ninety percent of the work. Because the tests you just got — those become a *precise specification* the AI has to satisfy. No more "looks right but doesn't actually work". No more vibes-based correctness. The tests are the spec.
>
> *Green*. Now you tell the agent to write the *minimum* code to make those tests pass. Nothing else. And because the tests exist, you know *instantly* when it's done. No guessing. No "is this finished?". The test runner is your judge.
>
> *Refactor*. You ask the agent to clean up the code — rename, restructure, simplify — and the tests are your safety net. Any refactor that breaks behaviour turns a test red and you catch it the same second.
>
> Look at the three prompts at the bottom. Real prompts I actually use. (...) Notice they're *three separate prompts*, not one big mega-request. That's deliberate. Smaller prompts mean shorter feedback loops, and shorter feedback loops mean *dramatically* better output. (...) The whole mental shift here is: you stop saying "I trust the AI" and you start saying "I trust the tests". (...) That is a *much* better deal.
>
> ▸ click

---

## Slide 10 — The Cheat Sheet  *(12:20 - 13:30)*

> Alright. Last slide. (...) *Pause the video. Take a screenshot. This one's the only one you need to remember.*
>
> Left side — the shortcuts. Tab is your most-used key, by *miles*. Control-K is inline edit. Control-L is Chat. Control-I is Agent. Control-Shift-L grabs the selected text and drops it into the chat. And the whole @-family — file, codebase, docs, web, git — sitting right there.
>
> Right side — the decision tree. (...) Do you need code *changed*? If no — use Chat. If yes — is the task big or unclear? If yes, start in Plan mode and scope it before any code moves. If no, jump straight to Agent. That's the whole flowchart. Tape it next to your monitor.
>
> At the bottom: model picks. (...) *Grunt work* — Haiku, GPT-4o-mini — cheap and fast. *Daily driver* — Claude Sonnet, GPT-4o — your default for ninety percent of the day. *When it matters* — billing code, auth code, security, the final polish — reach for Claude Opus or an o-series model. Match the model to the *stakes*.
>
> Three rules to take with you if you forget everything else I said. (...) *Tests first. Plan before big changes. Match the model to the stakes.* (...) Do those three things and you'll be in the top five percent of Cursor users by the end of the month.
>
> ▸ hold the slide for the outro

---

## Outro  *(13:30 - 13:45)*

> *(Stay on slide 10. Soft smile. Bring the energy down a hair to land.)*
>
> That's the agentic way. (...) Links to the rules templates, the AGENTS.md examples, and the source of this whole deck are in the description. (...) If this helped you, drop a like, subscribe for more Cursor deep-dives, and — happy shipping.

---

## Runtime breakdown

| Slide | Topic                                  |  Time |
|------:|----------------------------------------|------:|
| 1     | Title — the hook                 | 0:55  |
| 2     | What is Cursor?                        | 1:15  |
| 3     | Four ways to talk to it                | 1:35  |
| 4     | The @ symbol                           | 1:30  |
| 5     | Agent mode in depth                    | 1:30  |
| 6     | Plan mode                              | 1:15  |
| 7     | Rules &amp; AGENTS.md                  | 1:25  |
| 8     | MCP, Hooks, Background                 | 1:35  |
| 9     | TDD with agents                        | 1:20  |
| 10    | Cheat sheet                            | 1:10  |
| -     | Outro                                  | 0:15  |
|       | **Total**                              | **~13:45** |

If you want a tighter ~10-min cut, trim the cold open (slide 1) to one sentence, and condense slides 2 and 6 — the rest are load-bearing.

---

## Delivery notes (read once before recording)

- **Pace.** Aim for ~150 words per minute. The script is written at that pace. If you find yourself hurrying, you're rushing — slow down.
- **Pauses.** The `(...)` are pauses. They are doing work. Don't skip them — they're what gives the viewer a moment to *see* the slide.
- **Emphasis.** When you hit an *italicised* word, lean in — slightly louder, slightly slower. That's the word doing the teaching.
- **No filler.** No "uh", "um", "so basically", "kind of". The script doesn't have them; your delivery shouldn't either.
- **Smile when you talk.** It's audible. Especially on the outro and the punchlines.
- **Record in chunks.** Do one slide per take. If a slide goes badly, redo just that slide — don't re-record the whole thing. Stitch in the edit.
- **Levels:** -16 LUFS for YouTube, voice should peak around -6 dB. Quick test — record 10 seconds, listen on phone speakers. If you can hear it clearly, it's right.
