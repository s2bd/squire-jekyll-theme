---
layout: post
title: Welcome to Jekyll - Markdown Demo
date: 2025-07-13 12:00
---

# Welcome to Jekyll: A Markdown Demo

This post demonstrates the various Markdown features you can use in Jekyll with the Kramdown processor. Explore the examples below to see how to format content beautifully with this minimalistic theme, using Lora for body text and Open Sans for headers.

## Headings

Use hashtags (`#`) to create headings. The number of hashtags defines the heading level.

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

## Paragraphs and Line Breaks

Write paragraphs by adding text with a blank line between them. For a line break within a paragraph, add two spaces at the end of a line.

This is the first paragraph.

This is a second paragraph with a line break  
within it, achieved by adding two spaces.

## Emphasis

Use asterisks or underscores for emphasis:
- *Italic* or _Italic_
- **Bold** or __Bold__
- ***Bold and Italic*** or ___Bold and Italic___

## Lists

### Unordered Lists
Use `-`, `*`, or `+` for unordered lists:
- Item 1
- Item 2
  - Subitem 2.1
  - Subitem 2.2
- Item 3

### Ordered Lists
Use numbers followed by a period:
1. First item
2. Second item
   1. Subitem 2.1
   2. Subitem 2.2
3. Third item

### Definition Lists
Kramdown supports definition lists:
Term 1
: Definition for Term 1.
Term 2
: Definition for Term 2, which can span multiple lines  
  if you indent the continuation.

## Links

Create links using `[text](URL)`:
- [Visit Jekyll's official site](https://jekyllrb.com)
- Email me at [{{ site.email }}](mailto:{{ site.email }})

For automatic links, just include the URL: https://example.com

## Images

Embed images using `![alt text](URL)`:
![Sample Image](https://via.placeholder.com/600x300)
*Caption: A placeholder image.*

To reference images in your `assets` folder, use the `relative_url` filter:
![Local Image]({{ '/assets/images/sample.jpg' | relative_url }})
*Note: Add your own images to the `assets/images/` folder and update the path.*

## Code

### Inline Code
Use backticks for `inline code` snippets.

### Code Blocks
Use triple backticks or indent with four spaces for code blocks. Specify the language after the opening triple backticks for syntax highlighting.

```ruby
# Ruby code example
def hello_world
  puts "Hello, Jekyll!"
end
```

    // Indented code block (no syntax highlighting)
    function example() {
      console.log("Hello, world!");
    }

## Blockquotes

Use `>` for blockquotes:
> This is a blockquote. It can span multiple lines  
> and include *emphasis*, **bold**, or [links](https://jekyllrb.com).

Nested blockquotes:
> This is a blockquote.
>> This is a nested blockquote.

## Tables

Create tables using pipes (`|`) and hyphens (`-`) for headers:
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Row 1, Col 1 | Row 1, Col 2 | Row 1, Col 3 |
| Row 2, Col 1 | Row 2, Col 2 | Row 2, Col 3 |

Align text using colons:
| Left | Center | Right |
|:-----|:------:|------:|
| Left-aligned | Centered | Right-aligned |

## Horizontal Rules

Use three or more hyphens, asterisks, or underscores:
---
***
___

## Footnotes

Kramdown supports footnotes[^1]:
[^1]: This is a footnote. Add them using `[^1]` in the text and define the content anywhere in the document.

## Strikethrough

Use double tildes for ~~strikethrough~~ text.

## Task Lists

Create task lists with `- [ ]` for unchecked and `- [x]` for checked:
- [x] Install Jekyll
- [ ] Write a new blog post
- [ ] Deploy to GitHub Pages

## Escaping Characters

To display special Markdown characters, escape them with a backslash (`\`):
- A literal asterisk: \*
- A literal underscore: \_
- A literal hashtag: \#

## Kramdown-Specific Features

### Inline Attributes
Add classes, IDs, or other attributes using `{:.class #id}`:
This is a paragraph with a class and ID. {:.my-class #my-id}

### Abbreviations
Define abbreviations:
*[HTML]: HyperText Markup Language
*[CSS]: Cascading Style Sheets

Then use them: HTML and CSS are awesome.

## Embedding HTML

You can embed raw HTML if needed:
<div style="color: blue;">
  This is a blue div.
</div>

## Conclusion

This post showcases the power of Markdown in Jekyll. Experiment with these features to create rich, beautiful content. Edit this file in `_posts/2025-07-13-welcome-to-jekyll.md` to customize it, or create new posts with the same format (`YYYY-MM-DD-title.md`).

Happy blogging!

