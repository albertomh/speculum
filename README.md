<!-- markdownlint-disable MD041 -->
![speculum logo](speculum.svg "speculum")

Frontend toolkit for DepositDuck.  
Bootstrap 5 customised to use the project's palette, bootstrap-icons and HTMX.

## Develop

[![pnpm](https://img.shields.io/badge/pnpm-4e4e4e?logo=pnpm&logoColor=f69220)](https://sass-lang.com/dart-sass/)
[![bootstrap](https://img.shields.io/badge/Bootstrap_5-7952B3?logo=bootstrap&logoColor=white)](https://github.com/twbs/bootstrap)
[![bootstrap-icons](https://img.shields.io/badge/Bootstrap_Icons-ffffff?logo=bootstrap&logoColor=7952B3)](https://github.com/twbs/bootstrap)
[![sass](https://img.shields.io/badge/Dart_Sass-cf649b?logo=sass&logoColor=white)](https://sass-lang.com/dart-sass/)
[![htmx](https://img.shields.io/badge/htmx-white?logo=htmx&logoColor=3366CC)](https://github.com/bigskysoftware/htmx)

### Prerequisites

To develop speculum the following must be available locally:

- [pnpm](https://pnpm.io/installation)
- [clean-css-cli](https://www.npmjs.com/package/clean-css-cli)  
  Must be installed globally: `pnpm i clean-css-cli -g`

### Quickstart: run locally

```sh
# install dependencies
pnpm install

# compile SCSS to CSS and minify, placing
# output in the `dist/` directory
pnpm build
```

### Development workflow

TODO: add htmx to package.json
TODO: document bumping dependency versions

Follows the example laid out in [twbs/examples/tree/main/sass-js](https://github.com/twbs/examples/tree/main/sass-js).

This repo follows trunk-based development. This means:

- the `main` branch should always be in a releasable state
- use short-lived feature branches

Pre-commit hooks are available to prevent common gotchas and to lint & format code.

```sh
# install pre-commit hooks
pre-commit install
```

Please follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
guidelines when writing commit messages.
`commitlint` is enabled as a pre-commit hook. Valid commit types are defined in `.commitlintrc.yaml`.

## Deploy

The contents of `dist/` are currently hosted in a public Cloudflare R2 bucket with CORS
enabled to allow GET from `localhost:8000`.

### Cloudflare R2 CORS policy

NB. both `0.0.0.0` and `localhost` must be specified due to a quirk in how font-fetching works.

```json
[
  {
    "AllowedOrigins": [
      "http://0.0.0.0:8000",
      "http://localhost:8000"
    ],
    "AllowedMethods": [
      "GET"
    ]
  }
]
```

### Cut a release

TODO: automate this!

```sh
# 1. Build the latest version:
pnpm build

# 2. Update CHANGELOG and commit.

# 3. Tag and release in GitHub.

# 4. Manually transfer the contents of `dist/`to the Cloudflare
#    R2 bucket. This should be under `/static/speculum@M.m.p/`
#    where `M.m.p` is a semver tag.
```

## What's in a name?

[Speculum feathers](https://en.wikipedia.org/wiki/Speculum_feathers) give some ducks their
characteristic iridiscence.

---

&copy; 2024 Alberto MH  
This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
