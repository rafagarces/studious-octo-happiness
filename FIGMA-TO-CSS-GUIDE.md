# Figma to CSS Animation Guide

## 🎯 For Non-Technical Designers

This guide helps you translate animations from Figma into CSS that developers can implement. No coding knowledge required!

---

## 📋 Quick Reference: Animation Documentation Template

When you create an animation in Figma, fill out this simple form:

```
Animation Name: [e.g., "Button Hover Effect"]
Element: [e.g., "Primary Button"]
Trigger: [On Click / On Hover / On Load / On Scroll]

Changes:
- Property: [e.g., Opacity]
  From: [e.g., 100%]
  To: [e.g., 0%]

- Property: [e.g., Position Y]
  From: [e.g., 0px]
  To: [e.g., 20px]

Duration: [e.g., 300ms]
Easing: [Linear / Ease In / Ease Out / Ease In-Out / Custom]
Delay: [e.g., 0ms or 200ms]

Notes: [Any special behavior or context]
```

---

## 🎨 Step-by-Step: How to Document Your Figma Animation

### Step 1: Identify the Animation
- What is the animation called?
- Which element(s) does it affect?
- When should it happen? (hover, click, page load, etc.)

### Step 2: Find the Property Changes

In Figma Smart Animate, look at what changes between the two frames:

| Figma Property | CSS Property | How to Measure |
|----------------|--------------|----------------|
| **Position X** | `translateX` | Check X coordinate difference |
| **Position Y** | `translateY` | Check Y coordinate difference |
| **Width/Height** | `scale` | Calculate percentage change |
| **Rotation** | `rotate` | Note degrees (e.g., 45°) |
| **Opacity** | `opacity` | 0% = 0, 100% = 1 |
| **Border Radius** | `border-radius` | Note pixel or percentage value |

**Example:**
- Element moves from Y: 0px to Y: 20px → Write: "Position Y: 0px to 20px"
- Opacity changes from 100% to 0% → Write: "Opacity: 100% to 0%"

### Step 3: Check Duration

In Figma prototype settings:
- Look for "Duration" or "Time"
- Note the value in milliseconds (ms)
- Common values: 300ms (fast), 600ms (medium), 1000ms (slow)

### Step 4: Identify Easing Curve

Figma shows easing curves. Match yours to these:

| Figma Easing | What It Looks Like | Use Case |
|--------------|-------------------|----------|
| **Linear** | Straight diagonal line | Continuous motion, loaders |
| **Ease In** | Curve starts slow, ends fast | Exiting elements |
| **Ease Out** | Curve starts fast, ends slow | Entering elements ⭐ Most common |
| **Ease In-Out** | Curve slow-fast-slow | Smooth transitions |
| **Custom** | You drew your own curve | Note: "Custom curve" + screenshot |

### Step 5: Check for Delays

- Is there a delay before the animation starts?
- Note this value in milliseconds
- Example: "Delay: 200ms"

---

## 🎬 Pre-Built Animations You Can Use

Instead of documenting custom animations, you can reference these ready-made options:

### Basic Animations

| Animation Name | What It Does | Best For |
|----------------|--------------|----------|
| `fade-in` | Appears gradually | Any content loading |
| `fade-out` | Disappears gradually | Hiding elements |
| `slide-up` | Slides in from bottom | Cards, modals |
| `slide-down` | Slides in from top | Notifications |
| `slide-left` | Slides in from right | Side panels, menus |
| `slide-right` | Slides in from left | Navigation |

### Advanced Animations

| Animation Name | What It Does | Best For |
|----------------|--------------|----------|
| `scale-up` | Grows from smaller | Buttons, badges |
| `scale-down` | Shrinks from larger | Close animations |
| `zoom-in` | Dramatic zoom + fade | Hero images, popups |
| `bounce-in` | Bouncy entrance | Playful elements |
| `rotate-in` | Rotates while appearing | Creative elements |
| `shake` | Shakes left-right | Error states |
| `pulse` | Gentle breathing effect | Attention, notifications |
| `spin` | Continuous rotation | Loading spinners |

**How to use:** Just tell developers: "Use the `slide-up` animation for the card"

---

## 📝 Real-World Examples

### Example 1: Simple Button Hover

**Your Figma Setup:**
- Button opacity: 100% → 80%
- Duration: 200ms
- Easing: Ease Out
- Trigger: On Hover

**How to Document:**
```
Animation: Button Hover Fade
Element: Primary Button
Trigger: On Hover
Change: Opacity from 100% to 80%
Duration: 200ms
Easing: Ease Out
```

---

### Example 2: Modal Appearance

**Your Figma Setup:**
- Modal starts at Y: 20px, Opacity: 0%
- Ends at Y: 0px, Opacity: 100%
- Duration: 400ms
- Easing: Spring (bouncy curve)
- Trigger: On Click

**How to Document:**
```
Animation: Modal Entry
Element: Modal Dialog
Trigger: On Click (open button)
Changes:
- Position Y: 20px to 0px
- Opacity: 0% to 100%
Duration: 400ms
Easing: Spring / Custom (curved bounce)
```

**OR Simply Say:** "Use the `slide-up` animation"

---

### Example 3: Notification Toast

**Your Figma Setup:**
- Toast slides from Y: -50px to Y: 0px
- Fade in from 0% to 100% opacity
- Duration: 300ms
- Delay: 100ms (appears after brief pause)
- Easing: Ease Out

**How to Document:**
```
Animation: Notification Appear
Element: Toast Notification
Trigger: On Event (system notification)
Changes:
- Position Y: -50px to 0px
- Opacity: 0% to 100%
Duration: 300ms
Delay: 100ms
Easing: Ease Out
```

**OR Simply Say:** "Use the `slide-down` animation with a 100ms delay"

---

## 🎭 Figma Plugin Recommendations

These Figma plugins can help generate CSS automatically:

1. **Animator** - Exports keyframe animations
2. **Figmotion** - Advanced animation export
3. **CSS Gen** - Quick CSS style extraction

Ask your development team to help install these!

---

## ✅ Checklist Before Sharing with Developers

- [ ] Animation name/description is clear
- [ ] Trigger is specified (hover, click, load, etc.)
- [ ] All property changes are noted
- [ ] Duration is specified in milliseconds
- [ ] Easing curve is identified
- [ ] Any delays are noted
- [ ] Special behaviors are described

---

## 🤝 Working with Developers

### Good Communication

✅ **Good:** "The card should use the `slide-up` animation when it appears"

✅ **Good:** "Button opacity should fade from 100% to 80% over 200ms on hover using Ease Out"

❌ **Avoid:** "Make it animate smoothly"

❌ **Avoid:** "It should move nicely"

### Sharing Your Work

1. **Option 1:** Share Figma prototype link with documented animations
2. **Option 2:** Fill out the documentation template (above) in a shared doc
3. **Option 3:** Record a screen capture showing the animation
4. **Option 4:** Reference pre-built animations: "Use `fade-in` for this element"

---

## 🔧 Custom Animations

If our pre-built animations don't match your design:

1. Fill out the documentation template completely
2. Include a Figma prototype link
3. If using custom easing, take a screenshot of the curve
4. Add any timing or sequencing notes

Your developer will create a custom CSS animation based on your specs.

---

## 📞 Questions?

Can't find the right animation? Not sure how to describe something?

1. Show your developer the Figma prototype
2. Describe what you want in plain language
3. They can help you find or create the right animation

Remember: **It's better to over-communicate than under-communicate!**
