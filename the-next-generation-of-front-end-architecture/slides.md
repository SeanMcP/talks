---
layout: intro
---

# The Next Generation of<br/>Front-End Architecture

Sean McPherson, Software Engineer @ Khan Academy

---

# About me

- Front-end focused software engineer
- Currently work for Khan Academy
  - Non-profit that provides free, world-class education for anyone, anywhere
- Formerly
  - Niche.com (Pittsburgh)
  - TSYS (Atlanta)
  - Classroom teacher
- Live in Pittsburgh, PA

---

# About this talk

Learn about modern front-end architectures and their patterns

1. Architectures & Patterns
2. Examples & Tradeoffs
3. Recommendations
4. Questions

<!--
- We'll look at a five-ish front-end architectures
- And the patterns that make them work
- We'll look at examples of each architecture
- And analyze some of their tradeoffs
- Finally we'll end with some recommendations for choosing a front-end architecture
- Before leaving some time for questions at the end
-->

---

# Definitions

- **Patterns**: general and reusable solutions to commonly occurring problem 🧱

- **Architecture**: design decisions related to overall system structure and
  behavior 🏠
  - Comprises multiple patterns

[SEI CMU. (n.d.) "Software Architecture".](https://www.sei.cmu.edu/our-work/software-architecture/)

---
layout: center
---

# Architectures

<!--
- We're going to proceed through these in roughly chronological order
-->

---

# 🏠 Architecture: Static sites

- HTML files on a computer
- Accessed on the internet via an IP address
- Edited directed or updated by FTP/SSH

<!--
- The first architecture in web development was static
- All sites were just files stored on a computer somewhere that you could access on the internet
- When you sign up for hosting with one of the big companies, they give you access to a computer where you can store your static files
- There aren't any patterns for us to discuss here, beyond using the main web technologies: HTML, CSS, and JS
-->

---
layout: center
---

<img alt="CERN" src="/images/cern.png" />

<!--
- This is a copy of the first website ever created
- It's a static site
-->

---

# 🏠 Architecture: Server-rendered sites

- Applications running on a computer
- Receive network requests and respond with HTML
- Rely on HTML forms for user input
- Client-side JavaScript for interactivity
  - jQuery plugins for UI components
- Examples: Wordpress (PHP), Rails (Ruby), Django (Python), Express (Node.js)

<!--
- This next era was the beginning of web-based "applications"
- Brought truly dynamic content to the web
- Server-rendered sites used two main patterns...
-->

---

# 🧱 Pattern: Server-side rendering

Server-rendered sites

- Abbreviated SSR
- Server code that renders and returns HTML
- Server can interface with database
- Server-to-server requests are faster
- Secrets are kept on the server
- Current status: Solid

<!--
- Each pattern we discuss will have a status at the end
- "Solid" means that you could build your business on their pattern without worrying
- As we will see, other patterns inspire much less confidence...
-->

---

# 🧱 Pattern: Plugins

Server-rendered sites

- Isolated scripts that bring specific interactivity to a site
- JavaScript code that is paired with a DOM node
- JS runs on the client to create the UI in the DOM
- Powered by jQuery and MooTools
- Current status: Aging

<!--
- The status here means that you could use it today, but don't expect it to last long
- There are some contexts where plugins might be the best pattern
- Replaced by web components and islands (which we will discuss later)
- The server-rendered site architecture has some tradeoffs...
-->

---

# ⚖️ Tradeoffs

Server-rendered sites

- Full-page loads feel slow
- Server issues may increase time to first byte (TTFB)
  - Traffic surges
  - Global user base

---
layout: center
---

<img alt="MDN" src="/images/mdn.png" />

<!--
- Great example of a server-rendered site
- Besides the unparalleled quality of the documentation
- Focused on SEO
- Full-page loads aren't an issue
  - You're not primarily navigating the site a lot
  - Google search, then click the link that fits
-->

---

# 🏠 Architecture: Early single-page applications

- Abbreviated SPAs
- Highly interactive and immersive experiences
- Try to recreate native applications on the web
  - Initially desktop programs
  - Later mobile apps
- Needed to recreate browser functionality like routing
- Required browser plugins to run applications
- Examples: Macromedia Flash, Microsoft Silverlight

<!--
- This was a "Wild West" period for front-end architecture
- Anything was "possible"; anything goes
- Gave us some really interesting applications
- Introduced a few important patterns...
-->

---

# 🧱 Pattern: Client-side rendering

Single-page applications

- Single root node in an empty HTML page
- Large bundle that builds site on node when executed
- Typically created with a framework
- Client-side code handles all updates
- Current status: Solid

<!--
- Start with an empty HTML page and a bundle of client-side code
- The bundle generates the UI for the website
- The client-side code handles all updates to the UI
  - Toggling checkboxes
  - Opening/closing menus
-->

---

# 🧱 Pattern: Client-side navigation

Single-page applications

- All "navigation" occurs within a single HTML page
- Sometimes mocks URL changes with History API
- Client-side code determines what views to render
- Current status: Solid

---

# ⚖️ Tradeoffs

Early SPAs

- Depended on plugins
  > To view this content, please install Microsoft Silverlight
- Not accessible (see
  [WCAG "Robust"](https://www.w3.org/WAI/fundamentals/accessibility-principles/#robust))
- Poor performance
- Poor security

<!--
- Ultimately these technologies failed to revolutionize the web
- Steve Jobs famously killed Flash by not supporting it in the iPhone
- The patterns they introduced became the foundation behind...
-->

---

# 🏠 Architecture: Modern SPAs

- Same goals of early SPAs
- Powered by front-end JavaScript frameworks
  - Angular, Ember, React, Vue, Svelte
- Provide app-like experiences with web technologies
  - HTML, CSS, and a lot of JavaScript
- Maturation of previous era of SPAs
- Example: `create-react-app` and `react-router-dom`

---

# ⚖️ Tradeoffs

Modern SPAs

- Long initial loads
- Bad SEO
- Network request waterfalls
- Too easy to make inaccessible

<!--
- Once the SPA was up and running, it was great
- The industry needed a way to get the benefits of SPAs without those tradeoffs
- Enter...
-->

---
layout: center
---

<img alt="Figma" src="/images/figma.png" />

---

# 🏠 Architecture: Multi-page applications

- Abbreviated MPAs
- Combining patterns from server-rendered sites and SPAs
- Server-rendered pages
- Client-side navigation
- Powered by meta-frameworks
- Example: Next, Remix
  - Nuxt (Vue), SvelteKit

<!--
- These examples are all in JavaScript land
- But there are meta-frameworks for your preferred language too
- A friend called out Intertia as an interested option using PHP
-->

---

# 🧱 Pattern: SSR with client-side hydration

Multi-page applications

- Server renders HTML with JavaScript framework
- Browser paints with initial response from server
- Client fetches/executes JavaScript bundle
- Client-side JavaScript adds interactivity
- Current status: Solid

---

# 🧱 Pattern: Hybrid navigation

Multi-page applications

- Support client- & server-side navigation
- Page load/refresh makes server request
- User interaction trigger client-side navigation
- Performance benefits on first load
- User experience benefits on navigation
- Current status: Developing

---

# 🧱 Pattern: Hybrid rendering

Multi-page applications

- Configurable rendering for each route
- Statically-generated pages for static content
- Server-rendered pages for interactivity, personalization
- Current status: Developing

<!--
- Next and Astro support this for React sites
-->

---

# 🧱 Pattern: Islands

Multi-page applications

- Also called "Islands Architecture" (sorry!)
- Small, focused chunks of interactivity
- Pre-/server-rendered markup is progressively enhanced with client-side
  JavaScript
- Scripts can be requested and run independently
  - 🧱 Pattern: Progressive hydration
- Successor to Plugins pattern
- Current status: Developing

<!--
- I'm sorry about the naming confusion here
- I think the idea of islands better fits as a pattern
  - Especially because it can be used in multiple architectures
- Astro is a framework designed for islands
- Enables you to create sites with any JavaScript framework
- Provides client directives to components that allow you to configure when an island hydrates
-->

---
layout: center
---

<img alt="Notion" src="/images/notion.png" />

---

# 🏠 Architecture: Modern static sites

- Same features of early static sites
- Use modern tooling to generate HTML pages
  - Typically file-system based page generation
- Use islands pattern for interactivity
- Pages are cached on global CDNs
- Sometimes called "JAMstack"
- Examples: Astro, Next SvelteKit, Nuxt

<!--
- JAMstack was a term invented by host Netlify to advertise this architecture (hosted on their platform)
  > The core principles of pre-rendering, and decoupling, enable sites and
  > applications to be delivered with greater confidence and resilience than ever
  > before.
- Though the term "JAMstack" has faded into history, the architecture is still going strong
-->

---

# 🧱 Pattern: Static-site generation

Modern static sites

- Abbreviated SSG
- Automating the process of creating HTML pages
- Support for templates
- File system for directory structures
- Some handle bundling resources
- Current status: Solid

---

# ⚖️ Tradeoffs

Modern static sites

- Limited dynamic content
- Performance challenge to add significant interactivity
- Build times/resources for large sites

---
layout: center
---

<img alt="Microsoft Fluent Design" src="/images/ms-fluent-design.png" />

<!--
-->

---

# Architectures & Patterns

|                        | <TC>Static sites</TC> | <TC>Server-rendered<br/>sites</TC> | <TC>Single-page<br/>apps</TC> | <TC>Multi-page<br/>apps</TC> |
| ---------------------- | --------------------- | ---------------------------------- | ----------------------------- | ---------------------------- |
| Static-site generation | <Check/>              |                                    |                               | <Check/>                     |
| Server-side rendering  |                       | <Check/>                           |                               | <Check/>                     |
| Islands                | <Check/>              | <Check/>                           |                               | <Check/>                     |
| Client-side rendering  |                       |                                    | <Check/>                      | <Check/>                     |
| Client-side navigation |                       |                                    | <Check/>                      | <Check/>                     |
| Hybrid navigation      |                       |                                    |                               | <Check/>                     |
| Hybrid rendering       |                       |                                    |                               | <Check/>                     |

<!--
- This is a chart of the architectures we covered and the patterns they use
- Each have their focus
- Multi-page apps provide the most options
- We'll consider this more as we go into...
-->

---
layout: center
---

# Recommendations

---

# Recommendations

- All decisions are trade-offs
- Assess your needs
- Compare to each architecture's strengths & weaknesses

---

# Recommendation: Static sites

- Content focus
  - _e.g._ blogs, documentation
- SEO
- Little to no dynamic content
- Uniform experience for all users
- Easily cached on a CDN
- Patterns: static-site generation, islands
- Tools: Astro, Hugo, Eleventy

---

# Recommendation: Server-rendered sites

- Content focus
  - _e.g._ e-commerce, simple dashboards
- SEO
- Different experience for different users
  - _e.g._ localization, logged-in/-out
- Patterns: server-side rendering, islands
- Tools: Wordpress, your favorite language's framework

---

# Recommendation: Single-page applications

- Highly interactive web applications
  - _e.g._ Google Docs, Figma
- Elements that follow the user throughout their experience
  - _e.g._ music player, chat panel
- URL routing is not meaningful to user
- Long sessions
- SEO doesn't matter
- Internal application with hardware & connection guarantees
- Patterns: client-side rendering, client-side navigation
- Tools: Vite with your preferred front-end framework

---

# Recommendation: Multi-page applications

- Diverse content: static, interactive
  - _e.g._ Khan Academy, Jira
- Rich logged-out content
  - Server-side rendered
  - Pre-rendered routes for static content
  - Good performance
  - Good SEO
- Dynamic logged-in experiences
  - Client-side rendering/navigation
  - Immersive user experience
- Patterns: hybrid rendering, hybrid routing, islands
- Tools: Next, Remix, SveltKit, Nuxt

<!--
- But don't just take my word for it...
-->

---

# Meta-frameworks are the future

> If you want to build a new app or a new website fully with React, we recommend
> picking one of the React-powered frameworks popular in the community.
> Frameworks provide features that most apps and sites eventually need,
> including routing, data fetching, and generating HTML.

-- [React docs](https://react.dev/learn/start-a-new-react-project)

> We recommend using SvelteKit

-- [Svelte docs](https://svelte.dev/docs/introduction#start-a-new-project)

> We highly recommend giving [Nuxt] a try

-- [Vue docs](https://vuejs.org/guide/scaling-up/ssr.html#nuxt)

<!--
- If you're in React land, you may have heard a lot about React Server Components and how game-changing they are
- If you use a meta-framework like Next, you get the benefits of that new pattern out-of-the-box
-->

---

# Personal recommendations

- Astro: one framework for all architectures
  - Static sites
  - Server-rendered sites
  - SPAs
  - First-class islands support
- Meta-framework: Next or Remix
- Dark horse: Svelte & SvelteKit

<!--
- Since this is my talk, I'm going to end with some of my personal picks
  - Astro is a really interesting project that checks almost all of the boxes
  - You could have a single repository that generates static pages, server-renders content, and serves SPAs
  - Bonus: You get to use whatever front-end framework you want... even more than one
    - Probably don't do that!
- A safer bet might be to pick a meta-framework like Next or Remix
  - There are tons of documentation and examples out there for Next
- A finally, if you're open to options other than React: I highly recommend checking out Svelte
  - SvelteKit has its quirks, but Svelte is my favorite way to author web apps
  - It has a small bundles, fast interactions, and shaves off all of the React's painful edges
-->

---

# Other patterns to watch

- **View Transitions**: A browser-native way to animate page transitions
  - Improve experience for static & server-rendered sites
  - https://caniuse.com/view-transitions
- **Serverless/Edge functions**: On-demand servers to handle simple requests
  - Cheap option to add server-style functionality
  - Options for persistent data
- **Super HTML**: Libraries that add interactivity to HTML code
  - Make adding client-side interactions easier on statically-/server-rendered
    pages
  - Examples: htmx, Hotwire, Alpine.js
- **Web components**: The browser standard for creating reusable interactive
  elements
  - Supported by all major browsers: https://caniuse.com/custom-elementsv1
  - Frameworks to improve authoring experience: lit, Stencil

<!--
- I chose to focus on the growth in meta-frameworks for this talk, but
- There is a growing movement to make static and server-rendered sites more interactive
- Here are some patterns that we didn't have time to discuss that are worth keeping an eye on
-->

---
layout: center
---

# Questions?

---

# Special thanks

- Khan Academy for letting me speak here today
- Emily Janzer, Josh Smith, and Luke Rathbun for reviewing these slides
- Anne McPherson for giving up her evenings with me this month

---
layout: end
---

# Thank you!
