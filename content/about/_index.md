---
title: About
url: /about
layout: page
---

# About Me

Hello there 👋

My name is Andreas Buob. I live in Bern, Switzerland, and write software for a living. I'm currently employed by Swisscom.

My technical interests are primarily focussed around frontends and their architecture, especially in the context of monorepositories:

-   Maximize reusability across projects and organizations while maintaining operational independence
-   Unify dev-experience across multiple projects, to allow for seamless transfer of dev-resources
-   Strong focus on observability: Designing systems that achieve a high degree of observability out of the box

My interest in monorepositories led me to create [yanice](https://github.com/abuob/yanice) (_yet another incremental command executor_), a tool which allows for orchestrating
command-execution across multiple projects based on changed files (comparing a git revision with the working tree).
It furthermore allows to enforce boundaries between the projects.
Unlike many of the existing monorepo-tooling out there which follow an opinionated "zero-config"-approach, yanice aims to be "all-config",
where everything has to be configured and described, rather than relying on automatic inference.

For those who care about these things, I hold a BSc in Computer Science by ethz.

# About this website

If you're wondering why I have a website to begin with, I've outlined my reasons [here]({{< relref "/blog/2024-09-10-why-have-a-website.md" >}}).
From a technical point of view, it's just a little static website generated using [hugo](https://gohugo.io/), hosted on [GitHub pages](https://pages.github.com/).
The source code can be found [here](https://github.com/abuob/abuob.github.io).
Though I'm involved in quite a bit of frontend-programming at my day job, I'm obviously terrible at design,
please forgive me for the rather rudimentary layout.
