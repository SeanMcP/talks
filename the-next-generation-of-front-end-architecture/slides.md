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
3. Trends & Examples
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
We're going to proceed through these in roughly chronological order
-->

---

# Architecture: Static sites

- HTML files on a computer
- Accessed on the internet via an IP address
- Edited directed or updated by FTP/SSH

<!--
The first architecture in web development was static sites
These were files stored in a computer somewhere that you could access on the internet
When you sign up for hosting with one of the big companies, they give you access to a computer where you can store your static files
There aren't any patterns for us to discuss here, beyond using the main web technologies: HTML, CSS, and JS
Static 
-->

---

# Architecture: Server-rendered sites

- Applications running on a computer
- Receive network requests and respond with HTML
- Rely on HTML forms for user input
- Client-side JavaScript for interactivity
    - jQuery plugins for UI components
- Examples: Wordpress (PHP), Rails (Ruby), Django (Python), Express (Node.js)

---

# Pattern: Server-side rendering (SSR)

- Server code that renders and returns HTML
- Server can interface with database
- Server-to-server requests are faster
- Secrets are kept on the server
- Status: Solid

---

# Pattern: Plugins

<!-- TODO: Research this more -->

- Isolated scripts that bring specific interactivity to a site
- JavaScript code that is paired with a DOM node
- JS runs on the client to create the UI in the DOM
- Powered by jQuery and MooTools
- Status: Shaky

<!--
There are some contexts where plugins might be the best pattern
Replaced by islands and web components
-->

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
Ultimately these technologies failed to revolutionize the web
Steve Jobs famously killed Flash by not supporting it in the iPhone
But they introduced some lasting patterns...
-->

---

# Pattern: Client-side rendering

- Status: Solid

---

# Pattern: Client-side navigation

- Status: Solid

---

# Architecture: Modern SPAs

- Same goals of early SPAs
- Powered by front-end JavaScript frameworks
    - Angular, Ember, React, Vue, Svelte
- Provide app-like experiences with web technologies
    - HTML, CSS, and a lot of JavaScript
- Example: `create-react-app` and `react-router-dom`

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

---

# Pattern: Hybrid navigation

- Support client- and server-side navigation
- Performance benefits on first load
- User experience benefits on navigation

---

# Pattern: Hybrid rendering

- Configurable rendering for each route
- Statically-generated pages
- Server-rendered pages

---

# Pattern: Islands

- Successor to Plugins pattern

---

# Architecture: Modern static sites

- Same features of early static sites
- Use mordern tooling to generate HTML
- 

---

# Pattern: Static-site generation (SSG)

---