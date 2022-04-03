# ... Workshop

This repository contains [Workshop Materials](https://github.com/experimental-software/workshop-materials) for ...

## Init

### Create project

See https://github.com/experimental-software/workshop-materials#getting-started

### Update dummy content

After cloning the repository, you to replace the dummy content from the template with the content of your workshop materials:

- [ ] [Update license information](README.md#license)
- [ ] [Update dummy config](config.toml)
- [ ] [Update dummy home page text](content/_index.md)
- [ ] [Update dummy subject](content/subject-one)
- [ ] [Add legal text to imprint](content/imprint.html)
- [ ] Replace all occurences of the placeholder "..."

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
