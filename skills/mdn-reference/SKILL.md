---
name: mdn-reference
description: Research and apply Web Standards, Browser APIs, and CSS specifications using MDN. Use when a user asks about browser features, compatibility, modern web APIs, or needs to implement high-performance frontend logic according to latest standards.
---

# MDN Web Standards Reference

## Overview
This skill provides a systematic approach to implementing browser features using MDN (Mozilla Developer Network) as the single source of truth. It ensures that solutions are mathematically sound, highly compatible, and use modern "Baseline" APIs.

## Research Workflow

### 1. Verification
Search MDN for the specific API or feature. Focus on:
- **Status:** Is the API experimental, deprecated, or stable?
- **Compatibility:** Check the "Browser Compatibility" table at the bottom of the page.
- **Baseline:** Identify if the feature is "Baseline: Widely Available" or "Baseline: Newly Available".

### 2. Decision Logic
- **Widely Available:** Implement directly.
- **Newly Available:** Check project requirements. If support for older browsers (e.g., Safari 15) is needed, suggest a polyfill or fallback.
- **Experimental:** Only suggest if the user explicitly asks for "cutting edge" features. Always provide a "Feature Detection" block.

### 3. Modernization Patterns
Always favor modern, declarative APIs over legacy imperative ones:
- **`fetch()`** over `XMLHttpRequest`.
- **`IntersectionObserver`** over scroll event listeners.
- **`ResizeObserver`** over window resize listeners.
- **`CSS Grid/Flexbox`** over floats.
- **`Web Crypto`** over custom JS math for security.

## Implementation Guidelines

### Feature Detection
Always use explicit feature detection for non-baseline APIs:
```javascript
if ('EyeDropper' in window) {
  // Use modern API
} else {
  // Fallback behavior
}
```

### Compatibility Reporting
When providing a code snippet, include a brief "Forensic Compatibility" block:
- **Chrome:** {version}+
- **Firefox:** {version}+
- **Safari:** {version}+
- **Baseline Status:** {Widely/Newly Available/Experimental}

## Resources
- **[BASELINE.md](references/baseline.md):** Understanding the Web's "Baseline" interoperability metric.
- **[PATTERNS.md](references/patterns.md):** Common high-performance browser patterns.
