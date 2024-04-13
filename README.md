# speculum

Custom Bootstrap CSS for DepositDuck.

## Develop

[![bootstrap](https://img.shields.io/badge/Bootstrap_5-7952B3?logo=bootstrap&logoColor=white)](https://github.com/twbs/bootstrap)
[![sass](https://img.shields.io/badge/Dart_Sass-cf649b?logo=sass&logoColor=white)](https://sass-lang.com/dart-sass/)
[![pnpm](https://img.shields.io/badge/pnpm-4e4e4e?logo=pnpm&logoColor=f69220)](https://sass-lang.com/dart-sass/)

### Prerequisites

To develop speculum the following must be available locally:

- [pnpm](https://pnpm.io/installation)

### Development workflow

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

---

&copy; 2024 Alberto MH  
This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)
