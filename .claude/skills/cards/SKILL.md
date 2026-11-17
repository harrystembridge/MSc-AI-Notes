---
name: cards
description: Make flashcards from lecture content (PDF slide pages, note text, or screenshots) in the vault's CARD callout format. Use when the user asks for cards, flashcards, or revision questions for some content.
---

# Flashcard creation

## Output rules
- **Always output the cards in chat, inside one fenced code block, for the user to copy-paste.**
- **Never edit or append to vault files** unless the user explicitly asks.
- Brief one-line note after the block only if something was ambiguous or unreadable. No other commentary.

## Card format
Exactly this, with a blank line between cards:

```
> [!CARD] Question
> Answer
```

- Use LaTeX in `$...$` for maths (e.g. `$\sum_{i=1}^n w_i = 1$`).
- One fact per card. Questions must be self-contained (name the concept, don't say "this" or "the slide").
- Keep answers short; include the formula plus a few words defining its symbols where useful.
- Cover everything on the page: definitions, formulas, conditions, and the intuition/interpretation. Don't invent content that isn't in the source.
- Split multi-part results (e.g. a formula for total return and one for rate of return) into separate cards.

## Getting the source content
The user usually selects an embed like `![[CF - Lecture 5.pdf#page=7|...]]` in a note. Resolve the file by name from the vault root (`find . -name "<file>.pdf"`) and use the page number after `#page=`.

Try in order:
1. Read tool with `pages: "<n>"` (needs `pdftoppm`/poppler).
2. `pdftotext -f <n> -l <n> -layout <file> -` if poppler is installed.
3. macOS fallback: a Swift script using PDFKit (`PDFDocument.page(at: n-1)`) to print `.string` and render a PNG thumbnail to `/tmp`, then Read the PNG to check the maths. Keep scripts in `/tmp`, not the vault.

If the user pastes text or a screenshot instead, use that directly. If none of the above works, say so briefly and ask for a paste or screenshot.

Also check the surrounding note text (via the linked file) for context, such as definitions of symbols given just before the embed.
