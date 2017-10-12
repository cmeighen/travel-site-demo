# Travel Site Demo | [Site Link](https://cmeighen.github.io/travel-site-demo/)

## Description
This demo site is the result of completing this [web developer course](https://www.udemy.com/git-a-web-developer-job-mastering-the-modern-workflow).
The site was built with a mobile-first responsive design. It also features extensive developer tool configuration to assist in improving the overall development workflow.

## Details

### Gulp
This project uses Gulp to automate a significant amount of the developer workflow.

The gulp tasks are written into individual, modular files and required into the top level gulpfile.js. 

#### CSS Injection and Script Reloading
Rather than make changes to css and reload the page, we use a combination of the file watching functionality and browser-sync packages to automatically inject the changes into our page when any .css file in our repository is saved.

The Browsersync package starts a local server for our page and allows the injection of css into the currently loaded page by piping our css into the browserSync.stream function. 

We also trigger a page reload whenever a change is made to the js scripts by watching all .js files under our scripts directory and using browserSync.reload. 

#### PostCSS

PostCSS is used in this project to allow for many improvements to the process of styling. 

postcss-import allows the import of css files, enabling a more modular css file structure. 

postcss-mixins enables the use of mixins. In this project, this is primarily used to abstract our media queries and clearfix. 

postcss-nested allows nested CSS rules, which enables the use of the BEM convention. 

postcss-simple-vars lets us establish reusable variables within our CSS, such as sitewide, often reused colors. 

The autoprefixer package is used to process our css and automatically add vendor prefixes where applicable (based on the values from caniuse.com.

#### Sprites

To reduce the number of files the client must download, we consolidate our icon images into a single sprite graphic using gulp-svg-sprite.

We also generate a _sprite.css file that breaks establishes the bounds of each image within the sprite graphic and creates css rules using those values, allowing us to attach the icons as classes within our HTML.

#### Modernizr

To provide better support for other browsers, such as in the case of not having access to the flex property, the modernizr package is used to set classes on the html container based on the properties the browser supports.

#### CSS and JS minification

The gulp-uglify and gulp-cssnano packages are used to reduce the size of the .js and .css files downloaded by the client. 


### Node.js features

#### MobileMenu
A script is created to attach a click handler to the site header's expand menu button that toggles the expanded state of the mobile menu.

#### Modal
Handlers are added for the click on the open modal buttons and for the escape key press if the modal is open to trigger a closeModal event. 

#### RevealOnScroll
The waypoints package is used to enable a reveal transition on elements in the features and testomials sections. This is done by establishing waypoints along the page that act as triggers on any elements containing the class name ".feature-item" or ".testimonial".

#### StickyHeader
We use waypoints again here to attach handlers along the page that are triggered as the page is scrolled up or down that will add and remove classes from the header's nav elements. This provides a more interactive experience and a visual indicator of what section the viewer is in. 





