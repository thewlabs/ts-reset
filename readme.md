# TS Reset - Improved TypeScript's Built-in Typings

**Without `ts-reset`**:

- 🚨 `.json` (in `fetch`) and `JSON.parse` both return `any`
- 🤦 `.filter(Boolean)` doesn't behave how you expect
- 😡 `array.includes` often breaks on readonly arrays

`ts-reset` smooths over these hard edges, just like a CSS reset does in the browser.

**With `ts-reset`**:

- 👍 `.json` (in `fetch`) and `JSON.parse` both return `unknown`
- ✅ `.filter(Boolean)` behaves EXACTLY how you expect
- 🥹 `array.includes` is widened to be more ergonomic
- 🚀 And several more changes!
