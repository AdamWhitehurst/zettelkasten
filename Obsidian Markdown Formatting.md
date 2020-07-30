---

id: 202007251030
tags:
 - #markdown
 - #formatting
source: https://github.github.com/gfm/

---

# Obsidian Markdown Formatting Examples

Obsidian supports GitHub Flavored Markdown.

---

# Headings
---

# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

---
# Text
---

**BOLD**
*ITALIC*
__BOLD__
_ITALIC_
==HIGHLIGHT==
~~Strikethrough~~
__*==~~ALL~~==*__

---
# Lists
---

1. Ordered Lists
	1. Ignore
	2. Numbering
2. Can use One for every
3. But formatting calculates
4. actual numbers, and recalculates
	1. after additional lines

- Unordered List
	- Don't
	- Care
		- But give different
		- bullets

---
# Links
---

External Links:
- Unformatted: http://obsidian.md/
- Formatted: [obsidian website](http://obsidian.md/)

Internal Links:
- [[Hyperlinks]]
- [[Hyperlinks|Aliased Links (still goes to Hyperlink Page)]]

Embedding:
- Articles
![[Hyperlinks]]

![[Hyperlinks#See Also]]

- Images: Paste image from clipboard or use ! in front of internal link:
 ![[Pasted image 8.png]]
- Audio:
![[Untitled recording.webm]]

---
# Quotes
---

> A smart quote by some smart person

\- Mark Twain

---
# Code Blocks
---

- Fenced Code Blocks:
```js
// Supports almost any language
const obj = {};
```
- Inline Code Blocks: `inlineFunction() { }`

---
# Checkbox Lists
---

- [ ] Task 1
- [x] Task 2
- [ ] Task 3

---
# Tables
---

| Header Column 1 | Header Column 2 | Header Column 3 |
| :-------------- | :-------------: | --------------: |
| Left            |     Center      |           right |

---
# Footnotes
---

This links to a footnote [^1]

[^1]: This the footnote

---
# Math
---

Start and end with `$` or ``$$`` same as Code Blocks. 
Examples aren't valid formulas:

$$ 
\begin{vmatrix} 
a & b \\ c & d 
\end{vmatrix} = ad - bc
$$

$$
\sum \begin{vmatrix}
a & d & b\\ 
b & f & e
\end{vmatrix} = y^{\tfrac{v}{x}}
$$

See: [Online LaTeX Equation Editor](https://www.codecogs.com/latex/eqneditor.php)


## See Also
[[Obsidian Graph Formatting]]

## References
