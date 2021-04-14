# Abtion Github Pages Theme

## Usage 

### Public

If jekyll has not been added to your repository, clone it to your computer and run:

```sh
jekyll new .
```

Set in `_config.yml`:

```yml
baseurl: '/<github-repo-name>'
remote_theme: abtion/github-pages-theme

# OPTIONAL SEO SETTINGS
plugins:
  - jekyll-seo-tag

title: <Website title>
tagline: <Small click-bait description to appear in open graphic links)>
description: <Small click-bait description to appear in open graphic links)>
email: <your@email.com>
social:
  name: <Personal/artist or Company name>
  links:
    - https://github.com/<github-username>

defaults:
  - scope:
      path: ''
    values:
      image: /<your-open-graphic-link-image>.png
```

### Local

Add a `Gemfile`:

```ruby
source "https://rubygems.org"

group :jekyll_plugins do
  gem 'github-pages'
  gem 'jekyll-seo-tag'
end

gem 'wdm', '>= 0.1.0' if Gem.win_platform?
```

Install the gems

```sh
bundle install
```

Serve the application

```sh
bundle exec jekyll serve --livereload
```

If you wish to serve the version with licensed content then use port 3000

```sh
bundle exec jekyll serve --livereload --port 3000
```

## Folder Structure Explanation

The theme is forked from [Minima](https://github.com/jekyll/minima) therefore has all the necessary files and directories to have a new Jekyll site up and running with zero-configuration.

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

## Contributing

Bug reports and pull requests are welcome ❤️

## License

Please read 👉 [LICENSE]([https://link](https://github.com/abtion/github-pages-theme/blob/master/LICENSE.txt))
