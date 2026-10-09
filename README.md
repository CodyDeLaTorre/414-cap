# Cody De La Torre — Portfolio Capstone

A static HTML/CSS portfolio site for hiring managers to see who I am, my tools, my experience, and how to contact me.

- Live site: https://codydelatorre.github.io/414-cap/
- Repository: https://github.com/CodyDeLaTorre/414-cap

## Pages

- `index.html` — Home / About
- `experience.html` — Work history
- `tools.html` — Tools & Skills
- `contact.html` — Contact (demo form)

## Files

- `css/main.css` sets the cascade layer order and imports `01-tokens` through `08-print`
- `images/` holds the headshot in JPEG and WebP at 240, 320, and 480px
- See `ARCHITECTURE.md` for CSS architecture details

No JavaScript or frameworks. Open `index.html` in a browser to run it.

## Release notes

- Fixed color contrast, menu button name, nav landmark, current-page state, Experience headings, focus ring, and form labels/hints
- Added unique titles, meta descriptions, canonical links, Open Graph tags, and Person structured data
- Changed justified text to left-aligned and hid card-link arrows from screen readers
- Added a note that the contact form is a demo

## Known limitations

- The contact form doesn't send messages (needs JavaScript or a form service)
- Form errors aren't linked to their fields for screen readers
- Dark mode is only on Home and isn't saved across pages
- Tested on Windows only (Chrome, Firefox, Edge)

## AI disclosure

I used Claude to help with CSS ordering, explain syntax, and organize documentation. I verified all code, content, and test results myself.
