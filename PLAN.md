# Plan: Add a simple section navigation menu

Add a non-sticky navigation menu at the top of the website, with links that jump to each
section. Only `docs/index.html` and `AGENTS.md` are changed when this plan is carried out.

## Steps

1. Give each section an anchor target in `docs/index.html` by adding an `id` attribute to
   each of the five `<section>` opening tags:

   | Section | New `id` |
   |---|---|
   | About Me | `id="about"` |
   | Education | `id="education"` |
   | Interests & Hobbies | `id="interests"` |
   | Languages | `id="languages"` |
   | Contact | `id="contact"` |

   Do not change any existing text or content.

2. Add the navigation markup immediately inside `<div class="container">`, before
   `<header>`, using 4-space indentation to match the existing file:

   ```html
   <nav aria-label="Sections">
       <ul>
           <li><a href="#about">About Me</a></li>
           <li><a href="#education">Education</a></li>
           <li><a href="#interests">Interests &amp; Hobbies</a></li>
           <li><a href="#languages">Languages</a></li>
           <li><a href="#contact">Contact</a></li>
       </ul>
   </nav>
   ```

   Use `&amp;` for the ampersand. The menu is not sticky; it simply sits above the header.

3. Add a short-commented CSS block (as required by `AGENTS.md`) to the existing `<style>`
   block in `docs/index.html`, placed before the `@media` query. The rules must:
   - style `nav` with the existing light background `#f4f8fc`, a `16px` border radius,
     a top margin of `25px`, and horizontal padding;
   - override the existing `ul`/`li` rules inside `nav` with `display: flex`,
     `flex-wrap: wrap`, centered justification, `gap`, `list-style: none`, zero padding,
     and `margin-bottom: 0` on `nav li`;
   - style `nav a` with the heading colour `#0a2f6b`, `text-decoration: none`, and
     `font-weight: bold`, plus an underline on `:hover`;
   - inherit the existing Arial, Helvetica, sans-serif font stack.

4. Extend the existing `@media (max-width: 768px)` block with a small rule that reduces
   the `nav` padding and the `nav ul` gap so the links wrap cleanly on narrow screens.

5. Verify the result:
   - confirm all five `href="#..."` values exactly match their section `id` values;
   - click each link in a browser and confirm it jumps to the matching section and the
     URL gains the correct `#anchor` fragment;
   - check desktop and narrow-width layouts, and confirm existing colours, text, and
     sections are unchanged;
   - confirm the menu is not sticky and scrolls away with the page.

6. Update the "Current state" section in `AGENTS.md` so it lists all five sections:
   header, About Me, Education, Interests & Hobbies, Languages, Contact, footer.
