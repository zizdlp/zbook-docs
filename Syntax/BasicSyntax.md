# Basic Syntax

ZBook supports various formats and extension features, allowing users to easily write and format documents using the following basic syntax to enhance readability and presentation.

## Headings

Headings are used to organize content into sections. Users can create different levels of headings by adding `#` symbols. The more `#` symbols, the lower the heading level.

```markdown
# docTitle // Level 1 Heading

## title // Level 2 Heading

### subTitle // Level 3 Heading

#### subsubTitle // Level 4 Heading

##### subsubsubTitle // Level 5 Heading
```

## Footnotes

Footnotes are used to provide additional explanations or comments on specific parts of the text. Users can insert footnote markers in the main text, and the content will be displayed at the bottom of the page.

```markdown
hello[^1]

[^1]: hello is worked
```

## Lists

Markdown supports both ordered and unordered lists, suitable for listing items or steps. Nested lists can be created through indentation.

```markdown
This is a multi-level list

- list a
- list b
- list c
  1. list c.1
  2. list c.2
- list d
  - list d.a
  - list d.b
```

## Images

Users can insert images into documents and reference local image files using relative paths.

```markdown
This is an image
![Image](../assets/group_demo.png)
```

## Links

Markdown supports creating links to external websites or internal documents. External links use full URLs, while internal links point to other parts of the document.

```markdown
This is an external link:
[github](https://github.com)
This is an internal link:
[Formula](./Formula_and_Code.md)
```

Markdown also supports the following features in ZBook:

## Blockquotes

Blockquotes are used to emphasize a section of content, often for quoting other articles or paragraphs.

```markdown
> This is a blockquote, which can contain other Markdown elements.
```

## Tables

Tables are used to organize and display data. Users can create tables using vertical bars `|` and horizontal dashes `-`.

```markdown
| Header 1 | Header 2 | Header 3 |
| -------- | -------- | -------- |
| Content 1 | Content 2 | Content 3 |
| Content 4 | Content 5 | Content 6 |
```

## Strikethrough

Users can use strikethrough to indicate deleted or irrelevant text.

```markdown
~~This text will have a strikethrough~~
```

## Emphasis

Users can emphasize text by setting it in italics or bold using asterisks or underscores.

```markdown
_Italic_ or *Italic*
**Bold** or __Bold__
```

## Horizontal Rules

Horizontal rules are used to separate different sections of a document, typically between paragraphs. Users can create horizontal rules with three or more dashes, asterisks, or underscores.

```markdown
---
```

## Auto Links

Markdown automatically recognizes and converts URLs into clickable links, making it convenient to share external resources.

```markdown
https://github.com
```

These basic syntax features form the core of Markdown support in ZBook, allowing users to quickly write high-quality documents and meet various formatting needs.

## Admonition

Admonition is a feature used to insert content blocks for alerts, warnings, information, comments, etc., to highlight specific information in the document. Supported types include `info`, `note`, `warning`, `error`, and `tip`.

!!! info "Information Title"
    This is an information block used to provide useful tips or background information.

```markdown
!!! info "Information Title"
    This is an information block used to provide useful tips or background information.
```

??? warning "Information Title"
    This is an information block used to provide useful tips or background information.

```markdown
??? warning "Information Title"
    This is an information block used to provide useful tips or background information.
```
