# Welcome to MkDocs

All machines that would be working on the repo would need to install Python and MkDocs. If any plugins for MkDocs wanted to be used, each maintainer would also need to download the same plugin and version. 

This could possibly be mitigated if using Github to build the documentation. (Needs testing)

Using Github:

- Pages would be publicly visible unless NC account has [team subscription](https://github.com/organizations/plan) ($4/mo from my short research).
- Minimal time to convert.
- Could be set up to be automatically built on push (recommended) making no extra work for repo maintainers, or set up to be manually pushed via CLI command (mkdocs gh-deploy).

``` title="Github workflow"
name: Publish docs via GitHub Pages
on:
  push:
    branches:
      - master

jobs:
  build:
    name: Deploy docs
    runs-on: ubuntu-latest
    steps:
      - name: Checkout main
        uses: actions/checkout@v2

      - name: Deploy docs
        uses: mhausenblas/mkdocs-deploy-gh-pages@master
        # Or use mhausenblas/mkdocs-deploy-gh-pages@nomaterial to build without the mkdocs-material theme
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          CONFIG_FILE: mkdocs.yml
          EXTRA_PACKAGES: build-base
          # GITHUB_DOMAIN: github.myenterprise.com
          REQUIREMENTS: requirements.txt
```

Using self hosted:

- Everything would stay in house and not rely on an outside source.
- More time and services (Gitlab, or Gitea/Drone CI combo) would be required to set up.