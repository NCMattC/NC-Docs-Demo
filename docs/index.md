# Welcome to MkDocs

All machines that would be working on the repo would need to install Python and MkDocs. If any plugins for MkDocs wanted to be used, each maintainer would also need to download the same plugin and version. 

This could possibly be mitigated if using Github to build the documentation. (Needs testing)

Using Github:

- Pages would be publicly visible unless NC account has [team subscription](https://github.com/organizations/plan) ($4/mo from my short research).
- Minimal time to convert.
- Could be set up to be automatically built on push (recommended) making no extra work for repo maintainers, or set up to be manually pushed via CLI command (mkdocs gh-deploy).

Using self hosted:

- Everything would stay in house and not rely on an outside source.
- More time and services (Gitlab, or Gitea/Drone CI combo) would be required to set up.