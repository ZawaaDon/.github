# .github

Shared workflows and community health files for ZawaaDon repositories.

## Reusable Workflows

### `copal-ci.yml`

CI pipeline for [Copal](https://github.com/ZawaaDon/copal-template) algorithm components.

**Matrix**: GCC + Clang + MSVC × Linux/macOS/Windows (4 jobs)
**Checks**: Build with -Werror, run all tests, verify zero external dependencies

**Usage** in component repo's `.github/workflows/ci.yml`:

```yaml
name: CI
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  ci:
    uses: ZawaaDon/.github/.github/workflows/copal-ci.yml@main
    with:
      werror_option: COPAL_ODE_WERROR  # Replace with your component's option
```
