# TypeScript Library Starter

Opinionated template for TypeScript libraries. ESM-only, strict types, fast tooling.

## Stack

- **Language:** [TypeScript 7](https://www.typescriptlang.org/), base config from [`@2bad/tsconfig`](https://www.npmjs.com/package/@2bad/tsconfig)
- **Build:** [tsdown](https://tsdown.dev/) (Rolldown + oxc)
- **Test:** [Vitest](https://vitest.dev/) with v8 coverage (80% thresholds enforced)
- **Lint:** [oxlint](https://oxc.rs/docs/guide/usage/linter) with the [`@2bad/axiom`](https://www.npmjs.com/package/@2bad/axiom) ruleset
- **Format:** [oxfmt](https://oxc.rs/docs/guide/usage/formatter)
- **Post-build:** [publint](https://publint.dev/) + [arethetypeswrong](https://arethetypeswrong.github.io/), run as part of `pnpm build`
- **CI:** GitHub Actions (Linux + Windows, Node 26), CodeQL, Renovate
- **Publish:** npm [trusted publishing](https://docs.npmjs.com/trusted-publishers) with provenance on GitHub release

## Getting Started

1. Click **Use this template** on GitHub
2. Clone your new repository
3. Search and replace:
   - `ts-lib-starter` with your package name
   - `2BAD` with your name/organization (keep `@2bad/tsconfig` and `@2bad/axiom` as-is)
4. Update `author` and `contributors` in `package.json`
5. `pnpm install`

## Scripts

```bash
pnpm build            # compile to ESM + generate .d.ts, then validate with publint + attw
pnpm test             # run all tests
pnpm test:unit        # unit tests with coverage
pnpm test:integration # integration tests with coverage
pnpm check            # lint + format check + type check
pnpm fix              # auto-fix lint + formatting
```

## Project Structure

```
source/   # source code, tests co-located
build/    # compiled output (generated)
```

- `test:unit` and `test:integration` filter by filename, so name test files `*.unit.test.ts` or
  `*.integration.test.ts`.
- `~/` is an alias for `source/`. Imports use `.ts` extensions.
- The build keeps the source file tree, so every public entry point needs a matching block in `package.json` `exports`
  (see `./quotes/parts`).

## Publishing

Configure the package as a [trusted publisher](https://docs.npmjs.com/trusted-publishers) on npm for the `publish.yml`
workflow, then create a GitHub release. Prerelease versions such as `1.1.0-beta.0` are published under the matching
dist-tag (`beta`), everything else under `latest`.

## Requirements

- Node.js >= 26
- pnpm >= 12

## License

MIT
