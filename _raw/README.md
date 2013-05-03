# {%= pkg.name %} v{%= pkg.version %} [![{%= pkg.name %} build status](https://travis-ci.org/amsul/pickadate.js.png?branch=time-picker)](https://travis-ci.org/amsul/pickadate.js)

{%= pkg.description %}

{%
    fileSize_js_core = meta.fileSize( grunt.file.read( dirs.min.pickers + '/picker.js') )
    fileSize_js_date = meta.fileSize( grunt.file.read( dirs.min.pickers + '/picker.date.js') )
    fileSize_js_time = meta.fileSize( grunt.file.read( dirs.min.pickers + '/picker.time.js') )
    fileSize_css_default = meta.fileSize( grunt.file.read( dirs.min.themes + '/default.css') )
    fileSize_css_classic = meta.fileSize( grunt.file.read( dirs.min.themes + '/default.css') )
    fileSize_css_inline = meta.fileSize( grunt.file.read( dirs.min.themes + '/default.css') )
    fileSize_css_date = meta.fileSize( grunt.file.read( dirs.min.themes + '/picker.date.css') )
    fileSize_css_time = meta.fileSize( grunt.file.read( dirs.min.themes + '/picker.time.css') )
%}

#### To get started, check out the:

[Homepage]({%= pkg.homepage %}) - [Date picker]({%= pkg.homepage %}/date.htm) - [Time picker]({%= pkg.homepage %}/time.htm) - [API]({{%= pkg.homepage %}/api.htm)


#### To get it:

[Download v{%= pkg.version %}]({%= meta.gitrepo_url %}/archive/v{%= pkg.version.split('-')[0] %}.zip) or `git clone git://github.com/amsul/pickadate.js.git` or `bower install pickadate`




<br>
## Upgrading from v2 to v3

The v3 API is significantly different from v2 (all for the greater good!). So if you’re upgrading to v3, make sure to read the [changelog]({%= meta.gitrepo_url %}/blob/v3.0.0/CHANGELOG.md).





<br>
## Library files

The `lib` folder includes all the compiled library files as well as a `compressed` folder with the minified counter-parts.

### Pickers

There are currently two pickers: **date** and **time**.

File                    | Contents                 | Size (min & gzip)
----------------------- | ------------------------ | ----------------------
`picker.js`             | Base __*__               | {%= (fileSize_js_core.gzip/1024).toFixed(2) %}kb
`picker.date.js`        | Date picker              | {%= (fileSize_js_date.gzip/1024).toFixed(2) %}kb
`picker.time.js`        | Time picker              | {%= (fileSize_js_time.gzip/1024).toFixed(2) %}kb

__*__ The base script is **required** for any of the pickers to function.

_To support old browsers, namely IE8, **also include** the `legacy.js` file._


### Themes

All themes are [generated using Sass](#sass-styling) and compiled into the `themes` folder.

File                    | Contents                 | Size (min & gzip)
----------------------- | ------------------------ | ----------------------
`default.css`           | Base __*__               | {%= (fileSize_css_default.gzip/1024).toFixed(2) %}kb
`classic.css`           | Base __*__               | {%= (fileSize_css_classic.gzip/1024).toFixed(2) %}kb
`inline.css`            | Base __*__               | {%= (fileSize_css_inline.gzip/1024).toFixed(2) %}kb
`picker.date.css`       | Date picker              | {%= (fileSize_css_date.gzip/1024).toFixed(2) %}kb
`picker.time.css`       | Time picker              | {%= (fileSize_css_time.gzip/1024).toFixed(2) %}kb

__*__ Only one base stylesheet is **required**. Check out the [demos]({%= pkg.homepage %}/themes.htm) to choose one.

### Translations

The translations are copied into the `translations` folder. There are currently [{%= grunt.file.expand(dirs.min.translations + '/*.js').length %} languages]({%= pkg.repository.url.replace(/.git$/,'') %}/blob/v{%= pkg.version.split('-')[0] %}/lib/translations) included.


<br>
## Versioning

To maintain some consistency in the sort of changes to expect with version bumps, [Semantic Versioning guidelines](http://semver.org/) will now be followed as closely as possible:

`<major>.<minor>.<patch>`

Constructed as such:

- `major`: breaks backward compatibility (resets the `minor` and `patch`)
- `minor`: new additions with backward compatibility (resets the `patch`)
- `patch`: bug fixes and misc changes





<br>
## Bugs

Before opening a new issue, search the [Issues]({%= pkg.bugs %}) to see if anything similar already exists - there might already be an answer to your problem. You might also wanna check out the [Contributing]({%= meta.gitrepo_url %}/blob/v3.0.0/CONTRIBUTING.md) guide.





<br>
## Contributing

Before contributing any code to the project, please take a look at the [Contributing]({%= meta.gitrepo_url %}/blob/v3.0.0/CONTRIBUTING.md) guide.




<br>
## Building with Grunt

[Grunt](http://gruntjs.com/) `~{%= grunt.version %}` is used to build the project files. To get started, clone the project and then run:

- `npm install` to get the required node modules.
- `grunt --verbose` to confirm you have all the dependencies.


Read the Gruntfile to see the build tasks and relative directories of the source files.




<br>
<a name="sass-styling"></a>
## Styling with Sass

The picker themes are built using [Sass](http://sass-lang.com/) with Grunt. To customize the CSS output, read the `_variables.scss` file in the `_source/lib/themes` folder. You can specify:

- colors for the theme,
- sizes for the picker,
- media-query breakpoints,
- and a whole bunch of other stuff.


After making any changes, run `grunt sass:themes` to compile it into CSS.





<br><br>

---

© {%= grunt.template.date('yyyy') %} [Amsul](http://twitter.com/amsul_)

Licensed under [{%= pkg.licenses[0].type %}]({%= pkg.licenses[0].url %}).