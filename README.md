# Ian Bates – book landing pages

One Vercel site holding every book landing page used for Facebook ad tests.
Each book gets its own folder; the folder name is the page's web address.

Domain: `books.ianbatesauthor.com`, hosted on Vercel (DNS for ianbatesauthor.com is on Vercel; there is no main site at the bare domain).

| Folder | Live address |
|---|---|
| `thanks-for-nothing/` | `books.ianbatesauthor.com/thanks-for-nothing/` |

Each page's `og:image` (the Facebook link-preview picture) uses the full
`https://books.ianbatesauthor.com/<folder>/cover.jpg` address.

## How it's laid out

```
vercel.json             site-wide rules on Vercel (root goes to /thanks-for-nothing/)
index.html              root page: forwards to /thanks-for-nothing/ (for hosts without rules)
.htaccess               the same rules for Apache/cPanel hosting
thanks-for-nothing/
  index.html            the page
  cover.jpg             the cover (replace with the final export, same name)
```

## Adding a new book page

1. Make a new folder named after the web address you want, lower case with hyphens
   (e.g. `alcohol-is-lying/`).
2. Put that page's `index.html` and `cover.jpg` inside it.
3. Inside the page, point images at the folder: `src="/alcohol-is-lying/cover.jpg"`.
4. Push to `main`. Netlify publishes it within a minute.
5. Add a row to the table above.

## Rules every page follows (Facebook ad review)

- No swearing anywhere in the page text. A book's title may appear only on its cover image.
- Copy talks about the book and the author, never about the reader's drinking or health.
- Keep the withdrawal note in the footer.
- Each Amazon button uses its own Amazon Attribution link, separate from the
  tag used by direct-to-Amazon ads, so sales from each route can be compared.

Search each `index.html` for `REPLACE` to find what still needs filling in
(price, buy links, author photo).
