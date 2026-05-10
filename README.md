# MDN Reference Skill

An extension providing expertise in MDN Web Docs, browser standards, and modern web APIs. Originally built for Gemini CLI, it now includes universal configurations to support **Claude**, **Cursor**, **Cline/RooCode**, and **Windsurf**.

## Features

- **Web Standards Research:** Automated verification of API status and compatibility via MDN.
- **Modernization Patterns:** Guidance on using modern "Baseline" APIs (fetch, IntersectionObserver, etc.).
- **Compatibility Reporting:** Different compatibility blocks for major browsers.

---

## How to Use Across Different Agents

### Gemini CLI
You can install this extension directly from the GitHub repository.

```bash
gemini extensions install https://github.com/vikash-paf/mdn-reference-skill
```
After installation, reload your skills: `/skills reload`.

*Note: This repository is configured for the Gemini CLI Extension Gallery. Adding the `gemini-cli-extension` topic on GitHub will trigger automatic indexing.*

### Claude Projects & Custom GPTs
If you are using Claude (via the web UI) or ChatGPT, you can inject this skill directly into your AI's context:
1. Open the `claude_instructions.md` file in this repository.
2. Copy its contents.
3. Paste it into the "Custom Instructions" or "System Prompt" section of your Claude Project or Custom GPT.

### Cursor IDE
Cursor will automatically pick up the rules if you clone this repository or copy the rule file:
- The `.cursorrules` file at the root automatically directs Cursor's AI to read the MDN guidelines before writing frontend code.

### Cline / RooCode (VS Code)
Cline uses its own rule file to understand workspace constraints:
- The `.clinerules` file at the root directs the AI to follow the exact same MDN workflow.

### Windsurf IDE
Windsurf also supports local agent rules:
- The `.windsurfrules` file automatically enforces the MDN standards workflow when the AI assists you.
