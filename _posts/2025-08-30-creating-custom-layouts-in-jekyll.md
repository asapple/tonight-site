---
layout: post
title:  "Creating Custom Layouts in Jekyll"
date:   2025-08-30 14:30:00 +0800
categories: jekyll design
---

In today's post, we'll explore how to create custom layouts for your Jekyll site. Layouts are templates that wrap around your content, allowing you to have a consistent look and feel across your site.

## Understanding Layouts

Layouts live in the `_layouts` directory of your Jekyll site. Each layout file should contain the HTML structure for that layout, with a `{{ content }}` tag where the content will be inserted.

## Creating a Basic Layout

Here's a simple example of a layout file:

```html
<!DOCTYPE html>
<html>
<head>
  <title>{{ page.title }}</title>
</head>
<body>
  <header>
    <h1>My Site</h1>
  </header>
  <main>
    {{ content }}
  </main>
  <footer>
    <p>&copy; 2025 My Site</p>
  </footer>
</body>
</html>
```

## Using Layouts

To use a layout in a page or post, specify it in the front matter:

```yaml
---
layout: default
title: My Page
---
```

## Nested Layouts

You can also create nested layouts by referencing one layout from another:

```html
<!-- _layouts/page.html -->
---
layout: default
---
<article class="page">
  <h1>{{ page.title }}</h1>
  {{ content }}
</article>
```

This allows for more modular and reusable layout components.

## Conclusion

Custom layouts are a powerful feature of Jekyll that allow you to maintain consistency across your site while still having the flexibility to create unique page designs.