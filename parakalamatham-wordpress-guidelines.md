# ParakalaMatham WordPress Embed Guidelines

Use these defaults for future `parakalamatham.org` web-page work unless the user explicitly asks for a different pattern.

## Required Output Pattern

- Deliver WordPress-safe HTML fragments, not full HTML documents.
- Do not include:
  - `<!DOCTYPE html>`
  - `<html>`
  - `<head>`
  - `<meta>`
  - `<title>`
  - `<body>`
- Deliver a self-contained block that can be pasted inside a WordPress HTML block.

## CSS Scoping Rules

- Scope all CSS to the component wrapper.
- Prefer a unique wrapper class such as `.melkote-page` or another project-specific root.
- Do not style global selectors in a way that leaks into the theme:
  - avoid raw `body`, `html`, `img`, `a`, `p`, `h1`, `h2`, `ul`, `ol`, `figure`
  - if these need styling, scope them like `.component-root img`
- Avoid universal selectors unless also scoped, for example:
  - `.component-root, .component-root *, .component-root *::before, .component-root *::after`

## Layout Defaults

- Assume the page will be embedded inside a theme container that may already constrain width.
- Use a wide desktop layout, but keep responsive collapse for tablets and phones.
- Build mobile behavior directly into the component with CSS breakpoints.
- Use fluid images with `max-width: 100%` and `height: auto`.

## Asset Rules

- Prefer stable full URLs for uploaded images once the final WordPress upload path is known.
- Rely on WordPress-generated resized variants unless specifically requested not to.
- Keep image filenames upload-safe and consistent with the HTML references.

## Content Rules

- Keep placeholders visibly marked during draft stage.
- Keep speculative or unverified facts labeled as tentative.
- When the page is going public, remove internal editorial placeholders unless the user explicitly wants them to remain visible.

## Workflow Rule

- When the user pastes a full HTML page for WordPress review, first check:
  - whether it incorrectly includes document-level tags
  - whether CSS leaks globally
  - whether the layout depends too much on browser/body styles instead of a scoped wrapper
