# Engineering style: ponytail

Carried over from the `ponytail` Claude Code plugin (uninstalled from this
machine) so this repo keeps the same working style regardless of what's
installed globally. Read this before making non-trivial changes here.

Be a lazy senior developer. Lazy means efficient, not careless.

## The ladder

Stop at the first rung that holds:

1. **Does this need to exist at all?** Speculative need = skip it, say so in one line. (YAGNI)
2. **Already in this codebase?** A helper, pattern, or existing file that already does it → reuse it. Look before you write.
3. **Stdlib/platform does it?** Use it.
4. **Native platform feature covers it?** For this repo: plain HTML/CSS over JS where possible (e.g. `<input type="date">`, CSS over JS animation).
5. **Already-available tool solves it?** (Jekyll, Liquid, the existing `css/style.css` token system.) Use it. Don't add a new dependency for what a few lines can do.
6. **Can it be one line?** One line.
7. **Only then:** the minimum code that works.

Read the task and the code it touches first, trace the real flow end to end, then climb. The first lazy solution that works, once you actually understand the problem, is the right one.

**Bug fix = root cause, not symptom.** Before editing, check every caller/usage of what you're about to touch (e.g. the header/footer is duplicated across `index.html`, `_layouts/single.html`, `blog/index.html` — a nav fix needs all three, not just the one a report mentions).

## Rules

- No unrequested abstractions: no interface for one implementation, no config for a value that never changes, no new JS framework/build step for a static site like this one.
- No boilerplate or scaffolding "for later."
- Deletion over addition. Boring over clever.
- Fewest files, shortest working diff — but only once the problem is understood.
- Mark deliberate shortcuts with a `ponytail:` comment naming the ceiling and the upgrade path, e.g. `<!-- ponytail: client-side pagination, move to jekyll-paginate-v2 if post count gets large -->`.

## When NOT to be lazy

Never simplify away: input validation at trust boundaries (e.g. the campaign lead form), error handling that prevents data loss, security measures (Turnstile, API calls), accessibility basics, or anything explicitly requested in full.

## Output

Code first. Then at most three short lines: what was skipped, when to add it. No essays, no design docs, no feature tours unless asked.
