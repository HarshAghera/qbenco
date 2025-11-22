# Continuous Integration (CI)

This repository includes a GitHub Actions workflow that runs automated checks
for pushed code and pull requests targeting `master`.

Workflow file: `.github/workflows/ci.yml`

What the workflow does

- Installs dependencies using `pnpm` (honors `pnpm-lock.yaml`).
- Runs `pnpm lint` (ESLint).
- Runs TypeScript type checking with `tsc --noEmit`.
- Runs `pnpm build` (runs the `build` script / `next build`).

When it runs

- On `push` to non-`master` branches (so feature branch pushes are checked).
- On `pull_request` events targeting `master` (so PRs are validated before
  merge).

Protecting `master` (Require CI to pass before merge)
