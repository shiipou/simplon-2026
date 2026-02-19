### Core principles

- **Mobile‑first**: write base styles for small screens, add ascending media queries. **Why:** simpler cascade and better performance.
    
- **Separation of concerns**: HTML = semantics/structure; CSS = presentation. Use classes for styling, not element nesting.
    
- **Modular architecture**: split into **base**, **components**, **layout**, **pages**; keep files small and focused.
    

### Naming & structure

- **BEM** recommended: `block`, `block__element`, `block--modifier`.
    
    css
    
    ```
    .btn { }
    .btn--primary { }
    .card__title { }
    ```
    
- **Avoid** deep descendant selectors and `!important`. Prefer short, class-based selectors for performance.
    

### Variables, units & responsive sizing

- **CSS variables** in `:root` for colors, spacing, type scale:
    
    css
    
    ```
    :root {
      --brand: #0a74da;
      --gap: 1rem;
    }
    ```
    
- **Units**: use `rem` for typography, `clamp()`/`min()`/`max()` for fluid sizes, `%`/`fr` for layout flexibility.
    

### Layout & modern features

- **Flexbox** for 1‑dimensional layouts; **Grid** for 2‑dimensional. Use `gap` instead of margin hacks.
    
- Use `prefers-reduced-motion` and `:focus-visible` for accessibility.
    

### Performance & build

- **Normalize or reset** at project start for cross‑browser consistency.
    
- **Critical CSS** inline for first paint; lazy‑load non‑critical styles.
    
- **Tooling**: PostCSS + Autoprefixer, minification, and **stylelint** + Prettier in CI.
    

### Accessibility essentials

- **Contrast**: ensure WCAG‑compliant contrast ratios for text.
    
- **Keyboard focus**: never remove focus outlines; style `:focus-visible`.
    
- **Reduced motion**: respect `prefers-reduced-motion`.
    

### Quick checklist before commit

- **[ ]** Mobile‑first and documented breakpoints
    
- **[ ]** Variables centralized for colors/spacing/type
    
- **[ ]** No overly specific selectors; no `!important`
    
- **[ ]** Linting passes (stylelint) and build minified
    
- **[ ]** Accessibility checks: contrast, focus, reduced motion
    

### Short examples (practical snippets)

- **Responsive container**
    

css

```
.container {
  width: 100%;
  max-width: 1200px;
  margin-inline: auto;
  padding-inline: clamp(1rem, 4vw, 2rem);
}
```

- **Simple grid**
    

css

```
.grid { display:grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap:1rem; }
```

### Next steps I can provide

- **Generate a starter file tree** and sample `stylelint`/PostCSS configs tailored to your stack.
    
- **Create a one‑page critical CSS example** for your site.


## Source
https://laconsole.dev/cheatsheets/css