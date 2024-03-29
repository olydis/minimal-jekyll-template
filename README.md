---
---
# Minimal Jekyll Template that builds on [Cloudflare Pages](https://pages.cloudflare.com/)

For developers out there who like to start from scratch rather than with a fully styled special-purpose template.
May also be useful for learning Jekyll in a structured way, i.e. what's really Jekyll vs complicated configuration.

## Basics

Consider a basic static website that consists of `html`, `css`, `js` and media files like images.
They get served precisely as you wrote them (modulo your hoster compressing, injecting cookies, etc.).

Think of Jekyll as a superset of this world: Files still get served as-is, except for the following.

### Files *not* served

Anything that has a name starting with `_` won't get served.
This applies to both files (like `_config.yml`) and folders.

Files can also explicitly be ignored by listing them under field `exclude` in `_config.yml`.

### Files getting *processed*

Files starting with [YAML Front Matter](https://jekyllrb.com/docs/front-matter/) get processed.
This front matter can be empty, like on top of this very file here:
```
---
---
```

"Being processed" most notably means that one can use the [Liquid](https://shopify.github.io/liquid/basics/introduction/) templating language. `index.md` demonstrates how to refer to variables defined in `_config.yml` as well as in the front matter.

On top of that, some convenience file formats get compiled into their native counterparts, most notably:
- [`.md` files become equivalent `.html`](https://en.wikipedia.org/wiki/Markdown#Example)
- [`.scss`/`.sass` gets compiled into `.css`](https://en.wikipedia.org/wiki/Sass_(stylesheet_language)#Features).


## Magic

Setting certain variables in `_config.yml` or in front matter result in behavior beyond what one would expect from reading the above (that they are set and can be referred to with Liquid). The `exclude` field mentioned above is one such example. There is a lot of this magic behavior, so online resources are crucial. Here are notable examples.

### Layout

TODO

## Cloudflare

Deploying GitHub projects on Cloudflare is free even for private repositories and comes with [many perks](https://geekflare.com/cloudflare-advantages/). I find super fast load times around the globe and basic analytics (how many visitors and from where?) most valuable. 

Similar to [GitHub Pages](https://pages.github.com/), [Cloudflare Pages](https://pages.cloudflare.com/) will automatically build on each push. However, it also shows live logs of each build, which is useful for debugging!

### Setup
- [Register/Log in](https://pages.cloudflare.com/)
- `Create a project`
- Connect with GitHub, select project, `Begin setup`
- Under `Framework preset`, select `Jekyll`
- `Save and Deploy`
- Wait for first build to succeed
- `Continue to project`
- Done! This project here, for instance, is now published at https://minimal-jekyll-template.pages.dev/
- Set up custom domain if desired, under tab `Custom Domains` (well explained step-by-step process)
