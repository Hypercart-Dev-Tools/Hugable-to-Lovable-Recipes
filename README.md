# Hugable Lovable Recipes
Makes your Lovable code hugable for users.

This doc/system can be used by **non-technical users, rapid prototypers, and senior developers**.

## How to Use This System

### With Lovable AI:

**Step 1: Upload AGENTS.md**
Upload the AGENTS.md file into Lovable chat before requesting your first draft.

**Step 2: Instruct Lovable to Follow the Guide**
After uploading, paste this prompt into chat:

```
Please include AGENTS.md in the repo and follow the checklist-driven
architecture in AGENTS.md for all code you generate.
```

**Step 3: Audit First Draft**
Request a compliance audit against the compliance matrix:
```
Please audit the code against Section 0.1 (Compliance Matrix) in AGENTS.md
and report any violations.
```
See: [Section 0.1 (Compliance Matrix)](./AGENTS.md#01-compliance-matrix-living-dashboard)

**Step 4: Each Build Cycle**
Reset checkboxes in Section 0.1 and update "Last Audited" date in AGENTS.md header.

### With Other AI Assistants (Cursor, GitHub Copilot, Augment, etc.):
1. **Setup:** Add AGENTS.md to your project root
2. **During development:** Reference it in prompts: "Follow architecture rules in AGENTS.md"
3. **Before commits:** Manually verify compliance using Section 0.1 checklist
4. **When breaking rules:** Document in Section 13 (Changelog)

See [AGENTS.md Section 0](./AGENTS.md#0-how-to-use-this-doc) for detailed workflow.

## Architecture

This project follows a **checklist-driven architecture** approach. All architectural decisions, design patterns, and development workflows are documented in:

📋 **[AGENTS.md](./AGENTS.md)** - Checklist-Driven Architecture Guide for Lovable and other AI agents.

The AGENTS.md document provides:
- Pre-build, build, and post-build checklists
- SOLID principles applied to this stack
- State management patterns
- CMS content management guidelines
- Continuous audit and improvement processes

## Tech Stack Assumptions

- **Frontend**: React + TypeScript + Vite
- **Backend**: Supabase (database + auth + edge functions)
- **State Management**: Zustand
- **UI Components**: Component-based with unified layout system

## Why This System Works

This architecture guide is built on **proven software engineering principles** that have stood the test of time over decades:

### **SOLID Principles**
- **Single Responsibility**: Each component, service, and store has one clear purpose
- **Open/Closed**: Extend behavior through composition, not modification
- **Liskov Substitution**: Implementations are swappable without breaking contracts
- **Interface Segregation**: Small, focused interfaces prevent unnecessary dependencies
- **Dependency Inversion**: Depend on abstractions, not concrete implementations

### **DRY (Don't Repeat Yourself)**
- One canonical implementation per behavior (one layout system, one auth source, one CMS pattern)
- Service layers eliminate duplicate data access logic
- Typed contracts prevent reimplementation of the same logic

### **State Hygiene**
- Clear separation: local UI state vs. shared state vs. persisted data
- Explicit async state modeling (`idle | loading | success | error`)
- No duplicate writable copies of the same entity

### **Observability & Error Handling**
- Standardized error contracts across all boundaries
- Telemetry at every async operation
- Normalized error categories for consistent UX

### **Continuous Verification**
- Compliance matrix (Section 0.1) provides measurable checkpoints
- Violations log (Section 13) creates a learning feedback loop
- Automated + manual checks prevent architectural drift

**Result:** Maintainable, testable, and scalable codebases that AI assistants and human developers can confidently extend without introducing technical debt.

## Getting Started

```bash
# Install dependencies
bun install

# Run development server
bun run dev

# Type checking
bun run typecheck

# Linting
bun run lint

# Tests
bun run test

# Database diff
supabase db diff
```

## License

**Code:** This project's code is available under standard open-source terms.

**Documentation (AGENTS.md):**
Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Creative Commons Attribution 4.0 International)
© 2026 Hypercart DBA Neochrome, Inc.

When sharing or adapting AGENTS.md, you must:
- Credit "Hypercart DBA Neochrome, Inc." as the original author
- Provide a link to the CC BY 4.0 license
- Indicate if changes were made
- Not remove attribution notices

---

For detailed architectural guidelines and development checklists, see **[AGENTS.md](./AGENTS.md)**.
