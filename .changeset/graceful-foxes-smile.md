---
"markdown-to-jsx": patch
---

Fix null children crashing app in production

When `null` or `undefined` is passed as children to the `<Markdown>` component, it would previously crash the app in production. This fix handles these cases by converting them to empty strings.

### Usage Example

Before this fix, the following code would crash in production:

```jsx
<Markdown>{null}</Markdown>
<Markdown>{undefined}</Markdown>
```

After this fix, these cases are handled gracefully and render nothing.
