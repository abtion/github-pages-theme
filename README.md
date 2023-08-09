# Abtion Github Pages Theme

This is [inside.abtion.com](https://inside.abtion.com/) [Jekyll Theme](https://jekyllrb.com/docs/themes/). The content is managed in [the guidelines repo](https://github.com/abtion/guidelines).

## Run the theme locally

```sh
bundle install
```

Serve the application

```sh
bundle exec jekyll serve --livereload --port 3000
```

## Deploy

Changes in this repo will not autodeploy. Instead, the theme is pulled when [the guidelines](https://github.com/abtion/guidelines) get deployed. Therefore, you can either make an empty commit in that repo, or manually run the [CI](https://github.com/abtion/guidelines/actions).

## Folder Structure Explanation

The theme is forked from [Minima](https://github.com/jekyll/minima). 

### _layouts

- `default.html` - The base layout that lays the foundation for subsequent layouts. The derived layouts inject their contents into this file at the line that says `{{ content }}` and are linked to this file via [FrontMatter](https://jekyllrb.com/docs/frontmatter/) declaration `layout: default`.
- `navigation.html` - Used for the mobile view layout since there is not a sidebar.

### _includes

Refers to snippets of code that can be inserted in multiple layouts (and another include-file as well) within the same theme-gem.

### _sass

- `reset.scss` - a reset stylesheet is to reduce inconsistencies between browsers for things like default line heights, margins and font sizes of headings, and so on.
- `custom.scss` - a stylesheet that imports all the custom styles located in the sub-folder `custom`

#### custom

- `_base.scss` - global stylesheet
- `_syntax-highlighting.scss` - global style for code elements
- `_default.scss` - stylesheet target for `_layouts/default.html`
- `_navigation.scss` - stylesheet target for `_layouts/_navigation.html`

The remaining stylesheets are targeting code snippets in the `_includes` folder with a matching file name and a prefix `_`. Example: 

`_sass/custom/_header.scss` is targeting `_includes/header.html`

Note:

`_sass/custom/_search.scss` is targeting `_assets/search.html`

### assets

- `fonts/` - licensed fonts
- `images/` - header logo
- `js/` - javascript search functionality
- `main.scss` - an import of licensed fonts & custom sass styling
- `search.html` - a helper page for the search functionality for the theme, modified from https://github.com/CloudCannon/bakery-store-jekyll-template

## License

Please read 👉 [LICENSE]([https://link](https://github.com/abtion/github-pages-theme/blob/master/LICENSE.txt))
