# NotAlone
This is the source code for [notalone.gov](https://notalone.gov).

## How it works
NotAlone is a static HTML/CSS/JS site. The site's pages are maintained in simple [Markdown](https://help.github.com/articles/markdown-basics) files, which are compiled into HTML by [Jekyll](http://jekyllrb.com/).

The site navigation and lists of resources that appear on the `/resources` page are maintained in easy-to-read YAML files (".yml") in the `/_data` directory.

GitHub is our CMS for this project. Content editors have GitHub accounts, edit the Markdown and YAML files themselves, and preview the results on a [github.io](https://github.io) page. Pushes to the live server are, for now, handled by the development team.

The site's interactive features (the Crisis Service Locator, the Enforcement Map, and Search) are all JavaScript components, making Ajax ([CORS](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing)) calls to external data sources. Search is powered by [Beckley](https://github.com/18f/beckley). The curated list of searchable resources is in `/_data`.

### Compiling and publishing changes
We depend on a few Ruby gems:

* `gem install jekyll`
* `gem install kramdown`
* `gem install psych -- --enable-bundled-libyaml`

To keep our code updating continuously as we edit, we use `jekyll serve --watch --baseurl:""`. Markdown and YAML editing happens in the `gh-pages` branch, so the [preview page](https://18f.github.io/notalone) is automatically updated as we commit edits. The static compiled HTML is updated into the `master` branch. To generate the static files and push them to `master`, we run `rake publish`. (See the `Rakefile` in the root directory for details on how this works.)


## Contributing

Content and feature suggestions are welcome via GitHub Issues. Code contributions are welcome via pull request, although of course we cannot guarantee your changes will be included in the site.

### Public domain

This project is in the worldwide [public domain](LICENSE.md). As stated in [CONTRIBUTING](CONTRIBUTING.md):

> This project is in the public domain within the United States, and copyright and related rights in the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
>
> All contributions to this project will be relatedsed under the CC0 dedication. By submitting a pull request, you are agreeing to comply with this waiver of copyright interest.
