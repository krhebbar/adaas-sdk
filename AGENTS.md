# 🤖 AGENTS.md

## Purpose
This file defines the operating model for AI agents and human contributors responsible for generating and maintaining **TypeScript SDK documentation**. It establishes **goals, scope, and guardrails** so that automation produces clear, accurate, and human/agent-friendly docs in the **Fumadocs** format.

---

## 🎯 Core Objective
- Generate **comprehensive, human-readable documentation** for the TypeScript SDK.  
- Ensure all docs are **grounded in the actual SDK codebase** (no assumptions, no external knowledge).  
- Use **Fumadocs MDX components** for structure and consistency.  
- Provide a developer-first experience that is **easy to scan, easy to use, and actionable**.

---

## 📂 Scope of Work

### ✅ Allowed Files & Directories
- `REFERENCE.md` `README.md`  `CONTRIBUTING.md`
- `src/` → TypeScript SDK source files (primary ground truth).  
- `content/docs` → output location for SDK documentation.  

### ❌ Out of Scope
- Do not alter or generate code in the SDK itself.
- Do not document depricated interfaces or sdk features.
- Do not use external TypeScript/SDK knowledge not present in repo.  
- Do not modify build/infrastructure configs.  

---

## 🧭 Operating Guidelines

### Documentation Rules
- Every public **class, method, function, and type** must have a doc entry.  
- Documentation must include:  
  - **Name & Signature** (directly from SDK).  
  - **Description** (human-friendly, based only on code evidence).  
  - **Parameters** (with types, defaults, required/optional).  
  - **Return values**.  
  - **Error cases** (with verbatim error messages).  
  - **Usage examples** (based on repo patterns, never invented).  
- Use **Fumadocs MDX format**, including headless + UI components:  
  - [Fumadocs Headless Components](https://fumadocs.dev/docs/headless/components)  
  - [Fumadocs UI Components](https://fumadocs.dev/docs/ui/components)  

### Writing Standards
- **Voice**: Developer-first, concise, plain language.  
- **Terminology**: Match exact identifiers from SDK (no renaming).  
- **Formatting**:  
  - Code fences for snippets.  
  - Lists for parameters.  
  - Callouts for warnings/errors.  
- **Frontmatter required**: Each doc must start with `title` + `description`.  

---

## 📋 Validation Protocol
Before finalizing, agents must confirm:
- [ ] Every SDK function/class/type in `src/` is documented.  
- [ ] Parameter lists match exact type definitions.  
- [ ] Return values are documented accurately.  
- [ ] Error messages copied verbatim.  
- [ ] Usage examples reflect actual code patterns.  
- [ ] Docs render correctly in Fumadocs.  
- [ ] No external/speculative content added.  

---

## 🛡️ Guardrails
- **Ground Truth Only**: All content must come directly from SDK source.  
- **No Speculation**: Missing info must be left as placeholder/flagged.  
- **Consistency First**: Docs must be uniform across all SDK modules.  
- **Evidence Required**: Cite file paths and line numbers when referencing SDK code.  

---

## 🚀 Execution Flow
1. Identify SDK module or file in `src/`.  
2. Extract public API surface (classes, functions, types).  
3. Generate doc entry in **Fumadocs MDX format**.  
4. Apply Writing + Validation rules.  
5. Place in `content/docs/adaas-sdk/`.  
6. Commit with descriptive message (e.g., `docs: add SDK docs for auth module`).  

---

## 📌 Success Definition
- 100% of SDK public API surface documented.  
- Docs are accurate, grounded, and developer-friendly.  
- SDK docs structured and formatted with Fumadocs components.  
- No assumptions, no missing coverage, no inconsistencies.  

---

## 📚 Additional References
- [Fumadocs Headless Components](https://fumadocs.dev/docs/headless/components)  
- [Fumadocs UI Components](https://fumadocs.dev/docs/ui/components)  
