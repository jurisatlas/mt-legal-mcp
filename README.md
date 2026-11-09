# Malta Legal Research MCP Server (`mt-legal-mcp`)

**[Malti](#lang-mt) | [English Documentation](#english-documentation)**

---

<a id="lang-mt"></a>
## Server MCP tal-Liġijiet u l-Ġurisprudenza ta' Malta (`mt-legal-mcp`) — Malti

### Dwar dan ir-Repożitorju

Dan ir-repożitorju jipprovdi server Model Context Protocol (MCP) li jgħaqqad l-applikazzjoni tal-IA tiegħek (Claude Desktop, Cursor, Windsurf, VS Code / Copilot, Cline jew Antigravity) direttament ma' Legislation Malta (`legislation.mt`) u s-sistema tas-sentenzi tal-Qrati ta' Malta (`ecourts.gov.mt` — Qorti tal-Maġistrati, Qorti Ċivili, Qorti tal-Appell u l-Qorti Kostituzzjonali).

### Installazzjoni Mgħaġġla (Għażla tal-Applikazzjoni tal-IA)

1. **Niżżel:** Ikklikkja fuq **`<> Code` -> `Download ZIP`** fin-naħa ta' fuq u oħroġ il-folder fuq il-kompjuter tiegħek.
2. **Iftaħ l-Installatur:** Ikklikkja darbtejn fuq **`Click_Here_To_Install_Windows.bat`** (Windows) jew **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Agħżel il-Klijent tal-IA:** Immarka l-programmi tal-IA li tuża, ikklikkja installa u erġa' ibda l-applikazzjoni tal-IA tiegħek.

**Nota ta' Sigurtà:** L-installatur jaħdem biss fil-modalità ta' qari (read-only) u ma jmiss l-ebda fajl personali fuq il-kompjuter tiegħek.

### Ġerarkija tal-Qrati u Sorsi Uffiċjali

| Grad Ġudizzjarju | Qrati Koperti |
|:---|:---|
| **L-Ewwel Grad (Qorti tal-Maġistrati & Qorti Ċivili)** | Court of Magistrates (Malta & Gozo), Civil Court (First Hall, Commercial Section, Family Section) & Administrative Review Tribunal |
| **It-Tieni Grad (Qorti tal-Appell)** | Court of Appeal (Qorti tal-Appell — Superior & Inferior Jurisdiction) & Court of Criminal Appeal |
| **Il-Qorti Kostituzzjonali ta' Malta** | Constitutional Court of Malta (Qorti Kostituzzjonali) |

- **Legislation Malta Official Portal (legislation.mt):** [https://legislation.mt](https://legislation.mt) (`legislation.mt`, `justiceservices.gov.mt`)
- **eCourts Malta Judgments Online (ecourts.gov.mt — Magistrates, Civil, Commercial, Appellate & Constitutional Courts):** [https://ecourts.gov.mt/onlineservices/Judgements](https://ecourts.gov.mt/onlineservices/Judgements) (`ecourts.gov.mt`, `justiceservices.gov.mt`, `legislation.mt`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Malta (MT)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Malta**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | Court of Magistrates (Malta & Gozo), Civil Court (First Hall, Commercial Section, Family Section) & Administrative Review Tribunal |
| **Tier 2 — Regional / Cantonal / Appellate** | Court of Appeal (Qorti tal-Appell — Superior & Inferior Jurisdiction) & Court of Criminal Appeal |
| **Tier 3 — Supreme & Constitutional** | Constitutional Court of Malta (Qorti Kostituzzjonali) |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Legislation Malta Official Portal (legislation.mt) — [https://legislation.mt](https://legislation.mt)
  - *Indexed Legislation Domains:* `legislation.mt`, `justiceservices.gov.mt`
- **Court Decisions & Jurisprudence Archives:** eCourts Malta Judgments Online (ecourts.gov.mt — Magistrates, Civil, Commercial, Appellate & Constitutional Courts) — [https://ecourts.gov.mt/onlineservices/Judgements](https://ecourts.gov.mt/onlineservices/Judgements)
  - *Indexed Judicial & Open Case Law Domains:* `ecourts.gov.mt`, `justiceservices.gov.mt`, `legislation.mt`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Malta. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Malta. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Malta. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "mt-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/mt-legal-mcp/archive/refs/heads/main.zip",
        "mt-legal-mcp"
      ]
    }
  }
}
```
</details>
