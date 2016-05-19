
# CDD Generator v3.2.5

###(Out of date! To be revised)

## Features

A basic gulp build-kit, including our in-house scss starter template, based on the [generator-gulp-webapp](https://github.com/yeoman/generator-gulp-webapp)

Same features as [generator-gulp-webapp](https://github.com/yeoman/generator-gulp-webapp):

* CSS Autoprefixing
* BrowserSync
* [libsass](http://libsass.org)
* jslint
* Image optimization
* [Bower](http://bower.io)
* [pixrem](https://github.com/gummesson/gulp-pixrem) for automatic rem -> px fallback!

## The SASS base kit

Our in-house SASS base kit should be used as a base for all projects. It's been developed through a lot of iterations, currently structured like this:

* core - Contains a base set of partials that will be part of every project. These include the grid system, normalise, layout and helper classes/functions
* Foundation - This lays on top of core, adding project specific modifiers and config files containing project-wide variables.
* modules - This holds the projects modules. These are independent and reusable chunks of code that can be reused throughout the project and other projects.
* vendor - External libraries

For a full description on how to use this setup, check out our (Front-End Guidelines)[https://github.com/cddnation/FED-Guidelines]

---

### SASS Folder Structure

````
styles/
    |- main.scss ________________________________ # SCSS Imports for (projectName)
    |- _inbox.scss ______________________________ # Inbox (shame file)
styles\vendor/
    |- _external.scss ___________________________ # External styles
styles\modules/
    |- _module.scss _____________________________ # Example module
styles\mixins/
    |- _breakpoints.scss ________________________ # Responsive breakpoints.
    |- _typography.scss _________________________ # Typography mixins
    |- _utilities.scss __________________________ # General helper mixins
styles\foundation/
    |- _attributes.scss _________________________ # Global Attribute Modifiers
    |- _base.scss _______________________________ # Base-level tags
    |- _config.scss _____________________________ # Global Settings
    |- _fonts_.scss _____________________________ # Global Font loader
styles\core/
    |- _grid.scss _______________________________ # CSSWizandry grids
    |- _helpers.scss ____________________________ # Helpers (placeholders)
    |- _normalise.scss __________________________ # normalize.css v3.0.0 | MIT License | git.io/normalize
    |- _print.scss ______________________________ # Print media styles
````


## Getting Started

(First time only): To use this generator, run the following:

    npm install -g generator-cdd

Then, start the generator with yo: 

    yo cdd

The generator will ask you a few questions about common libraries to include. It has also got a perch setting, which alters where the bower includes gets injected in the gulp task.

If you get any errors, you might have to re-run npm install with sudo!

## Subgenerators

When writing your sass module, simply use the following subgenerator to generate a either a sass module or a js module in the appropriate /modules folder. This will be named for you, and sass partials will be injected into the loader main.scss.

    yo cdd:module


## Developing

When you start the build you need to tell gulp-pixrem the base font size, so that it can automatically generate px fallback values for <IE8. Look for the pixrem task and update to match your base font size.

Once this is done, use the following commands when developing:

- Run `gulp serve` to preview and watch for changes
- Run `bower install --save <package>` to install frontend packages using Bower
- Run `gulp` to minify and build your application into the /dist folder


### Generate Documentation:

The generator comes with frontend-md bundled.

- Run `frontend-md` to create a `FRONTEND.md` file with the folder structure and documentation from your js and scss files. Check their (github)[https://github.com/animade/frontend-md] for more information.

## License

MIT
