# Scripts

The package has no build: `src` is published as it is.

## Release

### `npm run changeset:add`

```sh
changeset
```

Asks for the bump (patch, minor, major) and a summary, and writes them in `.changeset/`.

### `npm run changeset:bump`

```sh
changeset version
```

Consumes the files in `.changeset/`: bumps `version` in `package.json` and adds the summary to `CHANGELOG.md`.

### `npm run build:release`

```sh
npm pack && changeset publish && git push --follow-tags
```

Stops at the first step that fails.

| Step                     | Does                                                             |
| ------------------------ | ---------------------------------------------------------------- |
| `npm pack`               | writes the `.tgz` that would be published, to check its contents |
| `changeset publish`      | publishes the version in `package.json` to npm and tags it       |
| `git push --follow-tags` | pushes the commits and the tag                                   |

Needs to be logged in to npm with an account that can publish `outgrid`.
