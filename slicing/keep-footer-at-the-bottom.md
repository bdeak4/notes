# Keep footer at the bottom

html:

```html
<body>
  <header>...</header>
  <main>...</main>
  <footer>...</footer>
</body>
```

css:

```css
body {
  min-height: 100vh;
  display: grid;
  grid-template-rows: auto 1fr auto;
}
```
