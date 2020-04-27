# connectedhealthcities
CHC Final Report website

Site is viewabile at https://connectedhealthcities.github.io

## Overview of site

Site is built using Github Pages, which uses [Jekyll] `3.8.5`

To edit content, it's really useful to understand:
    
- [Markdown] (Site is configured to use [Kramdown parser][Kramdown])
- [Yaml 1.1][Yaml]
- Jekyll's [Front Matter][Front-Matter] and [Assets][Jekyll Assets]

[Jekyll]: https://jekyllrb.com/
[Markdown]: https://www.markdownguide.org/
[Kramdown]: https://kramdown.gettalong.org
[Yaml]: https://yaml.org/spec/1.1/
[Front-Matter]: https://jekyllrb.com/docs/front-matter/
[Jekyll Assets]: [https://jekyllrb.com/docs/assets/]

**Do not use level one headings in the body** - the templates generate these from the page title. For inpage headings use level two headings (eg `## A Header`).

### _config.yml

non-default parts are:

- `header_pages` - list of paths to pages in to include in header menu
- `footer` - array parts that go in the very bottom of the footer
    - type: `page` or `text`
    - value: path to `page` or `text` to show
    - weight: ordering (lower is first)

### Global front-matter:

| name  | description |
|---    |---          |
| title | page title  |

see also [Jekyll SEO Tag]

[Jekyll SEO Tag]: https://jekyll.github.io/jekyll-seo-tag/


### Homepage - (index.md)

Has the following subsections:
    
| description                     | location                               | 
|---------------------------------|----------------------------------------| 
| Turquoise box, left hand side   | _page-sections/homepage/intro_left.md  |
| Turquoise box, right hand side  | _page-sections/homepage/intro_right.md |
| Main body, right hand side      | _page-sections/homepage/sidebar.md     |

### Section Heading - (/*.md, e.g. hub.md)

front-matter:

| name                   | description                                                  |
|---                     |---                                                           |
| title                  | page title                                                   |
| intro                  | `Markdown` of text in turqoise box                           |
| sidebar_image          | path to image in right hand side *(optional)*                |
| sidebar_image_caption  | Image description *required if sidebar_image is specified*   |
| section                | the `slug` of the section (used to identify sub-pages)       |

### Default page

front-matter:

| name                   | description                                                  |
|---                     |---                                                           |
| title                  | page title                                                   |
| intro                  | `Markdown` of text in turqoise box                           |
| section                | the `slug` of the section (used to identify sub-pages)       |
| parent                 | the parent page's `section`                                  |
| resources              | array of { `path` or `url`, and `title` } of any linked resources **optional** <br>eg:<br>`  path: /assets/hub/information-governance-final-report.pdf`<br>`title: Information Governance Final Report`<br><br>or<br>`  url: https://twitter.com/jack/status/20`<br>`title: Information Governance Final Report`|
| weight                 | value to determine order of pages in menus (lower weight comes first) |

### Footer

The contents of the footer are in `_page_sections/footer_left.md` and `_page_sections/footer_right.md`
