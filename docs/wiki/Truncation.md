# Truncation

**Last updated:** November 12, 2026

What happens when text doesn't fit. One set of rules for every theme, so a cut-off name looks and behaves the same everywhere. Decided as D75.

## The rules

1. **Make room first.** Running text (sentences, descriptions, notes) wraps and is never cut. Truncation is only for short labels in places with a fixed size: names in a list or table, tags, tabs, menu items, track and section names.
2. **Cut at the end, with an ellipsis (…).** One line by default. A card or tile title may run to two lines before it's cut. Never cut in the middle or at the start.
3. **Nothing is lost.** The full text stays in the page, so screen readers read all of it. When the text is cut, the full text shows in a tooltip on hover and on keyboard focus.
4. **Abbreviations come from the content, not the layout.** Use the short name people already use ("Perc" for percussion) as the label itself. CSS never shortens a word on its own.
5. **Never cut a number.** Times, timecode, dates, prices, counts, levels and percentages are never truncated: a cut number reads as a different number. Make room, show less precision (1:12 instead of 01:00:01:12:23), or show fewer labels. A ruler shows every other mark rather than clipping one.
6. **Keep at least three characters.** When a label can't show three characters and the ellipsis, it collapses to a marker (a dot or its icon) that keeps the name in its tooltip and for screen readers.

## In the code

The Text parts (Heading, Body, Label and Note) take `truncate`: the number of lines before the ellipsis. `truncate={1}` is one line. The full text stays in the page, and a `title` shows it on hover only while it's cut. In a control (a button, a tag, a row), the control's own tooltip carries the full name, and its accessible name is the full name.

## In Figma

The Text component's text uses Figma's **Truncate text** setting with **Max lines**, matching `truncate`. Numbers never get it.
