# Jilin Men Academic Website

This is a simple Jekyll/GitHub Pages academic website based on Academic Pages.
The homepage is intentionally data-driven so routine updates do not require
editing page layout code.

## Update Content

Most homepage content lives in:

```text
_data/profile.yml
```

Edit that file to update:

- `summary`: short biography on the homepage
- `news`: recent news
- `apps`: web apps and tools
- `publications`: selected publications grouped by year
- `presentations`: invited talks and conference presentations
- `training`: workshops and training activities
- `honors`: awards
- `service`: reviewer and guest-editor service

Site-wide identity and sidebar links live in:

```text
_config.yml
```

Header navigation lives in:

```text
_data/navigation.yml
```

Homepage layout lives in:

```text
_pages/about.md
```

Homepage styles live in:

```text
_sass/layout/_academic_home.scss
```

## Preview Locally

Install dependencies once:

```bash
bundle install
```

Preview the site:

```bash
bundle exec jekyll serve -l -H localhost
```

Then open:

```text
http://localhost:4000
```

On Windows, if native Ruby gems fail to compile, use RubyInstaller with MSYS2
development tools or the repository's Docker/DevContainer workflow.

## Deploy

Push changes to the GitHub repository. GitHub Pages will rebuild the site
automatically for `https://jilinmen.github.io`.
