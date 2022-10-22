# TBD Workshop

This repository contains [Workshop Materials](https://github.com/experimental-software/workshop-materials) for TBD.

## Init

This section contains hints for the setup of new workshop materials.
It can be deleted once the initial setup has been completed.

### Create project

See https://github.com/experimental-software/workshop-materials#getting-started

### Setup checklist

- [ ] [Update license information](README.md#license)
- [ ] [Update dummy config](config.toml)
- [ ] [Update dummy home page text](content/_index.md)
- [ ] [Update dummy subject](content/subject-one)
- [ ] [Add legal text to imprint](content/imprint.html)
- [ ] Replace all occurences of the placeholder "TBD"
- [ ] Create [publish script](#publish-script) or [GitHub Action](#github-action)
- [ ] What should be in the `.gitignore`?
- [ ] Optional: Update [reveal.js](https://github.com/hakimel/reveal.js/releases) in [upstream Hugo theme](https://github.com/experimental-software/workshop-materials/tree/master/static/reveal.js).

### Publish script

Here is an example how a `publish.sh` script might look like:

```
#!/usr/bin/env bash

set -e

hugo
rsync -r public/* www.experimental-software.com@ssh.strato.de:example-workshop
rsync -r public/.htaccess www.experimental-software.com@ssh.strato.de:example-workshop
```

### GitHub Action

If the workshop materials should be in a public repository and hosted by [GitHub Pages](https://pages.github.com/), then they can be automatically published after each commit with the help of [GitHub Actions](https://docs.github.com/en/actions).

Refer to https://github.com/peaceiris/actions-hugo#getting-started for instructions how to setup a GitHub Action for the Hugo-based workshop materials.

### License

This template repository is licensed under the [CreativeCommons Zero](https://creativecommons.org/share-your-work/public-domain/cc0/) license.

## Development

### Clone repository

Use the following command to clone the repository:

```
ORG=experimental-software
REPO=example
git clone --recurse git@github.com:${ORG}/${REPO}.git
```

### Run Hugo server

To a development server that always re-renders after every change, run the following command:

```
hugo server
```

### Build website

To generate the HTML for publication, run the following command:

```
hugo --destination docs/
```

## Content authoring

### Page structure

https://fontawesome.com/v5/search?m=free&s=solid%2Cbrands

### Tutorials

Tutorials provide the use with a step-by-step guide for a complex scenario. The content can be created using [Markdown](https://daringfireball.net/projects/markdown/) syntax.

Run the following command to add a new presentation in the `content` directory:

```
hugo new --kind tutorial subject-two/my-tutorial
```

### Articles

Articles provide a free-text page for guides for simple scenarios. The content can be created using [Markdown](https://daringfireball.net/projects/markdown/) syntax.

Run the following command to add a new article in the `content` directory:

```
hugo new --kind article subject-two/my-tutorial
```

### Presentations

Presentations provide slides for a high-level overview over a topic. The content can be created using plain HTML with the [reveal.js](https://revealjs.com/) syntax.

Run the following command to add a new presentation in the `content` directory:

```
hugo new --kind presentation subject-two/my-presentation
```

## Markdown extentions

Along with the Markdown syntax, you can use the following custom [Hugo shortcodes](https://gohugo.io/content-management/shortcodes):

### Info callout box

```
{{< info >}}
Lorem [impsum](https://example.com) dolor sit amet.
{{< /info >}}
```

### Tip callout box

```
{{< tip >}}
Lorem [impsum](https://example.com) dolor sit amet.
{{< /tip >}}
```

### Warning callout box

```
{{< warning >}}
Lorem [impsum](https://example.com) dolor sit amet.
{{< /warning >}}
```

### Table

```
{{< bootstrap-table table_class="table table-bordered" >}}

| Key | Value |
|--|--|
| `content-type` | `application/x-www-form-urlencoded` |

{{< /bootstrap-table >}}
```

### Image

```md
<img alt="Example" src="./img/example.jpg" width="30%" height="30%">
```

## Maintenance

### Improve theme

Usually, while working on the contents of a workshop, it turns out that the theme needs some improvements. Follow those steps in a workshop repository, to get started with improving the theme.

```bash
cd themes/workshop-materials
{
git remote remove origin
git remote add origin git@github.com:experimental-software/workshop-materials.git
git fetch origin
git checkout master
git branch --set-upstream-to=origin/master
}
```

### Update theme

```bash
{
git submodule update --remote
git add .
git commit -m "Update theme"
}

git push 
```

## License

TBD
