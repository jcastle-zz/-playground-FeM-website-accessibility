# FeM Website Accessibility

- Rob Dodson - Accessibility Lead at Google - check YouTube
- WebAIM.org - Checklist for accessibility
  - All websites should be perceivable, operable, understandable, and robust
- Course GitHub files - https://github.com/jkup/learn-a11y
  - Navigate to index.html to see content and exercises
- Course slides - https://docs.google.com/presentation/d/1_CRR-bJFX5Xt-2Tx_lPMDSMUtoxe8s8kAF7DDDXVvc8/edit#slide=id.p

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
  - Use buttons not divs or links - buttons tab-ble, can use space bar on them, have additional functionality
    - Anchors can be tabbed but miss buttons things such as on key down
  - Use section, article, etc. for better semantic meaning than div

## Focus control

- Run this anytime in console to get currently focused element
  - var currentElement = document.activeElement
  - most common use case is when doing modal (a close up), you can save where some is and focuse back on where the user left off
- Tabtrapping or focustrapping - grab all focusable children, listen for tab or shift tab, only do something if they go off edge of modal

## Working with screen readers

- Screenreader programs - JAWS, ZoomText Mac, Window-Eyes, NVDA, VoiceOver, ChromeVox
- Command F5 on Mac will turn on voice over
- Image tag for audio and video - use alt tag for the screen reader, don't use "image of" or "graphic of", upper case read letter by letter, skip image for reader by using alt=''
- Screen readers won't read with attributes display:none, visibility:hidden, <input hidden />
- Use CSS to hide from screen but read to screen reader
  - .screenreader { position: absolute; left: -10000px; width: 1px; height: 1px; overflow: hidden; }
  - same approach used for skip to navigation
- Label - often used for input fields on forms
- Aria-labelledby - can pass in multiple elements (e.g., aria-labelledby="billing address"), gets away from label, use this the most

## Semantic HTML

- Make sure language is always defined in HTML lang attribute - <html lang="en">
- Language in sections of page that are different should be identified too - <blockquote lang="es">
- Unknown words can be defined with glossary or definition list
- Don't just use div, span, and img without proper labeling or extra content (e.g., alt text)
- Elements have inherited functionality - headers should be used properly and style with CSS

## WAI-ARIA

- ARIA - Accessible Rich Internet Applications
- Role communicates to screen reader what the element represents
- aria-label and aria-describedby - use describedby for additional description
- aria provides tools for clicking, expanding, hover, etc., can add icons as css
- Live region - aria-live, aria-relevant - tells screen reader a certain area is updating
- Chrome dev ARIA tools - chrome://flags
- Accessibility tree - for content to be read out loud, it has to be in the tree (has something to do with dominos and loading content)
- Can you use aria-live without aria-relevant? - not sure if it cascades or not - this advance use case

## Accessibility in color and design

-
