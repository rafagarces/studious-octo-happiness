# Accessibility Features

## Overview

The Animation Library Demo (`demo.html`) has been designed to meet **WCAG 2.1 Level AA** accessibility standards, ensuring it's usable by everyone, including people with disabilities.

---

## ♿ Accessibility Features

### 1. **Keyboard Navigation**

#### Full Keyboard Support
- **Tab**: Navigate through all interactive elements
- **Enter/Space**: Activate buttons and controls
- **Shift + Tab**: Navigate backwards

#### Skip Link
- A "Skip to main content" link appears when you press Tab
- Allows keyboard users to bypass header and jump straight to content
- Essential for screen reader users and keyboard navigation

```html
<a href="#main-content" class="skip-link">Skip to main content</a>
```

### 2. **Screen Reader Support**

#### ARIA Labels
Every interactive element has descriptive ARIA labels:
```html
<button
  class="replay-btn"
  aria-label="Replay Fade In animation"
  aria-describedby="fade-in-title">
  Click to Replay
</button>
```

#### Live Regions
Screen readers announce when animations play:
```html
<div aria-live="assertive" aria-atomic="true" class="sr-only" id="status-announcement"></div>
```

Announcements include:
- "Playing Fade In animation"
- "Playing easing curve demonstrations"
- "Easing curve animations reset"

#### Semantic HTML
- Proper heading hierarchy (h1, h2, h3)
- `<main>` for main content
- `<section>` for distinct content areas
- `<footer>` for footer information
- `role="list"` and `role="listitem"` for card grids

#### Screen Reader Only Text
Descriptive text for screen readers that's visually hidden:
```html
<span class="sr-only">Animation starts fast and slows down at the end</span>
```

### 3. **Visual Accessibility**

#### Color Contrast
All colors meet **WCAG AA** contrast requirements:
- **Background to text**: 4.5:1 minimum
- **Button backgrounds**: Enhanced contrast ratios
- **Focus indicators**: High contrast 3px outlines

#### Focus Indicators
Visible focus states for all interactive elements:
```css
.replay-btn:focus {
  outline: 3px solid #667eea;
  outline-offset: 2px;
  border-color: #667eea;
}
```

**What you'll see:**
- Blue outline around focused elements
- Clear indication of where keyboard focus is
- Never removed or hidden

#### Text Readability
- Minimum font size: 0.9rem (14.4px)
- Clear font family (system fonts)
- Adequate line spacing
- High contrast text colors

### 4. **Reduced Motion Support**

#### Respects User Preferences
Automatically detects and respects `prefers-reduced-motion`:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

#### JavaScript Detection
```javascript
const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

if (prefersReducedMotion) {
  // Don't auto-play animations
  announce('Animations are disabled due to your reduced motion preference');
}
```

**How to enable reduced motion:**
- **macOS**: System Preferences → Accessibility → Display → Reduce motion
- **Windows**: Settings → Ease of Access → Display → Show animations
- **iOS**: Settings → Accessibility → Motion → Reduce Motion
- **Android**: Settings → Accessibility → Remove animations

### 5. **Interactive Elements**

#### Proper Button Usage
All clickable elements use proper `<button>` elements:
```html
<!-- ✅ Accessible -->
<button onclick="replayAnimation(this, 'fade-in', 'Fade In')">
  Click to Replay
</button>

<!-- ❌ Not used (inaccessible) -->
<div onclick="...">Click me</div>
```

#### Disabled State Management
Buttons are temporarily disabled during animations:
```javascript
button.disabled = true;
setTimeout(() => {
  button.disabled = false;
}, 600);
```

This prevents rapid clicking and provides clear feedback.

### 6. **Descriptive Content**

#### Page Title and Description
```html
<title>Animation Library Demo - Accessible Interactive Showcase</title>
<meta name="description" content="Interactive demo of CSS animation library with accessible controls and examples">
```

#### Section Headings
All sections have unique IDs and proper heading structure:
```html
<section aria-labelledby="entry-animations-heading">
  <h2 id="entry-animations-heading">Entry Animations</h2>
  ...
</section>
```

#### Code Examples
Code blocks are properly labeled:
```html
<div class="code-block" role="region" aria-label="Code example">
  <code>&lt;div class="fade-in"&gt;Your content&lt;/div&gt;</code>
</div>
```

---

## 🧪 Testing Accessibility

### Automated Testing Tools

1. **Lighthouse** (Chrome DevTools)
   - Open Chrome DevTools (F12)
   - Go to Lighthouse tab
   - Run accessibility audit
   - **Target Score**: 95+

2. **axe DevTools** (Browser Extension)
   - Install axe DevTools extension
   - Run scan on demo page
   - **Target**: 0 violations

3. **WAVE** (Web Accessibility Evaluation Tool)
   - Visit wave.webaim.org
   - Enter demo URL
   - Review issues

### Manual Testing

#### Keyboard Navigation Test
1. Close your mouse/trackpad
2. Press Tab repeatedly
3. Verify you can:
   - Navigate to all interactive elements
   - See clear focus indicators
   - Activate buttons with Enter
   - Use controls without mouse

#### Screen Reader Test

**macOS (VoiceOver)**
```bash
# Start VoiceOver
Cmd + F5

# Navigate
Control + Option + Arrow keys

# Activate elements
Control + Option + Space
```

**Windows (NVDA - Free)**
```
# Download from: nvaccess.org
# Start NVDA: Ctrl + Alt + N
# Navigate: Arrow keys
# Activate: Enter
```

**Test Checklist:**
- [ ] Page title is announced
- [ ] Heading structure is clear
- [ ] Button labels are descriptive
- [ ] Animation replays are announced
- [ ] All content is accessible

#### Color Contrast Test
1. Use browser color picker
2. Check contrast ratios
3. Minimum ratios:
   - Normal text: 4.5:1
   - Large text: 3:1
   - UI components: 3:1

#### Reduced Motion Test
1. Enable reduced motion in system settings
2. Reload demo page
3. Verify animations are minimal/instant
4. Check that page is still functional

---

## 📋 WCAG 2.1 Level AA Compliance Checklist

### Perceivable

- [x] **1.1.1** Non-text Content: Decorative emojis marked with `aria-hidden="true"`
- [x] **1.3.1** Info and Relationships: Proper semantic HTML structure
- [x] **1.3.2** Meaningful Sequence: Logical reading order
- [x] **1.4.1** Use of Color: Information not conveyed by color alone
- [x] **1.4.3** Contrast (Minimum): 4.5:1 for normal text, 3:1 for large text
- [x] **1.4.4** Resize Text: Text remains readable at 200% zoom
- [x] **1.4.10** Reflow: Content reflows at mobile sizes
- [x] **1.4.11** Non-text Contrast: UI components have 3:1 contrast
- [x] **1.4.12** Text Spacing: Content doesn't break with adjusted spacing

### Operable

- [x] **2.1.1** Keyboard: All functionality available via keyboard
- [x] **2.1.2** No Keyboard Trap: Users can navigate away from all elements
- [x] **2.1.4** Character Key Shortcuts: No single-key shortcuts
- [x] **2.4.1** Bypass Blocks: Skip link provided
- [x] **2.4.2** Page Titled: Descriptive page title
- [x] **2.4.3** Focus Order: Logical tab order
- [x] **2.4.4** Link Purpose: Link text is descriptive
- [x] **2.4.6** Headings and Labels: Clear headings and labels
- [x] **2.4.7** Focus Visible: Clear focus indicators
- [x] **2.5.3** Label in Name: Button text matches accessible name

### Understandable

- [x] **3.1.1** Language of Page: `lang="en"` specified
- [x] **3.2.1** On Focus: No context changes on focus
- [x] **3.2.2** On Input: No unexpected context changes
- [x] **3.3.1** Error Identification: Errors clearly identified
- [x] **3.3.2** Labels or Instructions: Clear instructions provided

### Robust

- [x] **4.1.1** Parsing: Valid HTML
- [x] **4.1.2** Name, Role, Value: All elements have proper ARIA
- [x] **4.1.3** Status Messages: Live regions for dynamic updates

---

## 🎯 Accessibility Best Practices Used

### 1. Progressive Enhancement
- Works without JavaScript
- Core content is accessible first
- Enhancements added progressively

### 2. Semantic HTML First
- Uses proper HTML elements
- ARIA added only when needed
- Never uses `<div>` when semantic element exists

### 3. Clear Language
- Simple, concise labels
- No jargon or technical terms
- Instructions are straightforward

### 4. Consistent Patterns
- All animation cards work the same way
- Predictable interaction patterns
- Consistent visual feedback

### 5. User Control
- Users can pause/stop animations
- Respects system preferences
- No auto-playing content (except one demo with respect to preferences)

---

## 🔧 For Developers: Maintaining Accessibility

### When Adding New Animations

1. **Add ARIA labels**
```html
<button
  class="replay-btn"
  aria-label="Replay [Animation Name] animation"
  aria-describedby="[animation-id]-title">
  Click to Replay
</button>
```

2. **Add screen reader announcement**
```javascript
announce(`Playing ${animationName} animation`);
```

3. **Ensure keyboard accessibility**
- Use `<button>` not `<div>`
- Never remove focus indicators
- Test with keyboard only

4. **Check color contrast**
```bash
# Use online tool: contrast-ratio.com
# Minimum ratios:
# - Normal text: 4.5:1
# - Large text (18pt+): 3:1
# - UI components: 3:1
```

### When Adding Interactive Elements

1. **Semantic HTML**
```html
<!-- ✅ Good -->
<button onclick="doSomething()">Action</button>

<!-- ❌ Bad -->
<div onclick="doSomething()">Action</div>
```

2. **Keyboard support**
```javascript
element.addEventListener('keydown', (e) => {
  if (e.key === 'Enter' || e.key === ' ') {
    e.preventDefault();
    // Handle action
  }
});
```

3. **ARIA attributes**
```html
<div role="button" tabindex="0" aria-label="Descriptive label">
  <!-- Only if you can't use <button> -->
</div>
```

---

## 📚 Additional Resources

### Standards
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)
- [WebAIM](https://webaim.org/)

### Testing Tools
- [Lighthouse](https://developers.google.com/web/tools/lighthouse)
- [axe DevTools](https://www.deque.com/axe/devtools/)
- [WAVE](https://wave.webaim.org/)
- [Color Contrast Checker](https://webaim.org/resources/contrastchecker/)

### Screen Readers
- [NVDA (Windows - Free)](https://www.nvaccess.org/)
- [JAWS (Windows - Paid)](https://www.freedomscientific.com/products/software/jaws/)
- [VoiceOver (Mac/iOS - Built-in)](https://www.apple.com/accessibility/voiceover/)
- [TalkBack (Android - Built-in)](https://support.google.com/accessibility/android/answer/6283677)

### Browser Extensions
- [Accessibility Insights](https://accessibilityinsights.io/)
- [Landmarks Browser Extension](http://matatk.agrip.org.uk/landmarks/)
- [HeadingsMap](https://chrome.google.com/webstore/detail/headingsmap)

---

## ✅ Summary

The demo is accessible to:
- ✅ Keyboard-only users
- ✅ Screen reader users
- ✅ Users with reduced motion preferences
- ✅ Users with color blindness
- ✅ Users with cognitive disabilities
- ✅ Users with motor disabilities
- ✅ Mobile device users
- ✅ Users with older browsers

**Accessibility is not a feature—it's a fundamental requirement.**

By making this demo accessible, we ensure that everyone, regardless of their abilities, can learn about and use the animation system.

---

**Questions or concerns about accessibility?**

File an issue or reach out to the team. Accessibility is everyone's responsibility! 🌟
