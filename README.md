# The largest heading
## The second largest heading
###### The smallest heading

## Bold

**This is bold text**

## Italic

*This text is italicized*	

## Strikethrough

~~This was mistaken text~~	

## Bold and nested italic

**This text is _extremely_ important**	

## All bold and italic	

***All this text is important***	

## Subscript	

<sub>This is a subscript text</sub>	

## Superscript

<sup>This is a superscript text</sup>	


## Quote

Text that is not a quote

> Text that is a quote
> Text that is a quote
> Text that is a quote


## Quoting code
Use `git status` to list all new or modified files that haven't yet been committed.


Some basic Git commands are:
```
git status
git add
git commit
```

## Links

This site was built using [GitHub Pages](https://pages.github.com/).

## Section links


[Contribution guidelines for this project](docs/CONTRIBUTING.md)

## Image

![This is an image](https://buddy.works/assets/svg/brands/buddy.svg)


## Specifying the theme an image is shown to

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/25423296/163456776-7f95b81a-f1ed-45f7-b7ab-8fa810d529fa.png">
  <source media="(prefers-color-scheme: light)" srcset="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
  <img alt="Shows an illustrated sun in light color mode and a moon with stars in dark color mode." src="https://user-images.githubusercontent.com/25423296/163456779-a8556205-d0a5-45e2-ac17-42d089e3c3f8.png">
</picture>



## List 

### Normal list

- George Washington
- John Adams
- Thomas Jefferson

### Order list

1. James Madison
2. James Monroe
3. John Quincy Adams


## Nested Lists

1. First list item
   - First nested list item
     - list item
     - list item
   - Second nested list item
     - list item
     - list item
2. Second list item
   - list item
   - list item
      - list item

## Task lists

- [x] #739
- [ ] https://github.com/octo-org/octo-repo/issues/740
- [ ] Add delight to the experience when all tasks are complete :tada:
- [ ] \(Optional) Open a followup issue

@github/support What do you think about these updates?

## emoji

@octocat :+1: This PR looks great - it's ready to merge! :shipit:

## Footnotes

Here is a simple footnote[^1].

A footnote can also have multiple lines[^2].  

You can also use words, to fit your writing style more closely[^note].

[^1]: My reference.
[^2]: Every new line should be prefixed with 2 spaces.  
  This allows you to have a footnote with multiple lines.
[^note]:
    Named footnotes will still render with numbers instead of the text but allow easier identification and linking.  
    This footnote also has been made with a different syntax using 4 spaces for new lines.
    
    
## Hiding content with comments

<!-- This content will not appear in the rendered Markdown -->


## Ignoring Markdown formatting

Let's rename \*our-new-project\* to \*our-old-project\*.


## Table

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |



## Diagrams

Here is a simple flow chart:

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```
