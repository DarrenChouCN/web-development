# HTML & CSS Notes

## Text Elements

- **`<strong>`**: Makes the font **bold**.
- **`<em>`**: Makes the font _italic_, which means "emphasize".

## Lists

- **`<ol>`**: Creates an ordered list and is used with the `<li>` tag.
- **`<ul>`**: Creates an unordered list and is also used with the `<li>` tag.

## Images and Attributes

- The `alt` attribute of the `<img>` tag is used to describe the image with a piece of text.

## Hyperlinks

- **`<a>`**: Creates a hyperlink, using the `href` attribute to specify the URL.
- **`target="_blank"`**: Opens the link in a new tab.
- **`a:visited`**: Styles a hyperlink that has been visited.
- **`text-decoration: none;`**: Removes underlines from hyperlinks.

## Semantic HTML

Semantic elements clearly define the structure of a webpage.

## CSS

### Types of CSS

1. **Inline CSS**: Declares styles inside an HTML tag. _(Not recommended)_
2. **Internal CSS**: Declares styles inside the `<style>` tag in the HTML file. _(Not recommended for large projects)_
3. **External CSS**: Links an external CSS file using the `<link>` tag. _(Recommended for better maintainability)_

---

## Styling Text

- **`text-transform`**: Defines text format (e.g., uppercase, lowercase).
- **`font-style`**: Specifies the font style (e.g., italic, normal).
- **`text-align`**: Defines text alignment (e.g., left, center, right).

---

## Class and ID Selectors

- **ID Selector (`#id`)**: Assigns an ID to an element and styles it using `#id` in CSS.
- **Class Selector (`.class`)**: Assigns a class to multiple elements and styles them using `.class` in CSS.

---

## Box Model & Borders

- **`<aside>`**: Adds a wrap box to the container.
- **`border: 1px solid #000;`**: Defines a border with a specific color.
- **Other border attributes**:
  - `border-top`
  - `border-bottom`
  - `border-left`
  - `border-right`

---

## Pseudo-classes

- **Definition**: Applies styles to elements based on their state.
- **Examples**:
  - `a:hover { font-weight: bold; text-decoration: underline; }`  
    _(Changes the hyperlink style when hovered over)_
  - `a:active { color: red; }`  
    _(Styles a hyperlink when clicked)_

---

## CSS Specificity & Priority

From **lowest** to **highest** priority:

1. Universal selector (`*`)
2. Element selectors (`p`, `div`, `li`, etc.)
3. Class (`.class`) or pseudo-class (`:hover`, `:focus`)
4. ID selector (`#id`)
5. Inline styles (`style="..."` in HTML)
6. **Declarations with `!important`** _(Overrides all other styles)_
