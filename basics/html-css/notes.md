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

## Styling Text

- **`text-transform`**: Defines text format (e.g., uppercase, lowercase).
- **`font-style`**: Specifies the font style (e.g., italic, normal).
- **`text-align`**: Defines text alignment (e.g., left, center, right).

## Class and ID Selectors

- **ID Selector (`#id`)**: Assigns an ID to an element and styles it using `#id` in CSS.
- **Class Selector (`.class`)**: Assigns a class to multiple elements and styles them using `.class` in CSS.

## Box Model & Borders

- **`<aside>`**: Adds a wrap box to the container.
- **`border: 1px solid #000;`**: Defines a border with a specific color.
- **Other border attributes**:
  - `border-top`
  - `border-bottom`
  - `border-left`
  - `border-right`

## Pseudo-classes

- **Definition**: Applies styles to elements based on their state.
- **Examples**:
  - `a:hover { font-weight: bold; text-decoration: underline; }`  
    _(Changes the hyperlink style when hovered over)_
  - `a:active { color: red; }`  
    _(Styles a hyperlink when clicked)_

## CSS Specificity & Priority

From **lowest** to **highest** priority:

1. Universal selector (`*`)
2. Element selectors (`p`, `div`, `li`, etc.)
3. Class (`.class`) or pseudo-class (`:hover`, `:focus`)
4. ID selector (`#id`)
5. Inline styles (`style="..."` in HTML)
6. **Declarations with `!important`** _(Overrides all other styles)_

## Width and Height Properties

- When the property is set to a **percentage**, the component adapts proportionally to the width and height of the browser.
- When using `auto`, the resource width and height are displayed automatically.

### Centering a block element (Important!)

```css
margin: 0 auto;
```

This centers the block element **horizontally** within its container.

---

## Block, Inline, and Inline-Block Elements

### Block-level Boxes

- Elements formatted visually as blocks.
- Key properties:
  1. Take up **100% of the parent’s width** by default.
  2. Always start on a **new line**.
  3. Follow the **box model** (respect margins, paddings, widths, etc.).

### Inline-Block Boxes

- Visually look like **inline elements**, but behave like **block elements inside**.
- Key properties:
  1. **Occupies only the necessary content space** (doesn’t stretch to full width).
  2. **Does not cause line breaks** (like inline elements).
  3. **Respects the box model**, meaning margins, paddings, widths, and heights apply properly.

### Inline Boxes

- Elements inside a line of text (e.g., `<span>`, `<a>`, `<strong>`).
- Key properties:
  1. **Only takes up as much space as its content**.
  2. **Does not respect width/height settings**.
  3. **Padding and margins only apply horizontally** (vertical margins are ignored).

---

## Absolute Positioning

- **Absolute elements** are positioned **relative to the nearest positioned ancestor** (`position: relative`), or the document itself if no positioned ancestor exists.
- Common properties used for positioning:

```css
top: 10px;
bottom: 20px;
left: 30px;
right: 40px;
```

- Unlike `relative`, **absolute elements are removed from the normal document flow**.

---

## Pseudo-elements & Pseudo-classes

### Pseudo-classes (single colon `:`)

- Define styles for a specific **state of an element** (e.g., `:hover`, `:focus`, `:nth-child()`).

### Pseudo-elements (double colon `::`)

- Used to **style parts of an element** (e.g., `::before`, `::after`).
- Example:

```css
h1::after {
  content: "✨";
  display: inline-block;
  padding: 5px;
  position: absolute;
  top: 10px;
  right: 15px;
}
```

This adds a **decorative symbol** (`✨`) after an `<h1>`.

---

## Float Elements (Deprecated in Modern Layouts)

- The `float` property is used for **wrapping text around an image** or creating multi-column layouts (but now replaced by Flexbox/Grid).
- Common issue: Floating elements break layouts!
- Solution: Use `clear: both` after floating elements:

```css
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```

---

## Box Sizing: border-box

- The **default width** of an element includes only its content (not padding/border).
- With `box-sizing: border-box`, padding and borders **do not** increase the element’s width.
- This is often set globally:

```css
* {
  box-sizing: border-box;
}
```

## Flexbox

### 1️. Container Properties (for `display: flex` elements)

- **`display: flex`** – Enables flexbox for the container.
- **`flex-direction`** – Defines the main axis:
  - `row` (default) → Left to right.
  - `row-reverse` → Right to left.
  - `column` → Top to bottom.
  - `column-reverse` → Bottom to top.
- **`justify-content`** – Aligns items along the main axis:
  - `flex-start` → Items align to the start.
  - `center` → Items align in the center.
  - `flex-end` → Items align to the end.
  - `space-between` → Space between items.
  - `space-around` → Space around items.
  - `space-evenly` → Equal space around items.
- **`align-items`** – Aligns items along the cross-axis:
  - `stretch` (default) → Items stretch to fill container.
  - `flex-start`, `center`, `flex-end`, `baseline`.
- **`align-content`** – Controls space between rows in a multi-line container.
- **`flex-wrap`** – Defines wrapping behavior:
  - `nowrap` (default) → No wrapping.
  - `wrap` → Wrap onto new lines.
  - `wrap-reverse` → Wrap in reverse order.
- **`gap`** – Defines space between flex items.

#### Example:

```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  gap: 10px;
}
```

---

### 2️. Item Properties (for flex items)

- **`flex-grow`** – Defines how much an item grows:
  - `0` → No growth.
  - `1` → Grows to fill available space.
- **`flex-shrink`** – Defines how much an item shrinks:
  - `0` → No shrinking.
  - `1` → Shrinks if needed.
- **`flex-basis`** – Defines the initial size of an item (`auto`, `px`, `%`).
- **`flex`** – A shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`:
  - `flex: 1;` → Takes all available space equally.
- **`order`** – Defines the order of items (default is `0`, lower values appear first).
- **`align-self`** – Aligns a specific item independently.

#### Example:

```css
.item {
  flex: 1; /* Grow equally */
}
.item:nth-child(2) {
  flex: 2; /* This item takes twice the space */
}
```

---

## CSS Grid

### 1️. Container Properties (for `display: grid` elements)

- **`display: grid`** – Enables grid layout.
- **`grid-template-columns`** – Defines columns:
  - `grid-template-columns: 100px 200px auto;`
  - `grid-template-columns: repeat(3, 1fr);`
- **`grid-template-rows`** – Defines rows:
  - `grid-template-rows: 100px 200px;`
- **`grid-auto-columns`** / **`grid-auto-rows`** – Defines implicit column/row sizes.
- **`gap`** – Defines spacing between rows and columns.
- **`justify-items`** – Aligns items horizontally (`start`, `center`, `end`, `stretch`).
- **`align-items`** – Aligns items vertically.
- **`justify-content`** – Aligns the grid container horizontally.
- **`align-content`** – Aligns the grid container vertically.

#### Example:

```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 100px 200px;
  gap: 10px;
}
```

---

### 2️. Item Properties (for grid items)

- **`grid-column`** – Defines which columns the item spans:
  - `grid-column: 1 / span 2;`
- **`grid-row`** – Defines which rows the item spans:
  - `grid-row: 2 / 3;`
- **`grid-area`** – Defines both row and column positions:
  - `grid-area: 2 / 1 / 3 / 3;`
- **`justify-self`** – Aligns an item horizontally.
- **`align-self`** – Aligns an item vertically.

#### Example:

```css
.item {
  grid-column: 1 / span 2;
  grid-row: 2 / 3;
}
```

---

## Flexbox vs. CSS Grid

### **When to Use Flexbox?**

- Best for layouts where elements are arranged in a **single row or column**.
- Used for **navigation bars, buttons, components** that need to dynamically adjust.

### **When to Use CSS Grid?**

- Best for **2D layouts**, where both **rows and columns** matter.
- Used for **page structures, dashboards, complex layouts**.

### **Key Difference**

- **Flexbox** is **one-dimensional** (row OR column).
- **Grid** is **two-dimensional** (rows AND columns).

---

Both **Flexbox** and **CSS Grid** are powerful tools! Mastering both will make your layouts efficient and scalable.
