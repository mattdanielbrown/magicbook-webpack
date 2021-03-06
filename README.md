## Magicbook webpack

This is a plugin that wraps webpack to use with magicbook. It will:

- Run webpack for each magicbook build
- Allow you to have separate webpack configs for builds
- Automatically place output relative to build folder

## Using the plugin

First install the NPM package, either in your `package.json` file in your book repo, or by running the following.

```
npm i magicbook-webpack
```

Just add the plugin to your config.

```json
{
  "addPlugins" : ["magicbook-webpack"]
}
```

Then add a link to your configuration file with a link to your webpack configuration file:

```json
{
  "webpack" : "webpack.config.js"
}

This can be done per build, so you can use a separate webpack configuration file per output.

```json
{
  "webpack" : "webpack.config.js",
  "builds" : [
    { "webpack" : "another.config.js" }
  ]
}

Then use the output from react in your layouts.

```html
<script src="{{ webpack.main }}"></script>
```
