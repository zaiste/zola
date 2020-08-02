+++
title = "Configuration"
weight = 40
+++

The default configuration is sufficient to get Zola running locally but not more than that.
It follows the philosophy of paying for only what you need; almost everything is turned off by default.

To change the configuration, edit the `config.toml` file.
If you are not familiar with TOML, have a look at [the TOML spec](https://github.com/toml-lang/toml).

Only the `base_url` variable is mandatory; everything else is optional. All configuration variables
used by Zola as well as their default values are listed below:


```toml
# The base URL of the site; the only required configuration variable.
base_url = "mywebsite.com"

# The site title and description; used in feeds by default.
title = ""
description = ""

# The default language; used in feeds.
default_language = "en"

# The site theme to use.
theme = ""

# When set to "true", all code blocks are highlighted.
highlight_code = false

# The theme to use for code highlighting.
# See below for list of allowed values.
highlight_theme = "base16-ocean-dark"

# When set to "true", a feed is automatically generated.
generate_feed = false

# The filename to use for the feed. Used as the template filename, too.
# Defaults to "atom.xml", which has a builtin template that renders an Atom 1.0 feed.
# There is also a builtin template "rss.xml" that renders an RSS 2.0 feed.
# feed_filename = "atom.xml"

# The number of articles to include in the feed. All items are included if
# this limit is not set (the default).
# feed_limit = 20

# When set to "true", files in the `static` directory are hard-linked. Useful for large
# static files. Note that for this to work, both `static` and the
# output directory need to be on the same filesystem. Note that the theme's `static`
# files are always copied, regardles of this setting.
# hard_link_static = false

# The taxonomies to be rendered for the site and their configuration.
# Example:
#     taxonomies = [
#       {name = "tags", feed = true}, # each tag will have its own feed
#       {name = "tags", lang = "fr"}, # you can have taxonomies with the same name in multiple languages
#       {name = "categories", paginate_by = 5},  # 5 items per page for a term
#       {name = "authors"}, # Basic definition: no feed or pagination
#     ]
#
taxonomies = []

# The additional languages for the site.
# Example:
#     languages = [
#       {code = "fr", feed = true}, # there will be a feed for French content
#       {code = "fr", search = true}, # there will be a Search Index for French content
#       {code = "it"}, # there won't be a feed for Italian content
#     ]
#
languages = []

# When set to "true", the Sass files in the `sass` directory are compiled.
compile_sass = false

# When set to "true", a search index is built from the pages and section
# content for `default_language`.
build_search_index = false

# A list of glob patterns specifying asset files to ignore when the content
# directory is processed. Defaults to none, which means that all asset files are
# copied over to the `public` directory.
# Example:
#     ignored_content = ["*.{graphml,xlsx}", "temp.*"]
ignored_content = []

# A list of directories used to search for additional `.sublime-syntax` files.
extra_syntaxes = []

# Optional translation object. The key if present should be a language code.
# Example:
#     default_language = "fr"
#
#     [translations]
#     [translations.fr]
#     title = "Un titre"
#
#     [translations.en]
#     title = "A title"


# Configuration of the link checker.
[link_checker]
# Skip link checking for external URLs that start with these prefixes
skip_prefixes = [
    "http://[2001:db8::]/",
]

# Skip anchor checking for external URLs that start with these prefixes
skip_anchor_prefixes = [
    "https://caniuse.com/",
]

# Various slugification strategies, see below for details
# Defauls to everything being a slug
[slugify]
paths = "on"
taxonomies = "on"
anchors = "on"

# Optional translation object. Keys should be language codes.
[translations]

# You can put any kind of data here. The data
# will be accessible in all templates.
[extra]
```

## Syntax highlighting

Zola currently has the following highlight themes available:

- [1337](https://tmtheme-editor.herokuapp.com/#!/editor/theme/1337)
- [agola-dark](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Agola%20Dark)
- [ascetic-white](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Ascetic%20White)
- [axar](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Axar)
- [ayu-dark](https://github.com/dempfi/ayu)
- [ayu-light](https://github.com/dempfi/ayu)
- [ayu-mirage](https://github.com/dempfi/ayu)
- [base16-ocean-dark](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Base16%20Ocean%20Dark)
- [base16-ocean-light](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Base16%20Ocean%20Light)
- [bbedit](https://tmtheme-editor.herokuapp.com/#!/editor/theme/BBEdit)
- [boron](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Boron)
- [charcoal](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Charcoal)
- [cheerfully-light](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Cheerfully%20Light)
- [classic-modified](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Classic%20Modified)
- [demain](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Demain)
- [dimmed-fluid](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Dimmed%20Fluid)
- [dracula](https://draculatheme.com/)
- [gray-matter-dark](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Gray%20Matter%20Dark)
- [gruvbox-dark](https://github.com/morhetz/gruvbox)
- [gruvbox-light](https://github.com/morhetz/gruvbox)
- [idle](https://tmtheme-editor.herokuapp.com/#!/editor/theme/IDLE)
- [inspired-github](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Inspiredgithub)
- [ir-white](https://tmtheme-editor.herokuapp.com/#!/editor/theme/IR_White)
- [kronuz](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Kronuz)
- [material-dark](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Material%20Dark)
- [material-light](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Material%20Light)
- [monokai](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Monokai)
- [nord](https://github.com/crabique/Nord-plist/tree/0d655b23d6b300e691676d9b90a68d92b267f7ec)
- [nyx-bold](https://github.com/GalAster/vscode-theme-nyx)
- [one-dark](https://github.com/andresmichel/one-dark-theme)
- [OneHalf](https://github.com/sonph/onehalf)
- [solarized-dark](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Solarized%20(dark))
- [solarized-light](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Solarized%20(light))
- [subway-madrid](https://github.com/idleberg/Subway.tmTheme)
- [subway-moscow](https://github.com/idleberg/Subway.tmTheme)
- [Tomorrow](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Tomorrow)
- [TwoDark](https://github.com/erremauro/TwoDark)
- [visual-studio-dark](https://tmtheme-editor.herokuapp.com/#!/editor/theme/Visual%20Studio%20Dark)
- [zenburn](https://github.com/colinta/zenburn)

Zola uses the Sublime Text themes, making it very easy to add more.
If you want a theme not listed above, please open an issue or a pull request on the [Zola repo](https://github.com/getzola/zola).

## Slugification strategies

By default, Zola will turn every path, taxonomies and anchors to a slug, an ASCII representation with no special characters.
You can however change that strategy for each kind of item, if you want UTF-8 characters in your URLs for example. There are 3 strategies:

- `on`: the default one, everything is turned into a slug
- `safe`: characters that cannot exist in files on Windows (`<>:"/\|?*`) or Unix (`/`) are removed, everything else stays
- `off`: nothing is changed, your site might not build on some OS and/or break various URL parsers

Since there are no filename issues with anchors, the `safe` and `off` strategies are identical in their case: the only change
is space being replaced by `_` since a space is not valid in an anchor.

Note that if you are using a strategy other than the default, you will have to manually escape whitespace and Markdown
tokens to be able to link to your pages. For example an internal link to a file named `some space.md` will need to be
written like `some%20space.md` in your Markdown files.
