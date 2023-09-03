# The Next Generation of Front-End Architecture

Sean McPherson Software Engineer, Khan Academy

---

# About me

- Software Engineer
  - Focused on front-end web development
- Currently work for Khan Academy
  - Non-profit that provides free, world-class education for anyone, anywhere
- Formerly
  - Niche.com (Pittsburgh)
  - TSYS (Atlanta)
  - Classroom teacher
- Live in Pittsburgh, PA

---

# About this talk

Learn about modern patterns for front-end architecture

1. A brief history of front-end architectures
2. The rise of single-page applications
3. Return to multi-page applications
4. Examples
5. Recommendations

<!-- TODO: Consider explaining two slide "tracks" -->

---

# Glossary

<!-- How would I present this? -->

- CSR: Client-side rendering
- CSN: Client-side navigation
- DX: Developer experience
- FCP: First contentful paint
- MPA: Multi-page application
- SEO: Search engine optimization
- SPA: Single-page application
- SSG: Static-site generation
- SSR: Server-side rendering
- UX: User experience

---

# A brief history of front-end architectures

We only have time for a brief tour of the past 30 years of web development, but
I want to focus on a few patterns that are helpful when understanding the
current front-end landscape.

---

# History: The beginning

- Static HTML files on a computer
- Accessed on the internet via an IP address
- Edited directly or updated by FTP or SSH
- (Still a thing)

<!-- When you sign up for hosting with one of the big companies like Host Gator, they give you access to a computer where you can store your static files -->

---

# History: Rise of servers

- Application running on a computer
- Server receives network requests and response with some HTML
- Rely on HTML forms for user input
- Client-side JavaScript for interactivity
  - jQuery plugins for UI components on sites
- Languages and frameworks:
  - PHP: WordPress, Drupal
  - Ruby: Rails
  - Python: Django
- (Still a thing)

---

# History: App-like experiences

- Highly interactive experiences
- Trying to recreate experience of native applications
  <!-- iPhone released in 2007 -->
  - Desktop and then later mobile
- Macromedia/Adobe Flash
  - Single HTML file
  - Loads SWF file with Flash Player
- Feel immersive

<!-- TODO: Some kind of transition where you mention the cons -->

---

# History: The end of Flash

- Flash, like Icarus, flew too close to the sun
- Beautiful and magical
  <!-- I'm sure many of your remember the joy of Flash games -->
- Security nightmare
  <!-- Popular vector for hackers during it's hayday -->
- Famously "killed" by Steve Jobs and the iPhone
  > Flash is a spaghetti-ball piece of technology that has lousy performance and
  > really bad security problems.
  >
  > -- Steve Jobs
- But he couldn't kill the dream of app-like experiences on the web

---

# Rise of single-page applications

<!-- First acronym of the day -->

- SPAs
- Applications that are entirely client-side rendered
- Influenced by native mobile apps
<!-- Unlike something like Flash that depended on plugins -->
- Provide app-like experiences with web technologies
  - HTML, CSS, and a lot of JavaScript
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
- In React-world: `create-react-app`, `react-router-dom`

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

# Static-site generation (SSG)

- "What if we pre-rendered the site?"
- Build-time rendering
- Usually for content-heavy sites
  - Blogs, documentation, etc.
- Jekyll, Hugo, Gatsby, Eleventy, etc.
- Provided the DX of modern front-end frameworks with the UX of static sites
- Easy to deploy
- Easy to scale
- Easy to cache

---

# JAMstack

- Squishy term invented by Netlify
  - JAM: JavaScript, APIs, Markup

> The core principles of pre-rendering, and decoupling, enable sites and
> applications to be delivered with greater confidence and resilience than ever
> before.
>
> -- [Jamstack.org](https://jamstack.org/what-is-jamstack/)

- Gave rise to the next generation of meta-frameworks
  - Next, Gatsby, Nuxt, etc.

---

# Server-side rendering (SSR)

> To really take your app to the next level, you'll want to server render your
> app.
>
> -- [Kent C. Dodds](https://kentcdodds.com/blog/remix-the-yang-to-react-s-yin)

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
  - Harder to host
  - Potential time to interactive (TTI) issues

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

---

# Meta frameworks are the future

> If you want to build a new app or a new website fully with React, we recommend
> picking one of the React-powered frameworks popular in the community.
> Frameworks provide features that most apps and sites eventually need,
> including routing, data fetching, and generating HTML.

-- [React docs](https://react.dev/learn/start-a-new-react-project)

> We recommend using SvelteKit

-- [Svelte docs](https://svelte.dev/docs/introduction#start-a-new-project)

> We highly recommend giving [Nuxt] a try

-- [Vue docs](https://vuejs.org/guide/scaling-up/ssr.html#nuxt)

---

# Hybrid routing

- Some meta-frameworks offer server-side rendering _with_ client-side navigation
  - _e.g._ Next, Remix, SvelteKit
- Get the SEO and performance benefits of SSR
- Get the interactivity of CSR

[Next "Linking and Navigating"](https://nextjs.org/docs/pages/building-your-application/routing/linking-and-navigating)
[Remix "Browser Framework"](https://remix.run/docs/en/main/pages/technical-explanation#browser-framework)
[SvelteKit "Routing"](https://kit.svelte.dev/docs/routing)

---

# Hybrid rendering

- Some meta-frameworks offer server-side rendering _and_ static-site generation
  - _e.g._ Astro, Next, SvelteKit
- Individual routes are configured for SSR or SSG
- Get the benefits of SSG and SSR on a page-by-page basis
- Use cases:
  - A company site (static) with an interactive portal (dynamic)
  - An e-commerce site (dynamic) with a blog (static)

---

# Islands architecture

- Render HTML pages at build time or on the server
- Inject placeholders for dynamic regions
- Hydrate interactive "islands" on the client
  - Progressive hydration
- A type of progressive enhancement
- The main idea: pre-rendering the HTML for islands
- Astro was built with this architecture in mind

- [Miller, Jason. (2020). _Islands architecture_](https://jasonformat.com/islands-architecture/)
- [Patterns.dev. (n.d.). _Islands architecture_](https://www.patterns.dev/posts/islands-architecture)

---

## Are SPAs dead?

- No: they remain a useful pattern for highly interactive web applications

## Should you be building an SPA?

- Probably not

---

# Recommendations

- All decisions are trade-offs
- Assess your needs
- Evaluate each architecture's strengths/weaknesses

---

# Recommendation: Static sites

- Content-driven sites
  - _e.g._ blogs, documentation, e-commerce
- Little/no dynamic content
- Uniform experience for all users
- Can be cached on a CDN

---

# Recommendation: Server-rendered sites

- Content-driven sites
  - _e.g._ blogs, documentation, e-commerce
- Different experiences for different users
  - _e.g._ logged-in vs. logged-out

---

# Recommendation: Single-page applications

- Highly interactive web applications
  - _e.g._ Google Docs, Trello, Figma, Spotify
- Elements that follow the user throughout their experience
  - _e.g._ music player, chat panel
- URL routing is not meaningful to the user
- Users expect long login sessions <!-- Why? Look this up. -->
- Doesn't need to be indexed by search engines
- Internal application with hardware/connection guarantees

---

# Recommendation: Multi-page applications

- The default pattern for web applications
- Server-side rendered content
  - Good performance for users
  - Good SEO
- Client-side navigation when valuable

---
