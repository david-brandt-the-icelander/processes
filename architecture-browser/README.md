# Architecture browser

A static web page that shows a repository's architecture from the JSON diagrams in its `.dev/` folders: the component, class, state and deployment diagrams described by the skills in [Agents/Skills](../Agents/Skills/README.md).

Live at <https://icelander.net/v1/apps/architecture-browser>. For example, [retro-games](https://icelander.net/v1/apps/architecture-browser?url=https://github.com/david-brandt-the-icelander/retro-games).

## Using it

- Open the page and give the address of a public repository, or of a folder in one. After that the address field is gone: the page shows that repository until the address changes.
- Or pass the address in the query string: `?url=https://github.com/owner/repo`. It takes a repository, a branch or tag (`/tree/<ref>`, slashes in the name included) and a folder (`/tree/<ref>/<folder>`).
- The left column lists the folders that have diagrams, as a tree; the letters after each name are the kinds of diagram there. The address of a folder's view ends in `#<folder>`, so it can be linked to.
- Each diagram is drawn, then listed in full: its parts, its relationships or transitions, and the source files it cites, linked to the repository.

## How it works

Everything runs in the browser. For GitHub it lists the repository with one call to the GitHub API (the default branch, then the recursive tree) and reads each `.dev/*.json` file from `raw.githubusercontent.com`. Unauthenticated, the GitHub API allows 60 requests an hour per address, and a page load uses two. For GitLab it uses the GitLab API's repository tree and raw file endpoints. Other hosts are not supported: a plain git server can't be listed from a browser.

Diagrams are drawn with [Mermaid](https://mermaid.js.org/) 11.4.1, loaded from jsDelivr. If it can't load, the tables still show everything. The page has no build step, no server and no other dependencies: it is one HTML file.

The styling is a placeholder. A design pass is still to come.

## Publishing

`index.html` is the source. The copy on icelander.net is `site/apps/architecture-browser.html` in the icelander.net repository; update it by copying this file there and deploying the site.
