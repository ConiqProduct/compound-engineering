---
name: frontend-design
description: This skill should be used when creating distinctive, production-grade frontend interfaces with high design quality. It applies when the user asks to build web components, pages, or applications. Generates creative, polished code that avoids generic AI aesthetics.
license: Complete terms in LICENSE.txt
---

This skill guides creation of distinctive, production-grade frontend interfaces that avoid generic "AI slop" aesthetics. Implement real working code with exceptional attention to aesthetic details and creative choices.

The user provides frontend requirements: a component, page, application, or interface to build. They may include context about the purpose, audience, or technical constraints.

## Design Thinking

Before coding, understand the context and commit to a BOLD aesthetic direction:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Tone**: Pick an extreme: brutally minimal, maximalist chaos, retro-futuristic, organic/natural, luxury/refined, playful/toy-like, editorial/magazine, brutalist/raw, art deco/geometric, soft/pastel, industrial/utilitarian, etc. There are so many flavors to choose from. Use these for inspiration but design one that is true to the aesthetic direction.
- **Constraints**: Technical requirements (framework, performance, accessibility).
- **Differentiation**: What makes this UNFORGETTABLE? What's the one thing someone will remember?

**CRITICAL**: Choose a clear conceptual direction and execute it with precision. Bold maximalism and refined minimalism both work - the key is intentionality, not intensity.

Then implement working code (HTML/CSS/JS, React, Vue, etc.) that is:
- Production-grade and functional
- Visually striking and memorable
- Cohesive with a clear aesthetic point-of-view
- Meticulously refined in every detail
- **WCAG 2.1 Level AA compliant** (accessibility is non-negotiable)

## Frontend Aesthetics Guidelines

Focus on:
- **Typography**: Choose fonts that are beautiful, unique, and interesting. Avoid generic fonts like Arial and Inter; opt instead for distinctive choices that elevate the frontend's aesthetics; unexpected, characterful font choices. Pair a distinctive display font with a refined body font.
- **Color & Theme**: Commit to a cohesive aesthetic. Use CSS variables for consistency. Dominant colors with sharp accents outperform timid, evenly-distributed palettes.
- **Motion**: Use animations for effects and micro-interactions. Prioritize CSS-only solutions for HTML. Use Motion library for React when available. Focus on high-impact moments: one well-orchestrated page load with staggered reveals (animation-delay) creates more delight than scattered micro-interactions. Use scroll-triggering and hover states that surprise.
- **Spatial Composition**: Unexpected layouts. Asymmetry. Overlap. Diagonal flow. Grid-breaking elements. Generous negative space OR controlled density.
- **Backgrounds & Visual Details**: Create atmosphere and depth rather than defaulting to solid colors. Add contextual effects and textures that match the overall aesthetic. Apply creative forms like gradient meshes, noise textures, geometric patterns, layered transparencies, dramatic shadows, decorative borders, custom cursors, and grain overlays.

NEVER use generic AI-generated aesthetics like overused font families (Inter, Roboto, Arial, system fonts), cliched color schemes (particularly purple gradients on white backgrounds), predictable layouts and component patterns, and cookie-cutter design that lacks context-specific character.

Interpret creatively and make unexpected choices that feel genuinely designed for the context. No design should be the same. Vary between light and dark themes, different fonts, different aesthetics. NEVER converge on common choices (Space Grotesk, for example) across generations.

**IMPORTANT**: Match implementation complexity to the aesthetic vision. Maximalist designs need elaborate code with extensive animations and effects. Minimalist or refined designs need restraint, precision, and careful attention to spacing, typography, and subtle details. Elegance comes from executing the vision well.

Remember: Claude is capable of extraordinary creative work. Don't hold back, show what can truly be created when thinking outside the box and committing fully to a distinctive vision.

## Accessibility Requirements (WCAG 2.1 Level AA)

**Accessibility is mandatory, not optional.** Beautiful design and accessibility are not mutually exclusive—they must work together.

### Required Implementation

- **Semantic HTML**: Use proper HTML5 elements (`<nav>`, `<main>`, `<article>`, `<section>`, `<header>`, `<footer>`)
- **ARIA Labels**: Add `aria-label` or `aria-labelledby` for icons, buttons without text, and complex widgets
- **Keyboard Navigation**: All interactive elements must be keyboard accessible (Tab, Enter, Space, Arrow keys)
- **Focus Indicators**: Visible focus states for all interactive elements (minimum 2px outline, high contrast)
- **Color Contrast**: Text meets WCAG AA standards (4.5:1 for normal text, 3:1 for large text ≥18pt or ≥14pt bold)
- **Alt Text**: All images have descriptive `alt` attributes (or `aria-hidden="true"` for decorative images)
- **Form Labels**: All inputs have associated `<label>` elements or `aria-label` attributes
- **Heading Hierarchy**: Logical heading structure (h1 → h2 → h3, no skipping levels)
- **Language**: Set `<html lang="en">` (or appropriate language)
- **Skip Links**: Provide skip navigation for keyboard users on multi-section pages
- **Error Messages**: Clear, descriptive errors associated with form fields using `aria-describedby`
- **Dynamic Content**: Use `aria-live` regions for content that updates dynamically

### Accessibility Testing

Before finalizing any frontend code:

1. **Keyboard Test**: Navigate entire interface using only keyboard
2. **Screen Reader Test**: Verify with at least one screen reader (VoiceOver, NVDA, or JAWS)
3. **Contrast Check**: Verify color contrast ratios meet WCAG AA standards
4. **Semantic Structure**: Validate HTML structure and ARIA usage

### Design + Accessibility Balance

- **Color**: Never rely solely on color to convey information (use icons, text, or patterns)
- **Motion**: Respect `prefers-reduced-motion` media query for animations
- **Focus**: Design focus indicators that match the aesthetic (custom styles, not just browser default)
- **Typography**: Ensure readable font sizes (minimum 16px for body text) and line heights (1.5 minimum)
- **Touch Targets**: Interactive elements should be at least 44×44px for touch devices

**Remember**: Great design is inclusive design. Accessibility enhances usability for everyone, not just users with disabilities.
