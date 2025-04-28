# Landing Page Maintenance Guide

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the main navigation and logo. To update:

1. **Logo Text**
```html
<!-- Find this line in the header -->
<a href="/" class="text-2xl font-bold text-indigo-600">Computerbril</a>
```
- Replace "Computerbril" with your desired logo text
- The `text-2xl` class controls size
- `text-indigo-600` controls the color

2. **Navigation Links**
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-indigo-600 transition-colors duration-300">Voordelen</a>
    <!-- More navigation items -->
</div>
```
- Update the text between `>` and `</a>` for each link
- Keep the class names intact to maintain hover effects

### Hero Section
Located at the top of the page with gradient background:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight mb-8 bg-gradient-to-r from-indigo-600 to-purple-600 bg-clip-text text-transparent">
    Computerbril Voor Dagelijks Gebruik
</h1>
```
- Replace the heading text while keeping the classes
- The gradient effect comes from `bg-gradient-to-r` and related classes

### Features Section
To add or modify feature cards:

1. Find the features grid:
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```

2. Copy an existing feature card and modify:
```html
<div class="bg-white p-8 rounded-2xl shadow-lg hover:shadow-xl transition-shadow duration-300">
    <div class="w-12 h-12 bg-indigo-100 rounded-full flex items-center justify-center mb-6">
        <!-- SVG icon here -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Your Feature Title</h3>
    <p class="text-gray-600">Your feature description</p>
</div>
```

## Fixing Broken Links

### Current Link Inventory
1. Navigation Menu Links:
```html
<a href="#features">Voordelen</a>
<a href="#benefits">Benefits</a>
<a href="#faq">FAQ</a>
<a href="#contact">Contact</a>
```
- These are internal links (marked with #)
- Ensure section IDs match these links exactly

2. Call-to-Action Links:
```html
<a href="https://computerbril.org/winkel" class="...">Bestel Nu</a>
```
- Replace with your actual shop URL
- Update all instances of this URL throughout the page

### Updating Links Step-by-Step
1. Internal Links:
   - Locate the section ID: `<section id="features">`
   - Ensure the corresponding link matches: `href="#features"`
   - Check all sections have matching IDs

2. External Links:
   - Replace placeholder URLs
   - Example:
   ```html
   <!-- From -->
   <a href="https://computerbril.org/winkel">
   <!-- To -->
   <a href="https://your-actual-shop.com">
   ```

## Linking Privacy and Terms Pages

### Adding Footer Links
1. Locate the footer section:
```html
<footer class="bg-gray-900 text-white py-16">
```

2. Add new links in an appropriate column:
```html
<div>
    <h3 class="text-xl font-bold mb-4">Legal</h3>
    <ul class="space-y-2">
        <li>
            <a href="/privacy.html" class="text-gray-400 hover:text-white transition-colors duration-300">Privacy Policy</a>
        </li>
        <li>
            <a href="/terms.html" class="text-gray-400 hover:text-white transition-colors duration-300">Terms of Service</a>
        </li>
    </ul>
</div>
```

### Maintaining Consistent Styling
- Copy existing footer link classes
- Use `text-gray-400` for normal state
- Use `hover:text-white` for hover state
- Keep the `transition-colors duration-300` for smooth effects

## Troubleshooting

### Common Issues
1. **Broken Internal Links**
   - Check that section IDs exactly match href values
   - IDs are case-sensitive
   - Remove any spaces in IDs

2. **Responsive Design Issues**
   - Don't remove `md:` or `lg:` prefixes from classes
   - Keep the grid structure intact
   - Test on multiple screen sizes

3. **Missing Styles**
   - Ensure TailwindCSS CDN link is present in head
   - Check for typos in class names
   - Maintain spacing between class names

### Need Help?
- Check the [TailwindCSS documentation](https://tailwindcss.com/docs)
- Validate HTML at [W3C Validator](https://validator.w3.org/)
- Test responsiveness using browser developer tools

Remember to always test changes across different devices and browsers before deploying to production.