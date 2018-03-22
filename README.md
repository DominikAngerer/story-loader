<p align="center">
  <h1 align="center">story-loader</h1>
  <p align="center">A <a href="https://www.storyblok.com" target="_blank">Storyblok</a> plugin to load stories as source of dropdown.</p>
</p>
<br><br>

## What is localized-story-loader-flat
If you're using a folder structure like:
```
-- home
-- locations
--- First Location
--- Second Location
```
you can now directly use this plugin to access all (for example) *locations* in a dropdown. If you're looking for a *localized* version (so we would look for `de` or `en` as root folders - look for the `localized-story-loader-flat`.

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production
npm run build
```

For more information see the [docs for field types](https://www.storyblok.com/docs/Guides/Creating-a-field-type-plugin).

## Configuration

![Story Loader configuration](http://img2.storyblok.com/300x0/f/39898/654x1028/16eef925ac/storyloader-config.jpg)

You can use the "Self" property so you won't have to add a global datasource to configure this plugin

First Datasource Entry: `token`    
Second Datasource Entry: `starts_with`
