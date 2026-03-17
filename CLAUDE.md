# Xloud Documentation Guidelines

Before creating or editing any documentation page, read and follow these guidelines completely.

## Purpose

These rules govern how all Xloud documentation pages are written. Every `.mdx` file produced must conform to this standard — no exceptions.

---

## Branding Rules

- Replace ALL mentions of **OpenStack** with **Xloud**
- Replace ALL mentions of **KVM** with **hypervisor**
- Maintain brand consistency in headings, body text, command explanations, and cross-references
- Product name is **Xloud** (not xloud, XLOUD, or X-loud)

---

## Document Structure

Every page must follow this structure (omit sections only if truly not applicable):

```
1. Title (frontmatter)
2. Overview
3. Architecture / Concepts  (if applicable)
4. Prerequisites
5. Configuration           (always with GUI/CLI Tabs)
6. Validation / Verification
7. Best Practices          (if applicable)
8. Troubleshooting         (if applicable)
```

---

## Frontmatter Template

```mdx
---
title: "Page Title"
description: "One-sentence description of what this page covers."
---
```

---

## Mandatory Mintlify Components

Use these components extensively — never write plain walls of text.

### Tabs (GUI vs CLI toggle) — REQUIRED in Configuration section

```mdx
<Tabs>
  <Tab title="GUI">
    <!-- GUI steps here -->
  </Tab>
  <Tab title="CLI">
    <!-- CLI steps here -->
  </Tab>
</Tabs>
```

### Steps — for all procedures

```mdx
<Steps>
  <Step title="Step Title">
    Step content here.
  </Step>
</Steps>
```

### Callouts

```mdx
<Note>Informational note.</Note>
<Warning>Critical warning — data loss, irreversible action, etc.</Warning>
<Tip>Optional best practice or shortcut.</Tip>
<Info>Background context or supporting detail.</Info>
```

### Code blocks

```mdx
<CodeGroup>
  ```bash title="Command Name"
  xloud command --flag value
  ```
</CodeGroup>
```

### Accordions — for optional deep explanations

```mdx
<Accordion title="Section Title">
  Content that is useful but not essential to the main flow.
</Accordion>
```

### Cards — for feature highlights or use cases

```mdx
<CardGroup cols={2}>
  <Card title="Feature Name" icon="icon-name">
    Short description.
  </Card>
</CardGroup>
```

### Tables — wherever structured comparison or reference data exists

```mdx
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| name      | string | Yes    | Resource name |
```

---

## GUI Section Rules

- If GUI steps exist in source → rewrite them properly using `<Steps>`
- If GUI steps are NOT in source → create realistic steps based on Xloud platform conventions
- If GUI is not applicable → state: _"This operation is performed via Xdeploy."_ then show Xdeploy steps

## CLI Section Rules

- Rewrite all commands cleanly — no unnecessary flags or clutter
- Add a one-line explanation below each command block (not verbose)
- Use `<CodeGroup>` for all code blocks
- Never mix GUI and CLI in the same step sequence

---

## Writing Style

| Do | Don't |
|----|-------|
| Enterprise tone (AWS / Azure style) | Community tutorial tone |
| Clear, direct, precise language | Storytelling or casual phrasing |
| "The instance is created." | "You guys can now create your instance!" |
| Second person singular "you" sparingly | "we", "you guys", "let's" |
| Concise but complete sections | Verbose over-explanations |

---

## Enhancements to Always Add

- Add validation steps even if absent from the source
- Add `<Note>` or `<Tip>` callouts where the source is vague or silent
- Improve flow — reorder steps if the source ordering is illogical
- Fill gaps in the source with realistic, accurate content
- Keep formatting consistent — same heading levels, same component patterns

---

## Output Checklist

Before finalizing any doc page, verify:

- [ ] All "OpenStack" replaced with "Xloud"
- [ ] All "KVM" replaced with "hypervisor"
- [ ] Frontmatter present with title + description
- [ ] Structure follows the 8-section template
- [ ] Configuration section uses `<Tabs>` with GUI and CLI tabs
- [ ] Procedures use `<Steps>` / `<Step>`
- [ ] At least one callout (`<Note>`, `<Tip>`, `<Warning>`, or `<Info>`) used
- [ ] Code blocks use `<CodeGroup>`
- [ ] Tables used where structured data exists
- [ ] Validation / Verification section present
- [ ] Enterprise tone throughout — no casual language
- [ ] Clean MDX — no raw text dumps, proper spacing and hierarchy
