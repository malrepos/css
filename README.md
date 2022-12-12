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

---

## Selectors

- selectors decide which element will get the style

#### Type Selectors

- the type selector matches the type of the element

```
p {
  color: green;
}
```

- in the is case the type selected is the <p> element
- the type selector does not include the angle <> brackets
- the type selector is sometimes referred to as tag name or element selector

#### Universal Selectors

- the universal selector selects all elements of any type
- th euniversal selector uses \*

```
* {
  font-family: Verdana;
}
```

#### Class Selectors

- HTML elements can have attributes

```
<p class='brand'>Sole Shoe Company</p>
```

- the above p element has a class atribute
- we can select this element using a period prepended to the class name

```
.brand {

}
```

#### Multiple Classes

- it's possible to add more than one class name to an HTML element's class attribute

```
<h1 class='green bold'> ... </h1>
```

and then write two CSS rulesets:

```
.green {
  color: green;
}

.bold {
  font-weight: bold;
}
```

#### ID Selectors

- an elements ID can only have a single value, and can only be used once
- se prepend the ID name with #

```
#large-title {

}
```

#### Attribute Selectors

- the attribute sleector can be used to target HTML elements that already contain attributes

```
[href]{
   color: magenta;
}
```

- the above would target all href atributes
- we can also target elements where the attribute contains any instance of a specific value

```
// say we have 2 images:

<img src='/images/seasons/cold/winter.jpg'>
<img src='/images/seasons/warm/summer.jpg'>

// and we target each separately

img[src*='winter'] {
  height: 50px;
}

img[src*='summer'] {
  height: 100px;
}
```

#### Pseudo-Class

- certain elements can change, or be in a different state, after certain interactions
- a pseudo class can be added to any selector
- :focus :visited :disabled :active are all pseudo classes
- it is always written as a colon followed by a name

```
p:hover {
  background-color: lime;
}
```

- In the above code, whenever the mouse hovers over a paragraph element, that paragraph will have a lime-colored background.

#### Classes and ID's

- CSS classes and IDs have different purposes, which can affect which one you use to style HTML elements.
- CSS classes are meant to be reused over many elements.
- an ID is meant to style only one element
- ID's override the styles of types and classes

#### Specificity

- Specificity is the order by which the browser decides which CSS styles will be displayed. A best practice in CSS is to style elements while using the lowest degree of specificity so that if an element needs a new style, it is easy to override.
- IDs are the most specific selector in CSS, followed by classes, and finally, type.

#### Chaining

- it's possible to require an HTML element to have 2 or more CSS selectors at the same time
- we combine multiple selectors : chaining

```
h1.special {

}
```

- above we select only the H1 eleemnts with a class of special

#### Descendant Combinator

- CSS also supports selecting elements that are nested within other HTML elements, also known as descendants.

```
<ul class='main-list'>
  <li> ... </li>
  <li> ... </li>
  <li> ... </li>
</ul>

// The nested <li> elements are descendants of the <ul> element

.main-list li {

}

// we select the <li> elements by targeting forst the parent element class
```

#### Chaining and Specificity

- Adding more than one tag, class, or ID to a CSS selector increases the specificity of the CSS selector.
- if there is another rule that is more general, it will be overriden

#### Ultiple Selectors

- it’s possible to add CSS styles to multiple CSS selectors all at once. This prevents writing repetitive code.

```
// the following has repetetive code:

h1 {
  font-family: Georgia;
}

.menu {
  font-family: Georgia;
}

// we can separate the selectors by a common to style both

h1,
.menu {
  font-family: Georgia;
}
```

---

# Visual Rules

### Font Family

- font-family property

```
h1 {
  font-family: Garamond;
}
```

- Web safe fonts are a group of fonts supported across most browsers and operating systems.
- When the name of a typeface consists of more than one word, it’s a best practice to enclose the typeface’s name in quotes

### Font Size

- font-size property

```
p {
  font-size: 18px;
}
```

- px means pixels,a way to measure font size

### Font Weight

- font-weight property
- controls how bold or thin text appears

```
p {
  font-weight: bold;
}
```

### Text Align

- text will always appear on the left side of the container
- text-align property will align text to the element that holds it (it's parent)

```
h1 {
  text-align: right;
}
```

- common values are
  - left
  - center
  - right
  - justify (spaces out text to align with right and left side of the parent element)

### Color and Background Color

- color can affect the following design aspects:
  - foreground color
  - background color
- foreground color is the color that elements appear in
- color: this property styles an element’s foreground color
- background-color: this property styles an element’s background color

```
h1 {
  color: red;
  background-color: blue;
}
```

### Opacity

- opacity is the measure of how transparent an element is
- It’s measured from 0 to 1, with 1 representing 100%, or fully visible and opaque, and 0 representing 0%, or fully invisible.

```
.overlay {
  opacity: 0.5;
}
```

### Background Image

- we can make the background of an element an image
- the value provided to background-image is a URL

```
.main-banner {
  background-image: url('https://www.example.com/image.jpg');
}
```

### Important

- !important can be applied to specific declarations, instead of full rules
- it will override any style no matter how specific it is
- should almost never be used

```
p {
  color: blue !important;
}

.main p {
  color: red;
}
```

- all elements will now appear blue, despite there being a more specific selector
