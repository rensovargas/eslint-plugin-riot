## eslint-plugin-riot
[![Build Status][travis-image]][travis-url]
[![NPM version][npm-version-image]][npm-url]
[![Code Climate][codeclimate-image]][codeclimate-url]

An [ESLint](http://eslint.org/) plugin to extract and lint scripts from [riot](riotjs.com) tag.

Supported extensions are `.html` and `.tag`.

lints `es6` and `text/javascript` script in tag.

### Usage

Install the plugin:

```sh
npm install --save-dev @rensovargas/eslint-plugin-riot
```

Add it to your `.eslintrc`:

```json
{
  "plugins": ["riot"]
}
```

Write your riot tag file with extension `.html` or `.tag`, and wrap your script with `<script type="es6"> </script>`, for example:

```html
<postcell>
  <div>
    <span>Id: {opts.data.postId}</span>
    <span>Title: <a href="#detail/{opts.data.postId}">{opts.data.title}</a></span>
    <span>{opts.data.likes} Likes</span>
    <button onclick={likePost}>Like</button>
  </div>

  <script type="es6">
  this.likePost = () => {
    riot.control.trigger(riot.VE.LIKE_POST, opts.data.postId)
  }
  </script>
</postcell>
```
