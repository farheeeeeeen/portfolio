HOW TO ADD A WRITING PIECE ("Read here")

1. Copy _template.html and rename it to a slug, e.g. positioning-is-proof.html
2. Fill in everything in [ square brackets ]: title, meta, standfirst, body.
   - Use <h2> / <h3> for headings
   - <blockquote> for a pull-quote
   - <figure> blocks for images (drop image files in writing/images/ and set src)
   - Delete any blocks you don't need (quote, figure, list are all optional)
3. In read.html, copy the "Read here" entry block and point its href at your new file.
4. Update the prev/next links at the bottom of each piece if you want them chained.

Paths: pages in /writing use ../ to reach the site root (e.g. ../index.html, ../read.html).
