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
| 7 | Short note on what changed in the workflow | Draft below: edit it in your own words |

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

Moving from plain CSS to Tailwind changed how I work in three ways. First, I stopped switching between two files: I style directly in the HTML, so I see the result of each change straight away and no longer invent class names like `.card-title` or `.section-alt`. Second, the CSS I wrote shrank from 116 lines to none, because the design tokens (colors, fonts, spacing) live in one `tailwind.config` and the classes come from a fixed scale. Third, responsive design became easier: a prefix such as `md:grid-cols-3` replaces a separate `@media` block. The trade-offs are that the HTML is longer and harder to read at first, repeated groups of classes (like the three cards) are copied instead of reused, and I had to learn the class names. Overall, Tailwind was faster for building and adjusting layouts.

## Push to GitHub

1. On github.com click **New repository**, name it `landing-page-css-vs-tailwind`, leave it empty (no README), and click **Create repository**.
2. In a terminal inside this folder:

```
git init
git add .
git commit -m "Add plain CSS and Tailwind versions of the landing page"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/landing-page-css-vs-tailwind.git
git push -u origin main
```

3. Copy the repository link and paste it with your workflow note into the submission box.

## Open in IntelliJ IDEA
1. **File > Open** and select this folder (`landing-page-css-vs-tailwind`).
2. In the Project panel, right-click `tailwind/index.html` (or `plain-css/index.html`), choose **Open In > Browser**, then pick a browser.
3. Tailwind needs an internet connection when you open its page, because it loads from the CDN.
4. Optional: IntelliJ's Tailwind CSS plugin (Settings > Plugins) adds class-name autocomplete.
