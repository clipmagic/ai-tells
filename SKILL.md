---
name: ai-tells
description: Reviews drafts for AI writing tells and can audit, rewrite, or create a separate cleaner version for ChatGPT, Codex, and compatible AI assistants. Use when the user explicitly asks for an AI-tells or de-AI review, such as "check this for AI tells", "does this sound like ChatGPT", "make this less AI-like", "run an AI-tells audit", "remove the AI smell", "humanise this draft", or "is this AI-y". When the requested action is unclear, ask whether the user wants an audit only, a rewrite, or a new version that leaves the original unchanged. Do not trigger for ordinary editing, polishing, proofreading, improving, rewriting, or writing feedback unless the user also expresses concern about AI-like wording or style.
---

# AI tells

A second-pass checker that flags possible AI writing tells in a draft and can audit it, rewrite it, or create a separate cleaner version. It is intended for ChatGPT, Codex, and compatible AI assistants. The catalogue is compressed from Wikipedia's "Signs of AI writing" page plus the goblin-era 2026 update.

## Modes

Three modes:

1. **Audit only.** Identify relevant tells, quote or locate the wording, briefly explain the category, and suggest what could change. Include a density estimate when it would help. Do not rewrite the draft.
2. **Rewrite this document.** Rewrite the supplied text or document to address the relevant tells while preserving meaning, intent, facts, and voice. Modify an existing file only when the user explicitly chooses this action or clearly asks to edit or overwrite the original.
3. **Create a new version.** Make a separate rewritten version and leave the original unchanged. Use a clear versioned filename, preserve the source's format and structure where practical, and verify that the original remains unchanged.

## Choose the action first

If the prompt clearly requests one of the three modes, proceed without asking. A request to identify, check, review, or audit the tells without changing the text selects **Audit only**. A request to rewrite pasted text selects **Rewrite this document**. A request for a copy, separate file, Version 2, or preservation of the original selects **Create a new version**.

For an existing file, a general request to rewrite, clean up, remove tells, make it less AI-like, or humanise it does not establish whether the original may be changed. If the prompt does not clearly select a mode, ask exactly:

> Would you like me to audit only, rewrite this document, or create a new version and leave the original unchanged?

Wait for the answer, then proceed based on the chosen action. Do not audit, rewrite, or modify a file before the choice is made.

Do not treat an ordinary request to edit, polish, proofread, improve, rewrite, or give writing feedback as an AI-tells request unless the user also mentions AI-like wording or style.

## Judgement and voice

The catalogue is guidance, not a prohibited-word list. A listed word, punctuation mark, or structure is not automatically bad. Judge the context, frequency, clustering, and effect on the passage. Density and combinations of signals matter more than any single match.

Preserve accurate technical terminology, Australian or British English, deliberate phrasing, natural contractions, dry humour, mild informality, intentional fragments or short paragraphs, genuine contrasts, and the writer's individual rhythm. Do not replace a listed word when it is the clearest or most natural choice in context.

Remove generic AI texture without flattening the writer's voice. Preserve existing slang, humour, and personal quirks when they are natural and appropriate; do not manufacture Australian slang, humour, informality, or quirks to make a draft appear human.

This skill is a specialised review, not a replacement for normal copy-editing or established personal or brand voice guidance. If a voice guide is supplied, follow it unless doing so would change facts or meaning.

## The catalogue

Use the categories below to inspect the draft. Report only contextually relevant matches. For each one, identify the wording, explain why it contributes to AI-like texture in this passage, and suggest a change or direction. Do not mechanically report or replace every catalogue match.

### Vocabulary tells

These words may appear at unusually high frequency in machine-generated text. Treat repetition, vagueness, and clustering as stronger signals than the presence of one word. Prefer a plainer or more specific alternative only when it improves the sentence.

**Tier 1, stronger catalogue signals when vague, repeated, or clustered:**
delve, tapestry, multifaceted, pivotal, intricate, robust, vibrant, meticulous, nuanced, leverage, foster, navigate, underscore, showcase, ensure, realm, garner, bolster, enduring, elevate, unwavering, testament, journey, landscape, ecosystem, paradigm.

**Tier 2, context-dependent:**
crucial, key, vital, significant, essential, comprehensive, holistic, seamless, dynamic, innovative, transformative, cutting-edge, state-of-the-art, harness, embrace, embark, dive into, dive deep.

**Tier 3, promotional language (inspect especially in marketing or about-page contexts):**
boasts a, nestled in, in the heart of, renowned for, exemplifies, stands as a testament, serves as a reminder, represents a shift, marks a turning point, indelible mark, deeply rooted, rich, profound, enhancing, showcasing, commitment to excellence.

When one appears, ask whether it is accurate, specific, and natural in context. Suggest a replacement only if a plainer or more precise word improves the passage.

### Structural tells

**Negative parallelism** ("not X, it's Y") is an overused AI structure when it appears mechanically or repeatedly. Flag formulaic instances, but preserve genuine contrasts and deliberate rhetorical phrasing. Examples:

- "It's not [a tool], it's [a thought partner]"
- "You're not [an X], you're [a Y]"
- "Not just A, but B"
- "It's not about A. It's about B."

**Bullet-everything.** A 1-3 sentence answer broken into bullets, or a markdown header used for a paragraph-length response. Suggest flowing prose when the structure is mechanical; keep lists, fragments, and short paragraphs that genuinely improve scanning or rhythm.

**Rule of three.** Adjective triads ("creative, thoughtful, and deeply considered") used for false comprehensiveness. Suggest one or two specific adjectives when the third item adds no meaning; keep purposeful triads.

**Outline-style conclusions.** Final paragraphs that read "Despite [challenges], [subject] continues to [vague positive outlook]." Suggest a specific ending, or no conclusion, when the existing one adds no substance.

**Title Case headings** when sentence case is the established convention. Convert only when it conflicts with the document's style.

**Skipping heading levels** (H2 directly to H4 with no H3). Flag when it reflects a mechanical outline or harms navigation; preserve intentional document structures that remain clear.

**Inline-header lists** (`- **Term:** description` repeated mechanically). Flag when the pattern feels mechanical; keep genuine definition or reference lists.

**Excessive boldface.** Bolding every key term mechanically. Suggest reducing it when the emphasis creates generic visual texture; preserve intentional emphasis and the document's established style.

### Tone and opener tells

These phrases often create generic assistant texture. Flag them when they are formulaic or unnecessary; preserve deliberate wording that suits the speaker and context:

- "Great question!"
- "Absolutely!"
- "Certainly!"
- "Of course!"
- "I'd be happy to help."
- "I'd love to help."
- "I'm here to help."
- "It's important to note that…"
- "It's worth noting that…"
- "It should be noted that…"
- "Interestingly,"
- "In conclusion,"
- "In summary,"
- "To summarize,"
- "To wrap up,"
- "Furthermore,"
- "Moreover,"
- "Additionally,"
- "However," used as the opening word of multiple paragraphs.

Test: if the sentence works better without the opener, suggest removing it. If the sentence adds no useful meaning, suggest removing or rewriting the sentence. Do not apply this mechanically.

### Punctuation tells

**Em dash overuse.** Frequent em dashes, especially at repeated clause boundaries, can be a signal. Treat the count as a prompt for judgement, not a hard limit. Suggest commas or full stops where they read better, but keep deliberate, useful em dashes.

**Curly quotes** in plain-text or markdown contexts where the surrounding ecosystem consistently uses straight quotes. Suggest conversion for consistency, not because curly quotes are inherently AI-like.

**Knowledge-cutoff disclaimers.** "As of my knowledge cutoff…", "I may not have current information…". Flag boilerplate disclaimers that add no value. Preserve necessary, specific warnings about currency or uncertainty.

**Sycophantic openers.** "What a wonderful question!", "I love this prompt!". Suggest removing them when they are formulaic; keep sincere reactions that fit the speaker's established voice.

### Content and analysis tells

**Vague attribution.** "Many experts say…", "Studies have shown…", "It is widely believed that…". Suggest a specific source, a more precise statement, or removal of an unsupported claim.

**Superficial -ing analysis.** Clauses that add no information: "highlighting their significance", "emphasizing their role", "underscoring their importance". Suggest removing or replacing the clause with actual analysis.

**Hedge stacking.** "May potentially possibly suggest." Suggest the strongest wording that remains accurate.

**Filler hedges.** "Somewhat", "relatively", "arguably", "perhaps", "potentially". Flag repeated or empty hedging. Keep uncertainty that is factually necessary; otherwise suggest a sharper claim or removal.

### Era-specific tells (current as of May 2026)

**More common in the current catalogue:**

- Goblin, gremlin, raccoon, troll, ogre, pigeon used as inserted internet whimsy. Flag only when the wording feels generic or out of character, not when the subject or writer naturally calls for it.
- Repeated "It's not X, it's Y" constructions.
- Mechanical markdown-bullet-everything.
- Formulaic "I'd be happy to help" openers.
- Title Case section headings that conflict with the document's style.

**Less common in the current catalogue:**

- "Delve" used vaguely or repeatedly.
- Em dashes at nearly every clause boundary.
- "Tapestry" used as a vague metaphor.

Update this section quarterly against the Wikipedia source. Demote trained-out tells to the second list, but never delete from the catalogue. Tells are cyclical and may return.

## Workflow

1. **Choose the action.** Follow an explicit audit, rewrite, or new-version instruction. If the action is unclear, ask the required question and wait for the user's choice.
2. **Read the input fully.** Don't skim. Identify its purpose, audience, variant of English, and existing voice. Density and combinations matter more than any single tell.
3. **Audit.** Use the catalogue to identify contextually relevant tells. Quote or locate the wording, name and briefly explain the category, and suggest what could change. For either rewrite mode, this audit may be internal unless the user also asks to see it.
4. **Estimate density when useful.** An approximate tells-per-100-words figure can help compare drafts, but it is a heuristic, not a detection score. Describe the texture as light, moderate, or heavy. A heavy result does not determine whether a draft can be revised: explain whether the issues are local or widespread and let the user decide whether to revise or start again.
5. **Carry out the chosen mode.** Stop after the findings for **Audit only**. For **Rewrite this document**, revise the supplied text or explicitly authorised source file. For **Create a new version**, copy the source, rewrite only the copy, and verify that the original is unchanged.
6. **Preserve the writer.** In either rewrite mode, preserve facts, technical language, intent, voice, language variant, deliberate style, and rhythm. Address the relevant generic texture without substituting a different set of AI tells.
7. **Self-audit a rewrite.** Check that it remains accurate, natural, and recognisably the same writer. Fix remaining generic texture without polishing away individuality.

## Output format

For **Audit only**, return:

**1. Audit.** A concise list of the relevant tells. For each, include the category, the exact phrase or location, a brief contextual explanation, and a suggested change. Do not flag catalogue items that are natural or necessary in context.

**2. Density estimate (optional).** Give an approximate tells-per-100-words figure and describe it as light, moderate, or heavy when that helps the user. Make clear it is not evidence of authorship.

For either rewrite mode, produce:

**Cleaner rewrite.** A revised version that addresses the relevant tells while preserving meaning and the writer's actual voice. If the user chose **Create a new version**, return the separate version and confirm that the original was left unchanged. If the issues are widespread, explain that a fresh draft may be easier, but still let the user decide how to proceed.

## What this skill does not do

- It does not detect or prove whether a text was AI-generated. AI detectors are unreliable. It reviews surface-level patterns regardless of authorship.
- It does not substitute for human editing. It catches surface tells. It cannot detect hollow thinking or missing voice. Those need a human pass.
- It does not create a person's voice. It removes generic AI texture while preserving voice already present. Pair it with a genuine personal or brand voice guide when one is available.

## Source and credit

- Wikipedia: Signs of AI writing. https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing


Built by Kyle Balmer at AI with Kyle. MIT licensed. Last updated 2026-05-04. Free to use, share, and modify. If the list dates, update it.
