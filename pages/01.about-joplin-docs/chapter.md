---
title: 'About joplin-docs'
date: '14:22 16-11-2021'
taxonomy:
    category:
        - docs
routes: {  }
slug: about-joplin-docs
---

# In a nutshell

The Joplin-docs objective is to unify the documentation. A user-friendly and qualitative area maintained by the community for new & advanced Joplin users. A place where official doc and extended doc (tip&tricks, howto) can live together.

Nowadays Joplin documentation is in a giant readme file and the rest is divided in the [Forum](https://discourse.joplinapp.org), official [website](https://joplinapp.org), [Discord](https://discord.gg/ha87Fu62) and [GitHub](https://github.com/laurent22/joplin/tree/dev/readme). When discovering the project, it’s a game of back and forth between those sources. The docs exist but is difficult to follow.

[Join us](https://discourse.joplinapp.org) on the  forum to continue the discussion, give a hand or share your thoughts about this initiative.

**Current features**

- Fuzzy search,
- Keep track of pages read,
- TOC,
- like/dislike buttons,
- Better navigation (sidebar toc always visible, search, breadcrumb, anchors),
- Git sync (currently disabled but working),
- Backend for Super-Editors & Admins,
- RSS feed

**Gotchas**
- Work in progress (demo proof of concept).
- Content structure is a proposal.
- Theming is a quick test.

**Pros**
- Flexible documentation website.
- Grav flat CMS behind for easy management.
- Content is markdown files.
- Easier to find specific docs or get the docs overview.
- Can live separately from the main app repo and get faster merge requests.

**Cons**
- There is a system in place already.
- Docs structure is different than the existing.

**Roadmap proposal**
- [ ] Side project or official documentation entry point. discussion?
- [ ] Define the structure.
- [ ] Define the content (a copy - or sync - the official /readme or only extend the docs only?).
- [ ] Deal with dynamic pages (eg plugins list)
- [ ] Define a workflow for contribution and content structure changes.
- [ ] Write contributing guidelines.
- [ ] Call for co-admins and moderators.
- [ ] Hosting & domain name discussion.
- [ ] Clean redesign with BS5

**Based on**
- [https://github.com/hibbitts-design/grav-skeleton-learn2-with-git-sync](https://github.com/hibbitts-design/grav-skeleton-learn2-with-git-sync)
- [https://github.com/getgrav/grav-learn](https://github.com/getgrav/grav-learn)
- Examples in use:
  - [learn.getgrav.net](https://learn.getgrav.org) use it for 7 years, +340 contributors.
  - [docs.ovh.com](https://docs.ovh.com/gb/en/dedicated/ip-fo-move) use it for 4 years, +200 contributors (with a clean implementation on their website).
