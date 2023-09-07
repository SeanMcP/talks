# The Next Generation of Front-End Architecture

Sean McPherson
Software Engineer, Khan Academy

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

1. Architectures
2. Patterns
3. Examples & Tradeoffs
4. Recommendations

---

# Definitions

**Patterns**: general and reusable solutions to commonly occurring problem

**Architecture**: design decisions related to overall system structure and behavior
- Comprises multiple patterns

[SEI CMU. (n.d.) "Software Architecture".](https://www.sei.cmu.edu/our-work/software-architecture/)

---

# Architectures

<!--
- We're going to proceed through these in roughly chronological order
-->

---

# Architecture: Static sites

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

# Architecture: Server-rendered sites

- Applications running on a computer
- Receive network requests and respond with HTML
- Rely on HTML forms for user input
- Client-side JavaScript for interactivity
    - jQuery plugins for UI components
- Examples: Wordpress (PHP), Rails (Ruby), Django (Python), Express (Node.js)

<!--
- This next era was the begining of web-based "applications"
- Brought truly dynamic content to the web
- Server-rendered sites used two main patterns...
-->

---

# Pattern: Server-side rendering (SSR)

- Server code that renders and returns HTML
- Server can interface with database
- Server-to-server requests are faster
- Secrets are kept on the server
- Status: Solid

<!--
- Each pattern we discuss will have a status at the end
- "Solid" means that you could build your business on their pattern without worrying
- As we will see, other statues inspire much less confidence...
-->

---

# Pattern: Plugins

- Isolated scripts that bring specific interactivity to a site
- JavaScript code that is paired with a DOM node
- JS runs on the client to create the UI in the DOM
- Powered by jQuery and MooTools
- Status: Shaky

<!--
- The status here means that you could use it today, but don't expect it to last long
- There are some contexts where plugins might be the best pattern
- Replaced by web components and islands (which we will discuss later)
- The server-rendered site architecture has some tradeoffs...
-->

---

# Tradeoffs: Server-rendered sites

- Full-page loads feel slow
- Server issues may increase time to first byte (TTFB)
    - Traffic surges
    - Global user base

---

# Architecture: Early single-page applications (SPAs)

- Highly interactive and immersive experiences
- Try to recreate native applications on the web
    - Initally desktop programs
    - Later mobile apps
- Needed to recreate browser functionality like routing
- Required browser plugins to run applications
- Examples: Macromedia Flash, Microsoft Silverlight

<!--
- This was an exciting time to build applications
- Magic of creating applications, games, and sites with Flash
- Introduced a few important patterns...
-->

---

# Pattern: Client-side rendering

- Single root node in an empty HTML page
- Large bundle that builds site on node when executed
- Typically created with a frameworks
- Client-side code handles all updates
- Status: Solid

---

# Pattern: Client-side navigation

- All "navigation" occurs within a single HTML page
- Sometimes mocks URL changes with History API
- Client-side code determines what views to render
- Status: Solid

---

# Tradeoffs: Early SPAs

- Depended on plugins
    > To view this content, please install Microsoft Silverlight
- Not accessible (see [WCAG "Robust"](https://www.w3.org/WAI/fundamentals/accessibility-principles/#robust))
- Poor performance
- Poor security

<!--
- Ultimately these technologies failed to revolutionize the web
- Steve Jobs famously killed Flash by not supporting it in the iPhone
- The patterns they introduced became the foundation behind...
-->

---

# Architecture: Modern SPAs

- Same goals of early SPAs
- Powered by front-end JavaScript frameworks
    - Angular, Ember, React, Vue, Svelte
- Provide app-like experiences with web technologies
    - HTML, CSS, and a lot of JavaScript
- Maturation of previous era of SPAs
- Example: `create-react-app` and `react-router-dom`

---

# Tradeoffs: Modern SPAs

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

# Architecture: Multi-page applications (MPAs)

- Combining patterns from server-rendered sites and SPAs
- Server-rendered pages
- Client-side navigation
- Powered by metaframeworks
- Example: Next, Remix
    - Nuxt (Vue), SvelteKit

---

# Pattern: SSR with client-side hydration

- Server renders HTML with JavaScript framework
- Browser paints with initial response from server
- Client fetches/executes JavaScript bundle
- Client-side JavaScript adds interactivity
- Status: Solid

---

# Pattern: Hybrid navigation

- Support client- & server-side navigation
- Page load/refresh makes server request
- User interaction trigger client-side navigation
- Performance benefits on first load
- User experience benefits on navigation
- Status: Developing

---

# Pattern: Hybrid rendering

- Configurable rendering for each route
- Statically-generated pages for static content
- Server-rendered pages for interactivity, personalization
- Status: Developing

<!--
- Next and Astro support this for React sites
-->

---

# Pattern: Islands

- Also called "Islands Architecture"
- Small, focused chunks of interactivity
- Pre-/server-rendered markup is progressively enhanced with client-side JavaScript
- Scripts can be requested and run independently
    - Pattern: Progressive hydration
- Successor to Plugins pattern
- Status: Developing

<!--
- Astro is a framework designed for islands
- Enables you to create sites with any JavaScript framework
- Provides client directives to components that allow you to configure when an island hydrates
-->

---

# Architecture: Modern static sites

- Same features of early static sites
- Use modern tooling to generate HTML pages
    - Typically file-system based page generation
- Use islands pattern for interactivity
- Pages are cached on global CDNs
- Examples: Astro, Next SvelteKit, Nuxt

---

# Pattern: Static-site generation (SSG)

- Automating the process of creating HTML pages
- Support for templates
- File system for directory structures
- Some handle bundling resources
- Status: Solid

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

- The new default pattern for web applications
- Server-side rendered content
    - Good performance for users
    - Good SEO
- Client-side navigation when valuable
    - Improved user experience
- Pre-rendered routes for static content
- Patterns: hybrid rendering, hybrid routing, islands
- Tools: Next, Remix, SveltKit, Nuxt

<!--
- But don't just take my word for it...
-->

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

# Personal recommendations

- Astro: one framework for all architectures
    - Static sites
    - Server-rendered sites
    - SPAs
    - First-class islands support
- Meta framework: Next or Remix
- Dark horse: Svelte & SvelteKit

<!--
- Since this is my talk, I'm going to end with some of my personal picks
- Astro is a really interesting project that checks almost all of the boxes
- You could have a single repository that generates static pages, server-renders content, and serves SPAs
- Bonus: You get to use whatever front-end framework you want... even more than one!
- Probably don't do that
- A safer bet might be to pick a meta framework like Next or Remix
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
- **Edge functions**: On-demand servers to handle simple requests
    - Cheap option to add server-style functionality
    - Options for persistent data
- **Super HTML**: Libraries that add interactivity to HTML code
    - Make adding client-side interactions easier on statically-/server-rendered pages
    - Examples: htmx, Hotwire, Alpine.js
- **Web components**: The browser standard for creating reusable interactive elements
    - Supported by all major browsers: https://caniuse.com/custom-elementsv1
    - Frameworks to improve authoring experience: lit, Stencil

<!--
- I chose to focus on the growth in meta frameworks for this talk, but
- There is a growing movement to make static and server-rendered sites more interactive
- Here are some patterns that we didn't have time to discuss that are worth keeping an eye on
-->

---

# Questions?

---

# Special thanks

- Khan Academy for letting me speak here today
- Emily Janzer, Josh Smith, and Luke Rathbun for reviewing these slides
- Anne McPherson for giving up her evenings with me this month