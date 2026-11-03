# Landing Page: Plain CSS vs Tailwind CSS

The same "Book Explorer" landing page built twice, so the two workflows can be compared.

| Version | Folder | How it is styled |
|---|---|---|
| Plain CSS | `plain-css/` | `index.html` + a 116-line `style.css` |
| Tailwind CSS | `tailwind/` | `index.html` only, utility classes, no CSS file |

Open either `index.html` in a browser (double-click it). The footer of each page says which version it is.

## Requirements and progress

| # | Requirement | Status |
|---|---|---|
| 1 | Start from a landing page built with plain CSS | Done: `plain-css/` |
| 2 | Rebuild it entirely with Tailwind utility classes (no custom CSS file) | Done: `tailwind/` |
| 3 | Both pages look the same (same layout, colors, fonts, spacing) | Done |
| 4 | Responsive design (mobile first, `sm:` and `md:` breakpoints) | Done |
| 5 | Tailwind installation | Done via the Play CDN (see below) |
| 6 | GitHub repository containing both versions | To do: push this folder (commands below) |


## Page sections
Sticky navbar, hero with two buttons, three feature cards, three "how it works" steps, call-to-action email form, footer.

## Tailwind installation
For speed this uses the Play CDN: `<script src="https://cdn.tailwindcss.com/3.4.17"></script>`, with the brand colors and fonts set in `tailwind.config`. For a real production site, use the Tailwind CLI instead (https://tailwindcss.com/docs/installation):

```
npm install -D tailwindcss@3
npx tailwindcss init
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

## Workflow note

When I rebuilt my landing page with Tailwind, the biggest change was that I stopped jumping between two files. With plain CSS I wrote the HTML, then went to style.css, then came back to check the result, and I spent a lot of time thinking up class names like .card-title or .section-alt. With Tailwind I just styled everything right in the HTML and saw the result straight away.

My CSS file went from 116 lines to nothing. The colors and fonts live in one place, the Tailwind config, and the spacing and text sizes come from a ready-made scale, so I stopped guessing values like 1.25rem. Making the page responsive was also quicker. Instead of writing a separate @media block, I added prefixes like md:grid-cols-3 right next to the element.





## Open in IntelliJ IDEA
1. **File > Open** and select this folder (`landing-page-css-vs-tailwind`).
2. In the Project panel, right-click `tailwind/index.html` (or `plain-css/index.html`), choose **Open In > Browser**, then pick a browser.
3. Tailwind needs an internet connection when you open its page, because it loads from the CDN.
4. Optional: IntelliJ's Tailwind CSS plugin (Settings > Plugins) adds class-name autocomplete.
