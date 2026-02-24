# TypeScript Library Starter

Opinionated template for TypeScript libraries. ESM-only, strict types, fast tooling.

## Stack

- **Build:** [tsdown](https://tsdown.dev/) (Rolldown + oxc)
- **Test:** [Vitest](https://vitest.dev/) with v8 coverage
- **Lint:** [oxlint](https://oxc.rs/docs/guide/usage/linter)
- **Format:** [oxfmt](https://oxc.rs/docs/guide/usage/formatter)
- **Post-build:** [publint](https://publint.dev/) + [arethetypeswrong](https://arethetypeswrong.github.io/)
- **CI:** GitHub Actions (Linux + Windows, Node 22 + 24)

## Getting Started

1. Click **Use this template** on GitHub
2. Clone your new repository
3. Search and replace:
   - `ts-lib-starter` with your package name
   - `2BAD` with your name/organization (keep `@2bad/tsconfig` as-is)
4. `pnpm install`

## Scripts

```bash
pnpm build            # compile to ESM + generate .d.ts
pnpm test             # run all tests
pnpm test:unit        # unit tests with coverage
pnpm test:integration # integration tests with coverage
pnpm check            # lint + format check
pnpm fix              # auto-fix lint + formatting
```

## Project Structure

```
source/   # source code, tests co-located
build/    # compiled output (generated)
```

## Requirements

- Node.js >= 24
- pnpm >= 10

## License

MIT
