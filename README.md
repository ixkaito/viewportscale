<p align="center"><img src="https://ixkaito.github.io/viewportscaler/img/logo.b5863405.svg" alt="ViewportScaler Logo"></p>

<h1 align="center">ViewportScale</h1>

<p align="center">To linearly scale font-size, margin, padding, etc. across viewport widths.</p>

## How to Use

1. Import `_viewportscale.scss` in your sass file:

   ```scss
   @import "viewportscale";
   ```

2. Now you can use the `vs` mixin like this:

   ```scss
   @include vs($property, $min-viewport-width, $min-size, $max-viewport-width, $max-size);
   ```

### Example 1

```scss
h1 {
    @include vs(font-size, 320px, 32px, 960px, 48px);
}
```

This will be compiled to:

```css
h1 {
    font-size: 32px;
}

@media screen and (min-width: 320px) {
    h1 {
        font-size: calc(2.5vw + 24px);
    }
}

@media screen and (min-width: 960px) {
    h1 {
        font-size: 48px;
    }
}
```

### Example 2

```scss
.container {
    @include vs(padding, 320px, 16px, 960px, 24px);
}
```

This will be compiled to:

```css
.container {
    padding: 16px;
}

@media screen and (min-width: 320px) {
    .container {
        padding: calc(1.25vw + 12px);
    }
}

@media screen and (min-width: 960px) {
    .container {
        padding: 24px;
    }
}
```

## License

[MIT License](https://github.com/ixkaito/viewportsize/blob/master/LICENSE)
