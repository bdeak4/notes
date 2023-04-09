# Loading indicator

html:

```html
<div class="spinner"></div>
```

css:

```css
.spinner {
  border-radius: 50%;
  width: 16px;
  height: 16px;
  border: 4px solid rgba(0, 0, 0, 0.2);
  border-left: 4px solid #000000;
  animation: spinner-animation 1.2s infinite linear;
}

@keyframes spinner-animation {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
```
