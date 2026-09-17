# LAZAREV. Clone — AI & ML Digital Product Design Agency

A static, single-page recreation of the [Lazarev](https://lazarev.kiev.ua/) agency landing page — an award-winning UX/UI and digital product design studio for AI & ML businesses.

Built with pure HTML, CSS, and vanilla JavaScript, powered by GSAP + ScrollTrigger for animations and Locomotive Scroll for smooth scrolling.

![Tech](https://img.shields.io/badge/HTML-CSS-JS-111.svg?logo=html5) ![](https://img.shields.io/badge/GSAP-3.12-green) ![](https://img.shields.io/badge/Locomotive%20Scroll-3.5-blue)

## Features

- **Animated hero section** — staggered load-in animation for the intro, with the "O" of PRODUCT rendered as an SVG logo.
- **Mega menu navigation** — expanding dropdown with staggered sub-menu animations on hover.
- **Marquee** — infinitely scrolling press/award logos (Forbes, Awwwards, PMI, Webby, etc.) with edge blur fades.
- **Mouse-following image** on insights list items (tracking cursor position on hover).
- **Interactive showreel** — click to play a full-screen video with a morphing scale/fade animation.
- **Case studies** — hover to play project videos over static cover images.
- **Service accordions** (UI/UX Design, Product Design) with expanding detail rows.
- **Design process section** — scroll-scrubbed overlapping list of product phases.

## Tech Stack

| Library          | Purpose                        | Version        |
| ---------------- | ------------------------------ | -------------- |
| GSAP             | Animations & timelines         | 3.12.5         |
| GSAP ScrollTrigger | Scroll-scrubbed animations    | 3.12.5         |
| Locomotive Scroll| Smooth scrolling              | 3.5.4          |
| Remixicon        | Icons                          | 4.2.0          |

All libraries are loaded via CDN (`cdn.jsdelivr.net` / `cdnjs.cloudflare.com`).

## Getting Started

No build step, dependencies, or package manager required. Just serve the folder:

```bash
# using Python
python -m http.server 5500
```

```bash
# using VS Code
# install the "Live Server" extension and click "Go Live"
```

Then open `http://localhost:5500` in your browser.

You can also simply double-click `index.html`, though an HTTP server is recommended so CDN resources and local videos are served reliably.

## Project Structure

```
lazarev-main/
├── index.html          # All page markup (single page)
├── style.css           # Global styles & layout (~720 lines)
├── script.js           # GSAP + Locomotive Scroll animations
└── accern-rhea-cover-big.mp4  # Local case-study video
```

## How It Works

- `script.js` wires up five animation modules, called on page load:
  - `locomotiveAnimation()` — initializes Locomotive Scroll and bridges it with GSAP ScrollTrigger.
  - `loadingAnimation()` — hero entrance timeline (scale + fade).
  - `navAnimation()` — mega-menu open/close on nav hover.
  - `page2Animation()` — floating thumbnail follows the cursor over each insight row.
  - `page3VideoAnimation()` — showreel toggle + hover-to-play case study videos.
  - `page6Animations()` — scrubbed reveal of the process timeline.
- `style.css` uses vw-based units throughout for a fluid, responsive layout.
- `index.html` is fully self-contained, pulling assets (fonts, images, SVGs) from the original Lazarev site's CDN and Webflow asset URLs.

## Notes

- This is a **learning/portfolio clone** for front-end animation practice; content, images, and videos belong to Lazarev.
- Hero title uses a custom outline/animated SVG (the green "O" in PRODUCT) with morph paths.
- Fonts referenced as `gilroy` — fall back to your system font unless you add the Gilroy webfont.