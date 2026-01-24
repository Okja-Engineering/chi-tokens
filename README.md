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
| `--font-size-1` to `--font-size-11` | 11px to 57px |
| `--font-weight-light/regular/medium/bold` | 300/400/500/700 |
| `--line-height-1` to `--line-height-11` | 16px to 64px |

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

### Motion (M3 Expressive)

#### Spring Tokens (for JS animation libraries)

| Token | Damping | Stiffness | Use Case |
|-------|---------|-----------|----------|
| `--spring-fast-spatial-*` | 0.9 | 1400 | Small components (buttons, switches) |
| `--spring-default-spatial-*` | 0.9 | 700 | Partial screen (sheets, drawers) |
| `--spring-slow-spatial-*` | 0.9 | 300 | Full screen transitions |
| `--spring-fast-effects-*` | 1.0 | 3800 | Small component color/opacity |
| `--spring-default-effects-*` | 1.0 | 1600 | Partial screen effects |
| `--spring-slow-effects-*` | 1.0 | 800 | Full screen effects |

**Spatial** springs allow overshoot (position, scale). **Effects** springs don't (color, opacity).

#### Duration Tokens (for CSS)

| Token | Value |
|-------|-------|
| `--duration-instant` | 0ms |
| `--duration-short1` to `short4` | 50-200ms |
| `--duration-medium1` to `medium4` | 250-400ms |
| `--duration-long1` to `long4` | 450-600ms |
| `--duration-extra-long1` to `extra-long4` | 700-1000ms |

#### Easing Tokens (for CSS)

| Token | Value | Use Case |
|-------|-------|----------|
| `--easing-standard` | cubic-bezier(0.2, 0, 0, 1) | Utility animations |
| `--easing-standard-accelerate` | cubic-bezier(0.3, 0, 1, 1) | Exiting screen |
| `--easing-standard-decelerate` | cubic-bezier(0, 0, 0, 1) | Entering screen |
| `--easing-emphasized` | cubic-bezier(0.2, 0, 0, 1) | Expressive M3 animations |
| `--easing-emphasized-accelerate` | cubic-bezier(0.3, 0, 0.8, 0.15) | Expressive exit |
| `--easing-emphasized-decelerate` | cubic-bezier(0.05, 0.7, 0.1, 1) | Expressive enter |

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

## Browser Support

Requires browsers supporting:
- CSS `light-dark()` function
- OKLCH color space
- CSS Cascade Layers (`@layer`)

**Supported:** Chrome 123+, Safari 17.5+, Firefox 120+

## License

MIT
