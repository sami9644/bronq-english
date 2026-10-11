# Bronq English School Website

A modern, responsive, single-page website for **Bronq English School**, an English language school in Addis Ababa, Ethiopia, with branches in **Megenagna** and **Summit**.

The whole site lives in one `index.html` file. There is no build step, no package manager, and no framework, so it is easy to edit, test, and deploy.

## Features

- Responsive layout that works on phones, tablets, and desktops
- Dark and light mode toggle that remembers the visitor's choice and follows their system setting by default
- Mobile navigation menu with a vanilla JavaScript toggle
- Smooth scrolling between sections
- English courses from A1 to C2, each in its own card
- Student testimonials carousel with star ratings, country, and level
- Contact and registration form with basic validation
- Branch details for Megenagna and Summit, plus a map placeholder
- Accessible by default: visible keyboard focus, labelled form fields, and reduced-motion support

## Sections

1. Navigation bar with a "Book a lesson" button
2. Hero
3. About us, mission, and four "Why choose us" pillars
4. Courses (A1, A2, B1, B2, C1, C2)
5. How it works (3 steps)
6. Student stories
7. Contact and registration
8. Footer

## Tech stack

| Purpose | Tool |
| --- | --- |
| Markup | HTML5 |
| Styling | [Tailwind CSS](https://tailwindcss.com/) 3.4.17 via CDN |
| Icons | [Lucide](https://lucide.dev/) 0.263.1 via CDN |
| Fonts | Bricolage Grotesque and DM Sans (Google Fonts) |
| Behavior | Vanilla JavaScript |

## Getting started

Clone the repository and open the file in a browser:

```bash
git clone https://github.com/YOUR-USERNAME/bronq-english-school.git
cd bronq-english-school
open index.html        # macOS
# or double-click index.html on Windows / Linux
```

To run it on a local server instead:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

An internet connection is needed the first time, because Tailwind, Lucide, and the fonts load from CDNs.

## Customizing

Everything is commented in `index.html` so you can find what to change quickly.

### Text and content

The data arrays at the top of the `<script>` block hold all the copy. Edit them and the page updates automatically.

| Array | Controls |
| --- | --- |
| `PILLARS` | The four "Why choose us" cards |
| `LEVELS` | The A1 to C2 course cards and the hero staircase |
| `STEPS` | The "How it works" steps |
| `STORIES` | Testimonials (name, country, level, rating, quote) |
| `BRANCHES` | Branch names, addresses, and phone numbers |

### Colors

Change the CSS variables at the top of the `<style>` block. Light mode is defined in `:root` and dark mode in `html.dark`.

```css
:root {
  --bg: #F5F7FB;
  --surface: #FFFFFF;
  --ink: #101B3A;
  --brand: #1B2E6B;
  --gold: #E8A317;
}
```

### Logo, photos, map, and social links

- **Logo:** replace the `b` square in the navigation bar with an `<img>` tag.
- **Testimonial photos:** the cards show initials. Replace the initials `<span>` in the testimonial template with an `<img>`.
- **Map:** replace the dashed placeholder `<div>` in the contact section with a Google Maps `<iframe>`.
- **Social links:** update the `href="#"` values in the footer.

### Contact details

Replace the placeholder phone numbers and the `info@bronqenglish.com` email address, and update the opening hours in the contact section.

## Making the contact form work

The form currently validates the fields and shows a thank-you message, but it does not send data anywhere. To receive submissions, connect it to a service. For example, with [Formspree](https://formspree.io/), find the `TODO` comment in the submit handler and add:

```js
fetch('https://formspree.io/f/YOUR_ID', { method: 'POST', body: new FormData(e.target) });
```

Note that the form fields use `id` attributes, so add a `name` attribute to each field if your service reads field names.



## Project structure

```
.
├── index.html    # The entire website (HTML, CSS, and JavaScript)
└── README.md
```



Works in current versions of Chrome, Edge, Firefox, and Safari.

## License

Add your license here, for example MIT or remove this section if the project is private.

## Contact

Bronq English School, Addis Ababa, Ethiopia
Branches: Megenagna and Summit
