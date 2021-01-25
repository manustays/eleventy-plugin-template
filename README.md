# Eleventy Plugin Template

> A starter environment for creating plugins for Eleventy (11ty).

Fork this repo, or select "Use this template" to get started.

> Note: this repo itself is a fork of [5t3ph/eleventy-plugin-template](https://github.com/5t3ph/eleventy-plugin-template) with minor tweaks (in `.eleventy.js`) and defaults of my own.

### Using this template

This template is setup to run a single page 11ty site for testing your plugin functionality. The build files are excluded from the final plugin package via `.npmignore`.

Your plugin functionality should live in/be exported from `.eleventy.js`. You will find a sample of creating a filter plugin in this template, including setting up a default config and merging user options.

**Be sure to update the `package.json` with your own details!**

### Testing your plugin

You can test your functionality within this project's local 11ty build by running `npm start`, but you'll also want to test it _as a plugin_.

From another local 11ty project, you can set the `require()` path relatively to your plugin's project directory, and then use it just as you would for a plugin coming from a package.

Example, assuming you place all your repositories within the same parent directory:

```js
const pluginName = require("../plugin-directory");

module.exports = (eleventyConfig) => {
  eleventyConfig.addPlugin(pluginName, { optionName: 'if needed' );
};
```

Then, run the project to test the plugin's functionality.

Note that making changes in the plugin source will likely require restarting the test project.

### Resources for creating an 11ty plugin

- Bryan Robinson's ["Create a Plugin with 11ty"](https://www.youtube.com/watch?v=aO-NFFKjnnE) demonstration on "Learn With Jason"

### Publish the plugin on npm:

1. Create an [account on npm](https://www.npmjs.com/)
2. On your terminal, run `npm login` and login with your credentials created in step-1.
3. Run `npm publish` to publish your package to npm.

---

**The following is a boilerplate for your final plugin README**.

## Usage

### STEP 1 – Install the plugin:

```bash
npm install --save-dev @username/eleventy-plugin-name
```

### STEP 2 – Include it in your `.eleventy.js` config file:

```js
const pluginName = require("@username/eleventy-plugin-name");

module.exports = (eleventyConfig) => {
  eleventyConfig.addPlugin(pluginName, {
    config_options: "value"
  });
};
```

> ⚠ You’re only allowed one module.exports in your configuration file! If one already exists, copy the content of the above into your existing module.exports function.

### STEP 3 – Use it in your templates:

```njk
{% ShortCodeName "value" %}
```

## Config Options

| Option      | Type    | Default       | Description              |
| ----------- | ------- | ------------- |--------------------------|
| option name | type    | default value | What does this option do |

## Config Examples

Show examples of likely configurations.

## Credits

Add credits if needed. Huge shout-out to the [awesome 11ty community](https://twitter.com/eleven_ty)!
