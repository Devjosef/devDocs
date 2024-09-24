# HTML

## Introduction
HTML (HyperText Markup Language) is the standard language for creating web pages and web applications. It describes the structure of a web page semantically and originally included cues for the appearance of the document.

## Basic Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>Hello World</h1>
</body>
</html>
```

## Common Use Cases
- Structuring web pages
- Embedding images, videos, and other media
- Creating forms for user input
- Linking to other web pages

## Advanced Features
- **Semantic HTML5 elements**: Use elements like `<article>`, `<section>`, `<nav>`, and `<aside>` to provide more meaning to the structure of your web pages.
- **Accessibility features**: Implement ARIA roles and attributes to improve accessibility for users with disabilities.
- **Forms and input types**: Utilize various input types (`<input type="email">`, `<input type="date">`, etc.) and form attributes (`required`, `pattern`, etc.) to enhance user input handling.

## Code Snippets
### Basic Form
```html
<form action="/submit" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    <button type="submit">Submit</button>
</form>
```

### Semantic HTML5 Elements
```html
<article>
    <header>
        <h1>Article Title</h1>
        <p>Published on <time datetime="2023-10-01">October 1, 2023</time></p>
    </header>
    <p>This is the content of the article.</p>
    <footer>
        <p>Author: John Doe</p>
    </footer>
</article>
```

### Accessibility with ARIA
```html
<button aria-label="Close" onclick="closeDialog()">X</button>

<nav aria-label="Main Navigation">
    <ul>
        <li><a href="/home">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
    </ul>
</nav>
```

## Tips & Best Practices
- **Use semantic elements**: Always use semantic HTML elements to improve accessibility and SEO.
- **Alt attributes**: Ensure all images have `alt` attributes to describe the image content for screen readers.
- **External styles and scripts**: Use external stylesheets and scripts to keep your HTML clean and maintainable.
- **Responsive design**: Use meta tags and responsive design techniques to ensure your web pages look good on all devices.
- **Validation**: Always validate your HTML to catch errors and ensure compatibility across different browsers.

## External Resources
- [MDN Web Docs: HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [W3Schools: HTML](https://www.w3schools.com/html/)
- [HTML Living Standard](https://html.spec.whatwg.org/)
- [WebAIM: Web Accessibility In Mind](https://webaim.org/)