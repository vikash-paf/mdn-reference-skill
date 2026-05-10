# High-Performance Browser Patterns

## 1. DOM Visibility (Intersection Observer)
Instead of listening to `scroll` events (which fire on every pixel and cause layout thrashing):
```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
});
observer.observe(document.querySelector('.reveal-item'));
```

## 2. Resource Cleaning (AbortController)
Always provide a way to cancel async tasks (fetch, timeouts) to prevent memory leaks and race conditions:
```javascript
const controller = new AbortController();
const signal = controller.signal;

fetch(url, { signal }).then(...)

// Cancel when user leaves page/closes component
controller.abort();
```

## 3. Storage Efficiency (IndexedDB via Wrapper)
For large data, use IndexedDB instead of LocalStorage to avoid blocking the main thread.
- **Pattern:** Use a lightweight promise wrapper (like idb-keyval style).
- **Fallback:** Fall back to LocalStorage only if IndexedDB is blocked.
