# FeM Website Accessibility

- Rob Dodson - Accessibility Lead at Google - check YouTube
- WebAIM.org - Checklist for accessibility
  - All websites should be perceivable, operable, understandable, and robust
- Course GitHub files - https://github.com/jkup/learn-a11y
  - Navigate to index.html to see content and exercises

## Keyboard navigation

- Add keyboard shortcuts for common tasks
  - Twitter - type Shift ? for keyboard shortcuts
  - Often follow Vim shortcuts - H, K, J, L
  - jkup/shortcut - keyboard shortcut generator
  - Basics of keyboard navigation is the tab key and tab-able elements
  - Tab-able elements - anchor <a>, button, input, select, textarea, iframe
  - Don't want every element tab-able - only interaction elements - not div, section, p, etc.
  - tabindex - Any element can be made tab-able by developers - <div tabindex="0">I'm focusable</div>
    - tabindex values - negative value, 0, positive value
      - negative value - element should be focusable, but not reachable via sequential keyboard navigation
      - 0 - elements should be focusable and reachable via sequential keyboard navigation, but order determined by the platform convention
      - positive value - same as 0 with being reachable given hierarchy of element - often an anti-pattern like a z-index
  - Visible focus - visually apparent which page element has the current keyboard focus (i.e., as you tab through the page, you should see where you are)
  - Skip links - use as a class (see example - https://frontendmasters.com/courses/web-accessibility/skip-links/)

## Focus control

## Working with screen readers

## Semantic HTML

## WAI-ARIA

## Accessibility in color and design
