# Ghali

Ghali is a free responsive multi-language theme for Ghost. It is based on one of the most popular fashion templates for Wordpress: Cali. It supports all the latest features of Ghost v3, including members and language files. It comes with a carousel, amazing typography and membership pages. Search and Disqus comments are ready to go and easily configured. Bootstrap and strict coding hygiene make customizations a breeze. Head over to the [releases](https://github.com/TerriGhost/Ghali/releases) page for the latest version.

[View DEMO](https://terrighost.github.io/ghali)

&nbsp;

![screenshot-desktop](https://raw.githubusercontent.com/terrighost/ghali/main/assets/screenshot-desktop.png)

&nbsp;


# First time using a Ghost theme?

Ghost uses a simple templating language called [Handlebars](http://handlebarsjs.com/) for its themes.

This theme has lots of code comments to help explain what's going on just by reading the code. Once you feel comfortable with how everything works, we also have full [theme API documentation](https://ghost.org/docs/api/handlebars-themes/) which explains every possible Handlebars helper and template.

**The main files are:**

- `default.hbs` - The parent template file, which includes your global header/footer
- `index.hbs` - The main template to generate a list of posts, usually the home page
- `post.hbs` - The template used to render individual posts
- `page.hbs` - Used for individual pages
- `tag.hbs` - Used for tag archives, eg. "all posts tagged with `news`"
- `author.hbs` - Used for author archives, eg. "all posts written by Jamie"
- `error.hbs` & `error-404.hbs` - Used for displaying theme errors

**Additional theme files are:**

- `screen.css` - All theme styles in one file
- `locales\en.json` - English language file
- `members\account.hbs` - Dedicated page for displaying member account information
- `members\signup.hbs` - **Great place for adding your sales pitch**
- `partials\` - Folder containing frequently used theme parts, including:
  - `comments.hbs` - Template file for the Disqus Comments
  - `header-background.hbs` - Responsive template, greatly improving loading times
  - `membership-plans.hbs` - Contains the description of the Free, Monthly and Annual plans
  - `navigation.hbs` - Overwrites the default Ghost navigation
  - `post-card.hbs` - Template for displaying a brief summary of a post
  - `post-carousel-card.hbs` - Used for individual carousel card
  - `site-header.hbs` - Basic template for the theme header
  - `site-nav.hbs` - The template for all elements of the navigation bar: social links, navigation, search and account menu
  - `subscribe-form.hbs` - Form for member sign up. **Insert your sales pitch**

# Installation

1. In the Ghost backend go to `Settings > Design` and click on `Upload a theme` under `Installed Themes`. Upload the latest Ghali release zip-file and click on `activate`.
2. Complete the setup by following these steps:
  * The picture in the "About" section on the homepage is set under `Settings > General`, in the `Publication Identity` section you can set the `Publication logo`
  * Create `API keys` for the search function.
    * Go to `Settings > Integrations`, head to the `Custom Integrations` section and click on `+ Add custom integration`
    * Choose a name, f.e. "Search", and click on `Create`
    * Copy the `Content API Key` and `API URL` in to the corresponding configuration fields below
  * Configure the theme by copying the following code in `Settings > Code Injection` in the `Site Header` area

```js
<script>
  // Configuration for Ghali theme
  var themeConfig = {
    // Your search API key
    searchKey: '11111a11aa111111a1a1a1111a',

    // Your API URL
    searchURL: 'http://localhost:2368',

    // Placeholder text for the search input field
    searchHint: 'Search...',

    // Your Disqus username (leave blank for no comments)
    disqusUsername: '',

    // Show "Powered by Ghost | Theme Ghali" in the footer
    showPoweredBy: true,
  };
</script>
```

  * Set the accent color of Portal to `#ee4073`
    * Go to `Settings > Labs` and click on `Members`
    * Click on the `Customize` button in the `Portal Settings` section
    * Set the `Accent Color` under `Look & Feel` to `ee4073`
  * Configure the routing to the custom member pages
    * Go to `Setting > Labs`
    * Click on the `Upload routes YAML` button in the `Beta Features` section
    * Upload the `routes.yaml` file from this repository

# Development

The stylesheets are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and [Gulp](https://gulpjs.com) installed globally. After that, from the theme's root directory:

```bash
# install dependencies
yarn install

# run development server
yarn dev
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
# create .zip file
yarn zip
```

# PostCSS Features Used

- Autoprefixer - Don't worry about writing browser prefixes of any kind, it's all done automatically with support for the latest 2 major versions of every browser.
- [Color Mod](https://github.com/jonathantneal/postcss-color-mod-function)

# Change log

* v1.0.0 Initial release

# Wish list

- Dark mode
- Additional sales options, such as pop-ups, banners, in-article call to action, etc
- Table of Content
- Sample content
- Additional membership plan table designs
- Additional post filter
- Extended article preview for non-paying members
- Dynamic reading time indicator

# License

Ghali is distributed under the terms of the [GNU GPL v3](LICENSE)

# Credits

* Cali https://demo.athemes.com/cali/ , (C) aThemes, [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html)
* Bootstrap http://getbootstrap.com/ , (C) 2011-2018 Twitter, Inc, [MIT](http://opensource.org/licenses/MIT)
* Owl Carousel http://owlgraphic.com/owlcarousel/ ,(C) Bartosz Wojciechowski, [MIT](http://opensource.org/licenses/MIT)
* FitVids http://fitvidsjs.com/ , (C) Chris Coyier, Paravel, [WTFPL](http://www.wtfpl.net/txt/copying/)
* PrismJS https://prismjs.com/ , (C) PrismJS, [MIT](http://opensource.org/licenses/MIT)
* Search in Ghost https://github.com/gmfmi/searchinGhost , (C) gmfmi, [MIT](http://opensource.org/licenses/MIT)
* Screenshot image https://www.pexels.com/photo/photo-of-man-using-headphones-3752835/ , (C) Andrea Piacquadio, [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)
* Screenshot image https://www.pexels.com/photo/man-love-people-woman-5029658/ , (C) Andrea Piacquadio, [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)
* Screenshot image https://www.pexels.com/photo/woman-in-purple-top-and-plaid-skirt-near-car-932402/ , (C) Godisable Jacob, [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)
* Screenshot image https://pixabay.com/photos/model-woman-portrait-sexy-984246/ , (C) Free-Photos, [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)
* Screenshot image https://www.pexels.com/photo/woman-in-red-jumping-1129605/ , (C) Artem Beliaikin, [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)
* Screenshot image https://unsplash.com/photos/O_XIvDy0pcs , (C) Christiana Rivers, [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/)
