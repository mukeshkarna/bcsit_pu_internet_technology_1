# Unit II: Hyper Text Markup Language (HTML)
**[8 Hrs.]**

---

## 1. Introduction to HTML

- **HTML (HyperText Markup Language)** — standard markup language to create structure/content of web pages.
- Not a programming language — a **markup** language (uses tags to describe content).
- Browser reads HTML, renders it as visual page.
- Current version: **HTML5**.
- Key components: **Tags** (`<tag>`), **Elements** (tag + content + closing tag), **Attributes** (extra info inside tag).

```html
<p class="intro">Welcome to our site</p>
```
- `<p>` = tag
- `<p class="intro">Welcome to our site</p>` = element
- `class="intro"` = attribute

---

## 2. Document Structure

Every HTML page follows this skeleton:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Company - Home</title>
</head>
<body>
    <h1>Welcome to My Company</h1>
    <p>We build great software.</p>
</body>
</html>
```

| Part | Purpose |
|---|---|
| `<!DOCTYPE html>` | Tells browser to render as HTML5 (consistent rendering across browsers) |
| `<html>` | Root element, wraps entire page |
| `<head>` | Metadata — not visible on page (title, charset, viewport, linked CSS/JS) |
| `<meta charset="UTF-8">` | Character encoding — supports all languages/symbols |
| `<meta name="viewport"...>` | Makes page **responsive** on mobile devices — used in every real project |
| `<title>` | Text shown on browser tab, also used by Google search results |
| `<body>` | Visible content of page |

**Real project use:** every production site (e-commerce, portfolio, dashboard) starts from this exact skeleton. Missing `viewport` meta = broken mobile layout, a very common bug.

---

## 3. Text Formatting

| Tag | Purpose | Example |
|---|---|---|
| `<h1>` to `<h6>` | Headings (h1 = most important) | `<h1>Main Title</h1>` |
| `<p>` | Paragraph | `<p>Some text</p>` |
| `<strong>` | Important text (bold, semantic) | `<strong>Warning</strong>` |
| `<em>` | Emphasized text (italic, semantic) | `<em>very</em> important` |
| `<b>` | Bold (visual only, no semantic meaning) | `<b>Bold</b>` |
| `<i>` | Italic (visual only) | `<i>Italic</i>` |
| `<u>` | Underline | `<u>Underlined</u>` |
| `<s>` / `<del>` | Strikethrough | `<s>$500</s> $400` |
| `<br>` | Line break (self-closing) | `Line1<br>Line2` |
| `<hr>` | Horizontal rule/divider | `<hr>` |

**Real project example — pricing card with discount:**
```html
<h2>Premium Plan</h2>
<p><s>$29.99/mo</s> <strong>$19.99/mo</strong></p>
<p><em>Limited time offer</em></p>
<hr>
<p>Cancel <u>anytime</u>, no questions asked.</p>
```

---

## 4. Links and Navigation

- Navigation menus built using `<nav>` + list (`<ul>/<li>`) + anchor tags.
- Used in header of nearly every website.

**Real project example — website navbar:**
```html
<nav>
    <ul>
        <li><a href="index.html">Home</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="products.html">Products</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

---

## 5. Hyperlink

- `<a>` (anchor) tag creates hyperlinks.
- Key attribute: `href` (destination URL).

| Attribute | Purpose | Example |
|---|---|---|
| `href` | Destination link | `href="https://google.com"` |
| `target="_blank"` | Open in new tab | used for external links |
| `title` | Tooltip text on hover | `title="Go to homepage"` |
| id + `#` | Jump to section on same page | `href="#contact"` |

**Real project examples:**
```html
<!-- External link, opens new tab (common in "Read More" / social links) -->
<a href="https://facebook.com/mypage" target="_blank">Follow us on Facebook</a>

<!-- Internal page link -->
<a href="about.html">Learn more about us</a>

<!-- Email link (contact page) -->
<a href="mailto:support@company.com">support@company.com</a>

<!-- Phone link (mobile-friendly contact) -->
<a href="tel:+9779800000000">+977-9800000000</a>

<!-- Same-page jump link (used in landing pages with sections) -->
<a href="#pricing">See Pricing</a>
...
<h2 id="pricing">Pricing</h2>
```

---

## 6. Images and Multimedia

### Images
```html
<img src="images/logo.png" alt="Company Logo" width="150" height="60">
```
| Attribute | Purpose |
|---|---|
| `src` | Path/URL of image |
| `alt` | Alternate text — shown if image fails to load, used by screen readers (accessibility), and SEO |
| `width` / `height` | Dimensions (in px) |

**Real project example — product card:**
```html
<div class="product-card">
    <img src="images/shoes.jpg" alt="Red running shoes" width="200" height="200">
    <h3>Running Shoes</h3>
    <p>Rs. 3,500</p>
</div>
```

### Multimedia — Audio & Video
```html
<!-- Video (e.g., tutorial site, landing page demo) -->
<video width="480" controls>
    <source src="demo.mp4" type="video/mp4">
    Your browser does not support video.
</video>

<!-- Audio (e.g., podcast site) -->
<audio controls>
    <source src="podcast.mp3" type="audio/mpeg">
    Your browser does not support audio.
</audio>
```
- `controls` — shows play/pause/volume UI.
- Fallback text shown only if browser doesn't support tag.

---

## 7. Lists, Tables, Forms and Input

### Lists
```html
<!-- Unordered list — e.g., feature list on landing page -->
<ul>
    <li>Free shipping</li>
    <li>24/7 support</li>
    <li>Money-back guarantee</li>
</ul>

<!-- Ordered list — e.g., step-by-step checkout guide -->
<ol>
    <li>Add item to cart</li>
    <li>Enter shipping details</li>
    <li>Make payment</li>
</ol>
```

### Tables
```html
<!-- Real project example: order summary table (e-commerce) -->
<table border="1">
    <caption>Order Summary</caption>
    <tr>
        <th>Item</th>
        <th>Qty</th>
        <th>Price</th>
    </tr>
    <tr>
        <td>T-Shirt</td>
        <td>2</td>
        <td>Rs. 1,200</td>
    </tr>
    <tr>
        <td colspan="2">Total</td>
        <td>Rs. 1,200</td>
    </tr>
</table>
```
| Tag | Purpose |
|---|---|
| `<table>` | Table container |
| `<tr>` | Table row |
| `<th>` | Header cell (bold, centered by default) |
| `<td>` | Data cell |
| `<caption>` | Table title |
| `colspan` / `rowspan` | Merge cells across columns/rows |

### Forms and Input
Forms are how real projects collect data — login, signup, checkout, contact, search.

```html
<!-- Real project example: signup form -->
<form action="/register" method="POST">
    <label for="name">Full Name:</label>
    <input type="text" id="name" name="name" placeholder="Enter your name" required><br>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required><br>

    <label for="password">Password:</label>
    <input type="password" id="password" name="password" required><br>

    <label for="gender">Gender:</label>
    <input type="radio" id="male" name="gender" value="male"> Male
    <input type="radio" id="female" name="gender" value="female"> Female<br>

    <label for="country">Country:</label>
    <select id="country" name="country">
        <option value="np">Nepal</option>
        <option value="in">India</option>
    </select><br>

    <input type="checkbox" id="terms" name="terms" required>
    <label for="terms">I agree to Terms & Conditions</label><br>

    <textarea name="message" rows="4" placeholder="Additional message"></textarea><br>

    <button type="submit">Register</button>
</form>
```

| Element/Attribute | Purpose |
|---|---|
| `action` | URL where form data is sent (server endpoint) |
| `method="GET/POST"` | GET = data in URL (search); POST = data in body (login/signup — more secure) |
| `type="text/email/password/radio/checkbox/date/number..."` | Input type — enables built-in browser validation (e.g., `email` checks `@`) |
| `name` | Key used to identify field's value on server-side |
| `placeholder` | Hint text inside empty field |
| `required` | HTML5 built-in validation — field must be filled |
| `label for="id"` | Links label to input (accessibility, click label to focus input) |
| `<select>/<option>` | Dropdown list |
| `<textarea>` | Multi-line text input |
| `<button type="submit">` | Submits form |

**This is exactly the pattern used in real login/signup/checkout/contact pages across almost every website.**

---

## 8. Semantic HTML

- Tags that clearly describe their **meaning/purpose**, not just appearance.
- Improves **SEO**, **accessibility** (screen readers), and code readability.
- Used in virtually all modern real-world websites instead of generic `<div>` soup.

| Semantic Tag | Purpose |
|---|---|
| `<header>` | Top section — logo, nav, title |
| `<nav>` | Navigation links |
| `<main>` | Main unique content of page |
| `<section>` | Thematic grouping of content |
| `<article>` | Self-contained content (blog post, news article) |
| `<aside>` | Side content (sidebar, ads, related links) |
| `<footer>` | Bottom section — copyright, links, contact |

**Real project example — typical blog page layout:**
```html
<header>
    <h1>Tech Blog</h1>
    <nav>
        <a href="index.html">Home</a>
        <a href="blog.html">Blog</a>
    </nav>
</header>

<main>
    <article>
        <h2>Understanding HTML5</h2>
        <p>Published on Sept 10, 2026</p>
        <p>HTML5 introduced many semantic tags...</p>
    </article>

    <aside>
        <h3>Related Posts</h3>
        <ul>
            <li><a href="#">CSS Basics</a></li>
            <li><a href="#">JavaScript Intro</a></li>
        </ul>
    </aside>
</main>

<footer>
    <p>&copy; 2026 Tech Blog. All rights reserved.</p>
</footer>
```

**Why it matters in real projects:**
- Google ranks semantic pages better (SEO).
- Screen readers announce sections properly (accessibility, legally required in many countries).
- Team members read/maintain code faster (`<header>` vs `<div class="header-maybe">`).

---

## Quick Recap (Exam Points)

- HTML = markup language, not programming language; structures web content.
- Basic structure: `<!DOCTYPE html> → <html> → <head> → <body>`.
- `<head>` = metadata (not visible); `<body>` = visible content.
- `<strong>`/`<em>` = semantic emphasis; `<b>`/`<i>` = visual only.
- `<a href="">` creates hyperlinks; `target="_blank"` opens new tab.
- `<img src="" alt="">` — `alt` required for accessibility/SEO.
- Tables: `<table>`, `<tr>`, `<th>`, `<td>`, `colspan`/`rowspan`.
- Forms: `action`, `method` (GET/POST), `<input type="">`, `required`, `<label for="">`.
- Semantic tags (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`) replace generic `<div>` for meaning, SEO, accessibility.

---

## Possible Exam Questions

### Short Answer / Conceptual
1. What is HTML? Explain its role in web development.
2. Differentiate between `<b>` and `<strong>`, `<i>` and `<em>`.
3. What is the purpose of the `<!DOCTYPE html>` declaration?
4. Explain the basic structure of an HTML document with a diagram/example.
5. What is the difference between `<head>` and `<body>` sections?
6. What are meta tags? Explain `charset` and `viewport` with examples.
7. What is semantic HTML? Why is it important? Give any four semantic tags with their use.
8. Differentiate between GET and POST methods in forms.
9. What is the use of the `alt` attribute in the `<img>` tag?
10. Differentiate ordered list and unordered list with example.
11. What is the difference between `colspan` and `rowspan` in HTML tables?
12. Explain any five form input types with examples.
13. What is the difference between `<div>` and semantic tags like `<section>`/`<article>`?

### Long Answer / Programming
1. Write HTML code to design a **student registration form** with fields: name, email, password, gender (radio), course (dropdown), and a submit button.
2. Design an HTML page using **semantic tags** (`header`, `nav`, `main`, `section`, `footer`) for a personal portfolio website.
3. Write HTML code to create a **table** displaying a mark-sheet with subject, credit hours, and grade, including a merged "Total" row.
4. Create an HTML page with a **navigation bar**, an image gallery (minimum 3 images), and a footer with copyright text.
5. Write HTML to embed a video and audio file on a webpage with proper fallback text.
6. Design a simple **product page** using `<img>`, `<h1>`-`<h3>`, `<p>`, `<s>` (discount price), and an "Add to Cart" button.
7. Explain with example how hyperlinks can be used for (a) external website, (b) email, (c) same-page navigation.

### True/False or Fill in the Blanks (objective-style)
1. `<br>` is a self-closing tag. (True)
2. The `<head>` section content is visible in the browser window. (False)
3. `required` attribute in HTML5 forms enables built-in validation. (True)
4. `<em>` and `<i>` produce visually identical output but differ in semantic meaning. (True)
5. The default HTTP method for a form is _______ (GET).
6. _______ tag is used to define the main unique content of a page (main).
