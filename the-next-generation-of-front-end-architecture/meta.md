**Title:**

- The next generation of front-end architecture
- There are back again
- Back to the future
- What’s old is new
- Nothing new under the sun

**Subtitle:**

**Presentation details:**

In recent years, we have seen a significant shift in front-end architecture from
client-side rendering and single-page applications (CSR/SPAs) to server-side
rendering and multi-page applications (SSR/MPAs). In this talk we will analyze
this trend in its historical context, explore specific examples in the React
ecosystem, and discuss its implications for building robust front-end
applications.

**Please tell us about your topic of interest/presentation:**

This presentation will be slides-driven, and will include some code and
technical information. A rough outline:

- Introduction
- Thesis
- A brief history of serving websites
- Rise of SPAs
- Return to MPAs
- Examples
- Recommendations
- Conclusion
- Q&A

---

Architectures:

- Static sites
- Server-rendered sites
- Single-page applications
- Multi-page applications
- Islands?

Patterns:

- SSG
- SSR
- CSR
- CSN
- Hybrid routing
- Hybrid rendering
- Islands?
- Plugins?

---

> Explore different front-end architecture in a roughly chronological order

> Build our library of architectures and patterns as we go

Outline

- Arch: static sites
- Arch: server-rendered sites
  - Pattern: server-side rendering
  - (Maybe) Pattern: plugins
  - Example: Wordpress
- Arch: single-page applications
  - Pattern: client-side rendering
  - Pattern: client-side navigation
  - Example: `create-react-app` with `react-router-dom`
- Arch: multi-page applications
  - Pattern: server-side rendering _with_ client-side hydration
  - Pattern: hybrid rendering
  - Pattern: hybrid routing
  - Pattern: islands
  - Example: Next and Remix (other: SvelteKit, Nuxt)
- Arch: static sites (revisted)
  - Pattern: static-site generation
  - Pattern: islands [x]
  - Example: Gatsby and Astro (other: Jekyll, Hugo, Eleventy)

---

## Resources

- https://www.webdesignmuseum.org/web-design-history History
- https://www.codeinwp.com/blog/history-of-website-builders/ History
- https://www.patterns.dev/posts/rendering-patterns
- https://jasonformat.com/islands-architecture/

---

## Timeline

- ~~9/2 S: Today~~
- ~~9/4 M:~~
  - [x] Ask two other reviewers
- ~~9/5 T:~~
- ~~9/6 W:~~
  - [x] Send to reviewers
- ~~9/7 R:~~
- 9/8 F:
  - [ ] List feedback
  - [ ] Make changes
- 9/9 S:
  - [ ] Submission

---

## Feedback

- Luke
  - [x] Add reference to Inertia.js
  - [x] Temper language about Flash
  - [ ] Pick color/icon for architecture vs pattern
- Emily
  - [ ] Differentiate between architecture, pattern slides
  - [ ] Visualizations to connect patterns to architectures
  - [x] Be explicit about "island architecture" being classified a pattern
  - [x] Consider "Current status" instead (it might have been the best option at
        the time)
  - [x] Reconsider "shaky" status: maybe unpopular or risky or something else
  - [x] Clarify outline ("Architectures & Patterns" maybe)
  - [x] Typo "a frameworks"
  - [x] Make MPA recommendation fit template from other recommendations
  - [x] Settle on "meta frameworks" or "meta-frameworks"
  - [x] Consider adding React Server Components to pattern
- Josh
  - [ ] Mention JAMstack
  - [ ] "Statues" typo
  - [ ] Serverless in addition to "Edge functions"
