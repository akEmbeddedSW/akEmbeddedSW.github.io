# Configuration

## Plugins

There are a number of plugins installed, some of which may need configuration, details are below where appropriate.

### Dark-Light Theme

[docsify Dark Light Theme Documentation](https://docsify-darklight-theme.boopathikumar.me/#/configuration?id=default-themes-configuration)

### Code Highlighting

docsify uses [Prism](https://prismjs.com) to highlight code blocks in your pages. Prism supports the following languages by default:

- Markup - `markup`, `html`, `xml`, `svg`, `mathml`, `ssml`, `atom`, `rss`
- CSS - `css`
- C-like - `clike`
- JavaScript - `javascript`, `js`

This template also adds `bash`, and `json`.

Support for [additional languages](https://prismjs.com/#supported-languages) is available by loading the language-specific [grammar files](https://cdn.jsdelivr.net/npm/prismjs@1/components/) via CDN e.g.:

```html
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-bash.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/prismjs@1/components/prism-php.min.js"></script>
```

!> This `<script>` tag should be placed at the end of index.html, with all the other languages

### Alert Boxes

Not a lot to configure here currently, you can change between `flat` or `callout` theme.  Currently recommend `callout`, as `flat` does not look good in dark mode. TODO: add some CSS to make `flat` look good in dark mode.

```html
<script>
  window.$docsify = {
    'flexible-alerts': {
      style: 'callout'
    }
  };
</script>
```

### Tabs

Options are set within the [`window.$docsify`](https://docsify.js.org/#/configuration) configuration under the `tabs` key:

```html
<script>
  window.$docsify = {
    // ...
    tabs: {
      persist    : true,      // default
      sync       : true,      // default
      theme      : 'classic', // default
      tabComments: true,      // default
      tabHeadings: true       // default
    }
  };
</script>
```

- persist: Determines if tab selections will be restored after a page refresh/revisit.
- sync: Determines if tab selections will be synced across tabs with matching labels.
- theme: Sets the tab theme. A value of false will indicate that no theme should be applied, which should be used when creating custom tab themes.  Accepts: `'classic'`, `'material'`, `false`.
- tabComments: Determines if tabs within a tab set can be defined using HTML comments.  This is set to false in the template as tabComments will not render in Stash/Bitbucket, whereas headers will render just without the tabs.
- tabHeadings: Determines if tabs within a tab set can be defined using heading + bold Markdown.

[docsify Tabs documentation](https://jhildenbiddle.github.io/docsify-tabs/#/?id=options)

### Copy code

Adds a button to copy code to the clipboard for code blocks.

Button text can be customized as follows:

```html
<script>
  window.$docsify = {
    // docsify-copy-code (defaults)
    copyCode: {
        buttonText : 'Copy to clipboard',
        errorText  : 'Error',
        successText: 'Copied'
    }
  }
</script>
```

[docsify Copy Code documentation](https://github.com/jperasmus/docsify-copy-code)

### Pagination

Probably nothing to be changed here.

```html
<script>
  window.$docsify = {
    pagination: {
        previousText: 'PREVIOUS',
        nextText: 'NEXT'
        crossChapter: true,
        crossChapterText: true,
    },
  }
</script>
```

- previousText: The text of the previous label.
- nextText: the text of the next label.
- crossChapter: allow pagination to jump from chapter to chapter
- crossChapterText: display the chapter name

[docsify Pagination documentation](https://github.com/imyelo/docsify-pagination)

### Search

Just works, can be configured for with this documentation.

[Full Text Search documentation](https://docsify.js.org/#/plugins?id=full-text-search)

### Zoom Image

Nothing to configure.

### Bitbucket/Stash

Not a lot to configure, basically all this is doing is putting the BitBucket logo in the corner rather than the GitHub logo.

[docsify BitBucket Documentation](https://docsify-bitbucket.github.io/#/)

### Mermaid

You can optionally customize [mermaid.run](https://mermaid.js.org/config/usage.html#using-mermaid-run) configuration with this props :

```html
<script>
  window.$docsify = {
    mermaidConfig: {
    querySelector: ".mermaid"
    }
  };
</script>
```

### Linter

Our preferred config for `davidanson.vscode-markdownlint` VSCode extension is explained below, and the documentation is  
available on [GitHub](https://github.com/DavidAnson/markdownlint/blob/main/doc/Rules.md).  The configuration is included in the `.markdownlink.jsonc` file included in the template.

#### Rules & Settings

- **MD001** *heading-increment/header-increment* - Heading levels should only increment by one level at a time
- **MD003** *heading-style/header-style* - Heading style should be opening # only
- **MD004** *ul-style* - Unordered list's are defined by dashes
- **MD005** *list-indent* - Inconsistent indentation for list items at the same level
- **MD007** *ul-indent* - Unordered list are not indented for the first level, subsequent levels are indented by two spaces
- **MD009** *no-trailing-spaces* - No trailing spaces, except 2 trailing spaces to force a new line
- **MD010** *no-hard-tabs* - No hard tabs, **including in code blocks**
- **MD011** *no-reversed-links* - Reversed link syntax
- **MD012** *no-multiple-blanks* - No multiple consecutive blank lines
- **MD013** *line-length* - Line length limit is disables
- **MD014** *commands-show-output* - No dollar signs used before commands without showing output
- **MD018** *no-missing-space-atx* - No space after hash on atx style heading
- **MD019** *no-multiple-space-atx* - Multiple spaces after hash on atx style heading
- **MD022** *blanks-around-headings/blanks-around-headers* - Headings should be surrounded by blank lines
- **MD023** *heading-start-left/header-start-left* - Headings must start at the beginning of the line
- **MD024** *no-duplicate-heading/no-duplicate-header* - Headings must be unique
- **MD025** *single-title/single-h1* - Only one H1
- **MD026** *no-trailing-punctuation* - No trailing punctuation in headings except ?
- **MD027** *no-multiple-space-blockquote* - Only one space after blockquote symbol
- **MD028** *no-blanks-blockquote* - No back to back blockquotes or notifications
- **MD029** *ol-prefix* - Ordered list item prefix is either all 1's or ordered.
- **MD030** *list-marker-space* - One space after list markers
- **MD031** *blanks-around-fences* - Fenced code blocks should be surrounded by blank lines
- **MD032** *blanks-around-lists* - Lists should be surrounded by blank lines
- **MD033** *no-inline-html* - Inline HTML is allowed
- **MD034** *no-bare-urls* - No Bare URLs used
- **MD035** *hr-style* - Horizontal rule style must be consistent
- **MD036** *no-emphasis-as-heading/no-emphasis-as-header* - Don't use bold instead of headings
- **MD037** *no-space-in-emphasis* - No leading or trailing spaces inside emphasis markers
- **MD038** *no-space-in-code* - No leading or trailing spaces inside code span elements
- **MD039** *no-space-in-links* - No leading or trailing spaces inside link text
- **MD040** *fenced-code-language* - Fenced code blocks should have a language specified
- **MD041** *first-line-heading/first-line-h1* - First line in a file should be a top-level heading
- **MD042** *no-empty-links* - No empty links
- **MD043** *required-headings/required-headers* - Required heading structure is not enforced
- **MD044** *proper-names* - Proper names should have the correct capitalization
- **MD045** *no-alt-text* - Images should have alternate text (alt text)
- **MD046** *code-block-style* - Code block should be fenced not indented
- **MD047** *single-trailing-newline* - Files should end with a single newline character
- **MD048** *code-fence-style* - Code fences are defined with backticks
- **MD049** *emphasis-style* - Emphasis style should be using asterisks not underscores
- **MD050** *strong-style* - Strong style should be  using asterisks not underscores
- **MD051** *link-fragments* - Link fragments should be valid
- **MD052** *reference-links-images* - Reference links and images should use a label that is defined
- **MD053** *link-image-reference-definitions* - Link and image reference definitions should be needed

> [!NOTE]
> There is an exception to most of these rules for code blocks, as the languages they contain may not follow the same rules.

To enable or disable rules at a particular location within a file, add one of these markers to the appropriate place (HTML comments don't appear in the final markup):

- Capture the current rule configuration: `<!-- markdownlint-capture -->`
- Restore the captured rule configuration: `<!-- markdownlint-restore -->`
- Disable all rules: `<!-- markdownlint-disable -->`
- Disable all rules for the current line: `<!-- markdownlint-disable-line -->`
- Disable all rules for the next line: `<!-- markdownlint-disable-next-line -->`
- Disable one or more rules by name: `<!-- markdownlint-disable MD001 MD005 -->`
- Enable one or more rules by name: `<!-- markdownlint-enable MD001 MD005 -->`
- Disable one or more rules by name for the current line: `<!-- markdownlint-disable-line MD001 MD005 -->`
- Disable one or more rules by name for the next line: `<!-- markdownlint-disable-next-line MD001 MD005 -->`
