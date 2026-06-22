# Install in ChatGPT, Gemini, or Microsoft Copilot

The skill is written for Claude Code / Cowork (drop the `.skill` bundle in and it just works). But the same source files run inside any client that accepts attached project files plus a system prompt, you just attach them by hand instead of using a one-click installer. The setup below uses ChatGPT Projects as the reference; Gemini Gems and Microsoft Copilot Agents follow the same shape.

## ChatGPT (Projects)

1. Clone or download this repository so you have the source files locally.
2. Open ChatGPT, click your name, and create a new **Project**. Name it `airlock AI policy generator`.
3. Upload every file in this folder to the Project:
   - `SKILL.md`
   - `template.html`
   - `examples/sample-vandermeer.html`
   - `examples/sample-vandermeer-inputs.json`
   - `i18n/en.json`, `i18n/nl.json`, `i18n/fr.json`, `i18n/de.json`
4. In the Project's **instructions** field, paste:

   > Follow `SKILL.md` exactly. When you produce the final document, render using `template.html`. Use `examples/sample-vandermeer.html` as the style reference. For non-English output, load the matching `i18n/{lang}.json` for all fixed text.

5. Open a new conversation inside the Project and say:

   > Generate our AI policy.

ChatGPT will start the interview defined in `SKILL.md`.

## Gemini (Gems)

1. Create a new Gem at gemini.google.com/gems.
2. Paste the contents of `SKILL.md` into the **Instructions** field.
3. Attach the rest of the source as knowledge files: `template.html`, the `examples/` folder, the `i18n/` folder.
4. Start the Gem with: `Generate our AI policy.`

## Microsoft Copilot (Agent Builder)

1. Open Copilot Studio or the Copilot Agent Builder in Microsoft 365.
2. Create a new agent. Paste `SKILL.md` into the instructions field.
3. Upload the rest of the folder as knowledge sources.
4. Start with: `Generate our AI policy.`

## Important notes

- **The skill quality scales with the model.** GPT-4o, Gemini 1.5 Pro, and Copilot's GPT-4 backend all handle this well. Smaller or older models will produce a thinner result.
- **The HTML rendering step is the most sensitive part.** If the model struggles to produce `template.html`-shaped output, ask it to re-render with the line: *"Re-render exactly using template.html, do not invent layout."*
- **The chat draft must be approved before HTML generation.** This is baked into `SKILL.md` itself, but if a model skips the validation step, prompt it: *"Show me the full draft in chat first; do not generate any file until I reply approve."*
- **Privacy.** Your conversation goes to whichever provider you use (OpenAI, Google, Microsoft). It does not touch airlock.

## Native Claude experience

If you use Claude (Desktop, Code, or Cowork), use the `.skill` bundle from the Releases page instead. It's one drag-and-drop install, no Project setup. See the main [README](README.md).
