# uni_module_template

Drupal module template for Xenyo Uni Framework.

## Quick start

### Decide module name

Decide on a name for your new module. The name must:

- Only include lowercase letters, digits and underscores.
- Begin with the namespace of the client or site, depending on the scope of the module.

### Create GitHub repository

Create a new GitHub repository based on this template. You can select this
template when creating the repository or click the *Use this template* button at
https://github.com/xenyo/uni_module_template.

Clone the new repository to the `web/modules/custom` directory of your Drupal project.

### Update name and description

Update the name and description in the following files:

- composer.json
- package.json
- README.md
- uni_module_template.info.yml

In addition, rename `uni_module_template.info.yml` and delete `hidden: true` from the file.

### Publish to Satis

Open an issue at https://github.com/xenyo/satis to request your module to be added to https://packages.xenyo.net.

Once added, you will be able to install your module using Composer.

## Default configuration

`uni_module_template.info.yml` includes default configuration for the following contrib modules:

- Asset Autoload https://www.drupal.org/project/asset_autoload
- Components! https://www.drupal.org/project/components

## Build system

The module provides a build system for compiling `*.scss` and `*.mjs`
files out of the box.

### Usage

Install dependencies:

```
npm install
```

Build once:

```
npm run build
```

Watch files for changes:

```
npm run watch
```

### Build sources

Every file ending with `.mjs` and `.scss` in the module or any subdirectory will be automatically picked up by the build system.

Files inside `node_modules` are excluded for obvious reasons.

Files with filenames that begin with an underscore are also excluded. This is mainly to allow some files to be imported instead of being built directly.

### Build outputs

Each build output will be placed next to the corresponding source file, along with the sourcemap. For example:

| Source | Output |
| --- | --- |
| example1.scss | example1.css<br>example1.map |
| example1.mjs | example1.js<br>example1.map |
| foo/bar/example2.scss | foo/bar/example2.css<br>foo/bar/example2.map |
| foo/bar/example2.mjs | foo/bar/example2.js<br>foo/bar/example2.map |

Build outputs are always optimized and minified for production. There
is no separate development build.

All build outputs should be checked in to git.

## Sass utils

`@xenyo/sass-utils` is available out of the box.

To use it, add the following to the top of any sass file:

```scss
@use 'sass-utils' as *;
```

You can add custom variables and mixins to `sass-utils/_index.scss`.

See https://github.com/xenyo/sass-utils for details.
