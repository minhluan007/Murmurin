# Cursor Rules for Haravan Theme (Auto + Composer + Token Efficient)

## 1. Core Objective

Priority order:

1. Correctness
2. Stability
3. Maintainability
4. Token efficiency

---

## 2. Context Efficiency (CRITICAL)

Before acting:

- Read ONLY relevant parts of code
- DO NOT scan entire project unless necessary
- Focus on:
  - current file
  - directly referenced snippets
  - related JS/CSS if clearly linked

IGNORE:

- unrelated sections
- unused snippets
- large schema blocks unless needed

---

## 3. Minimal Thinking Protocol

Model MUST:

- Avoid verbose reasoning
- Do NOT explain internal thinking
- Use short decision logic

Example:
BAD → long explanation
GOOD → "Use variant price to fix dynamic update"

---

## 4. Minimal Change Rule

STRICT:

- Edit smallest possible unit:
  - single line > block > file

- NEVER:
  - rewrite full file
  - reformat code
  - touch unrelated logic

---

## 5. Output Compression (VERY IMPORTANT)

### Required format:

1. Files changed (short list)

2. Diff only (no full code)

Example:

- {{ product.price }}

* {{ product.selected_or_first_available_variant.price }}

---

### DO NOT:

- explain obvious changes
- repeat unchanged code
- add comments unless necessary

---

## 6. Smart Skipping Strategy

SKIP explaining if:

- change is trivial
- pattern is standard Haravan

ONLY explain if:

- logic is non-obvious
- potential side effects exist

---

## 7. Anti-Hallucination Rules

NEVER:

- invent Liquid objects
- assume variables exist

If unsure:

- fallback safely

{% if product %}
{{ product.title }}
{% endif %}

---

## 8. Haravan Safety Rules

### Liquid

- Always null-check
- Avoid deep nesting

### Schema

- NEVER:
  - change id
  - remove fields

### JS

- No global scope
- No heavy logic

---

## 9. Multi-file Editing Control

Only allow multi-file changes if:

- clearly required

Otherwise:

- keep to single file

---

## 10. Destructive Guard

NEVER:

- delete files
- rewrite sections
- modify checkout logic

---

## 11. Token Optimization Rules

### Reduce token usage by:

- Short responses
- No repetition
- No restating problem
- No long explanations

---

### Prefer:

✔ inline fix
✔ diff format
✔ minimal text

---

### Avoid:

✘ full file output
✘ verbose explanation
✘ duplicated code

---

## 12. Self-Check (Lightweight)

Before output:

- Is change minimal?
- Is it safe?
- Is response short?

If YES → output immediately

---

## 13. Decision Strategy

If multiple solutions:

- choose:
  - least code
  - least risk
  - least token

---

## 14. Performance Awareness

- Avoid adding JS unless necessary
- Prefer Liquid where possible
- Avoid repeated DOM queries

---

## 15. Reusability

If duplication detected:

- suggest briefly
- DO NOT implement unless asked

---

## 16. Response Style

- concise
- direct
- diff-first
- no filler text

---

## 17. Golden Rules

Fix only what is broken
Do not over-explain
Less tokens = faster + safer
