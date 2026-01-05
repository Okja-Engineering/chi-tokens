# @okja/chi-tokens

Design tokens for the Chi design system - colors, typography, spacing, radius, shadow, and motion.

## Installation

```bash
npm install @okja/chi-tokens
```

## Usage

### Import all tokens

```javascript
import tokens from '@okja/chi-tokens';

console.log(tokens.spacing[4]); // "16px"
console.log(tokens.radius.md);  // "12px"
```

### Import specific color palettes

```javascript
import grayscale from '@okja/chi-tokens/colors/grayscale';
import blue from '@okja/chi-tokens/colors/blue';
import purple from '@okja/chi-tokens/colors/purple';

console.log(grayscale.light.primary);     // "oklch(49.4% 0.163 264.05)"
console.log(grayscale.dark.surface);      // "oklch(15% 0.005 264.05)"
```

## Available Tokens

### Typography

| Token | Values |
|-------|--------|
| `font-family` | `sans`, `serif`, `mono` |
| `font-size` | `1`-`9` (12px-60px) |
| `font-weight` | `light`, `regular`, `medium`, `bold` |
| `line-height` | `1`-`9` (16px-60px) |
| `letter-spacing` | `1`-`3` |

### Spacing

| Token | Value |
|-------|-------|
| `1` | 4px |
| `2` | 8px |
| `3` | 12px |
| `4` | 16px |
| `5` | 24px |
| `6` | 32px |
| `7` | 40px |
| `8` | 48px |
| `9` | 64px |

### Radius

| Token | Value |
|-------|-------|
| `none` | 0 |
| `xs` | 4px |
| `sm` | 8px |
| `md` | 12px |
| `lg` | 16px |
| `xl` | 28px |
| `full` | 9999px |

### Shadow

Shadows are provided for both `light` and `dark` modes with levels `1`-`5`.

```javascript
tokens.shadow.light[3]  // Light mode, level 3
tokens.shadow.dark[3]   // Dark mode, level 3
```

### Motion

| Token | Values |
|-------|--------|
| `duration` | `instant`, `short1`-`short4`, `medium1`-`medium4`, `long1`-`long4`, `extra-long1`-`extra-long4` |
| `easing` | `linear`, `ease`, `ease-in`, `ease-out`, `ease-in-out`, `standard`, `emphasized`, etc. |

### Other

| Token | Description |
|-------|-------------|
| `container` | Max-width breakpoints (`1`-`4`) |
| `icon-size` | Icon sizes (`sm`, `md`, `lg`, `xl`) |
| `scaling` | Scale factors (`90`-`110`) |
| `radius-factor` | Radius multipliers (`none`, `small`, `medium`, `large`) |

## Color Palettes

Each color palette (`grayscale`, `blue`, `purple`) includes light and dark mode variants:

**Primary colors**: `primary`, `on-primary`, `primary-container`, `on-primary-container`

**Secondary colors**: `secondary`, `on-secondary`, `secondary-container`, `on-secondary-container`

**Tertiary colors**: `tertiary`, `on-tertiary`, `tertiary-container`, `on-tertiary-container`

**Error colors**: `error`, `on-error`, `error-container`, `on-error-container`

**Surface colors**: `surface`, `on-surface`, `surface-variant`, `on-surface-variant`, `surface-container`, `surface-container-low`, `surface-container-high`, `surface-container-highest`

**Utility colors**: `outline`, `outline-variant`, `inverse-surface`, `inverse-on-surface`, `inverse-primary`, `scrim`, `shadow`

Colors use the OKLCH color space for perceptual uniformity.

## License

MIT
