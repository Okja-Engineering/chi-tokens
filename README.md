# @okja/chi-tokens

Low-level CSS design tokens for building themes. **If you're building an application, use `@okja/chi-themes` instead.**

This package provides the foundational design tokens consumed by `@okja/chi-themes`. It's useful if you're creating custom themes or need granular control over the design system.

## Installation

```bash
npm install @okja/chi-tokens
```

## Usage

```css
@import '@okja/chi-tokens/tokens.css';
@import '@okja/chi-tokens/colors/grayscale.css';
```

Tokens are on `:root` and wrapped in `@layer tokens`.

## Token Reference

### Spacing

| Token | Value |
|-------|-------|
| `--space-1` | 4px |
| `--space-2` | 8px |
| `--space-3` | 12px |
| `--space-4` | 16px |
| `--space-5` | 24px |
| `--space-6` | 32px |
| `--space-7` | 40px |
| `--space-8` | 48px |
| `--space-9` | 64px |

### Typography

| Token | Value |
|-------|-------|
| `--font-sans` | system-ui, -apple-system, 'Segoe UI', sans-serif |
| `--font-serif` | georgia, 'Times New Roman', serif |
| `--font-mono` | 'SF Mono', monaco, 'Courier New', monospace |
| `--font-size-1` to `--font-size-9` | 12px to 60px |
| `--font-weight-light/regular/medium/bold` | 300/400/500/700 |
| `--line-height-1` to `--line-height-9` | 16px to 60px |

### Radius

| Token | Value |
|-------|-------|
| `--radius-none` | 0 |
| `--radius-xs` | 4px |
| `--radius-sm` | 8px |
| `--radius-md` | 12px |
| `--radius-lg` | 16px |
| `--radius-xl` | 28px |
| `--radius-full` | 9999px |

### Shadow

| Token | Description |
|-------|-------------|
| `--shadow-0` | none |
| `--shadow-1` | Subtle |
| `--shadow-2` | Low |
| `--shadow-3` | Medium |
| `--shadow-4` | High |
| `--shadow-5` | Highest |

### Motion

| Token | Value |
|-------|-------|
| `--duration-instant` | 0ms |
| `--duration-short1` to `short4` | 50-200ms |
| `--duration-medium1` to `medium4` | 250-400ms |
| `--duration-long1` to `long4` | 450-600ms |
| `--easing-standard` | Standard easing |
| `--easing-emphasized` | Emphasized easing |

### Colors

| Token | Description |
|-------|-------------|
| `--color-primary` | Primary brand |
| `--color-on-primary` | Text on primary |
| `--color-surface` | Surface background |
| `--color-on-surface` | Text on surface |
| `--color-error` | Error states |
| `--color-outline` | Borders |

## Color Palettes

- `colors/grayscale.css` - Neutral (default)
- `colors/blue.css` - Corporate blue
- `colors/purple.css` - Creative purple

Colors use `light-dark()` for automatic dark mode:

```css
--color-surface: light-dark(oklch(99% 0.005 264deg), oklch(15% 0.005 264deg));
```

## Architecture

- **CSS Cascade Layers** - `@layer tokens` for clean cascade control
- **`light-dark()` function** - Automatic dark mode colors
- **OKLCH color space** - Perceptual uniformity
- **Scaling support** - `var(--scaling, 1)` multiplier

## License

MIT
