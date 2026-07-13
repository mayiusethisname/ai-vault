---
name: webapp-testing
description: Use when testing, debugging, or verifying a local web application, frontend UI, browser behavior, rendered DOM, console errors, responsive layout, screenshots, or user flows with Playwright or browser automation.
---

# Webapp Testing

Verify the app in a real browser when UI behavior matters. Static code inspection is not enough for dynamic frontend bugs.

## Workflow

1. Determine how the app runs: static HTML, dev server, frontend/backend pair, or already-running URL.
2. Start or identify the server and note the URL.
3. Wait for the app to load fully before inspecting DOM or taking screenshots.
4. Capture console errors and failed network requests.
5. Inspect rendered DOM and screenshots before choosing selectors.
6. Test the user flow with stable selectors such as roles, labels, text, or test IDs.
7. Verify desktop and mobile viewports when layout matters.

## Playwright Pattern

Use a reconnaissance-then-action flow:

```python
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=True)
    page = browser.new_page(viewport={"width": 1280, "height": 800})
    page.goto("http://localhost:5173")
    page.wait_for_load_state("networkidle")
    page.screenshot(path="screen.png", full_page=True)
    print(page.content()[:2000])
    browser.close()
```

## Checks

- Page is not blank.
- Main controls are visible and clickable.
- Text does not overlap or overflow.
- Console has no relevant errors.
- Network requests needed for the flow succeed.
- State changes persist when expected.
- Mobile layout remains usable.

## Common Pitfalls

- Inspecting DOM before JavaScript finishes rendering.
- Clicking selectors guessed from source instead of rendered state.
- Testing only the happy path.
- Ignoring console errors because the visible UI appears fine.
