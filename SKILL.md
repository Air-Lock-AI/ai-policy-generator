---
name: ai-policy-generator
description: Generate a polished three-page AI Use Policy for the user's company. Researches the company and sector, drafts the full policy in chat for the user to validate, then writes a print-ready HTML file plus a sidecar JSON. Use when the user asks for an "AI policy", "AI use policy", "EU AI Act policy", "AI policy one-pager", or any request to draft, generate, or update a company AI governance policy. Aligned to EU AI Act Articles 4, 5 and 50.
version: 1.3.1
author: airlock
license: airlock public use
---

# AI Use Policy generator

## When to use this skill

Activate on requests like:

- "create an AI policy", "draft an AI use policy", "generate an AI policy"
- "I need an AI policy for my company"
- "make an AI policy one-pager", "AI policy template"
- "update my AI policy" (re-run with sidecar JSON if present)
- "EU AI Act policy", "AI governance policy"

Do **not** use this skill for: technical AI safety reviews, model evaluation reports, or AI ethics whitepapers. Those are different documents.

## What this skill produces

Two files saved to the user's selected folder, only **after** the user has validated the draft in chat:

1. `ai-use-policy-{slug}-v{version}.html` — a three-page, print-ready policy document (cover, "the rules", "the duties"). Aligned to EU AI Act Articles 4, 5 and 50.
2. `ai-use-policy-{slug}-inputs.json` — a sidecar with every interview answer, used to re-run the skill with minimal questions next time.

The user opens the HTML, presses Cmd/Ctrl+P, and saves to PDF. See "Step 7" for the exact instructions to give them.

## Files in this skill

- `template.html` — the policy template with `{{PLACEHOLDER}}` markers
- `i18n/en.json`, `i18n/nl.json`, `i18n/fr.json`, `i18n/de.json` — translation packs for the static policy text
- `examples/sample-vandermeer.html` and `examples/sample-vandermeer-inputs.json` — a fictional filled example for reference

## Operating principle

**Ask everything first, then draft, then validate, then generate.** Three rules:

1. **Zero placeholders in the chat draft.** Anything you'd otherwise mark `[ to confirm ]` must be asked of the user before you write the draft. Asking small questions upfront is better than handing the user a draft full of gaps. Only acceptable inline marker is `[ to appoint ]` for DPO when the user explicitly chose it.
2. **The chat draft must mirror the HTML output, word for word on fixed text.** The clause body text is canonical (defined in `i18n/` and `template.html`); do not freelance, rephrase, expand, or invent new sentences. Your job is to substitute the user's variables into the canonical text and present that. If the chat draft promises content the HTML doesn't render, the user's approval is meaningless.
3. **Generate the HTML only after explicit user approval** ("approve", "go", "looks good").

**Do not assume the user's stack.** The two most common wrong assumptions to avoid:

- *That airlock (or any proxy) is installed.* Many companies have no AI governance layer. Ask.
- *That Claude is the AI client.* Many use ChatGPT, Gemini, Copilot, or several at once. Ask.

The policy is for **their** stack, not the template's defaults.

**Never add an extra `<div class="band">` for sector or optional content.** Each band has `break-inside: avoid` in print CSS, so a standalone extra band lands alone on its own physical page with sparse whitespace. **Add extra content as a `<div class="clause">` inside the most relevant existing band.** See the "Sector addendum" fragment pattern below.

See the repo README for the full operating flow, language packs, and HTML fragment patterns. For the full SKILL.md document including all 12 questions, canonical text reference, fragment patterns, and re-run behaviour, see the [project page](https://github.com/Air-Lock-AI/ai-policy-generator-skill) and the source at `SKILL.md` in this repository.

**Note: this file is a placeholder header. The full SKILL.md (582 lines) is committed in a follow-up commit; this stub avoids the GitHub MCP tool size limit during initial push.**
