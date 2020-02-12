# Slender Poster

[![CircleCI](https://img.shields.io/circleci/build/github/obviateio/hugo-slender-poster)](https://circleci.com/gh/obviateio/hugo-slender-poster/tree/master)
![GitHub issues](https://img.shields.io/github/issues/obviateio/hugo-slender-poster)
![GitHub stars](https://img.shields.io/github/stars/obviateio/hugo-slender-poster?style=social)

A bootstrap 4 based blog theme for [Hugo](https://gohugo.io/) static-site-generator. Forked from [hugo-theme-chunky-poster](https://github.com/puresyntax71/hugo-theme-chunky-poster). Original design was based on the [Prisma blog](https://www.prisma.io/blog/) and modified from there.

**Note:** While based originally on the Chunky Poster theme, several key pieces of functionality were modified, making this theme a not-drop-in-replacement.

# Screenshot

# Features

* Multi-author
* Image processing
* Basic i18n
* Prism
* LazyLoad
* Commento
* Image gallery
* Pagination

# Usage

```shell
cd your-hugo-side
git submodule add https://github.com/obviateio/hugo-slender-poster.git themes/hugo-slender-poster
```
or
```shell
cd your-hugo-site
git clone https://github.com/obviateio/hugo-slender-poster.git ./themes/hugo-slender-poster
```

Check out the configuration at [`exampleSite/config.toml`](exampleSite/config.toml) for configuring your Hugo site.

## Authors

The authors structure is based on this [blog post](https://www.netlify.com/blog/2018/07/24/hugo-tips-how-to-create-author-pages/).

1. Add the taxonomy ["author"](exampleSite/config.toml#L28).
2. `hugo new authors/john-doe/_index.md`
3. Configure the author metadata `twitter`.
4. Configure the author metadata `images`. First image on the list will be used as the avatar and on the profile page. Images are page resources under the author e.g. `content/authors/john-doe/image.png`.
5. Assign the author to a content:

    ```yaml
    ---
    authors: ["John Doe"]
    ---
    ```

## Featured images

The images structure is inspired by this [blog post](https://forestry.io/blog/how-to-use-hugo-s-image-processing-with-forestry/).

**Step 1** - Create file `content/images/index.md` with the [front matter](https://gohugo.io/content-management/front-matter/):
```yaml
---
headless: true
---
```

**Step 2** - Add the image (ex: `your-image.png`) to be used as featured image, to `content/images` (ex: `content/images/your-image.png`)


**Step 3** - Add the `featured_image` property to your post front matter:

```yaml
---
featured_image: "your-image.png"
---
```

## Prism

Configure [Prism](https://prismjs.com/) under `[params.prismJS]` and set `enable` to `true`. Change the theme under `theme`.

```toml
[params]
  [params.prismJS]
    enable = true
    theme = "okaidia"
```

## Commento

Configure [Commento](https://commento.io/) under `[params.commento]`. Set `enable` to `true` and add the URL at `url`:

```toml
[params]
  [params.commento]
    enable = true
    theme = "https://somename.commento.io"
```

## Share

Enable sharing under `params` with `share` set to `true` and disable per-post sharing by setting `share` to `false` in the front matter.

```toml
[params]
  share = true
```

```yaml
---
share: false
---
```

## Image gallery

The image gallery feature uses the [`ekko-lightbox`](https://github.com/ashleydw/lightbox/) and `figure` shortcode. This is just a simple implementation of the lightbox gallery feature from the library.

# Customization

Fork the project and run `yarn watch` during development.

The application javascript file is located at `src/js/app.js`.

For customizing SCSS, the main entrypoint is at `src/scss/style.scss`. Bootstrap variables can be overridden in the `_variables.scss` file. The theme's styles are located at `src/scss/slender-poster.scss`.

# Credits / Inspirations

* [Chunky Poster](https://github.com/puresyntax71/hugo-theme-chunky-poster)
* [Ezhil](https://github.com/vividvilla/ezhil)
* [Victor Hugo](https://github.com/netlify-templates/victor-hugo)
* [hugo-theme-even](https://github.com/olOwOlo/hugo-theme-even)
* [Blank](https://github.com/vimux/blank/)
* [CleanWhite](https://github.com/zhaohuabing/hugo-theme-cleanwhite)

Images from [Unsplash](https://unsplash.com/) and [Freepik](https://www.freepik.com/).

# License

This theme is released under the [MIT license](LICENSE).
