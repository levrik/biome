---
"@biomejs/biome": patch
---

Fixed an issue where lint fixes were silently dropped when applied inside Vue, Astro, or Svelte template expressions, such as `{{ }}` interpolations, `{ }` expressions, and directive attribute values (e.g. `:tabindex="..."`). Previously, `biome check --write` reported the diagnostic with a correct fix preview, but the file was left unchanged. Biome now correctly writes the fix back into the host document for all of these cases.
