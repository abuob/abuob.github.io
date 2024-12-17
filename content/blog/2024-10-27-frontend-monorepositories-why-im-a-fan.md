---
title: "Frontend Monorepositories: Why I'm a fan"
date: 2024-10-27T10:06:56+02:00
tags: []
draft: false
slug: 'frontend-monorepositories-why-im-a-fan'
---

When I started to work professionally on a bigger frontend project for the first time, I joined a multi-repository-setup:
There was our main repository and then several library-repositories, which published npm-packages that our main-repository depended upon.

The libraries were relatively simple: Small setup, fast builds and on their own relatively easy to deal with.
The pain was integrating them back into our main repository: It required multiple pull-requests across different repositories,
and forced us in some cases to fix breaking changes caused by someone else who made a change but did not update the version in our main repository, delegating that work to whoever had to update next.

We were rather unhappy with that particular situation and ultimately combined all the different projects into a single monorepository.
Since then, I've worked on multiple projects with a monorepository-setup, have written tooling for them (e.g. [yanice](https://github.com/abuob/yanice)) and administered their technical setup,
and have become incredibly fond of them. As elaborated below, they provide an array of benefits but also impose a lot of difficult challenges which one must solve, which I happen to love doing.

## Monorepository: Move challenges from process to technical

In a multi-repository-setup, a lot of organizational process is required to ensure the moving parts aren't breaking each other.
For example: If we open a pull-request for a library, how can we know that it doesn't break a consumer?
Consumers must either be mandated to use some form of Contract Tests, which I find often rather impractical in the frontend-space, or alternatively,
that whoever changes the library is mandated to ensure it doesn't break any consumer, which in turn often involves a lot of manual overhead, like testing library-release-candidates and whatnot.
All of this is rather hard to enforce, and "quick changes" to one library can cause a lot of work downstream -
especially if this work, as is often the case in enterprise-projects I've seen so far, is delegated to whichever poor sod is next required to update library-versions.

In a monorepository, such a process is obsolete: If one touches a library within the monorepository, every project consuming that library can directly run its test against it,
catching breaking changes in the same pull-request, ensuring that no change can be made without passing existing tests.

## Consistency across projects

Furthermore, it is much easier to enforce consistency across different projects: Establishing patterns, linting rules, project-crossing tests and general dev-experience consistency is much easier
to achieve when everything is in a single place. It also forces all the different participants to talk with each other:
Instead of everyone having their own little garden (separate repository) where they can do whatever they want, there's visibility and accountability towards everyone in the monorepository.
Even just knowing who works on which part of the monorepository and getting frequently exposed to their work can help a lot to bridge organizational gaps between devs,
making it easier to collaborate across teams and other organizational units.

## The price one pays

Monorepositories are no silver bullet. There's a hefty price to be paid; it brings a lot of challenges with it.
If they are not properly addressed, it will cause a lot of friction for the involved developers, and will generally be a worse situation than a multi-repository-setup.

The most obvious price is pipeline performance: As all projects are in the same place and as we decidedly want to make sure any change does not break any single project, all tests that are impacted
by any given change must be run. This can be very resource intensive, and brings challenges like having some form of "change-detection" in the pipeline to ensure
we really only run the tests that need to be run (to address this particular challenge, I've built the aforementioned [yanice](https://github.com/abuob/yanice)).

The same is true for local tooling: Developers require utility-scripts which allow them to only format, lint and test "their" changes,
rather than running everything locally every time they touch something.

Another challenge is what I call "premature DRY": Now that we can share code very easily across projects, we're inclined to do this a bit too much.
It is vital to shape the dependency-graph between the different projects so that the "hot paths" (parts which are touched often) aren't relied on by too many at the same time.
Libraries that include names like "common", "shared", "core" etc. are very tempting but, as I had to learn the hard way over multiple attempts, tend to grow too uncontrolled
and make proper change-detection for efficient pipelines essentially impossible.

## Higher floor, higher ceiling

These challenges must not be underestimated: Having a big monorepository with a bad developer experience is a terrible situation to be in.
Devs will start to loath the long build pipelines and some will look for easy solutions to improve the situation ("let's make some checks optional!"),
and if it takes too much time to run tests (or any other checks) locally, will simply try to avoid or work around them as much as they get away with.
This leads to bad test coverage, which then leads to people starting to break each other's projects, which in turn will lead to friction between teams, and so on.
It's a vicious cycle that must be avoided at all costs.

To sum it up: If the challenges are not properly addressed, a multi-repository-setup is probably preferable,
because there it's at least easy to assign responsibilities and keep the build-process relatively simple and cheap, at the cost of process overhead.
But if one is willing and capable to pay the price and address the difficult challenges monorepositories pose (challenges which I personally happen to really like),
the ceiling of what one can do with them is much higher than what is possible with a multi-repository-setup.
