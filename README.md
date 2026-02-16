# Animation System: Figma to CSS

A complete solution for converting Figma animations to CSS, designed for collaboration between designers and developers.

## 🎯 Overview

This animation system bridges the gap between Figma prototypes and CSS implementation, making it easy for non-technical designers to communicate animation requirements to developers.

## 📦 What's Included

### Core Files

1. **`animation-tokens.json`**
   - Central configuration file with all animation definitions
   - Includes duration scales, easing curves, and animation presets
   - Single source of truth for animation properties

2. **`animations.css`**
   - Complete CSS animation library
   - Ready-to-use animation classes
   - CSS custom properties (variables)
   - Utility classes for delays, durations, and hover effects

3. **`demo.html`**
   - Interactive showcase of all animations
   - Visual reference for designers and developers
   - Live easing curve demonstrations
   - Open in browser to see animations in action

### Documentation

4. **`FIGMA-TO-CSS-GUIDE.md`** 📘
   - **For designers:** Step-by-step guide to document Figma animations
   - Simple templates and examples
   - No technical knowledge required
   - Pre-built animation reference

5. **`EASING-REFERENCE.md`** 📐
   - Complete Figma-to-CSS easing conversion guide
   - Visual representations of easing curves
   - Decision-making guide for choosing easings
   - Technical specifications and cubic-bezier values

## 🚀 Quick Start

### For Designers

1. **Learn the System**
   ```bash
   Read: FIGMA-TO-CSS-GUIDE.md
   ```

2. **View Available Animations**
   ```bash
   Open: demo.html (in any browser)
   ```

3. **Document Your Animations**
   - Use pre-built animations when possible
   - Follow the documentation template for custom animations
   - Reference EASING-REFERENCE.md for easing curves

### For Developers

1. **Include the CSS**
   ```html
   <link rel="stylesheet" href="animations.css">
   ```

2. **Use Animation Classes**
   ```html
   <!-- Simple usage -->
   <div class="fade-in">Content</div>

   <!-- With delay -->
   <div class="slide-up delay-200">Content</div>

   <!-- With custom duration -->
   <div class="zoom-in duration-slow">Content</div>
   ```

3. **Use CSS Variables**
   ```css
   .custom-animation {
     animation: my-keyframes 300ms var(--easing-spring);
     animation-delay: var(--duration-fast);
   }
   ```

## 🎬 Available Animations

### Entry Animations
- `fade-in` - Simple fade in
- `slide-up` - Slide from bottom
- `slide-down` - Slide from top
- `slide-left` - Slide from right
- `slide-right` - Slide from left
- `scale-up` - Grow from smaller
- `scale-down` - Shrink from larger
- `zoom-in` - Dramatic zoom in
- `zoom-out` - Dramatic zoom out
- `rotate-in` - Rotate while appearing
- `bounce-in` - Bouncy entrance

### Attention Animations
- `shake` - Shake effect (for errors)
- `pulse` - Pulsing effect
- `spin` - Continuous rotation (loaders)

### Hover Effects
- `hover-scale` - Scale up on hover
- `hover-lift` - Lift up with shadow
- `hover-fade` - Fade on hover

### Utility Classes

**Delays:**
- `delay-100` through `delay-1000`

**Durations:**
- `duration-instant` (100ms)
- `duration-fast` (200ms)
- `duration-normal` (300ms)
- `duration-moderate` (400ms)
- `duration-slow` (600ms)
- `duration-slower` (800ms)

## 📖 Usage Examples

### Example 1: Simple Card Entry
```html
<div class="card fade-in">
  <h2>Card Title</h2>
  <p>Card content...</p>
</div>
```

### Example 2: Staggered List Items
```html
<ul>
  <li class="slide-up">Item 1</li>
  <li class="slide-up delay-100">Item 2</li>
  <li class="slide-up delay-200">Item 3</li>
  <li class="slide-up delay-300">Item 4</li>
</ul>
```

### Example 3: Modal Appearance
```html
<div class="modal scale-up duration-moderate">
  <h2>Modal Title</h2>
  <p>Modal content...</p>
</div>
```

### Example 4: Button with Hover Effect
```html
<button class="hover-scale">
  Click Me
</button>
```

### Example 5: Loading Spinner
```html
<div class="spinner spin">⚙️</div>
```

### Example 6: Custom Animation with Variables
```css
.custom-element {
  animation: custom-keyframes
             var(--duration-normal)
             var(--easing-spring);
}

@keyframes custom-keyframes {
  from {
    opacity: 0;
    transform: translateY(20px) rotate(-5deg);
  }
  to {
    opacity: 1;
    transform: translateY(0) rotate(0deg);
  }
}
```

## 🎨 Workflow: Designer to Developer

### Phase 1: Design (Designer)
1. Create animations in Figma
2. Review available pre-built animations in `demo.html`
3. Document animations using `FIGMA-TO-CSS-GUIDE.md` template

### Phase 2: Handoff
- Share Figma prototype link
- Share filled documentation template
- Reference pre-built animation names when possible

### Phase 3: Implementation (Developer)
1. Use pre-built animations directly
2. For custom animations:
   - Reference designer's documentation
   - Extract properties and timing
   - Create custom CSS or add to library

### Phase 4: Review
- Designer reviews implementation
- Adjustments made using duration/delay classes
- Iterate until perfect match

## 🔧 Customization

### Adding New Animations

1. **Define in tokens** (`animation-tokens.json`):
```json
{
  "animations": {
    "my-new-animation": {
      "duration": "400ms",
      "easing": "ease-out",
      "description": "Description here",
      "properties": {
        "from": { "opacity": 0 },
        "to": { "opacity": 1 }
      }
    }
  }
}
```

2. **Add to CSS** (`animations.css`):
```css
@keyframes my-new-animation {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.my-new-animation {
  animation: my-new-animation 400ms ease-out both;
}
```

### Modifying Existing Animations

Edit `animations.css` directly, or adjust via CSS custom properties:

```css
:root {
  --duration-normal: 400ms; /* Changed from 300ms */
  --easing-ease-out: cubic-bezier(0, 0, 0.4, 1); /* Custom curve */
}
```

## 📱 Browser Support

- ✅ Chrome/Edge (all versions)
- ✅ Firefox (all versions)
- ✅ Safari 12+
- ✅ iOS Safari 12+
- ✅ Android Chrome

**Note:** Animations automatically respect `prefers-reduced-motion` for accessibility.

## ♿ Accessibility

The system includes built-in accessibility support:

```css
@media (prefers-reduced-motion: reduce) {
  /* All animations reduced to near-instant */
}
```

Users who prefer reduced motion will see instant transitions instead of animations.

## 🎓 Learning Resources

### For Designers
1. Start with `FIGMA-TO-CSS-GUIDE.md`
2. Open `demo.html` to see animations
3. Use `EASING-REFERENCE.md` when documenting

### For Developers
1. Review `animations.css` for available classes
2. Check `animation-tokens.json` for customization
3. Reference `EASING-REFERENCE.md` for timing functions

## 💡 Best Practices

### For Designers
- ✅ Use pre-built animations when possible
- ✅ Document duration in milliseconds
- ✅ Specify trigger clearly (hover, click, load)
- ✅ Include "why" in your notes
- ❌ Don't use vague terms like "smooth" or "nice"

### For Developers
- ✅ Use CSS variables for consistency
- ✅ Test on real devices
- ✅ Respect accessibility preferences
- ✅ Keep animations subtle and purposeful
- ❌ Don't override animation timing arbitrarily

## 🐛 Troubleshooting

### Animation Not Playing
- Check element visibility (display: none blocks animations)
- Verify CSS file is loaded
- Check browser console for errors

### Animation Too Fast/Slow
- Use duration utility classes: `duration-fast`, `duration-slow`
- Or override inline: `style="animation-duration: 500ms;"`

### Animation Feels Wrong
- Try different easing curves (see `EASING-REFERENCE.md`)
- Adjust duration
- Test on real devices (performance varies)

## 📊 Project Structure

```
.
├── animation-tokens.json       # Source of truth for animations
├── animations.css              # Complete CSS library
├── demo.html                   # Interactive showcase
├── FIGMA-TO-CSS-GUIDE.md      # Designer documentation
├── EASING-REFERENCE.md        # Easing curve guide
└── README.md                   # This file
```

## 🔄 Version Control

When committing changes:

```bash
# For token changes
git commit -m "feat: add new bounce-out animation"

# For documentation updates
git commit -m "docs: clarify easing curve examples"

# For CSS updates
git commit -m "style: adjust spring easing timing"
```

## 🤝 Contributing

### Adding New Animations
1. Add to `animation-tokens.json`
2. Implement in `animations.css`
3. Add example to `demo.html`
4. Document in relevant guides

### Improving Documentation
1. Identify confusing sections
2. Add examples or clarifications
3. Test with actual designers/developers
4. Submit changes

## 📞 Support

### For Designers
- Reference `FIGMA-TO-CSS-GUIDE.md` first
- View `demo.html` for visual examples
- Ask your developer team for clarification

### For Developers
- Check `animation-tokens.json` for specs
- Review `EASING-REFERENCE.md` for timing
- Test in `demo.html` before implementing

## 🎉 Success Metrics

This system is successful when:
- ✅ Designers can document animations independently
- ✅ Developers understand requirements clearly
- ✅ Implementation matches Figma prototypes
- ✅ Less back-and-forth between teams
- ✅ Consistent animation language across product

## 📝 License

Open source - feel free to modify and use in your projects.

---

**Ready to get started?**

1. 🎨 **Designers:** Open `FIGMA-TO-CSS-GUIDE.md`
2. 💻 **Developers:** Open `demo.html` in your browser
3. 🤝 **Both:** Bookmark `EASING-REFERENCE.md`

Let's create beautiful, consistent animations together! 🚀
