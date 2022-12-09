# css

A primer on CSS - using the CodeCademy course.

## Course Notes

- cascading tile sheets

### CSS Anatomy

- **declarations** are the core of CSS
  - they apply a style to the selected element
- There is CSS Ruleset
- There is CSS InLine

- Ruleset Terms:

- Selector—The beginning of the ruleset used to target the element that will be styled.
- Declaration Block—The code in-between (and including) the curly braces ({ }) that contains the CSS declaration(s).
- Declaration—The group name for a property and value pair that applies a style to the selected element.
- Property—The first part of the declaration that signifies what visual characteristic of the element is to be modified.
- Value—The second part of the declaration that signifies the value of the property.

### Inline Styles

- it is possible to write CSS directly within HTML
- you can add the <style> element directly to the opening tag

```
<p style='color: red;'>I'm learning to code!</p>
```

- inline styles are rarely used when creating a website

### Internal Stylesheet

- you can create CSS code in it's own dedicated section with a <style>element nested inside the <head>.

```
<head>
  <style>
    p {
        color: red;
        font-size: 20px;
        }

  </style>
</head>
```

### External Stylesheet

- You can create an external stylesheet by using the .css file name extension, like so: style.css
- You can use the <link> element to link HTML and CSS files together.
- The <link> element must be placed within the head of the HTML file.
- <link> attributes:
    - href — like the anchor element, the value of this attribute must be the address, or path, to the CSS file.
    - rel — this attribute describes the relationship between the HTML file and the CSS file.

```
<link href='https://www.codecademy.com/stylesheets/style.css' rel='stylesheet'>
```

- If the CSS file is stored in the same directory as your HTML file, then you can specify a relative path instead of a URL:

```
<link href='./style.css' rel='stylesheet'>
```
