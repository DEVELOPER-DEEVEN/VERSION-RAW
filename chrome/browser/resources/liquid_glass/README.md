# Liquid Glass UI for L Browser

## Overview

The Liquid Glass UI system provides a modern, glass morphism design language with smooth, liquid-like animations. This system brings a premium, polished look to the L browser interface inspired by modern Apple-style fluidity.

## Features

- **Glass Morphism Effects**: Translucent backgrounds with blur and saturation
- **Smooth Animations**: Custom cubic-bezier curves for liquid-smooth transitions
- **Responsive Design**: Adapts to light and dark themes
- **Multiple Components**: Pre-built styles for buttons, cards, dialogs, panels, and inputs
- **Animation Utilities**: Ready-to-use animation classes for fade, scale, and shimmer effects

## Quick Start

### Basic Usage

Include the CSS file in your WebUI component:

```html
<link rel="stylesheet" href="chrome://resources/liquid_glass/liquid_glass.css">
```

### Apply Liquid Glass Effect

```html
<!-- Basic glass container -->
<div class="liquid-glass">
  Your content here
</div>

<!-- Glass button -->
<button class="liquid-glass-button">Click Me</button>

<!-- Glass card -->
<div class="liquid-glass-card">
  <h2>Card Title</h2>
  <p>Card content with glass effect</p>
</div>
```

## Available Components

### 1. Base Glass Container (`.liquid-glass`)

The foundation class that provides the core glass morphism effect:
- Semi-transparent background
- Backdrop blur and saturation
- Rounded corners
- Subtle shadow and border
- Smooth hover transitions

### 2. Glass Button (`.liquid-glass-button`)

Styled button with glass effect:
- Gradient background
- Hover elevation
- Active press feedback
- Smooth scaling

### 3. Glass Card (`.liquid-glass-card`)

Card container with enhanced glass effect:
- Larger padding
- Stronger blur
- Hover lift animation
- Perfect for content blocks

### 4. Glass Dialog (`.liquid-glass-dialog`)

Modal/dialog with strongest glass effect:
- Maximum blur for emphasis
- Entry animation
- Enhanced shadow
- Large border radius

### 5. Glass Panel (`.liquid-glass-panel`)

Side panel or toolbar style:
- Vertical gradient
- Medium blur
- Suitable for navigation

### 6. Glass Input (`.liquid-glass-input`)

Text input with glass styling:
- Subtle background
- Focus state with glow
- Border highlight on focus
- Smooth transitions

## Animation Classes

### Entry Animations

```html
<!-- Fade and slide up -->
<div class="liquid-glass liquid-animate-in">Content</div>

<!-- Slower animation -->
<div class="liquid-glass liquid-animate-in-slow">Content</div>

<!-- Scale in -->
<div class="liquid-glass liquid-animate-scale">Content</div>
```

### Staggered Animations

For lists, add stagger classes to create cascading effects:

```html
<div class="liquid-glass liquid-animate-in liquid-stagger-1">Item 1</div>
<div class="liquid-glass liquid-animate-in liquid-stagger-2">Item 2</div>
<div class="liquid-glass liquid-animate-in liquid-stagger-3">Item 3</div>
```

### Effects

```html
<!-- Shimmer loading effect -->
<div class="liquid-glass liquid-shimmer">Loading...</div>

<!-- Hover lift -->
<div class="liquid-glass liquid-lift">Hover me</div>
```

## Variants

### Frosted Glass (`.liquid-glass-frosted`)

Stronger blur effect for more prominent glass:

```html
<div class="liquid-glass-frosted">
  Heavily frosted content
</div>
```

### Glossy Surface (`.liquid-glass-glossy`)

Adds a glossy highlight to the top:

```html
<div class="liquid-glass liquid-glass-glossy">
  Glossy effect
</div>
```

## CSS Variables

Customize the theme by overriding CSS variables:

```css
:root {
  --liquid-glass-bg: rgba(255, 255, 255, 0.13);
  --liquid-glass-blur: 24px;
  --liquid-glass-saturation: 2;
  --liquid-glass-border-radius: 18px;
  --liquid-transition-normal: 0.5s cubic-bezier(0.34, 1.56, 0.64, 1);
}
```

## Dark Theme Support

The system automatically adjusts colors for dark theme using `prefers-color-scheme`:

```css
@media (prefers-color-scheme: dark) {
  /* Automatically applied darker variants */
}
```

## Platform-Specific Integration

### WebUI (HTML/CSS/JS)

Already implemented in the CSS file. Simply include and use the classes.

### Native UI (C++ Views)

For native C++ UI components, apply similar effects using platform APIs:

**macOS**: Use `CALayer` with blur effects:
```objc
layer.backgroundColor = [NSColor colorWithWhite:1.0 alpha:0.13];
layer.cornerRadius = 18.0;
// Add CIFilter for blur
```

**Windows**: Use Acrylic/Fluent Design APIs:
```cpp
// Enable acrylic background
CompositionBrush brush = compositor.CreateHostBackdropBrush();
```

**Linux**: Use compositor effects where available.

## Examples

### Complete Dialog Example

```html
<div class="liquid-glass-dialog liquid-animate-scale">
  <h2>Welcome to L</h2>
  <p>Experience the new Liquid Glass interface</p>
  <button class="liquid-glass-button">Get Started</button>
</div>
```

### Settings Panel

```html
<div class="liquid-glass-panel">
  <h3>Settings</h3>
  <input type="text" class="liquid-glass-input" placeholder="Search settings...">
  <div class="liquid-glass-card">
    <h4>Appearance</h4>
    <p>Customize your browser look</p>
  </div>
</div>
```

## Best Practices

1. **Performance**: Use backdrop-filter sparingly as it can be GPU-intensive
2. **Contrast**: Ensure text remains readable over glass backgrounds
3. **Layering**: Stack glass elements carefully to maintain visual hierarchy
4. **Animations**: Don't overuse animations; apply them purposefully
5. **Accessibility**: Maintain sufficient color contrast for accessibility

## Browser Support

- Chrome/Chromium: Full support
- Safari: Full support (webkit prefixes included)
- Firefox: Partial support (backdrop-filter may need flags)
- Edge: Full support

## Future Enhancements

- Platform-specific native blur implementations
- Additional component variants
- More animation presets
- Theme customization UI
- Performance optimizations

## Contributing

When adding new components or effects:
1. Follow the existing naming convention (`liquid-glass-*`)
2. Use CSS variables for consistency
3. Include hover/active states
4. Add smooth transitions
5. Test in light and dark themes
6. Document usage in this README

## License

Copyright 2024 The L Authors. All rights reserved.
