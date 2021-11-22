# Joplin-docs
An attempt to refactor the project documentation. See the [about page](https://xaa.fyi/joplin-docs/about-joplin-docs) for more details.

Web access: [https://xaa.fyi/joplin-docs](https://xaa.fyi/joplin-docs)  
Joplin official website (and documentation):  [joplinapp.org](https://joplinapp.org)

## Roadmap proposal

1) add the existing docs and find a way to auto sync the `/readme` if it stays the official source.
2) extend the docs with the best tips & tricks, receipts from the forum posts and elsewhere.

## Tech

- Based on: Grav flat cms (no database).
- Content: markdown format.
- Langage: php.
- Requirement: >=php7.3, sqlite3 (for fuzzy search).
- Examples in use:
  - [learn.getgrav.net](https://learn.getgrav.org) use it for 7 years, +340 contributors.
  - [docs.ovh.com](https://docs.ovh.com/gb/en/dedicated/ip-fo-move) use it for 4 years, +200 contributors (with a clean implementation on their website).
