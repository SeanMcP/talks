# The Next Generation of Front-End Architecture

Sean McPherson Software Engineer, Khan Academy

---

# About me

- Software Engineer at Khan Academy
- Formerly Niche.com (Pittsburgh) and TSYS (Atlanta)
- Focused on all areas of front-end development

---

# A brief history of serving websites

<!-- This is the part that I feel least qualified to discuss, so finding a resource to cite would be really helpful -->

## The beginning

- Files on a computer
- Accessible by IP address
- Updated by FTP
- Still a thing!

## Rise of servers

- Application running on a computer
- Server receives requests, sends HTML
- Client-side JavaScript (jQuery) for interactivity
- PHP: WordPress, Drupal
- Ruby: Rails
- Python: Django
- Still a thing!

---

# Rise of single-page applications

- SPAs
- Applications that are entirely client-side rendered
- Influenced by native mobile apps
- Provide app-like experiences on the web
- Coincided with the rise of front-end frameworks
  - Angular, Ember, React, etc.

---

# Client-side rendering (CSR)

- Almost empty HTML file
- JavaScript bundle
- On page load, client requests and executes JavaScript bundle
- JavaScript in the client renders the entire application
- JavaScript makes additional requests to APIs
- JavaScript handles all interactions/updates
- External requests to save data

---

# SPAs

- Pros
  - Fast
  - App-like
  - Easy to build
- Cons
  - Slow to load
    - So many spinners
  - Poor SEO
  - Poor accessibility
  - Poor performance on low-end devices
  - Reinventing the wheel

> There shouldn't be a loading spinner on a website.

---

# JAMstack

<!-- Not sure if this is worth keeping -->

---

# Server-side rendering

Example: Node.js and React

## Server render

- Node server receives a request
- Server makes additional requests to database, APIs, etc.
- Server builds a React component tree
- React components (run on the server) make additional requests
- Server renders React component tree to string
- Server sends HTML to client

## Client hydration

- Browser receives HTML response and paints immediately
- Browser downloads JavaScript bundle
- Browser executes JavaScript
- React creates a client-side component tree based on the server-rendered HTML
  and JavaScript bundle
- React attaches event listeners to DOM nodes

---

# SSR

- Pros
  - Fast first contentful paint (FCP)
  - Better SEO
  - Better accessibility
  - Better performance
- Cons
  - Harder to build

---

# Return to multi-page applications

- Making good webapps is hard
- Meta-frameworks for building applications
  - Next & Remix for React
  - Nuxt for Vue
  - ~~Sapper~~/SvelteKit for Svelte
  - SolidStart for Solid
  - QwikCity for Qwik
- Server-side rendering
- Client-side hydration
