# Color Classes Extension For Quarto

Add simple to use tailwindcss inspired css classes to apply your theme colors to elements.

![](color-classes.webp)

## Installing

```bash
quarto add emilhvitfeldt/quarto-color-classes
```

This will install the extension under the `_extensions` subdirectory.
If you're using version control, you will want to check in this directory.

## Using

Add the following file name `_extensions/emilhvitfeldt/color-classes/color-classes.scss` to `theme` in your yaml file. Like so:

```yaml
format:
  revealjs: 
    theme: 
      - default
      - styles.scss
      - _extensions/emilhvitfeldt/color-classes/color-classes.scss
```

It is important that it is placed **after** another scss file. In this case `styles.scss`. In the `styles.scss` file use [Maps](https://slidecrafting-book.com/scss.html#using-maps-to-store-theme-colors) to store a selection of colors. Like so:

```scss
/*-- scss:uses --*/
$colors: (
  "white": #ffffff,
  "black": #0d0c0c,
  "grey-light": #bcbcbd,
  "grey-dark": #51504f,
  "yellow": #ef9329,
  "red": #920c1a,
  "blue": #043892,
  "green": #949f5c,
);
```

It is important that this happens in `/*-- scss:uses --*/`.

If this is set up correctly then you have access to an array of css classes to use in your document. `*` in the below classes are the names used in `$colors`, so `text-black` makes the text black, `bg-grey-light` gives it a light grey background.

- `bg-*`: Sets the background color of an element
- `text-*`: Sets the text color of an element
- `decoration-*`: Sets the text decoration color of an element
- `border-*`: Sets the border color of an element
- `outline-*`: Sets the outline color of an element
- `fill-*`: Sets the fill color of SVG elements
- `stroke-*`: Sets the stroke color of svg elements 

These names are highly inspired by [tailwindcss](https://tailwindcss.com/docs/colors#using-color-utilities).

## Example

Here is the source code for a minimal example: [example.qmd](example.qmd).

