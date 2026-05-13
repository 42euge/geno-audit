# geno-audit — Ecosystem Compliance Auditor

`geno-audit` validates that geno-* repos meet the conventions required for installation and management by `geno-tools`. Auditing is infrastructure, not optional — every ingestion path (public registry, enterprise namespace, direct URL) gates through this checklist.

## Skills

| Skill | Slash command | Purpose |
|-------|---------------|---------|
| geno-audit | /geno-audit | Full compliance audit with auto-fix and PR creation |

## Audit sections

1. `.geno` directory convention
2. Manifest (`genotools.yaml`)
3. SKILL.md content and frontmatter
4. Skill nomenclature
5. Agent instruction files (GENO.md, CLAUDE.md, etc.)
6. Documentation (`docs/`, `mkdocs.yml`)
7. Repo hygiene
8. Agent-agnostic language
9. Installation compliance
10. Ecosystem freshness
11. Command prefix aliasing
12. Single source of truth enforcement
13. Skill observability (trace emission, context loading)

## Tiers

- **Required (FAIL)** — blocks installation
- **Recommended (WARN)** — blocks public registry, advisory for enterprise
- **Optional (INFO)** — informational

## Repo structure

```
geno-audit/
├── GENO.md
├── SKILL.md -> skills/geno-audit/SKILL.md
├── CLAUDE.md
├── genotools.yaml
└── skills/
    └── geno-audit/SKILL.md
```

Previously lived inside `geno-tools` at `skills/geno-audit/`. Extracted because the audit skill is substantial (693 lines) and evolves independently of the package manager.
