
## Folders
### Abstracts folder
The ```abstracts/``` folder gathers all Sass tools and helpers used across the project. Every global variable, function, mixin and placeholder should be put in here.
The rule of thumb for this folder is that it should not output a single line of CSS when compiled on its own. These are nothing but Sass helpers.

### Base folder
The ```base/``` folder holds what we might call the boilerplate code for the project. In there, you might find the reset file, some typographic rules, and probably a stylesheet defining some standard styles for commonly used HTML elements

- _base.scss
- _reset.scss
- _typography.scss


###  Layout folder
The ```layout/``` folder contains everything that takes part in laying out the site or application. This folder could have stylesheets for the main parts of the site (header, footer, navigation, sidebar…), the grid system or even CSS styles for all the forms.

- _grid.scss
- _header.scss
- _footer.scss
- _sidebar.scss
- _forms.scss
- _navigation.scss

### Components folder
For smaller components, there is the ```components/``` folder. While layout/ is macro (defining the global wireframe), components/ is more focused on widgets. It contains all kind of specific modules like a slider, a loader, a widget, and basically anything along those lines. There are usually a lot of files in components/ since the whole site/application should be mostly composed of tiny modules.

- _media.scss
- _carousel.scss
- _thumbnails.scss


### Pages folder
If you have page-specific styles, it is better to put them in a ```pages/``` folder, in a file named after the page. For instance, it’s not uncommon to have very specific styles for the home page hence the need for a _home.scss file in pages/.

- _home.scss
- _contact.scss

### Themes folder
On large sites and applications, it is not unusual to have different themes. There are certainly different ways of dealing with themes but I personally like having them all in a ```themes/``` folder.

- _theme.scss
- _admin.scss

### Vendors folder
And last but not least, most projects will have a vendors/ folder containing all the CSS files from external libraries and frameworks – Normalize, Bootstrap, jQueryUI, FancyCarouselSliderjQueryPowered, and so on. Putting those aside in the same folder is a good way to say “Hey, this is not from me, not my code, not my responsibility”.

- _normalize.scss
- _bootstrap.scss
- _jquery-ui.scss
- _select2.scss

### Vendors-extensions folder
If you have to override a section of any vendor, there should be a 8th folder called ```vendors-extensions/``` in which you may have files named exactly after the vendors they overwrite.
For instance, ```vendors-extensions/_bootstrap.scss``` is a file containing all CSS rules intended to re-declare some of Bootstrap’s default CSS. This is to avoid editing the vendor files themselves, which is generally not a good idea.

### Shame folder
There is an interesting concept that has been made popular by Harry Roberts, Dave Rupert and Chris Coyier that consists of putting all the CSS declarations, hacks and things we are not proud of in a shame file. This file, dramatically titled ```_shame.scss```, would be imported after any other file, at the very end of the stylesheet.

## Main file
The main file (usually labelled main.scss) should be the only Sass file from the whole code base not to begin with an underscore. This file should not contain anything but @import and comments.

Files should be imported according to the folder they live in, one after the other in the following order:
- abstracts/
- vendors/
- vendors-extensions
- base/
- layout/
- components/
- pages/
- themes/
- shame/

