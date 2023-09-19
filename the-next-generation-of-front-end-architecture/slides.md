---
layout: intro
title: The Next Generation of<br/>Front-End Architecture
---

# The Next Generation of<br/>Front-End Architecture

Sean McPherson, Software Engineer @ Khan Academy

<!--
- It's great to be speaking here at TechFest
- This is my first in-person conference after two remote events
- It feels great to be back in the same room as other people
- This is _The Next Generation of Front-End Architecture_
- And before I being, I feel like I need to apologize
- When I came up with the title of this talk...
  - the connection to the Star Trek series didn't occur to me
- So if you came here for a Star-Trek-themed talk, I'm sorry to disappoint you
- But... if you're willing to stick around...
  - I think you'll enjoy this discussion of modern front-end architecture
- Before I go any further, let me introduce myself...
-->

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

<!--
- My name is Sean McPherson
- and I'm a software engineer mostly in the world of front-end web development
- I work for Khan Academy, which is...
- KHAN_ACADEMY_TAGLINE
- If you're interested in EdTech and especially AI in education...
  - I'd love to chat afterwards
- Before Khan Academy, I worked for Niche.com which...
  - Is headquartered here in Pittsburgh (Any Niche folks here?)
- And before that I lived in Atlanta and worked for TSYS
- And once upon a time, I was a classroom teacher
- I live here in Pittsburgh--just over the river in Wilkinsburg---with my family
- And I'm excited to be here today talking about front-end architecture...
-->

---

# About this talk

Learn about modern front-end architectures and their patterns

Focus on the JavaScript ecosystem

1. Architectures & Patterns
2. Examples & Tradeoffs
3. Recommendations
4. Questions

<!--
- Today our goal is to LEARNING_OBJECTIVE
- I'm going to focus on the JavaScript ecosystem
  - But the concepts will be applicable in other language environments
- We're going to look at a five-ish front-end architectures
- And the patterns that make them work
- We'll look at examples of each architecture
- And analyze some of their tradeoffs
- Finally we'll end with some recommendations for choosing an architecture
- Before leaving some time for questions at the end
- Alrighty, let's kick it off with some terms...
-->

---

# Definitions

<!-- TODO: Consider switching the order -->

- **Patterns**: general and reusable solutions to commonly occurring problem 🧱

- **Architecture**: design decisions related to overall system structure and
  behavior 🏠
  - Comprises multiple patterns

[SEI CMU. (n.d.) "Software Architecture".](https://www.sei.cmu.edu/our-work/software-architecture/)

<!--
- We're going to be talking about patterns and architectures
- For the purpose of this talk, we're going to use some definitions that are...
  - Lightly edited from PGH's own Software Engineering Institute at CMU
- Patterns are PATTERN_DEFINITION
- And architectures as ARCHITECTURE_DEFINITION
- To help distinguish between the two, I'll use emojis to key you in
  - The brick emoji for patterns
    - a general and reusable component that is used to build something bigger
  - And the house emoji for architectures
    - Something that is made up of multiple patterns, like bricks in a house
- Does that sounds reasonable? Yeah? Alright.
- Let's get started with...
-->

---
layout: center
---

# Architectures

<!--
- BODY
- We're going to proceed through these in roughly chronological order
- And this isn't going to be an exhaustive list of all front-end architectures
- We'll focus on the ones that are still relevant today
- The first architecture historically and the first one we'll look at is...
-->

---

# 🏠 Architecture: Static sites

- HTML files on a computer
- Accessed on the internet via an IP address
- Edited directed or updated by FTP/SSH

<!--
- ARCHITECTURE_TYPE
- All sites were just files stored on a computer somewhere...
  - that you could access on with an internet connection
- Any updates to the site required changing those static files directly...
- Or using a protocol like FTP or SSH
- This might sound ancient to some of you, depending on your experience
- But this is still a common practice for serving websites today
- When you sign up for hosting with one of the big companies like Host Gator...
  - They give you access to a computer where you can store your static files
- There aren't any patterns for us to discuss here...
  - Beyond using the main web technologies: HTML, CSS, and JS
- Let's at an example with the first website ever...
-->

---
layout: center
---

<a href="http://info.cern.ch/hypertext/WWW/TheProject.html">
  <img alt="The WWW info page from CERN" src="/images/cern.png" />
</a>

<!--
- The WWW info page from CERN
- Created by Tim Berners-Lee
- It is just a few static HTML pages on the same computer for thirty years
- Another example of a static site is...
-->

---
layout: center
---

<a href="https://www.spacejam.com/1996">
  <img alt="Space Jam" src="/images/space-jam.png" />
</a>

<!--
- The famous Space Jam website
- Survived the test of time thanks to this simple architecture
-->

---

# ⚖️ Tradeoffs

Static sites

- Content is... static
- Low/no interactivity
- No dynamic content

<!--
- The tradeoffs for these original static sites it that the content is static
- There is little to interact with
- There is no concept of a logged-in experience
- You could make network requests that communicate with a server...
  - But at that point you should probably consider building a...
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
- TITLE
- This next era was the beginning of web-based "applications"
- Brought truly dynamic content to the web
- TODO: Expand these notes
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
- The status here means that you could use it today...
  - But don't expect it to last long
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

<!--
- Best for short sessions
- Thanks to network latency, navigation multiple pages in a session...
  - Is heavier than loading everything up front
- A great example of a server-rendered site today is...
-->

---
layout: center
---

<a href="https://developer.mozilla.org/en-US/">
  <img alt="MDN" src="/images/mdn.png" />
</a>

<!--
- MDN
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
  - Spun up a whole industry of Flash games that I remember fondly
- Just a little tangent: I got started in web development thanks to Flash.
  - The first sites I built were in Flash or for hosting Flash apps
  - So forgive me but I look back on this era with some rose-tinted glasses
- Okay, tangent over!
- This architecture introduced a few important patterns...
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
- I'm classifying this pattern as "Solid" because of...
  - Later advancements with other frameworks that we'll discuss
- FTR: I do **not** recommend building a new SPA with Flash or Silverlight!
- A pattern that goes hand-in-hand with client-side rendering is...
-->

---

# 🧱 Pattern: Client-side navigation

Single-page applications

- All "navigation" occurs within a single HTML page
- Sometimes mocks URL changes with History API
- Client-side code determines what views to render
- Current status: Solid

<!--
- TITLE
- This is giving the user the experience of navigating between pages...
  - Without actually leaving the initial page
- Since the "navigation" happens entirely on the client...
  - Transitions can be almost instantaneous
- They can even be animated to give the user that native experience
- This pattern is also "Solid" because it is useful today in certain contexts
- Even though both SPA patterns are solid, there were some notable tradeoffs...
-->

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
- Their reliance on non-web technologies was a major issue
  - I remember the days of talking to my grandparents over the phone...
  - And trying to walk through the process of installing Flash or Silverlight
- A11y: non-web technologies left users with disabilities out in the cold
  - Screenreaders couldn't access the content
  - Keyboard users couldn't interact with the apps

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

<!--
- TITLE
- This is probably what we all think of when we hear "SPA"
- It built upon the previous iteration of the architecture...
  - With new frameworks powered by JavaScript
- These frameworks made it possible to provide an app-like experience...
  - But with native web technologies
- This is the era of `create-react-app`, where bootstrapping a new SPA...
  - Required a single command in the terminal
  - And the willingness to go fast and break things
- A great use case for the modern SPA architecture are...
-->

---
layout: center
---
<a href="https://www.figma.com/">
  <img alt="Figma" src="/images/figma.png" />
</a>

<!--

- Highly interactive web applications like Figma
- If you're building something that is closer to an app than a website...
  - Then SPA is probably the best architecture for your project
  - Figma is like that: it's basically Adobe Illustrator in the browser
- But problems arise when you try to use this architecture in other contexts...
-->

---

# ⚖️ Tradeoffs

Modern SPAs

- Long initial loads
- Bad SEO
- Network request waterfalls
- Too easy to make inaccessible

<!--
- Once the SPA was up and running, it was great
- But the initial load was a major issue
- Chaining network requests to load all of the JavaScript and CSS
- SEO: initially Google's web crawler couldn't index any content on SPAs
  - That has changed, but long load times result in poor web vitals
- A11y: it was too easy to make inaccessible
  - The frameworks didn't provide any guardrails
  - And the community didn't always have the knowledge to make them accessible
- To address some of these concerns, another "modern" architecture emerged...
-->

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
- TITLE
- These used leveraged modern tooling and frameworks originally used for SPAs...
  - To generate static sites
- These sites can add interactivity with the islands pattern...
  - That we'll look at in a moment
- The static files of the sites can be cached on global CDNs like CloudFlare...
  - To provide a fast loading experience for users around the world
- This architecture is sometimes called "JAMstack"
  - Which stands for JavaScript, APIs, and Markup
  - But what exactly that meant was never very clear
- JAMstack was a term invented by host Netlify...
  - To advertise this architecture (hosted on their platform)
  > The core principles of pre-rendering, and decoupling, enable sites and
  > applications to be delivered with greater confidence and resilience than ever
  > before.
- Though the term "JAMstack" has faded into history...
  - The architecture is still going strong
- Some patterns that are important to this architecture are...
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

<!--
- TITLE
- This is the pattern that makes static sites an attractive option for...
  - Modern developer
- Developers get to use the tools that they are familiar with...
  - Like React, Vue, or Svelte
  - To template, style, and generate a large number of HTML pages
- Static-site generators run against a directory and...
  - Look for any filetype (usually markdown) that they can convert into HTML
- Some static-site generators handle tricky things like...
  - Resource bundling, and responsive images out of the box
- This is a "solid" pattern for generating static sites with...
  - Tens to hundreds to thousands of pages
- Once you have the pages generated, modern static sites use...
-->

---

# 🧱 Pattern: Islands

Multi-page applications

- Small, focused chunks of interactivity
- Pre-/server-rendered markup is progressively enhanced with client-side
  JavaScript
- Scripts can be requested and run independently
  - 🧱 Pattern: Progressive hydration
- Successor to Plugins pattern
- Also called "Islands Architecture" (sorry!)
- Current status: Developing

<!--
- Islands for interactivity
- These are small, focused chunks of interactive and/or dynamic content
- They are typically server-rendered or pre-rendered, which means...
  - The initial markup is available to the browser on the first load
- Individual scripts then run on the client to...
  - Progressively enhance the markup with data and event listeners
  - This step is called "hydration"
- Some libraries support progressive hydration, which means...
  - The developer can configure when the hydration happens (load, scroll, etc.)
- I view these as the successor to plugins because they provide an initial state
- This pattern is frequently referred to as the "Islands Architecture"
  - I'm sorry about the naming confusion!
- I think the idea of islands better fits as a pattern
  - Especially because it can be used in multiple architectures
- If you're interested in exploring this pattern, I recommend...
  - Looking into Astro, which is a framework designed around islands
- A good example of modern static sites is...
-->

---
layout: center
---

<a href="https://fluent2.microsoft.design/">
  <img alt="Microsoft Fluent Design" src="/images/ms-fluent-design.png" />
</a>

<!--
- A documentation site like Microsoft's Fluent Design
- This site is built with Astro and showcases...
  - The patterns of modern static sites
- All of the pages are generated at build time and then cached for visitors
- There are islands sprinkled throughout the docs pages...
  - To enable the visitor to interact with the design system
- While the architecture is a good fit for some sites, there are...
-->


---

# ⚖️ Tradeoffs

Modern static sites

- Limited dynamic content
- Performance challenge to add significant interactivity
- Build times/resources for large sites

<!--
- Tradeoffs
- Islands provide an option for dynamic content, but...
  - By design that will be limited to small sections of the page
- And coordinating the the interactions between multiple islands
  - Becomes a logistical and performance challenge
- And finally build times can grow significantly as...
  - The number of pages increases
- Typically static-site generators will generate every page on every build...
  - Even if the content hasn't changed, which gets expensive
- Some try to only generate pages that contain information that has changed...
  - But that is a hard problem to solve
-->

---

# 🏠 Architecture: Multi-page applications

- Abbreviated MPAs
- Combining patterns from server-rendered sites and SPAs
- Powered by meta-frameworks
- Server-side rendering _and_ client-side rendering
- Full-page navigation _and_ client-side navigation
- Example: Next, Remix
  - Nuxt (Vue), SvelteKit

<!--
- TITLE
- This is a new architecture that combines aspects of...
  - Server-rendered sites and single-page applications
- Out of the box, these meta-frameworks provide...
  - Server-side rendering
  - Client-side rendering
  - Server-side navigation
  - Client-side navigation
- The big examples in the React space are Next and Remix
  - But most JS rendering libraries have a meta-framework like...
  - Nuxt for Vue and SvelteKit for Svelte
- These examples are all in JavaScript land
  - But there are meta-frameworks for your preferred language too
  - A friend called out Intertia as an interested option using PHP
- Multi-page apps expand on some previous patterns like...
-->

---

# 🧱 Pattern: SSR with client-side hydration

Multi-page applications

- Server renders HTML with JavaScript framework
- Browser paints with initial response from server
- Client fetches/executes JavaScript bundle
- Client-side JavaScript adds interactivity
- Current status: Solid

<!--
- TITLE
- Similar to server-side rendering, there is a server running that renders HTML
- This response is available to the browser on initial load
- Shortly after, the client fetches and executes the JavaScript bundle...
- That takes the markup that was initially rendered on the server...
- And "hydrates" it with interactivity
- In React, this involves calling `hydrate` or `hydrateRoot` on the client...
  - To create a virtual DOM tree on a DOM node that was rendered on the server
  - (Hopefully those trees match, otherwise client-side React with re-render)
- This is a solid pattern for improving web vitals for...
  - A web app that uses a JS rendering library
- After SSR with client-side hydration, the next pattern is...
-->

---

# 🧱 Pattern: Hybrid navigation

Multi-page applications

- Support client- & server-side navigation
- Page load/refresh makes server request
- User interaction trigger client-side navigation
- Performance benefits on first load
- User experience benefits on navigation
- Current status: Developing

<!--
- TITLE
- This involves supporting both client- and server-side navigation
- When a user first visits your site, they see a server-rendered page
- The client is hydrated in the background, adding interactivity
- When the user navigates within your app, client-side navigation kicks in...
- And handles the navigation without a page request to the server
- At any point when the user hits refresh, they get a server-rendered page
- This provides the performance benefits of server-side rendering...
  - And the positive user experience of client-side navigation
- This pattern is still developing, because...
  - It is tied closely to the meta-frameworks that support it
- This pattern has some overlap with...
-->

---

# 🧱 Pattern: Hybrid rendering

Multi-page applications

<!-- TODO: Incorporate client-side rendering -->

- Configurable rendering for each route
- Statically-generated pages for static content
- Server-rendered pages for interactivity, personalization
- Current status: Developing

<!--
- TITLE
- This patterns allows you to predetermine when you want each page rendered
- For static content, you can generate the HTML at build time...
  - And serve the files like a static-site architecture
- For pages that require interactivity or personalization...
  - You can server-render the page on the fly
- Next and Astro support this for React sites
-->

---
layout: center
---

<a href="https://www.notion.so/">
  <img alt="Notion" src="/images/notion.png" />
</a>

---

# Architectures & Patterns

|                        | <div style="text-align:center">Static sites</div> | <div style="text-align:center">Server-rendered<br/>sites</div> | <div style="text-align:center">Single-page<br/>apps</div> | <div style="text-align:center">Multi-page<br/>apps</div> |
| ---------------------- | ------------------------------------------------- | -------------------------------------------------------------- | --------------------------------------------------------- | -------------------------------------------------------- |
| Static-site generation | <div style="text-align:center">✅</div>           |                                                                |                                                           | <div style="text-align:center">✅</div>                  |
| Server-side rendering  |                                                   | <div style="text-align:center">✅</div>                        |                                                           | <div style="text-align:center">✅</div>                  |
| Islands                | <div style="text-align:center">✅</div>           | <div style="text-align:center">✅</div>                        |                                                           | <div style="text-align:center">✅</div>                  |
| Client-side rendering  |                                                   |                                                                | <div style="text-align:center">✅</div>                   | <div style="text-align:center">✅</div>                  |
| Client-side navigation |                                                   |                                                                | <div style="text-align:center">✅</div>                   | <div style="text-align:center">✅</div>                  |
| Hybrid navigation      |                                                   |                                                                |                                                           | <div style="text-align:center">✅</div>                  |
| Hybrid rendering       |                                                   |                                                                |                                                           | <div style="text-align:center">✅</div>                  |

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
