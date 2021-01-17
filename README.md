# Workshop Materials Template

## Getting started

```
git clone --recurse https://github.com/experimental-software/workshop-materials-template.git ${PROJECT_NAME}
```

To reset the branch history, run:

```
cd ${PROJECT_NAME}
git checkout --orphan main
git add .
git commit -m "Initial commit"
```

## TODO

After cloning the repository, you need to do the following steps:

- [ ] [Update dummy config](config.toml)
- [ ] [Update dummy home page text](content/_index.md)
- [ ] [Update dummy subject](content/subject-one)
- [ ] [Add legal text to imprint](content/imprint.html)

## Development

### Run Hugo server

To a development server which always re-renders after every change, run the following command:

```
hugo server
```

### Build website

To generate the HTML for publication, run the following command:

```
hugo --destination docs/
```

## License

This template repository is licensed under the [CreativeCommons Zero](https://creativecommons.org/share-your-work/public-domain/cc0/) license.
