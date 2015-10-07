Some Angular Project
====================

> A single page application built using [NPM](https://npmjs.com), [Gulp](http://gulpjs.com), [Bower](http://bower.io), [Angular](http://angularjs.org), and [Less](http://lesscss.org).

Browser Support
---------------

| Operating System | Browsers                                                |
|:-----------------|:--------------------------------------------------------|
| Windows 7        | IE 9, Firefox, Chrome                                   |
| Windows 8        | IE10, Firefox (latest version), Chrome (latest version) |
| Windows 8.1      | IE 11                                                   |
| Mac OS X 10.10+  | Safari, Chrome                                          |
| iOS7             | iPhone Safari, iPad Safari                              |
| iOS8             | iPhone Safari, iPad Safari                              |

Getting Started with Development
--------------------------------

1.	Install [NPM](https://npmjs.com), [Gulp](http://gulpjs.com), and [Bower](http://bower.io).
2.	Run `npm i` & `bower install` in the project directory to grab project dependencies.
3.	Run `gulp` to build the project to the `web` directory.
4.	Alternatively, run `gulp serve` to build, serve the project, and watch for changes using [Browsersync](http://browsersync.io)

Code Style
----------

-	Use LF, not CRLF, for all line endings in all non-binary files.
-	Use spaces, not tabs.
-	Use 4 spaces, not two.
-	Use no more than one blank line in a row.

### JS

-	Follow [John Papa's Angular Styleguide](https://github.com/johnpapa/angular-styleguide/)
-	Use single quotes.
-	Declare all variables at the top of your functions to play nice with JavaScript hoisting and scoping.
-	End all appropriate JavaScript lines with semi-colons.
-	Define all functions as a function expressions, and name them as often as possible. i.e. var functionName = function functionName() {};
-	Always use triple equality.
-	Always use brackets to surround code blocks (Ifs, fors, whiles, etc..) and always start the code block on it's own line (even if it's short).

### CSS

-	Use double quotes.
-	Avoid contextual selectors.
-	Avoid IDs in selectors.
-	Use `-` only to indicate a sub-component, namespace, or state
-	Use `_` only to indicate a component modifier (alternate, optional behavior).
-	Use camelCase for component, modifier, and utility class names

### Breakpoints

Suffix any class meant to target a particular breakpoint as such: `<className>[@xs|@sm|@lg|@xl]` (eg. `u-vr@sm` for vertical rhythm on the small breakpoint). Note the `@` must be escaped as `\@` in css definitions).

#### Utilities

Utility classes can be applied directly to an element within a component.

Syntax: `u-<utilityName>[@xs|@sm|@lg|@xl]` (eg. `u-vr@sm` for vertical rhythm on the small breakpoint)

Keep utility classes with similar concerns in the same `.less` file. Be cautious changing utility classes; they represent global behavior.

#### Components

Each `.less` file should contain a single CSS component, named in camelCase. Sub components may be included in the same file, prefixed with the root component name.

```
.media {
    /* ... */
}

.media-obj {
    /* ... */
}

.media-bd {
    /* ... */
}
```

```
<div class="media">
    <img class="media-obj" />
    <div class="media-bd"> &hellip; </div>
</div>
```

*Note that if you have a sub-components nested 3 or more layers deep, it may be time to consider a refactor to break that up into multiple components*

#### Component modifiers

Components may have modifiers to change their behavior. Modifiers should be included in html in addition to the base component class.

```
<!-- media object with image positioned on the right -->
<div class="media media_r">
    <img class="media-obj" />
    <div class="media-bd"> &hellip; </div>
</div>
```

Project Structure
-----------------

```
/raml                           *raml api documentation for reference*
/src                            *unbuilt src files*
    /assets
        /fonts                  *web font assets*
        /icons                  *SVG assets for icon CSS component*
        /less                   *CSS partials*
            /base               *variables, resets, webfonts, and global mixins*
            /core               *atomic CSS components with little to no sub-components*
            /layout             *CSS components which control layout and placement of elements*
            /landmarks          *Singleton UI components not intended for reuse*
            /utils              *utility CSS styles*
    /scripts                    *Angular module folders; sub-folder organization is by feature*
```
