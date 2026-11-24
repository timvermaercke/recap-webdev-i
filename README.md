# Buy my car

The HTML for this page is finished. Your job is to style it in `styles/main.css`.

Open `index.html` in a browser and refresh after each step. Work from top to bottom. Write the narrow layout first, then add the wider layouts in the media-query step.

## Rules

- Edit `styles/main.css` only. Leave `index.html` as it is.
- Do not add JavaScript.
- Do not use CSS variables. Write the color value in the declaration and put the color name in a comment, like `#1c1916 /* ink */`.
- The fonts are already loaded in the HTML. Use **Outfit** for text and **Fraunces** for headings.
- Photos need a network connection. They come from Unsplash.

## Colors

| Name | Value | Use it for |
| --- | --- | --- |
| ink | `#1c1916` | text, and the button hover |
| muted | `#5e564c` | secondary text |
| paper | `#f4efe6` | the page background |
| card | `#fffaf4` | cards, the price, the form, button text |
| line | `#e0d6c8` | borders |
| orange | `#e07a2f` | the logo dot, the nav underline |
| orange-deep | `#b4531a` | kickers, links, the main button |
| sand | `#f7e1c8` | the table header |
| row | `#fbf6ee` | the group cells in the table body |
| price | `#f8e6d4` | the asking-price row |
| white | `#ffffff` | the form fields |

## 1. Base

Set `box-sizing: border-box` on every element, including `::before` and `::after`.

On `body`:

- remove the default margin
- set the text color to ink and the background to paper
- set the font to Outfit, with `"Segoe UI", sans-serif` as fallbacks
- use a font size around `1.05rem` and a line-height around `1.6`

On `img`, set `max-width: 100%` and `height: auto` so photos shrink with the page.

On `h1` and `h2`, use Fraunces, a weight of `650`, a tight line-height, and a small negative letter-spacing. Give `h1` a size that grows with the viewport (`clamp`) and `h2` a smaller one. Reset their margins so the kicker sits close above them.

Give paragraphs a bottom margin. Set the default link color to orange-deep.

## 2. Page wrapper

`.wrap` keeps the content from stretching across a wide monitor.

- width: `min(1080px, calc(100% - 2rem))`
- center it with `margin-inline: auto`

## 3. Header

The header is a flexbox. On a narrow screen the logo sits above the navigation. From 640px up they share one row. You write the narrow version here and the row in the media-query step.

`.site-header`:

- `position: sticky` and `top: 0`, with a `z-index` so content scrolls underneath it
- background paper, so the page does not show through
- a bottom border in the line color

`.bar`:

- `display: flex`
- `flex-direction: column`
- `align-items: flex-start`
- a gap of about `0.75rem`
- vertical padding of about `0.9rem`

## 4. Logo

`.logo` is a flex row: the dot and the words "Buy my car" sit next to each other, centered, with a small gap. The link is ink, has no underline, and uses a font weight of `600`.

`.logo-mark` is the orange dot:

- width and height about `0.8rem`
- `border-radius: 50%`
- background orange

The pulse animation from step 14 goes on this dot.

## 5. Navigation

`.site-nav ul` is also a flexbox. Remove the bullets and the default margin and padding. Let the items wrap, with a small gap.

`.site-nav a`:

- ink, no underline
- a transparent bottom border about `2px` thick, so the hover does not shift the link
- a little vertical padding

## 6. Kicker, intro and note

Every section starts with a `.kicker`: "Private sale", "The car", "Photos", "Specs", "Contact".

`.kicker`:

- orange-deep
- small size, about `0.78rem`
- weight `600`
- letter-spacing around `0.12em`
- `text-transform: uppercase`
- a small margin under it, and no extra margin above

`.intro` is the grey sentence under a heading. Cap it at about `40rem` and color it muted.

`.note` is the small print in the form and the footer. Muted, about `0.9rem`.

## 7. Hero

`.hero` is a grid with one column and a gap of about `1.5rem`. Add vertical padding so it does not touch the header. The two-column layout comes in the media-query step.

`.hero-photo` has no margin. The image inside it:

- `display: block` and `width: 100%`
- `aspect-ratio: 3 / 2` and `object-fit: cover`
- a border radius of about `16px`
- a soft shadow, `0 10px 30px rgba(48, 32, 16, 0.08)`

`.lede` is the sentence under the title. Cap it at about `38rem` and set the size to about `1.1rem`.

The rise animation from step 14 goes on `.hero-copy`.

## 8. Price and buttons

`.price` is the asking price. Make it an inline flex column so "Asking price" stacks above "€4 800".

- card background, line border, radius about `12px`
- padding around `0.7rem 1rem`
- Fraunces, about `1.8rem`
- the `span` inside it is Outfit, muted, small, uppercase, with a little letter-spacing

`.hero-actions` is a flex row that wraps, with a gap of about `0.7rem`.

`.button` and `button` share one rule:

- inline-block, no border, radius about `8px`
- background orange-deep, text card
- `font: inherit` and weight `600`
- padding around `0.75rem 1.15rem`
- `cursor: pointer`

`.button-quiet` is the second action, "Make an offer". It has a transparent background, ink text, and an inset box-shadow of `1.5px` in ink so it reads as an outline. On hover, fill it with ink and switch the text to paper.

## 9. Story and facts

`.block` is the vertical rhythm for The car, Photos, Specs and Contact. Give it padding of about `2.75rem` on top. Also set `scroll-margin-top: 5rem` so a clicked nav link is not hidden behind the sticky header.

`.story-grid` is a one-column grid with a gap of about `1.5rem`.

`.facts` is a grid of two columns. Remove the list margin, padding and bullets. Each `li` is a card: card background, line border, radius about `12px`, padding about `0.9rem 1rem`.

The `span` in a fact is muted and small, and `display: block` so the label sits above the number. The `strong` is Fraunces, about `1.35rem`.

## 10. Photo grid

`.photo-grid` is a one-column grid with a gap of about `1rem`.

Each `figure`:

- margin `0`
- `overflow: hidden`, so the zoom in step 17 stays inside the card
- card background, line border, radius about `14px`

Each image:

- block, full width, height `auto`
- `aspect-ratio: 7 / 9` and `object-fit: cover`, so the nose and the tail stay in frame

The third photo is the wide one of both doors. Target it with `.photo-grid figure:nth-child(3) img` and set `aspect-ratio: 12 / 7`.

`figcaption` is muted, about `0.95rem`, with padding around `0.75rem 1rem 1rem`.

## 11. Specs table

The HTML already uses `rowspan` and `colspan`. You only style the table. Do not change the cells.

`.scroll-hint` stays hidden for now (`display: none`). You show it on small screens in the media-query step.

`.table-scroll` lets the sheet slide sideways when it is wider than the phone:

- `overflow-x: auto`
- card background, line border, radius about `14px`

`.spec-table`:

- `width: 100%`
- `min-width: 38rem`, so the columns stay readable and the wrapper scrolls
- `border-collapse: collapse`

The `caption` sits on top, aligned left, with some padding and a weight of `600`.

`th` and `td`:

- padding about `0.75rem 1rem`
- a bottom border in the line color
- text aligned left, `vertical-align: top` so a rowspan cell lines up with its first row

`thead th` gets the sand background and a slightly smaller font. `tbody th` gets the row background.

`.price-row th` and `.price-row td` get the price background, no bottom border, and a weight of `600`.

## 12. Offer form

`.offer-form` is a card: padding about `1.25rem`, card background, line border, radius about `16px`, and the same soft shadow as the hero photo.

`.form-grid` is a one-column grid with a gap of about `1rem`. The two-column layout comes later.

`.field` is a flex column with a small gap, so the label sits above the control. Labels are weight `600`. `.optional` is muted and weight `400`.

`input`, `select` and `textarea`:

- width `100%`
- line border, radius about `8px`
- white background, ink text
- `font: inherit`
- padding about `0.7rem 0.75rem`

Let the textarea resize vertically and give it a `min-height` of about `8rem`.

On `:focus`, remove the default outline, set the border to orange-deep, and add `box-shadow: 0 0 0 3px rgba(180, 83, 26, 0.2)`.

`.check` is the licence row. Switch that field to a row, align the items to the start, and add a gap. The checkbox itself is about `1.1rem`, with a little top margin, and `accent-color` orange-deep. Its label is weight `400`.

## 13. Footer

`.site-footer` has a top margin of about `3rem` and a top border in the line color.

`.footer-bar` is a flex column with a small gap and vertical padding of about `1.5rem 2rem`. Zero the margin on the paragraphs inside it.

The email link has no underline.

## 14. Keyframes

Add two `@keyframes` rules.

`rise` moves `.hero-copy` in on load:

- from: opacity `0`, `translateY(16px)`
- to: opacity `1`, `transform: none`

Apply it as `animation: rise 0.7s ease both`.

`pulse` is the loop on `.logo-mark`:

- at `0%` and `100%`: scale `1`, opacity `1`
- at `50%`: scale `1.45`, opacity `0.55`

Apply it as `animation: pulse 2.6s ease-in-out infinite`.

## 15. Transitions

Transitions are separate from the keyframes. Add them on the properties that change during hover and focus.

- `.logo`: color, about `0.2s`
- `.site-nav a`: color and border-color, about `0.2s`
- `.button` and `button`: background-color and transform, about `0.2s`
- `.photo-grid img`: transform, about `0.45s`
- `input`, `select`, `textarea`: border-color and box-shadow, about `0.2s`
- `.footer-bar a`: color, about `0.2s`

Then the states:

- `.logo:hover` and `.logo:focus-visible`: color orange-deep
- `.site-nav a:hover` and `:focus-visible`: color orange-deep, bottom border orange
- `.button:hover`, `button:hover` and the matching `:focus-visible`: background ink, `translateY(-2px)`
- `.button-quiet:hover` and `:focus-visible`: background ink, text paper
- `.photo-grid figure:hover img` and `:focus-within img`: `scale(1.05)`
- `.footer-bar a:hover` and `:focus-visible`: color ink

## 16. Media queries

Keep writing the narrow styles outside these blocks. Add the queries at the end of the file.

**Under 640px** — `@media (max-width: 639px)`

- show `.scroll-hint` with `display: block`

**From 640px** — `@media (min-width: 640px)`

- `.bar` becomes a row: `flex-direction: row`, `align-items: center`, `justify-content: space-between`
- `.form-grid` becomes two columns
- `.span-2` stretches across both columns with `grid-column: 1 / -1`

**From 800px** — `@media (min-width: 800px)`

- `.hero` becomes two columns, about `1.15fr` and `0.85fr`, items centered, gap about `2.5rem`, a bit more padding on top
- `.story-grid` becomes two columns, about `1.3fr` and `0.9fr`, aligned to the start
- `.facts` stays two columns
- `.photo-grid` becomes two columns
- the third photo spans both columns with `grid-column: 1 / -1`
- `.block` gets more padding on top, about `4rem`

**From 1040px** — `@media (min-width: 1040px)`

- `.facts` becomes one column, so the four facts stack beside the story

**Reduced motion** — `@media (prefers-reduced-motion: reduce)`

- turn animation and transition off on every element, including `::before` and `::after`

## Check your page

- On a phone width, the header stacks, the hero is one column, the form is one column, and the spec sheet slides sideways. The hint above the table is visible.
- From 640px, the logo and the nav share a row, and the form fields sit in pairs. The visit field, the message, the checkbox and the button still span the full form.
- From 800px, the photo sits beside the title, the facts sit beside the story, and the third photo spans the gallery.
- The logo dot pulses. The hero text rises in once. Links, photos, fields and the button move on hover and focus.
- Resizing the window does not cause a horizontal scrollbar on the page. The table may scroll inside its own card.
