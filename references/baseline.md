# Web Baseline Status

Baseline is a web interoperability metric that tells you when a feature is safe to use across all major browser engines (Blink, Gecko, WebKit).

## Baseline Widely Available
A feature becomes "Widely Available" when it has been supported by the most recent two major versions of all major browsers for at least **30 months**.
- **Usage:** Safe for all production environments without polyfills.

## Baseline Newly Available
A feature is "Newly Available" as soon as it is supported by the current versions of all major browsers.
- **Usage:** Safe for modern-only apps; requires polyfills for users on older OS/Browser versions (e.g., old iOS).

## Not Yet Baseline
Features that are only in one or two engines.
- **Usage:** Requires strict feature detection and fallbacks.
