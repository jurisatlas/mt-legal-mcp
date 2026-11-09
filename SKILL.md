---
name: mt-legal-mcp-skill
description: Official Malta (MT) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Malta Legal Research & Multi-Tier Case Law Skill (`mt-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Malta (MT)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:MT:CA:2024:100 or Cap. 16`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** Court of Magistrates (Malta & Gozo), Civil Court (First Hall, Commercial Section, Family Section) & Administrative Review Tribunal
   - **Second Instance (Cantonal / Regional / Appellate):** Court of Appeal (Qorti tal-Appell — Superior & Inferior Jurisdiction) & Court of Criminal Appeal
   - **Supreme & Constitutional Instance:** Constitutional Court of Malta (Qorti Kostituzzjonali)
   - **Primary Tiered Database:** eCourts Malta Judgments Online (ecourts.gov.mt — Magistrates, Civil, Commercial, Appellate & Constitutional Courts) (`https://ecourts.gov.mt/onlineservices/Judgements`)
