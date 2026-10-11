# Go Template

A deterministic, CI-ready Go repository template using [mise](https://mise.jdx.dev/) for toolchain management and [hk](https://hk.jdx.dev/) for quality checks and Git hooks.

## Start a repository from this template

1. Create a repository from `kejne/go-template` on GitHub.
2. Change the `module` path in `go.mod` to the new repository path.
3. Rename or replace `cmd/app`.
4. Review and adapt `AGENTS.md` for the project.
5. Install tools and hooks:

   ```sh
   mise install
   hk install
   ```

6. Run the canonical local check:

   ```sh
   hk check
   ```

The GitHub Actions workflow runs `hk check --all`. The pre-push hook additionally runs `gosec` and `govulncheck`. Commits are required to use conventional commit messages.

## Included files

- `mise.toml` pins the Go toolchain and quality/security tools.
- `hk.pkl` defines formatting, vetting, linting, tests, module-tidy, workflow, and security checks.
- `AGENTS.md` gives coding agents the repository rules, Go layout, TDD guidance, and strict approval-test policy.
- `BOOTSTRAP_PROMPT.md` is a reusable prompt for bootstrapping the same baseline in another repository.
- `.github/workflows/ci.yml` runs the checks in CI with pinned actions.
- `.github/dependabot.yml` keeps GitHub Actions dependencies current.

## License

MIT
