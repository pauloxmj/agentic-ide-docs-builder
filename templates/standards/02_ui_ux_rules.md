<template target_path="docs/standards/02_ui_ux_rules.md">
# UI/UX Rules & Styling Architecture

> **Agent Directive:** Always reference these rules when creating or modifying user interfaces. If the design requires a token or utility not listed here or in the foundation files, flag it for human review.

## 1. Core Styling Engine
[Extract styling methodology, e.g., Tailwind CSS v3, CSS Modules, Styled Components]

## 2. Design Tokens
[Read the tailwind config or global CSS to extract core tokens]
- **Primary Color:** `[color_name]` (`[hex]`)
- **Typography:** `[font_family]`

## 3. Component Usage
[Extract UI pattern]
- [e.g., Use atomic design. Do not build custom buttons; import from `@/components/ui/button`]

## 4. Accessibility (a11y)
- **Keyboard Navigation:** Every interactive element must be reachable and actionable via keyboard.
- **Focus States:** Distinct, visible focus rings.
- **Contrast:** Ensure text passes WCAG AA contrast ratio.
</template>
