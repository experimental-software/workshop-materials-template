# ... Workshop

This repository contains [Workshop Materials](https://github.com/experimental-software/workshop-materials) for ...

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
- [ ] Replace all occurences of the placeholder "..."
- [ ] Create [publish script](#publish-script) or [GitHub Action](#github-action)

### Publish script

Here is an example how a `publish.sh` script might look like:

```
#!/usr/bin/env bash

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

### Tutorials

#### Add a new tutorial

Run the following command to add a new presentation in Hugo's `content` directory:

```
hugo new --kind tutorial subject-two/my-tutorial
```

#### Content syntax

The tutorials can be created using [Markdown](https://daringfireball.net/projects/markdown/) syntax.

#### Content syntax extensions

Along with the Markdown syntax, you can use the following custom [Hugo shortcodes](https://gohugo.io/content-management/shortcodes):

**Info callout box**

```
{{< info >}}
Lorem [impsum](https://example.com) dolor sit amet.
{{< /info >}}
```

**Tip callout box**

```
{{< tip >}}
Lorem [impsum](https://example.com) dolor sit amet.
{{< /tip >}}
```

**Warning callout box**

```
{{< warning >}}
Lorem [impsum](https://example.com) dolor sit amet.
{{< /warning >}}
```

### Presentations

#### Presentation syntax

The presentations can be created using plain HTML with the [reveal.js](https://revealjs.com/) syntax.

#### Add a new presentation

Run the following command to add a new presentation in Hugo's `content` directory:

```
hugo new --kind presentation subject-two/my-presentation
```

## Maintenance

### Update theme

```
git submodule update --remote
git add .
git commit -m "Update theme"
```

## License

...
