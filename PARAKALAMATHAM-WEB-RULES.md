# ParakalaMatham Web Rules

Apply these defaults for pages intended for `parakalamatham.org` unless explicitly told otherwise.

## Default Delivery Mode
- Do **not** build a full standalone website or full HTML document.
- Build a **custom HTML fragment** intended to plug into an existing WordPress page.
- Assume the WordPress page template is **`Unboxed Content`**.

## Required Technical Pattern
- Output must be safe for a WordPress HTML block.
- Do not include:
  - `<!DOCTYPE html>`
  - `<html>`
  - `<head>`
  - `<meta>`
  - `<title>`
  - `<body>`
- Keep CSS scoped to the component wrapper so it does not leak into the site theme.

## Layout Assumption
- The surrounding page shell, header, footer, and site navigation already exist.
- The custom block should supply only the content section for that page.
- Responsiveness must be built into the embedded block itself.

## Review Checklist
- Is this an embeddable fragment rather than a full document?
- Is it compatible with the `Unboxed Content` page template?
- Is all CSS scoped locally?
- Does it avoid interfering with global WordPress / theme styles?
