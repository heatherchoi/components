# Copycat

Copycat is a [Sass](http://sass-lang.com/)-based starter theme that outputs
accessible HTML5 markup. It uses a mobile-first responsive approach and
leverages [SMACSS](https://smacss.com/) to organize styles as outlined in the
[Drupal 8 CSS architecture guidelines](https://www.drupal.org/node/1887918).
This encourages a component-based approach to theming through the creation of
discrete, reusable UI elements. Copycat is heavily integrated with
[Pattern Lab](http://patternlab.io/) and the
[Component Libraries](https://www.drupal.org/project/components) module,
allowing Drupal and Pattern Lab to share the same markup.

For more information, view the
[Copycat GitHub repo](https://github.com/taoti/copycat).
To submit bug reports or feature requests, visit the
[Copycat issue queue](https://github.com/taoti/copycat/issues).

### Global Prerequisites
The following packages need to be installed on your system in order to use
Copycat.

- [npm](https://www.npmjs.com/get-npm)
- [gulp](https://gulpjs.com/docs/en/getting-started/quick-start)

In addition, in order to compile Twig files, Pattern Lab requires that PHP be available on the command line.

## Installation

1. Place the Copycat theme in your site’s theme directory. (e.g.,
themes/copycat) Read documentation on
[installing themes](https://drupal.org/getting-started/install-contrib/themes)
for more information.

2. Install the
[Component Libraries](https://www.drupal.org/project/components) module.
Since many of the Drupal templates reference twig files inside Pattern Lab using
Twig namespaces, this module is required for the theme to function.

3. Enable the Copycat Helpers module. This module comes packaged with the theme,
but must be manually enabled for the theme to function.

4. Optional: Install the
[Twig Field Value](https://www.drupal.org/project/twig_field_value) module.
This is not required, but will make working with Twig templates easier.

5. Optional: Install the
[Twig Tweak](https://www.drupal.org/project/twig_tweak) module.
This is not required, but will make working with Twig templates easier.

6. Optional: Because Copycat is a starter theme, you may want to rename the
Copycat directory or copy its contents to a new custom theme directory based on
the name of your project.

The easiest way to accomplish this is to use
[Drush](https://github.com/drush-ops/drush).
Type `drush copycat --help` for more information.

If you can’t use Drush, then manually replace all instances of 'copycat'
within this directory with a machine-readable name of your choice, including
folder names, filenames, and all occurrences within files. This custom name must
start with a letter and may only contain lowercase letters, numbers, and
underscores.

Edit the .info.yml file and update the theme name and description. You can also
change the screenshot image (images/screenshot.png) shown on the Appearance
admin page.


## Configuration

Copycat includes several theme-specific settings for managing classes output by
Drupal, which you can change at admin/appearance/settings/copycat.


### Compiling Pattern Lab and Sass

[LibSass](http://sass-lang.com/libsass) is required to compile the Sass into
CSS. Copycat includes Gulp tasks to compile the CSS and generate the compiled
Pattern Lab files and to watch both for changes. To use these tasks, first run
the following NPM command in the theme folder.

```
npm install
```

To initiate the Gulp build tasks that compile the Sass and Pattern Lab files and watch for changes, run the following command in the theme directory:

```
gulp
```

To initiate the Gulp build tasks only (without watching for changes), run the following command in the theme directory:

```
gulp copycatBuild
```

### Creating New Components

Copycat includes a script to generate new component files. To use, run the
following command in the theme folder.

```
node component
```

### Build Artifacts

By default, the compiled Pattern Lab and Sass files (e.g., /pattern-lab/
and /css/) are ignored by Git as these files are built during deployment.
To change this, edit the included .gitignore file.

### Sass/Gulp dependencies

* [Breakpoint](http://breakpoint-sass.com): Easy to write media queries.

* [Sass](http://sass-lang.com): CSS on steroids. Adds nested rules, variables,
mixins, selector inheritance, and more.

* [Sass Globbing](https://github.com/mikevercoelen/gulp-sass-glob): Adds
glob-based imports to Sass.

* [Autoprefixer](https://github.com/postcss/autoprefixer): Adds necessary
browser CSS property prefixes during Sass compilation.
