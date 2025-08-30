---
title: "Latex Blog Post"
date: 2025-05-01
draft: true
description: "Description about latex testing post."
params:
    math: true
---

## Using LaTeX in Your Hugo Academic Website

This guide explains how to write LaTeX in your markdown files and how it will render on your website.

## LaTeX Syntax in Markdown

You can include LaTeX equations in your Hugo markdown files using the following delimiters:

1. **Inline equations**: Use `$...$` or `\\(...\\)`
2. **Display equations**: Use `$$...$$` or `\\[...\\]`

## Examples

### Basic Equations

For inline equations like $E=mc^2$, just write: `$E=mc^2$`

For displayed equations:

```LaTeX
$$
E = mc^2
$$
```

Which renders as:

$$
E = mc^2
$$

### Fractions

```LaTeX
$$\frac{n!}{k!(n-k)!} = \binom{n}{k}$$
```

Renders as:

$$\frac{n!}{k!(n-k)!} = \binom{n}{k}$$

### Summations and Integrals

```LaTeX
$$\sum_{i=1}^{n} x_i$$
```

Renders as:

$$\sum_{i=1}^{n} x_i$$

```LaTeX
$$\int_{a}^{b} f(x) \, dx$$
```

Renders as:

$$\int_{a}^{b} f(x) \, dx$$

### Matrices

```LaTeX
$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$
```

Renders as:

$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$

### Aligned Equations

```LaTeX
$$
\begin{align}
\dot{x} & = \sigma(y-x) \\
\dot{y} & = \rho x - y - xz \\
\dot{z} & = -\beta z + xy
\end{align}
$$
```

Renders as:

$$
\begin{align}
\dot{x} & = \sigma(y-x) \\
\dot{y} & = \rho x - y - xz \\
\dot{z} & = -\beta z + xy
\end{align}
$$

## LaTeX in Different Content Types

You can use LaTeX in any markdown file in your Hugo site:

1. **Blog posts**: Great for explaining mathematical concepts
2. **Preprints summaries**: Add equations that appear in your papers
3. **Research pages**: Include mathematical formulations of your research problems
4. **Teaching materials**: Add equations for courses or tutorials

## Advanced Usage

### Custom Macros

You can define custom LaTeX macros by adding them to the KaTeX configuration in your `head.html` partial:

```html
<script>
    document.addEventListener("DOMContentLoaded", function() {
        renderMathInElement(document.body, {
            delimiters: [
                {left: '$$', right: '$$', display: true},
                {left: '$', right: '$', display: false},
                {left: '\\(', right: '\\)', display: false},
                {left: '\\[', right: '\\]', display: true}
            ],
            macros: {
                "\\R": "\\mathbb{R}",
                "\\vec": "\\boldsymbol"
            },
            throwOnError : false
        });
    });
</script>
```

This defines `\R` as a shorthand for `\mathbb{R}` (the real numbers symbol) and enhances the `\vec` command.

## Troubleshooting

1. **Equations not rendering**: Make sure your markdown file is being processed by Hugo correctly
2. **Escaping backslashes**: In some contexts, you might need to double backslashes in LaTeX commands
3. **Syntax errors**: Check the browser console for KaTeX error messages

## Tips for Academic Writing

1. **Consistent notation**: Keep your mathematical notation consistent across your website
2. **Equation numbering**: For long documents, consider using equation numbering
3. **Accessibility**: Provide text descriptions of important equations for screen readers
