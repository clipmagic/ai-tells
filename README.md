# ai-tells

Clip Magic's customised version of the original [`ai-tells`](https://github.com/kdgbalmer/ai-tells) skill by Kyle Balmer. It reviews drafts for possible AI writing tells and can produce a cleaner rewrite when asked. It is intended for ChatGPT, Codex, and compatible AI assistants.

## What it does

Ask for an AI-tells or de-AI review and the skill checks the draft against a catalogue of possible signals across vocabulary, structure, tone, punctuation, and content. It identifies relevant wording, explains why it may contribute to generic AI texture, suggests changes, and can estimate tell density when useful.

The skill supports an audit-only review, a rewrite of the supplied document, or a separate rewritten version that leaves the original unchanged. If your prompt does not make the intended action clear, it asks you to choose before proceeding. Its catalogue is guidance rather than a prohibited-word list: context and combinations of signals matter, and clear terminology or deliberate style should remain intact.

The catalogue is compressed from Wikipedia's "Signs of AI writing" page plus the goblin-era 2026 update. It covers everything from Tier 1 markers like *delve*, *tapestry*, and *leverage*, through structural tells like negative parallelism ("It's not X, it's Y"), down to era-specific leaks like the OpenAI goblin family.

## Install

### Option 1: Codex skill

1. Create an `ai-tells` folder inside your Codex skills directory.
2. Place `SKILL.md` inside that folder.
3. Ask Codex to run an AI-tells review, or invoke the skill directly if your setup supports named skills.

For a standard personal installation, the resulting path is usually `~/.codex/skills/ai-tells/SKILL.md`.

### Option 2: ChatGPT or another compatible assistant

Add `SKILL.md` using the assistant's supported skill, project-instruction, or custom-instruction mechanism. Automatic discovery depends on the platform, but the trigger boundary described below should remain the same.

### Option 3: System prompt

Paste the contents of `SKILL.md` into a system prompt or custom instructions. The catalogue can still be useful without a formal skill mechanism.

## Usage

The skill is intentionally narrow. Trigger phrases include:

- "Check this for AI tells."
- "Does this sound like ChatGPT?"
- "Make this less AI-like."
- "Run an AI-tells audit."
- "Remove the AI smell."
- "Humanise this draft."
- "Is this AI-y?"

Ordinary requests to edit, polish, proofread, improve, rewrite, or give feedback on writing should not trigger this skill unless the request also expresses concern about AI-like wording or style. This keeps it from interfering with normal copy-editing or work in an established personal or brand voice.

The available actions are:

- **Audit only:** identify the relevant tells, briefly explain them and suggest changes without rewriting.
- **Rewrite this document:** apply the changes to the supplied text or an explicitly authorised source file.
- **Create a new version:** rewrite a separate copy and leave the original unchanged.

If the prompt does not clearly select one, the skill asks:

> Would you like me to audit only, rewrite this document, or create a new version and leave the original unchanged?

It waits for your answer, then proceeds with the chosen action. Clear instructions such as "audit only", "rewrite this pasted text", "edit the original document", or "create Version 2 and preserve the original" proceed without the extra question. For an existing file, a general request to humanise or clean up the writing triggers the question because it does not specify whether the source file may be changed.

## Updating

The AI tell landscape shifts every 3-6 months as model trainers patch the most-mocked tells and new ones emerge. To keep the skill fresh:

1. Open https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing
2. Add new tells to the relevant category in `SKILL.md`.
3. Move trained-out tells to the "Mostly trained out" subsection.
4. Bump the date in the "Era-specific tells" section.

Never delete from the catalogue. Tells are cyclical and may return.

## Limitations

- This is not an AI detector and does not prove whether text was written by AI. Authorship cannot be reliably determined from these surface patterns.
- It removes surface-level AI tells. It cannot detect hollow thinking or missing voice, and it does not create a person's voice. Those need a human pass or a genuine voice guide.
- A listed word, punctuation mark, or structure is not automatically bad. The skill should preserve accurate terminology, language variant, deliberate phrasing, useful em dashes, humour, informality, and individual rhythm when they fit the context.

## License

MIT. Free to use, share, fork, modify. Attribution appreciated but not required.

## Credit

This repository is Clip Magic's customised version of the original [`kdgbalmer/ai-tells`](https://github.com/kdgbalmer/ai-tells) project.

The original skill was built by [Kyle Balmer](https://aiwithkyle.com) at AI with Kyle. Original author and source credit are retained here.

Compressed from:

- Wikipedia: [Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)
- OpenAI: [Where the goblins came from](https://openai.com/index/where-the-goblins-came-from/)
- Christensen, J.S. (2024). [The end of AI detection](https://www.sciencedirect.com/science/article/pii/S2666389924002083)

If the catalogue dates, send a PR.
