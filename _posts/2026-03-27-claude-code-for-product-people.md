---
layout: post
title:  "Claude Code for Product People: Setup and Mindset Shift"
date:   2026-03-27
categories:
permalink: blog/claude-code-for-product-people
---

It's Tuesday afternoon. An experiment you've been running for three weeks just hit statistical significance. The numbers are messier than you hoped. You have a growth review in two hours where you'll need to make a call. You also have a PRD to update, six tickets to create for the next iteration, and a release announcement to draft before end of day. Oh, and you just remembered you have to present your roadmap to the C-suite tomorrow morning.

_Welcome to PM life!_

You open Notion, read the first readout, copy the key metric into a doc, open Jira, start a ticket, realize you need to check what the last epic covered, open another tab, lose the metric you just copied, and start again.

The hard part (deciding what the experiment actually means) isn't what's slowing you down. It's that your brain wasn't designed to hold ten documents open simultaneously while tracking what each one means for the next.

That's what Claude Code does for PMs. It doesn't generate text faster. No one needs more AI slop.

Instead, it can work wonders if you use it to eliminate the steps that only exist because humans can't hold all of that in working memory at once: the context-switching, the copy-pasting, the re-reading a doc you've already read for that one sentence you know is there.

## What is Claude Code?

It's a CLI tool you install in a terminal (or use in other places like VS Code). Setup takes about 15 minutes. Once it's running, you can connect it to your actual PM stack like your issue tracker, your docs platform, your comms tools, etc. From there, it reads and writes across all of them in a single session.

And if you use it the right way, it can _actually_ transform how you (and your team) get work done. AI is shifting how Product teams work, and even though I've used LLMs since GPT-3, my "aha" (or "oh shit") moment came with my time using Claude Code since it's made me shift how I work.

This post covers how Product people can set it up, what the workflows look like in practice, and how to build a configuration that gets more useful over time. Not because the AI improves. Because the context you've given it does.

### Why Claude Code is different for PMs

If you've only seen Claude Code described as "a coding tool," that framing undersells it.

And don't let the "code" part of it disuade you. I'm not a stranger to the terminal, so it was easy to jump in, but believe me, you don't have to have that kind of background to start with Claude Code.

It's not a chat interface. You don't ask it questions and read the answers. It reads and writes files, runs commands, and connects to external tools through integrations you configure. Once those are set up, a single session can pull data from your issue tracker, synthesize three Notion pages, draft tickets, and update your roadmap. The difference from every other AI tool is that it's acting across systems, not answering questions about one thing at a time.

One orientation point since I mentioned it earlier: Claude Code runs in your terminal, not a browser or desktop app. If that's new territory, it mostly disappears into the background once you're through setup.

Where does it shine? tasks that require holding a lot of context at once and need to be trained on data sets. Synthesis across sources, cross-system work, structured repetitive tasks, anything where knowing your team's full context produces meaningfully better output.

Where isn't it generally a good fit? Quick single-tool lookups, real-time collaborative work, tasks where you're actively shaping the output as it develops. Use it wrong and it's a very slow text editor.

One expectation to calibrate before we get to setup: Claude Code holds full context within a session. Cross-session memory (knowing your conventions, your active initiatives, how you prefer to write) requires a memory system you build and maintain. That's the next section, and it's where most of the long-term value actually comes from.

### The three modes, and where most PMs get stuck

Most PMs who try Claude Code use it as a document generator. You have a PRD to write, you describe what you need, Claude drafts it. Faster than starting from scratch. But you're still driving every step manually. That's mode one, and it's the lowest-leverage way to use the tool.

There are three modes:

* **Document generator:** faster output, same manual orchestration. You're in control of every step, Claude fills in the blanks. Useful. Not transformative.

* **Thinking partner:** you bring finished work; Claude interrogates it. Instead of asking Claude to write your PRD, you ask it to tear apart the one you've written: "What's missing? What's assumed without data? What would my most skeptical stakeholder push back on first?" The output isn't a draft. It's a stress-test before you walk into the room.

* **Workflow executor:** you define the goal, Claude handles the sequencing. It reads the right sources, produces the right outputs, in the right format. A competitive teardown that normally takes 90 minutes of tab-switching becomes a 10-minute session. This is where it stops feeling like a faster version of what you already do.

Most PMs stay stuck in mode one because modes two and three require setup. Not a lot. But specific setup. The rest of this post is that setup.


### Setting up your environment

The part most people skip is also the part that determines whether the setup compounds or plateaus by week two.

Three things to configure: your standing instructions, your memory system, and your tool connections.

**CLAUDE.md: your standing instructions**

CLAUDE.md is a file that loads automatically at the start of every session. It's where you tell Claude what it needs to know to work with you: your role and team context, how you prefer to write, which tools you use, and any standing challenges you want applied to your work. It can live at the project level (applies to that project) and / or globally in your home directory (applies everywhere). Most PMs want both.

The writing config matters more than it looks, at least for me. Documents written with AI assistance have a recognizable texture: vague verbs, inflated significance, formulaic structure. For anyone reviewing your work, this becomes a legibility issue. If the writing sounds like AI, it's hard to tell where your thinking ended and execution began. Configuring Claude to write in your voice and flag vocabulary you want avoided fixes this at the source.

**Memory: context that compounds**

Four types worth maintaining: your role and how you work, feedback on what Claude should and shouldn't do, active initiatives and their current status, and where things live across your tools. These are markdown files that Claude reads at session start. The compounding happens because context that would otherwise reset every session gets loaded automatically instead.

The key habit: after important decisions, write them down explicitly. A session where you define your team's ticket format should end with that format saved to a memory file. Future sessions start with it already loaded.

I have a ton of memories in my setup, and I've manually added 0 of them. Fortunately, Claude is very good at setting those up. Although they'll need to be updated from time to time.

**MCPs: connecting your actual tools**

MCPs (Model Context Protocol servers) give Claude read/write access to external tools. Connecting to Jira, Notion, or Slack requires a community-maintained or custom MCP server for each. 

What each unlocks in practice: 
* Issue tracker = ticket creation with full prior-epic context that Claude holds but you'd have to manually reconstruct
* Docs platform = draft and synthesize across pages without copy-pasting
* Comms = announcements in your team's actual format

What's worth knowing before connecting everything is that each MCP adds token overhead from its tool definitions, and that overhead scales with how many tools the server exposes. Connect several MCP-heavy integrations, and you've used a meaningful chunk of context before writing a word. Keep it to two or three, use only what you need for a given session, and run /clear between unrelated tasks. Compact the convo when necessary. I created my own ["HUD" for Claude Code that keeps tract of these things in a non-intrusive way, so feel free to install it here.](https://github.com/btrav/claude-mini-hud)

In some cases, a tool might not have an MCP, though working with APIs is great, and you can even set up the Claude extension in your browser to do some heavy lifting if needed.

Now for repeatable workflows, you'll want to learn about skills.

### Skills: one-command workflows

Skills are custom slash commands you define once and invoke whenever you need them. You build a /prd-review command (what it checks, how it's structured, what it flags), and from then on, typing /prd-review runs that exact review every time. They live as markdown files in your project directory, so they're easy to share and update as your team's conventions change.

If you've asked Claude to do the same type of work three times, make it a Skill.

PM examples worth building:

- **/prd-review:** structured review against problem validation, scope, success criteria, and dependencies. Surfaces gaps before you share with anyone
- **/ticket:** creates tickets from PRD requirements with full context, dependency callouts, and flags for anything that needs clarification
- **/announcement:** release posts or messages in your team's format
- **/data-request:** structured analysis requests for your data team, under 200 words, with the right framing so you get back what you actually asked for

**The reference library pattern**

One level up: build reference files that certain Skills read when invoked. Your team's working definition of activation. Your last three experiment results. The prioritization framework you actually use. Claude reads those files when the Skill runs, so the output reflects your team's specific conventions. A reference file might be ten lines. The value is that you stop re-explaining the same context and start getting answers calibrated to how your team actually works.

**Challenge mode**

The most useful Skill to build is when it's a critic. If you're used to being coddled by ChatGPT then buckle up. The best thing I've done is configure Claude to give things to me straight and challenge me constantly. Getting a reality check from the latest model can be humbling, but it makes my work so much better.

Define a command that activates a critical lens on whatever you bring to it: "What's missing? What's assumed without data? What would my most skeptical stakeholder cut first?"

That's the Skill that converts Claude from document generator to thinking partner as a standing default. No remembering to ask for it every time.

### The sub-agent advantage

What sets Claude Code apart from other AI tools is that it can run multiple perspectives simultaneously, each with access to your tools and files, not just parallel chat tabs. I absoultely love this.

**Cross-functional review**

Before a big stakeholder review, brief parallel agents with specific personas: product design, engineering, strategy, finance. Each reviews the same document and flags different concerns based on its functional lens.

The quality depends entirely on how well the personas are specified. "Review this as an engineer" returns a generic response. "Review this as an engineer who cares about API rate limits, migration complexity, and timeline realism. Flag anything the PRD assumes without specifying" returns something you can act on. The work is in the briefing, not the prompting.

You might even build subagents based on real personalities!

Note that even well-briefed agents can converge if the personas aren't distinct enough. If two return nearly identical feedback, the briefs need tightening, not the tool.

**Research synthesis**

Run agents against multiple sources simultaneously. That means five research docs, three experiment readouts, and a compiled Slack summary. Pull findings into a single view. What used to take the better part of a day of manual triangulation can happen in a single session. Useful for quarterly planning, initiative kick-offs, or any time you're working from scattered context.

**Multi-round validation**

The same pattern works in sequence. Run an agent to pressure-test a concept before you've committed to a plan. Run a different one to review the plan before the build starts. Run a third to check implementation against the original requirements. The output from each round informs the next.

One thing that carries across all three: output quality scales with the context you've built. A current CLAUDE.md, maintained memory files, and the right integrations are the difference between useful and generic. Keep in mind that sub-agents inherit the context you've given Claude.

### What this looks like in practice

The intro's Tuesday afternoon was a setup. Here's what it actually looks like once this is running.

Note the scenarios below assume you've connected your issue tracker and docs platform. Without those integrations, the same workflows apply. You paste the relevant content rather than Claude pulling it directly.

**Experiment results to next iteration**

You have three experiment readouts and the prior epic from your issue tracker. In a single session: Claude reads all three, pulls the key learnings, identifies what the prior implementation covered vs. what was deferred, and drafts ticket text for the next iteration with full context and dependency callouts. It flags two requirements that conflict with an initiative already in flight. You make the calls, finalize the tickets in the tool, send a stronger brief to the team.

**PRD from scattered inputs**

You have research notes, a compiled Slack summary from stakeholder review, and a half-finished Google Doc. Claude reads all of it, drafts a PRD in your team's format, then runs /prd-review (the custom skill from the previous section) to surface gaps before you've shared it with anyone. It flags three requirements that lack supporting data and two that overlap with an existing initiative. Then it runs sub-agents for your other trio members and a couple stakeholders. You make the judgment calls. The first draft you share is substantially stronger than what you'd have sent otherwise.

**The recurring deliverable**

Do you create any recurring deliverables? Yes, you do, so read this part carefully since it's going to save you a ton of time.

This is the one that accumulates value fastest. Sprint planning doc. Weekly exec summary. Competitive teardown. Sprint recap. Pick whichever one you produce on a fixed cadence. Once Claude knows your format, your data sources, and your team's conventions (because you've put them in CLAUDE.md and memory), producing the next iteration is a single session. The one-time investment is defining the format once. After that, the tenth week feels completely different from the first.

This is what compounding looks like in practice. It's not a dramatic time save on any single task per se, but quality is higher, content is more consistent, and it frees up your brain for things that need higher level thinking.

### The team-level angle

Everything above applies to one PM. The more interesting question for leads: how do you raise the floor for the whole team?

A few things worth standardizing:

**Shared reference files:** team conventions belong here. Ticket format, announcement structure, how your team defines success criteria, writing rules. Check it into your project repo. Individual PMs keep their personal config in a global file that layers on top, but the shared file sets the baseline. Someone has to own it, typically the team lead or whoever cares most about process quality. Without an owner, it drifts the same way individual memory files do. Work with your team to find the right formats here.

**Shared Skills:** someone builds the first /prd-review. Check it into the same repo. When a PM refines it, everyone pulls the update instead of drifting in separate directions. The maintenance cost is lower than it sounds; the gain is that your team's recurring PM work has a consistent floor.

**Individual memory stays individual.** Personal working style, role context, how you prefer to communicate. Shared config is for conventions. Individual files are for context. Mixing them creates noise that degrades both.

One norm worth making explicit is if your PMs are using Claude to draft PRDs, to establish the expectation that they can defend every claim in the document without referring back to Claude. The goal is work that's faster and better reasoned. Claude handles the coordination. The PM still owns the thinking.


### Making it compound, and keeping it that way

The failure mode that actually ends adoption isn't a bad experience. It's slow drift.

The setup that worked in week one stops giving useful output by week six. Not because the tool changed, but because your context did. Initiatives ship. Teams reorganize. Tools move. Project memory describes something from three months ago. Reference files point to an archived Notion page. Skills run against conventions your team has abandoned.

After any significant event (a shipped feature, a completed quarter, a new tool rollout) spend a few minutes updating the relevant memory files. It's cheaper than catching it mid-session, when Claude is confidently working from stale context.

Run /insights periodically to take stock of your actual usage. Which workflows are you actually running? Where are you still doing manual work that could be systematized? The answer shifts as your role evolves, and it tells you where to invest next.

The compounding stops when the maintenance stops.

### Pitfalls

A few things that reliably slow people down:

**Treating output as autopilot** Claude can produce plausible-looking documents with wrong assumptions baked in. Review everything, especially dates, metrics, ownership, and any claim about a specific initiative's status.

**Skipping context** The more specific the input, the better the output. Paste the actual content: prior epic details, constraint notes, relevant decisions. If you have the relevant MCP connection in place, links work. If you don't, they don't.

**Stopping at document generation** If it still feels like a fast text editor after a month, the earlier sections on memory and skills are what's missing.

**Memory going stale** Outdated project context produces outputs that are 80% right, which is harder to catch than obviously wrong. Keep it current.

**Connecting too many MCPs** Each integration (Jira, Notion, Slack) adds token overhead at session start. Connect what you need for the session, nothing more.

**Fighting the tool for the wrong task** The clearest signal of this is when you're spending more time prompting than the task would take to just do yourself. Stop and either rethink the prompt or rethink whether this is the right task for the tool.

## Closing Thoughts

What Claude Code removes are coordination costs, not thinking. Synthesis, context-holding, pulling together three Notion pages and a Jira epic into one coherent view: those are the steps that exist only because humans have limited working memory. When Claude handles them, what's left is the actual job: problem definition, judgment calls, stakeholder decisions, the work that requires a human.

That's what the setup is for. Not to make you faster at the old job. To make room for the work that actually needs you.

The setup takes an initial investment, sure. An hour or two to start with. Then additional time, especially the first couple weeks. The compounding starts after that.