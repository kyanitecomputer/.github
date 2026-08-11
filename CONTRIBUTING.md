# Contributing to Kyanite

Thanks for your interest in contributing. These guidelines apply to every
repository in the [Kyanite](https://github.com/kyanitecomputer) organization.

Everything here is **experimental** — interfaces move fast. If you plan a large
change, open an issue first so we can agree on direction before you invest time.

## Ground rules

- Be respectful. This project follows the [Code of Conduct](CODE_OF_CONDUCT.md).
- Keep changes focused. One logical change per pull request.
- Match the style and structure of the code around you.

## Building and testing

CI runs the **same [Dagger](https://dagger.io) pipeline you run locally**, so if
it passes on your machine it passes in CI. Install Dagger, then from a repo:

```sh
dagger call check      # lint + test + build (see the repo's dagger.json for functions)
```

Language-specific tooling (also invoked by the Dagger pipeline):

- **Go:** `gofmt`, `go vet`, `golangci-lint`, `go test ./...`
- **Rust:** `cargo fmt --check`, `cargo clippy -- -D warnings`, `cargo test`
- **C:** `cppcheck` and the host unit tests (`make check`)
- **Web:** `biome check`, build, and Playwright end-to-end tests

## Commits

- Use [Conventional Commits](https://www.conventionalcommits.org/):
  `type(scope): summary` — e.g. `feat(spi): add 4-byte FMC driver`.
  Common types: `feat`, `fix`, `docs`, `refactor`, `perf`, `test`, `build`,
  `ci`, `chore`.
- Keep each commit self-contained and building.

## Developer Certificate of Origin (DCO)

We use the [DCO](https://developercertificate.org/) instead of a CLA. Every
commit must be signed off, certifying you have the right to submit it under the
project license:

```sh
git commit -s -m "feat(scope): summary"
```

This appends a `Signed-off-by: Your Name <you@example.com>` trailer. Use a real
name and a reachable email.

## License and file headers

Contributions are dual-licensed under **Apache-2.0 OR MIT** — the same terms as
the project (inbound = outbound). By submitting a contribution you agree to
license it under both.

New source files should carry an SPDX header, for example:

```
// SPDX-License-Identifier: Apache-2.0 OR MIT
// Copyright (c) The Kyanite Authors
```

## Pull requests

1. Fork and branch from the default branch.
2. Make your change; add or update tests.
3. Ensure `dagger call check` passes locally.
4. Sign off your commits (DCO) and use Conventional Commit messages.
5. Open the PR, describe the change, and link any related issues.

A maintainer will review. Thanks for contributing!
