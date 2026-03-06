Bare `http(s)` URLs in page content are auto-linkified client-side in `_includes/head/custom.html`.

Post visibility:
- `published: true` makes a post visible on `/blog/` and reachable at its post URL.
- `published: false` keeps the post out of `/blog/` and prevents Jekyll from publishing its page, feed entry, and sitemap entry.

Blog citations:
- Use kramdown footnotes to create paper-style citations with superscript numbers in the text and a references list at the bottom of the post.
- Example:

```md
This is a citation in the text.[^1]

[^1]: [Article title](https://example.com/article)
```
