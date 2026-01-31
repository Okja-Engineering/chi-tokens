# Contributing

Thanks for your interest in contributing to @ankh-studio/tokens.

## Setup

```bash
git clone https://github.com/ankh-studio/tokens.git
cd tokens
nvm use
npm install
```

## Development

```bash
npm run lint    # Check CSS style
npm run build   # Compile tokens to dist/
```

## Making Changes

1. Create a branch from `main`
2. Make your changes in `src/`
3. Run `npm run lint` and `npm run build`
4. Submit a pull request

## Code Style

- CSS custom properties only (no preprocessors)
- Follow existing naming conventions (`--category-variant`)
- Run `npm run lint` before committing

## Design Decisions

Significant changes should be discussed first. For new token categories or architectural changes, consider proposing an [ADR](./docs/adr/).

## Questions

Open an issue for discussion before starting large changes.
