---
description: Ingest a raw dump of GitHub links (with loose category headings) and add them to README.md
---

The user will paste a messy list of GitHub repo URLs, often with free-form category headers scattered through it (e.g. "DESKTOP/OS", "VOICE AGENTS", "TO CLASSIFY"). Your job is to turn that into clean, well-placed entries in `README.md`.

## Steps

1. **Parse the dump.** Extract every `https://github.com/owner/repo` URL. Note any nearby free-form heading the user wrote above each URL — treat it as a *hint* about where they think it belongs, not a binding instruction.

2. **Deduplicate against the existing README.** Read `README.md` and skip any repo already present (match on `owner/repo`, case-insensitive). Report skipped duplicates at the end.

3. **Fetch metadata in one batch.** Use a single `Bash` call that loops over all new repos:
   ```bash
   for r in owner1/repo1 owner2/repo2 ...; do
     echo "=== $r ==="
     gh api "repos/$r" --jq '{full_name, description, language}' 2>&1 || echo "NOT FOUND"
   done
   ```
   Flag anything that 404s or redirects to a different `full_name` (use the canonical name).

4. **Classify against [SCOPE.md](../../SCOPE.md).** For each repo, decide:
   - **In scope?** If it fails the "agent loop runs on user's device" test (e.g. pure cloud SaaS, pure inference engine, IDE-only), exclude it and list it under "Excluded (out of scope)" in your final report with a one-line reason.
   - **Which section?** Map to the existing README sections:
     1. AI Coding Agents (CLI) — first-party vs third-party
     2. Tooling Around Agent CLIs — Session & Task Managers / Orchestrators / Tools & MCP Servers / Context & Data Access
     3. Multi-Agent Frameworks
     4. Harnesses & Specifications
     5. Computer-Use & Agent Operating Systems
     6. Desktop GUIs & Cowork Clones
     7. Personal AI Assistants
     8. Terminal Assistants
     9. Protocols
     10. Wallets & Payments
   - **New section needed?** If several repos in the dump cluster around a theme that doesn't fit any existing section (e.g. "Voice Agents", "Embodied / Robotics", "Mobile Agents", "Memory", "Browser Extensions", "Email Agents", "Research Assistants", "Gateways & Proxies"), propose a new section. Don't create a new section for a single entry unless the user's dump clearly signals it.
   - The user's free-form header is a strong hint but override it if SCOPE.md says otherwise. When in doubt, note the ambiguity in the final report rather than silently guessing.

5. **Insert entries.** For each accepted repo, add an entry in the correct section using the existing format:
   ```markdown
   #### [name](https://github.com/owner/repo)

   ![Stars](https://img.shields.io/github/stars/owner/repo?style=social) ![Last commit](https://img.shields.io/github/last-commit/owner/repo) <other badges>

   <1–2 sentence description, usually derived from the GitHub description>

   **Language:** <lang> · **Author:** [owner](https://github.com/owner)

   ---
   ```
   - Maintain **alphabetical order within each section/subsection**.
   - Only add capability badges (Local, MCP, Tools, Use) when you have evidence from the description — don't guess.
   - Use Type badge (1st-party / 3rd-party) for coding agents in §1.

6. **Update the Table of Contents** if you added any new sections.

7. **Commit and push** in a single commit. Message format:
   ```
   Ingest N entries: <short summary of themes>
   ```

8. **Report back** with:
   - Count of added entries, grouped by section
   - Any new sections created
   - Skipped duplicates
   - Excluded (out of scope) entries with one-line reasons
   - Anything ambiguous you'd like the user to confirm

## Notes

- If the user's dump repeats a URL that's already in the README under a different section, don't move it — just note it as a duplicate.
- If a repo looks archived or dead (`archived: true`, or last commit years old), still add it but mention it in the report.
- Don't invent descriptions — if the GitHub description is empty, use a brief neutral placeholder and flag it in the report.
- Keep capability claims conservative. The SCOPE doc is explicit that badges are best-effort and under-claiming is better than over-claiming.
