# AIKDNA — KDNA Open Protocol & Toolchain

[Website (`aikdna.com`)](https://aikdna.com) · [中文官网 (`aikdna.cn`)](https://aikdna.cn) · [Case Studies & Benchmarks](https://aikdna.com/en/explore/systems) · [中文案例与实测](https://aikdna.com/zh/explore/systems) · [KDNA Reader (macOS)](https://aikdna.com/en/downloads)

**KDNA (`.kdna`) is an open, portable, permanently account-free file format for human thinking, judgment, and taste.**

Each `.kdna` work packages structured judgments—question, core claim, reasoning, trade-offs, stop boundaries, and common misuses—into a versioned file that humans can read directly in **KDNA Reader** and AI Agents can load selectively (`catalog` → `exact_selection`) with supporting premises and constraints kept intact.

---

## Active Public Repositories (Container `0.6.0`)

| Repository | Package / Releases | Role |
| :--- | :--- | :--- |
| [`aikdna/kdna`](https://github.com/aikdna/kdna) | `@aikdna/kdna-core@0.37.11` · `@aikdna/kdna-read@0.13.5` | Open Container `0.6.0` specification, schemas, conformance suites, Core admission/crypto SDK, and Selective Read SDK ([中文 README](https://github.com/aikdna/kdna/blob/main/README.zh.md)) |
| [`aikdna/kdna-cli`](https://github.com/aikdna/kdna-cli) | `@aikdna/kdna-cli@0.45.2` | Official CLI (Node.js `>=22`, offline & account-free): `init`, `validate-input`, `create`, `protect`, `unprotect`, `inspect`, `validate`, `read`, `diff`, `source-open`, `source-pack`, `convert` |
| [`aikdna/kdna-skills`](https://github.com/aikdna/kdna-skills) | `@aikdna/kdna-mcp-server@0.8.4` | Agent Skills (`kdna-creator`, `kdna-loader`) for Claude Code / Cursor / Codex / Antigravity and optional local stdio MCP adapter |
| [`aikdna/kdna-assets`](https://github.com/aikdna/kdna-assets) | [GitHub Releases](https://github.com/aikdna/kdna-assets/releases) | Official public `.kdna` works: bilingual *KDNA Whitepaper* `v1.0.2` (`CC BY 4.0`, 45 judgments) plus bilingual `human-writing-system` `v1.0.1` and `code-review-system` `v1.0.2` (`Apache-2.0`, 22 judgments each) |
| [`aikdna/kdna-reader-releases`](https://github.com/aikdna/kdna-reader-releases) | [`v0.3.4-build30`](https://github.com/aikdna/kdna-reader-releases/releases/tag/v0.3.4-build30) | Signed & Apple-notarized macOS Apple Silicon **KDNA Reader** binary releases and SHA-256 checksums (free offline built-in Whitepaper & local `.kdna`; optional free `KDNA ID` for multi-tab comparison) |

---

## Try One Command (Node.js `>=22`, Account-Free)

```sh
# Download an official bilingual exemplar and browse its 22-judgment catalog
curl -fsSLo kdna-code-review-system-1.0.2.en.kdna \
  https://aikdna.com/downloads/exemplars/v1/kdna-code-review-system-1.0.2.en.kdna
npx -y @aikdna/kdna-cli@0.45.2 read kdna-code-review-system-1.0.2.en.kdna \
  --mode catalog --allow-read --format human
```

---

## Observed 192-Run Benchmark Summary & Honest Trade-Offs

Across two public bilingual exemplars ([Overview & Full Artifact Table](https://aikdna.com/en/explore/systems) · [中文总览](https://aikdna.com/zh/explore/systems) — `2` models × `4` arms × `12` leak-free cases per domain, `192` total runs):

- **Human-Sounding Writing (`v1.0.1`, 96 runs · [Case Study](https://aikdna.com/en/explore/human-writing)):** Selective Read achieved **`23/24` (`95.8%`)**, matching equal-length full Markdown (`23/24`, vs `11/24` no-system / `12/24` short prompt), cutting Step-3 context **`-85.2%`** and total input tokens **`-39.7%` to `-45.2%`**.
- **Code Review (`v1.0.2`, 96 runs · [Case Study](https://aikdna.com/en/explore/code-review)):** Defect & P0 strict accuracy reached **`17/18` (`94.4%`)** (overall literal-strict **`20/24`** vs full Markdown **`22/24`**), cutting Step-3 context **`-84.0%`** and total input tokens **`-52.6%` to `-54.5%`**.
- **Trade-offs & Counterexample:** Selective Read adds **1 selection round-trip (`+8–38s`)**, and on Group 3 good-PR counterexamples `GPT-6-Luna` produced false blocks where the graph lacked a `conflicts_with` edge between `#19` and `#01`.

---

## Links & Security

- **Start Here:** [`aikdna/kdna` Documentation (EN)](https://github.com/aikdna/kdna/blob/main/docs/start-here.md) · [中文文档](https://github.com/aikdna/kdna/blob/main/docs/start-here.zh.md)
- **Community Discussions:** [`aikdna/kdna/discussions`](https://github.com/aikdna/kdna/discussions)
- **Security Reporting:** [`aikdna/kdna/SECURITY.md`](https://github.com/aikdna/kdna/blob/main/SECURITY.md)
