# Figma Material Design Alignment

## Overview

The animation system has been updated to align with **Figma Material Design** naming conventions for durations and easing curves. This ensures seamless collaboration between designers working in Figma and developers implementing animations.

---

## 📏 Duration Conventions

### New Naming (Figma Material Design)

Based on your Figma screenshots:

| Token | Value | Use Case |
|-------|-------|----------|
| `xs` | 50ms | Micro-interactions, instant feedback |
| `s` | 150ms | Quick transitions, hover states |
| `m` | 200ms | Standard UI animations, fades |
| `l` | 400ms | Emphasized movements, slides |
| `xl` | 600ms | Complex animations, rotations |
| `xxl` | 1000ms | Continuous animations, loaders |

### CSS Variable Usage

```css
/* Use the new duration variables */
.my-element {
  animation: my-animation var(--duration-m) var(--easing-regular-decelerate);
}
```

### Utility Classes

```html
<!-- Use new duration classes -->
<div class="fade-in duration-l">Content</div>
<div class="slide-up duration-m">Content</div>
```

---

## 🎨 Easing Curve Conventions

### Material Design Easing Curves

Based on your Figma "Bezier Curves Material" screenshot:

| Token | Cubic-Bezier Value | Description | Use Case |
|-------|-------------------|-------------|----------|
| `linear` | `cubic-bezier(0, 0, 0, 0)` | Constant speed | Progress bars, spinners |
| `standard` | `cubic-bezier(0.35, 0, 0.63, 1)` | Balanced curve | General transitions |
| `emphasized-accelerate` | `cubic-bezier(0.3, 0.0, 0.8, 0.15)` | Starts fast, exits quickly | Exiting elements |
| `emphasized-decelerate` | `cubic-bezier(0.05, 0.7, 0.1, 1.0)` | Starts slow, ends gently | **Entering elements ⭐ Most common** |
| `regular-accelerate` | `cubic-bezier(0.3, 0, 1, 1)` | Gentle speed up | Simple exits |
| `regular-decelerate` | `cubic-bezier(0, 0, 0, 1)` | Gentle slow down | Simple entrances |

### Legacy Curves (Original Figma Bezier Curves)

For compatibility, we've kept the original Figma bezier curves as "legacy" variants:

| Token | Cubic-Bezier Value | Description |
|-------|-------------------|-------------|
| `legacy-emphasized-accelerate` | `cubic-bezier(0.7, 0, 0.8, 0)` | Original emphasized accel |
| `legacy-emphasized-decelerate` | `cubic-bezier(0.08, 0.7, 0.12, 1.17)` | Original emphasized decel (bouncy) |
| `legacy-regular-accelerate` | `cubic-bezier(0.6, 0, 1, 1)` | Original regular accel |
| `legacy-regular-decelerate` | `cubic-bezier(0, 0, 0.3, 1.1)` | Original regular decel |

---

## 🔄 Migration Guide

### Old to New Mapping

#### Duration Variables

```css
/* OLD → NEW */
--duration-instant   → --duration-xs    (100ms → 50ms)
--duration-fast      → --duration-m     (200ms → 200ms) ✅ Same
--duration-normal    → --duration-m     (300ms → 200ms)
--duration-moderate  → --duration-l     (400ms → 400ms) ✅ Same
--duration-slow      → --duration-xl    (600ms → 600ms) ✅ Same
--duration-slower    → --duration-xxl   (800ms → 1000ms)
```

#### Duration Utility Classes

```html
<!-- OLD → NEW -->
<div class="duration-instant">  → <div class="duration-xs">
<div class="duration-fast">     → <div class="duration-m">
<div class="duration-normal">   → <div class="duration-m">
<div class="duration-moderate"> → <div class="duration-l">
<div class="duration-slow">     → <div class="duration-xl">
<div class="duration-slower">   → <div class="duration-xxl">
```

#### Easing Variables

```css
/* OLD → NEW (Approximate mapping) */
--easing-ease-out        → --easing-regular-decelerate
--easing-ease-in         → --easing-regular-accelerate
--easing-ease-in-out     → --easing-standard
--easing-spring          → --easing-emphasized-decelerate
--easing-ease-out-cubic  → --easing-emphasized-decelerate
--easing-ease-in-cubic   → --easing-emphasized-accelerate
```

---

## 📋 Updated Animation Definitions

All pre-built animations now use the new Figma-aligned tokens:

```json
{
  "fade-in": {
    "duration": "m",           // 200ms
    "easing": "regular-decelerate"
  },
  "slide-up": {
    "duration": "l",           // 400ms
    "easing": "emphasized-decelerate"
  },
  "scale-up": {
    "duration": "m",           // 200ms
    "easing": "emphasized-decelerate"
  },
  "rotate-in": {
    "duration": "xl",          // 600ms
    "easing": "emphasized-decelerate"
  }
}
```

---

## 💡 Figma to CSS Workflow

### For Designers

When documenting animations in Figma:

1. **Duration**: Use the letter sizes (XS, S, M, L, XL)
   - Example: "Duration: M (200ms)"

2. **Easing**: Reference the Material Design curve names
   - Example: "Easing: Emphasized Decelerate"
   - Example: "Easing: Regular Accelerate"

3. **Documentation Template**:
```
Animation: Button Hover
Element: Primary Button
Duration: S (150ms)
Easing: Regular Decelerate
Properties: Scale from 1 to 1.05
```

### For Developers

Translate Figma specs directly to CSS:

```css
.button-hover {
  transition: transform var(--duration-s) var(--easing-regular-decelerate);
}

.button-hover:hover {
  transform: scale(1.05);
}
```

Or use pre-built animations:

```html
<div class="fade-in duration-m">Content</div>
```

---

## 🎯 Common Patterns

### Entering Elements (Recommended)

```css
/* Material Design recommendation for entering elements */
animation: fade-in var(--duration-m) var(--easing-emphasized-decelerate);
```

**Why Emphasized Decelerate?**
- Feels natural and responsive
- Draws attention at the start
- Settles gently into place

### Exiting Elements

```css
/* Material Design recommendation for exiting elements */
animation: fade-out var(--duration-s) var(--easing-emphasized-accelerate);
```

**Why Emphasized Accelerate?**
- Exits quickly to make room for new content
- Doesn't linger unnecessarily
- Feels snappy and responsive

### Micro-Interactions

```css
/* For hover states, clicks, toggles */
transition: transform var(--duration-s) var(--easing-regular-decelerate);
```

### State Changes

```css
/* For tabs, toggles, menu selections */
transition: all var(--duration-m) var(--easing-standard);
```

---

## 🔍 Visual Comparison

### Emphasized Decelerate (Most Common)
```
Speed
 ^
 |    *****
 |   *     ***
 |  *         **
 | *            **
 |*                *
 +-------------------> Time
Start            End
```
**Use for**: Entering elements, slides, scale-ups

### Regular Decelerate
```
Speed
 ^
 |     ****
 |    *    **
 |   *       **
 |  *          **
 | *             *
 +-------------------> Time
Start            End
```
**Use for**: Fades, simple transitions

### Emphasized Accelerate
```
Speed
 ^
 |                *
 | **            *
 |   **         *
 |     ***     *
 |        *****
 +-------------------> Time
Start            End
```
**Use for**: Exiting elements, dismissals

---

## 📚 Reference Tables

### Duration Decision Matrix

| Animation Type | Recommended Duration | Why |
|----------------|---------------------|-----|
| Micro-interactions (hover, click) | `xs` or `s` | Instant feedback |
| Simple fades | `m` | Quick but noticeable |
| UI transitions (tab change) | `m` | Standard timing |
| Emphasized movements (slide, scale) | `l` | Needs attention |
| Complex animations (rotate, multi-step) | `xl` | Multiple properties |
| Continuous (loading, pulse) | `xxl` | Looping animations |

### Easing Decision Matrix

| Motion Direction | Recommended Easing | Why |
|-----------------|-------------------|-----|
| Element entering | `emphasized-decelerate` | Natural, draws attention |
| Element exiting | `emphasized-accelerate` | Quick exit |
| Simple fade in | `regular-decelerate` | Subtle entrance |
| Simple fade out | `regular-accelerate` | Subtle exit |
| State change | `standard` | Balanced |
| Continuous motion | `linear` | Constant speed |

---

## ✅ Validation Checklist

When implementing animations:

- [ ] Duration uses Figma convention (xs, s, m, l, xl, xxl)
- [ ] Easing matches Figma Material Design curves
- [ ] Entering elements use `emphasized-decelerate` or `regular-decelerate`
- [ ] Exiting elements use `emphasized-accelerate` or `regular-accelerate`
- [ ] Micro-interactions use `xs` or `s` duration
- [ ] Complex animations use `l` or `xl` duration
- [ ] CSS variables used instead of hardcoded values
- [ ] Animations respect `prefers-reduced-motion`

---

## 🔗 Cross-Reference

- **animation-tokens.json**: Source of truth for all tokens
- **animations.css**: CSS implementation with variables
- **FIGMA-TO-CSS-GUIDE.md**: Designer documentation
- **EASING-REFERENCE.md**: Detailed easing curve guide
- **demo.html**: Live examples of all animations

---

## 💬 Questions?

### "Should I use Material or Legacy curves?"

**Use Material Design curves** (`emphasized-decelerate`, `regular-decelerate`, etc.) - they're the current standard and match Figma's Material Design guidelines.

**Use Legacy curves** only if:
- You need the exact original Figma bezier curves
- You're maintaining existing animations
- You specifically need the bounce effect from `legacy-emphasized-decelerate`

### "Which easing should I use most often?"

For 80% of cases, use:
- **Entering elements**: `emphasized-decelerate` + duration `l`
- **Simple fades**: `regular-decelerate` + duration `m`
- **Exiting elements**: `emphasized-accelerate` + duration `s`
- **Hover states**: `regular-decelerate` + duration `s`

### "How do I convert my existing animations?"

1. Check the migration guide above
2. Replace old variable names with new ones
3. Test in the browser
4. Adjust duration/easing if needed

---

## 🎉 Benefits of Alignment

✅ **Consistent language** between design and development
✅ **Faster implementation** - direct mapping from Figma
✅ **Industry standard** - Material Design conventions
✅ **Better documentation** - clearer naming
✅ **Easier maintenance** - fewer custom values

---

**Last Updated**: With Figma Material Design conventions from provided screenshots
