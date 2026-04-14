# survy-agent-skills

Agent skills for the [`survy`](https://github.com/hoanghaoha/survy) Python library — reference documents designed for LLM-based coding assistants (Claude, Copilot, and similar tools) so they can read, understand, and write correct `survy` code without hallucinating parameters or inventing methods.

Each skill is a self-contained directory with a `SKILL.md` entry point plus supporting scripts, references, and sample assets.

---

## 📦 Skills

### `survey-analysis`

Use this skill when working with survey data through the `survy` API — loading CSV/Excel/JSON/SPSS files, handling multiselect questions, computing frequencies and crosstabs, exporting to SPSS, updating labels and value indices, filtering respondents, and related tasks.

Contents:

- **`SKILL.md`** — complete API reference with compact-vs-wide format explanation, JSON schema, and gotchas
- **`references/api_reference.md`** — quick-lookup method signatures
- **`scripts/validate_survey.py`** — check a survey file for missing labels and unset value indices
- **`scripts/batch_export.py`** — export a survey to all formats in one pass
- **`assets/sample_data.csv`** / **`assets/sample_data_compact.csv`** — sample datasets for testing

### `questionnaire-reading`

Use this skill when the user wants to read, parse, or understand a questionnaire design document (`.docx`, `.xlsx`, `.pdf`, or plain text). Produces a standardised `questionnaire-design.md` that captures every question's ID, label, answer options, and routing/skip logic — structured so an agent can later use it to build or update `survy` metadata accurately.

Contents:

- **`SKILL.md`** — input formats, parsing guidance, and the target `questionnaire-design.md` schema
- **`scripts/parse_questionnaire.py`** — starter script for extracting questions from design documents
- **`assets/sample_questionnaire_design.md`** — reference example of the target output format

---

## 🚀 Installation

The skill files are included in the repo under `/skills`. If your AI tool supports skill installation:

```bash
npx skills add https://github.com/hoanghaoha/survy
```

Or clone/ copy the skill directories into your agent's skill location. For Claude Code:

```bash
git clone https://github.com/hoanghaoha/survy-agent-skills.git
cp -r survy-agent-skills/survey-analysis ~/.claude/skills/
cp -r survy-agent-skills/questionnaire-reading ~/.claude/skills/
```

Or place them under a project-local `.claude/skills/` directory. Other agent tools that support the SKILL.md format can load these directly.

---

## 🔗 Related

- **[`survy`](https://github.com/hoanghaoha/survy)** — the Python library these skills describe

---

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.
