# Focus ring

<!--*
# Document freshness: For more information, see go/fresh-source.
freshness: { owner: 'lizmitchell' reviewed: '2023-05-08' }
tag: 'docType:reference'
*-->

<!-- go/md-focus-ring -->

<!-- [TOC] -->

Focus rings are accessible outlines for components to show keyboard focus.

Focus rings follow the same heuristics as
[`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible)<!-- {.external} -->
to determine when they are visible.

![Three elements with a focus ring that moves between them.](images/focus/hero.gif "A focus ring moving across elements.")

*   Design article (*coming soon*)
*   API Documentation (*coming soon*)
*   [Source code](https://github.com/material-components/material-web/tree/main/focus)
    <!-- {.external} -->

## Usage

Focus rings display on keyboard navigation. They may be attached to a control in
one of three ways.

1.  Attached to the parent element

    ```html
    <style>
      .container {
        position: relative;
        --md-focus-ring-shape: 8px;
      }
    </style>
    <button class="container">
      <md-focus-ring></md-focus-ring>
    </button>
    ```

1.  Attached to a referenced element

    ```html
    <style>
      .container {
        position: relative;
        --md-focus-ring-shape: 8px;
      }
    </style>
    <div class="container">
      <md-focus-ring for="control"></md-focus-ring>
      <input id="control">
    </div>
    ```

1.  Attached imperatively

    ```html
    <style>
      .container {
        position: relative;
        --md-focus-ring-shape: 8px;
      }
    </style>
    <div class="container">
      <md-focus-ring id="ring"></md-focus-ring>
      <button id="ring-control"></button>
    </div>
    <script>
      const focusRing = document.querySelector('#ring');
      const control = document.querySelector('#ring-control');
      focusRing.attach(control);
    </script>
    ```

> Note: focus rings must be placed within a `position: relative` container.

### Animation

The focus ring animation may be customized or disabled using CSS custom
properties.

```html
<style>
  :root {
    --md-focus-ring-duration: 0; /* disabled animation */
  }
</style>
```

## Accessibility

Focus rings are visual components and do not have assistive technology
requirements.

## Theming

Focus rings supports [Material theming](../theming.md) and can be customized in
terms of color and shape.

### Tokens

Token                    | Default value
------------------------ | --------------------------
`--md-focus-ring-color`  | `--md-sys-color-secondary`
`--md-focus-ring-offset` | `2px`
`--md-focus-ring-shape`  | `9999px`
`--md-focus-ring-width`  | `3px`

*   [All tokens](https://github.com/material-components/material-web/blob/main/tokens/_md-comp-focus-ring.scss)
    <!-- {.external} -->

### Example

![Image of a focus ring with a different theme applied](images/focus/theming.png "Focus ring theming example.")

```html
<style>
:root {
  --md-focus-ring-shape: 0px;
  --md-focus-ring-width: 2px;
  --md-sys-color-secondary: #4A6363;
}
</style>

<button>
  <md-focus-ring></md-focus-ring>
</button>
```
