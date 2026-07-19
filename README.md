# HTML Tutorial

This repository contains my notes and examples for learning HTML.

## Table of Contents
- [Basic Document Structure](#basic-document-structure)
- [Headings](#headings)
- [Paragraphs](#paragraphs)
- [Block vs Inline Elements](#block-vs-inline-elements)
- [Anchor Elements](#anchor-elements)
- [Lists](#lists)
- [Forms](#forms)
- [Images](#images)
- [Divs and Spans](#divs-and-spans)
- [ID Attribute](#id-attribute)
- [Horizontal Rule](#horizontal-rule)
- [Semantic HTML](#semantic-html)

---

## Basic Document Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
</head>
<body>
    <!-- Content here -->
</body>
</html>
```

- `<!DOCTYPE html>`: Declares the document type and HTML version (HTML5)
- `<html>`: Root element of the HTML document
- `<head>`: Contains metadata about the page
- `<meta charset="UTF-8">`: Sets the character encoding to UTF-8
- `<meta name="viewport" ...>`: Controls page dimensions and scaling on mobile devices
- `<title>`: Sets the page title (displayed in browser tab)
- `<body>`: Contains all visible content rendered on the page

---

## Headings
```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>
```
- Headings range from `<h1>` (largest) to `<h6>` (smallest)
- Used to structure document content hierarchically

---

## Paragraphs
```html
<p>Your paragraph text here</p>
```
- `<p>` tag defines a paragraph
- Automatically adds space before and after the text

---

## Block vs Inline Elements

### Block Elements
- Take full available width
- Start on a new line
- Examples: `<div>`, `<p>`, `<h1>`-`<h6>`, `<ul>`, `<ol>`

### Inline Elements
- Take only necessary width
- Do not start on a new line
- Examples: `<span>`, `<a>`, `<strong>`, `<em>`, `<u>`, `<s>`

```html
<strong>Bold Text</strong>
<em>Italic Text</em>
<u>Underlined Text</u>
<s>Strikethrough Text</s>
```

---

## Anchor Elements
```html
<a href="https://example.com" target="_blank">Link Text</a>
```
- `href`: URL the link points to
- `target="_blank"`: Opens link in new tab/window

---

## Lists

### Unordered List
```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

### Ordered List
```html
<ol>
    <li>First</li>
    <li>Second</li>
    <li>Third</li>
</ol>
```

---

## Forms
```html
<form action="" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" placeholder="Enter your name">
    
    <label for="password">Password:</label>
    <input type="password" id="password" name="password">
    
    <!-- Radio Buttons (select one) -->
    <input type="radio" id="cat" name="pet" value="cat">
    <label for="cat">Cat</label>
    
    <!-- Checkboxes (select multiple) -->
    <input type="checkbox" id="tea" name="drink" value="tea">
    <label for="tea">Tea</label>
    
    <!-- Dropdown -->
    <select name="monuments" id="monuments">
        <optgroup label="Inside Delhi">
            <option value="qutub-minar" selected>Qutub Minar</option>
        </optgroup>
    </select>
    
    <!-- Datalist -->
    <input list="browsers" name="browser">
    <datalist id="browsers">
        <option value="Chrome">
        <option value="Firefox">
    </datalist>
    
    <button type="submit">Submit</button>
</form>
```

---

## Images
```html
<img src="image-url.jpg" width="300" alt="Description of image">
```
- `src`: Image source URL
- `alt`: Alternative text (for accessibility, displays if image fails to load)
- `width`/`height`: Set image dimensions

---

## Divs and Spans

### Div
```html
<div>This is a block-level container</div>
```
- Block-level element
- Used to group and divide content

### Span
```html
<span>This is an inline container</span>
```
- Inline element
- Used to target specific content

---

## ID Attribute
```html
<div id="unique-id"></div>
```
- Uniquely identifies an element on a page
- Only one element can have the same ID per page

---

## Horizontal Rule
```html
<hr>
```
- Self-closing element
- Separates sections of content

---

## Semantic HTML

Semantic HTML uses elements that carry meaningful descriptions of their content, making pages more accessible and SEO-friendly. Non-semantic elements like `<div>` and `<span>` say nothing about their content — semantic elements do.

### Key Semantic Elements

#### `<header>`
- Represents introductory content or navigational aids for a page or section
- Typically holds the site logo, main heading, and `<nav>`

#### `<nav>`
- Defines a block of navigation links
- Use `aria-label` when there are multiple `<nav>` elements on the page to distinguish them for screen readers
```html
<nav aria-label="Primary Navigation">
    <ul>
        <li><a href="#">Link</a></li>
    </ul>
</nav>
```

#### `<main>`
- Represents the primary, dominant content of the page
- There should only be **one** `<main>` per page

#### `<section>`
- Groups thematically related content, usually with a heading
- Use `aria-labelledby` pointing to a heading's `id` for better accessibility
```html
<section aria-labelledby="section-heading">
    <h2 id="section-heading">Section Title</h2>
    <p>Content...</p>
</section>
```

#### `<article>`
- Represents self-contained, independently distributable content
- Examples: blog posts, news articles, forum entries

#### `<aside>`
- Contains content tangentially related to the surrounding content
- Commonly used for sidebars, pull quotes, or supplementary info

#### `<footer>`
- Represents the footer for its nearest sectioning ancestor
- Typically holds copyright info, author details, or related links

---

### Other Useful Semantic Elements

#### `<figure>` and `<figcaption>`
- `<figure>`: Wraps self-contained media (images, diagrams, code snippets)
- `<figcaption>`: Provides a caption for the `<figure>`
```html
<figure>
    <img src="image.jpg" alt="Description">
    <figcaption>Caption text</figcaption>
</figure>
```

#### `<time>`
- Represents a specific point in time or a duration
- `datetime` attribute provides a machine-readable format (ISO 8601)
```html
<time datetime="PT3H">3 Hours</time>   <!-- duration: 3 hours -->
<time datetime="07:00">7 am</time>      <!-- time of day -->
```

#### `<abbr>`
- Marks an abbreviation or acronym
- `title` attribute provides the full expansion on hover
```html
<abbr title="Side Bar">SB</abbr>
```

#### `<details>` and `<summary>`
- `<details>`: A disclosure widget the user can open/close
- `<summary>`: The visible label/heading for the `<details>` widget
```html
<details>
    <summary>Click to expand</summary>
    <p>Hidden content shown when expanded.</p>
</details>
```

#### `<mark>`
- Highlights text for reference or notation purposes
```html
<p>Lorem <mark>ipsum dolor sit</mark> amet.</p>
```

#### `&copy;`
- HTML entity that renders the © copyright symbol
```html
<p>&copy; Aditya Jha</p>
```

---

### Why Use Semantic HTML?
- **Accessibility**: Screen readers use semantic elements to help users navigate content
- **SEO**: Search engines better understand page structure and content relevance
- **Readability**: Code is easier to read and maintain
- **Standards**: Follows modern HTML5 best practices
