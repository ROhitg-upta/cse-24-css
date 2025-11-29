## Repository overview

This is a small static HTML/CSS exercise repository. Pages are stand-alone, single-file demos that teach basic CSS concepts (box model, floats, inline-block, simple layout). There is no build system or framework.

Key files/directories
- `amazon.html`, `boxmodel.html`, `inlineblock.html`, `float.html` — demo pages. Each contains its own `<style>` block and markup.
- `thumbnail-1.webp` — an image referenced by `float.html`.
- `cse-24-css/` — present but currently empty in this workspace (place for extra assets or exercises).

Why this structure matters for an AI agent
- Changes should favor small, localized edits to HTML files (these are the project’s unit of composition).
- Avoid adding heavy tooling or changing global editor settings. The author expects simple, copy-editable HTML/CSS files.

Project-specific patterns and conventions
- Single-file pages: styles are embedded in a `<style>` block at the top of each HTML file. When adding new styles, prefer the same pattern unless you add a new shared CSS file and update pages explicitly.
- `.outer` container: most pages use a top-level `.outer` container with `width: 80%`, `margin: auto`, and a border — follow this for visual consistency when creating new examples.
- Naming: file and class names use lowercase and simple words (kebab-case preferred for filenames, e.g., `new-example.html`).
- Images live in the repository root and are referenced by relative path (e.g., `thumbnail-1.webp`). Do not change image filenames unless also updating references.

How to run / preview locally
- There is no build step. Open any `.html` file in a browser to preview.
- Recommended quick previews:
  - Use VS Code Live Server extension (Start Live Server) to auto-reload pages.
  - Or run a simple local server from PowerShell:

    python -m http.server 8000

  then open `http://localhost:8000/` in the browser.

Editing guidance for the AI agent
- Keep edits minimal and local: modify a single `.html` demo unless the user asks for a cross-file change.
- Preserve DOCTYPE and language attributes (`<!DOCTYPE html>`, `<html lang="en">`).
- When adding examples, follow the existing visual structure: include an `.outer` wrapper, a `<style>` block, and semantic markup (headings, paragraphs, `<footer>` when needed).
- If adding CSS that affects flow (floats, clears), prefer non-invasive fixes that preserve the original demonstration intent. Example: if a footer is intended to sit below floated content, add a clearfix to the page rather than removing the floated element.

Examples pulled from the codebase (use these as templates)
- `float.html`: demonstrates an image floated left with text wrapping. The file references `thumbnail-1.webp` and places a `<footer>` inside `.outer` — use the page as a canonical float/clear example.
- `inlineblock.html`: contains repeated product cards (`.book`, `.headphone`, `.watch`) implemented with `display: inline-block` — reuse the `.book` pattern for additional product cards.

When to create new files vs edit existing ones
- Create a new HTML file when adding a distinct lesson or demo (name it `lesson-name.html`).
- Edit an existing file to fix typos, small style tweaks, or to expand the demonstrated example in-place.

What not to change
- Do not introduce build tooling, package manifests, or dependency managers for this repository.
- Do not rename or move assets (images) without updating all references.

If you need more context
- Ask the maintainer whether they want a shared CSS file or prefer single-file demos. Also confirm where to place new assets (root vs `cse-24-css/`).

If you edit files, include a short commit message that names the file(s) changed and the purpose (e.g., `Add clearfix to float.html to demonstrate footer clearance`).

— End of instructions —