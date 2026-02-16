# Easing Curves Reference Guide

## 📐 Figma to CSS Easing Conversion

This guide helps you convert Figma's easing curves to CSS cubic-bezier values.

---

## Standard Easing Curves

### Linear
- **Figma Name:** Linear
- **CSS Value:** `linear`
- **Cubic-Bezier:** `cubic-bezier(0, 0, 1, 1)`
- **CSS Variable:** `var(--easing-linear)`
- **Description:** Constant speed from start to finish
- **Best For:** Loading spinners, continuous rotations, progress bars
- **Visual:** Straight diagonal line

```css
animation: my-animation 300ms linear;
```

---

### Ease
- **Figma Name:** Ease (default)
- **CSS Value:** `ease`
- **Cubic-Bezier:** `cubic-bezier(0.25, 0.1, 0.25, 1)`
- **CSS Variable:** `var(--easing-ease)`
- **Description:** Gentle acceleration and deceleration
- **Best For:** General purpose animations
- **Visual:** Gentle S-curve

```css
animation: my-animation 300ms ease;
```

---

### Ease In
- **Figma Name:** Ease In
- **CSS Value:** `ease-in`
- **Cubic-Bezier:** `cubic-bezier(0.42, 0, 1, 1)`
- **CSS Variable:** `var(--easing-ease-in)`
- **Description:** Starts slow, accelerates toward the end
- **Best For:** Elements exiting the screen, fade outs
- **Visual:** Curve starts flat, becomes steep

```css
animation: my-animation 300ms ease-in;
```

---

### Ease Out ⭐ Most Common
- **Figma Name:** Ease Out
- **CSS Value:** `ease-out`
- **Cubic-Bezier:** `cubic-bezier(0, 0, 0.58, 1)`
- **CSS Variable:** `var(--easing-ease-out)`
- **Description:** Starts fast, decelerates toward the end
- **Best For:** Elements entering the screen, most UI animations
- **Visual:** Curve starts steep, becomes flat
- **Why Popular:** Feels responsive and natural

```css
animation: my-animation 300ms ease-out;
```

---

### Ease In-Out
- **Figma Name:** Ease In-Out
- **CSS Value:** `ease-in-out`
- **Cubic-Bezier:** `cubic-bezier(0.42, 0, 0.58, 1)`
- **CSS Variable:** `var(--easing-ease-in-out)`
- **Description:** Starts slow, speeds up, then slows down again
- **Best For:** Smooth transitions between states, toggles
- **Visual:** Symmetrical S-curve

```css
animation: my-animation 300ms ease-in-out;
```

---

## Advanced Easing Curves

### Ease In Quad
- **Cubic-Bezier:** `cubic-bezier(0.55, 0.085, 0.68, 0.53)`
- **CSS Variable:** `var(--easing-ease-in-quad)`
- **Description:** Quadratic acceleration (gentle)
- **Best For:** Subtle entry animations

---

### Ease Out Quad
- **Cubic-Bezier:** `cubic-bezier(0.25, 0.46, 0.45, 0.94)`
- **CSS Variable:** `var(--easing-ease-out-quad)`
- **Description:** Quadratic deceleration (gentle)
- **Best For:** Smooth, natural entrances

---

### Ease In-Out Quad
- **Cubic-Bezier:** `cubic-bezier(0.455, 0.03, 0.515, 0.955)`
- **CSS Variable:** `var(--easing-ease-in-out-quad)`
- **Description:** Balanced quadratic curve
- **Best For:** Symmetric transitions

---

### Ease In Cubic
- **Cubic-Bezier:** `cubic-bezier(0.55, 0.055, 0.675, 0.19)`
- **CSS Variable:** `var(--easing-ease-in-cubic)`
- **Description:** Strong acceleration
- **Best For:** Dramatic exits

---

### Ease Out Cubic
- **Cubic-Bezier:** `cubic-bezier(0.215, 0.61, 0.355, 1)`
- **CSS Variable:** `var(--easing-ease-out-cubic)`
- **Description:** Strong deceleration
- **Best For:** Dynamic, snappy entrances

---

### Ease In-Out Cubic
- **Cubic-Bezier:** `cubic-bezier(0.645, 0.045, 0.355, 1)`
- **CSS Variable:** `var(--easing-ease-in-out-cubic)`
- **Description:** Strong S-curve
- **Best For:** Pronounced state changes

---

## Special Effects

### Spring (Material Design)
- **Figma:** Custom curve with overshoot
- **Cubic-Bezier:** `cubic-bezier(0.16, 1, 0.3, 1)`
- **CSS Variable:** `var(--easing-spring)`
- **Description:** Overshoots slightly, then settles
- **Best For:** Modern, playful UI elements
- **Visual:** Curve goes slightly above 1.0

```css
animation: my-animation 400ms var(--easing-spring);
```

---

### Bounce
- **Figma:** Custom curve with bounce effect
- **Cubic-Bezier:** `cubic-bezier(0.68, -0.55, 0.265, 1.55)`
- **CSS Variable:** `var(--easing-bounce)`
- **Description:** Overshoots on both ends, bouncy feel
- **Best For:** Attention-grabbing elements, playful designs
- **Visual:** Curve dips below 0 and above 1

```css
animation: my-animation 600ms var(--easing-bounce);
```

---

### Ease In Back
- **Cubic-Bezier:** `cubic-bezier(0.6, -0.28, 0.735, 0.045)`
- **CSS Variable:** `var(--easing-ease-in-back)`
- **Description:** Pulls back before accelerating forward
- **Best For:** Dramatic, anticipatory effects

---

### Ease Out Back
- **Cubic-Bezier:** `cubic-bezier(0.175, 0.885, 0.32, 1.275)`
- **CSS Variable:** `var(--easing-ease-out-back)`
- **Description:** Overshoots target, then settles back
- **Best For:** Engaging, lively entrances

---

### Ease In-Out Back
- **Cubic-Bezier:** `cubic-bezier(0.68, -0.55, 0.265, 1.55)`
- **CSS Variable:** `var(--easing-ease-in-out-back)`
- **Description:** Pulls back at start, overshoots at end
- **Best For:** Exaggerated, dynamic transitions

---

## 🎯 Quick Decision Guide

### What should I use for...?

| Use Case | Recommended Easing | Duration |
|----------|-------------------|----------|
| Button hover | `ease-out` | 200ms |
| Modal appearing | `spring` | 400ms |
| Notification toast | `ease-out` | 300ms |
| Menu sliding in | `ease-out-cubic` | 300ms |
| Card loading | `ease-out` | 400ms |
| Error shake | `ease-in-out` | 500ms |
| Loading spinner | `linear` | 1000ms |
| Tooltip appear | `ease-out` | 200ms |
| Dropdown open | `ease-out` | 250ms |
| Page transition | `ease-in-out` | 600ms |

---

## 🔄 Converting Custom Figma Curves

If Figma shows a custom bezier curve:

### Step 1: Identify the Control Points
Figma's bezier editor shows 4 points:
- Start: (0, 0) - always fixed
- Control Point 1: (x1, y1)
- Control Point 2: (x2, y2)
- End: (1, 1) - always fixed

### Step 2: Extract Values
Look at the coordinates shown in Figma for the two middle control points.

Example:
- If Figma shows: `P1: (0.42, 0)` and `P2: (0.58, 1)`
- CSS becomes: `cubic-bezier(0.42, 0, 0.58, 1)`

### Step 3: Use the CSS
```css
animation: my-animation 300ms cubic-bezier(0.42, 0, 0.58, 1);
```

---

## 📊 Easing Curve Visualizations

### Understanding the Graph

```
1.0 |           ___---
    |       ___/
    |    __/
    |  _/
0.0 |_/________________
    0                  1
    Start          End
```

- **X-axis:** Time (0 = start, 1 = end)
- **Y-axis:** Progress (0 = beginning state, 1 = final state)
- **Slope:** Speed of animation
  - Steep = Fast
  - Flat = Slow

---

## 🔧 How to Test Easings

### Method 1: Use the Demo File
1. Open `demo.html` in a browser
2. Scroll to "Easing Curves" section
3. Click "Play" to see all easings in action

### Method 2: Browser DevTools
1. Inspect any element
2. Add CSS animation
3. Use Chrome/Firefox animation timeline
4. Adjust cubic-bezier values in real-time

### Method 3: Online Tools
- [cubic-bezier.com](https://cubic-bezier.com)
- [easings.net](https://easings.net)
- Chrome DevTools Bezier Editor

---

## 💡 Pro Tips

### Tip 1: Default to Ease-Out
When in doubt, use `ease-out`. It's the most natural feeling for UI elements entering the screen.

### Tip 2: Match Easing to Motion
- **Entering:** Use `ease-out` or `spring`
- **Exiting:** Use `ease-in`
- **Continuous:** Use `linear`

### Tip 3: Duration Affects Feel
- Fast (200-300ms): Responsive, snappy
- Medium (400-500ms): Smooth, noticeable
- Slow (600ms+): Dramatic, prominent

### Tip 4: Don't Overuse Bounce/Spring
These are attention-grabbing. Use sparingly for key interactions only.

### Tip 5: Test on Real Devices
Easing can feel different on different screen sizes and performance levels.

---

## 📝 Designer's Cheat Sheet

Copy this to your Figma workspace:

```
Common Figma → CSS Translations:

Linear          → linear
Ease Out        → ease-out (USE THIS MOST!)
Ease In         → ease-in
Ease In-Out     → ease-in-out
Custom Spring   → cubic-bezier(0.16, 1, 0.3, 1)
Custom Bounce   → cubic-bezier(0.68, -0.55, 0.265, 1.55)

Recommended Durations:
Micro: 100-200ms
Fast: 200-300ms
Normal: 300-400ms
Slow: 500-600ms
```

---

## 🤝 Working with Developers

When documenting your Figma animations:

✅ **Do This:**
- "Use ease-out easing"
- "Use spring easing (overshoot curve)"
- "Custom bezier: (0.42, 0, 0.58, 1)"

❌ **Avoid:**
- "Make it smooth"
- "It should flow nicely"
- "Similar to the other one"

---

## Additional Resources

- [MDN: animation-timing-function](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)
- [Material Design Motion](https://material.io/design/motion/speed.html)
- [Apple Human Interface Guidelines - Motion](https://developer.apple.com/design/human-interface-guidelines/motion)
