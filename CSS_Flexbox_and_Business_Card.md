# CSS Flexbox – Understanding Layouts Through a Business Card Project

## 1. Introduction to Flexbox

CSS Flexbox (Flexible Box Layout) is a CSS layout method used to arrange elements inside a container.

It helps us position items horizontally or vertically and control the space and alignment between them.

For example, when creating a business card, we may want to display a profile image on the left and personal information on the right. Flexbox makes this layout easier.

## 2. Understanding `display: flex`

To use Flexbox, we first need to make the parent element a flex container.

```css
.B-card {
    display: flex;
}
```

Here, `.B-card` is the parent container.

When we apply `display: flex`, its direct child elements become flex items. By default, they are arranged in a horizontal row.

**Why is this useful?**

Without Flexbox, elements may follow their normal document flow. Flexbox gives us more control over how these elements are arranged.

## 3. Understanding `flex-direction`

The `flex-direction` property controls the direction in which flex items are arranged.

There are two commonly used values:

### Row

```css
.B-card {
    display: flex;
    flex-direction: row;
}
```

- Arranges items horizontally.
- Places items from left to right.
- Useful when an image and text need to appear side by side.

### Column

```css
.B-card {
    display: flex;
    flex-direction: column;
}
```

- Arranges items vertically.
- Places items one below another.
- Useful when the image should appear above the profile information.

**Important:** `flex-direction` is the correct property for choosing row or column. Writing `flex: column` does not achieve this layout.

## 4. Understanding `justify-content`

The `justify-content` property controls the alignment of flex items along the main axis.

```css
.B-card {
    display: flex;
    justify-content: center;
}
```

Some commonly used values are:

- `center` – places items in the center.
- `flex-start` – places items at the beginning.
- `flex-end` – places items at the end.
- `space-between` – places space between items.
- `space-around` – adds space around items.
- `space-evenly` – distributes space evenly.

The main axis depends on the `flex-direction` value.

## 5. Understanding `align-items`

The `align-items` property controls the alignment of items along the cross axis.

```css
.B-card {
    display: flex;
    align-items: center;
}
```

Common values include:

- `center`
- `flex-start`
- `flex-end`
- `stretch`

For example, when using `flex-direction: row`, `align-items: center` can vertically align the image and text.

## 6. Applying Flexbox to a Business Card

Consider this HTML structure:

```html
<div class="B-card">
    <img src="profile.png" alt="Profile picture">

    <div class="info">
        <h2>Your Name</h2>
        <p>Web Developer</p>
    </div>
</div>
```

We have three important elements:

- `.B-card` – the parent container.
- `img` – the profile image.
- `.info` – the information section.

We can use the following CSS:

```css
.B-card {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
```

The `gap` property adds space between the image and information section.

**What happens when we change these properties?**

- Changing `row` to `column` places the image above the text.
- Changing `justify-content` changes the position along the main axis.
- Changing `align-items` changes the alignment along the cross axis.
- Changing `gap` increases or decreases the space between the image and text.

This shows how small CSS changes can affect the complete layout.

## 7. Common Mistakes While Learning Flexbox

### Mistake 1: Using `display: flexbox`

Incorrect:

```css
display: flexbox;
```

Correct:

```css
display: flex;
```

### Mistake 2: Using `flex: column`

Incorrect:

```css
flex: column;
```

Correct:

```css
flex-direction: column;
```

### Mistake 3: Linking the wrong CSS filename

If the actual stylesheet is named `styles.css`, but HTML links to `style.css`, the browser will not find the correct file.

Correct:

```html
<link rel="stylesheet" href="styles.css">
```

Always check that the filename and path in HTML match the actual file.

## 8. Final Learning Points

Flexbox is useful for creating clean and flexible webpage layouts.

The important properties covered in this practice are:

| CSS Property | Purpose |
