# Korat
This package contains a base structure to start a front-end project.

It's called Korat because I'm a crazycat lady and a Korat cat is as small as this starterkit :)

It uses Gulp and Sass.

You can choose between 2 versions:
With sprites or with icon font management

The gulpfile tasks allow you to:

- Compress and concatenate SCSS
- Compress and concatenate JS
- Generate sourcemaps for each CSS/JS files
- Optimize images
- Create an icon font based on SVG files
- Create multiple sprites with SVG and PNG fallback
- Include HTML parts (like header/footer...)
- Add [Fabricator](http://fbrctr.github.io/) in order to create styleguide
- Reload your browser at each code update
- Check for accessibility issues
- Create a clean delivery zip of your project

## Installation
1. Install [Python 2.7](https://www.python.org/downloads/release/python-2711/)
2. Extract this package at the root of your project
3. Install Gulp globally with `npm install -g gulp` command
4. Run the `npm install` command to install all required node modules
5. Run `gulp` command.
6. Enjoy !

## Usage
You have to edit the gulpfile to change the urlSync variable (L.51) and the other paths if you need to.

### HTML
The editable HTML (your page template like home.html, contact.html) are in **site/html**  
The included HTML parts (header, footer, everything common to all pages) are in **site/inc**  
The HTML template you create have to be placed in **site/html**.  
A mix will be made with the included files and the result will be generated at the root of the project.

You can refer to **site/html/index.html** as an example

More doc here: [https://www.npmjs.com/package/gulp-file-include](https://www.npmjs.com/package/gulp-file-include)

### Icon font

1. Set a font name in gulpfile.js (search var myFont)
2. Put your SVG icons in the icon_font folder
3. Run `gulp iconfont` command. The font is generated in **site/css/font**
4. Call you font in CSS with @font-face.

More doc here: [https://www.npmjs.com/package/gulp-iconfont](https://www.npmjs.com/package/gulp-iconfont)

### Sprites
As an example, 3 different locations are available (global, mobile, home). It allows to create a sprite for mobile, one for home and one for header/footer/whatever-repeats-in-all-your-pages.

It's useful to avoid too big sprites.

1. Set locations for sprites in gulpfile (search var folder)
2. Put your SVG icons **saved in tiny 1.1** in the folder your need
3. Run `gulp sprites` command (if you're not already use `gulp` command). The sprite files are generated in **site/img** folder
4. Call you sprite as the example provided in screen.scss.

More doc :

- [https://www.npmjs.com/package/gulp-svg2png](https://www.npmjs.com/package/gulp-svg2png)
- [https://www.npmjs.com/package/imagemin-svgo](https://www.npmjs.com/package/imagemin-svgo)
- [https://www.npmjs.com/package/gulp-svg-spritesheet](https://www.npmjs.com/package/gulp-svg-spritesheet)


### Styleguide/Fabricator
If you are on Windows, you may need to install Python 2.7.

If you want to add a styleguide to your project, just use the `gulp styleguide` command.  
It will untar Fabricator in the **styleguide** folder.  
To install it, you just have to be in the styleguide folder and launch the command `npm start`  
Every time you will update CSS/JS in your project, it'll be updated in the styleguide folder (by default in **styleguide/src/assets/toolkit**).  
Follow the doc for more informations [http://fbrctr.github.io/docs/] (http://fbrctr.github.io/docs/)

### Accessibility check
Just run the `gulp axe` command. It will report all accessibility issues in your console and in the a11yResult.json file.
This file will be located in the aXeReports directory.

More doc :

- [https://www.npmjs.com/package/gulp-axe-webdriver](https://www.npmjs.com/package/gulp-axe-webdriver)

### List of modules used ###

- [https://www.npmjs.com/package/gulp-plumber](https://www.npmjs.com/package/gulp-plumber)
- [https://www.npmjs.com/package/gulp-sass](https://www.npmjs.com/package/gulp-sass)
- [https://www.npmjs.com/package/gulp-clean-css](https://www.npmjs.com/package/gulp-clean-css)
- [https://www.npmjs.com/package/gulp-shell](https://www.npmjs.com/package/gulp-shell)
- [http://www.browsersync.io/docs/gulp/](http://www.browsersync.io/docs/gulp/)
- [https://www.npmjs.com/package/gulp-uglify](https://www.npmjs.com/package/gulp-uglify)
- [https://www.npmjs.com/package/gulp-sourcemaps](https://www.npmjs.com/package/gulp-sourcemaps)
- [https://www.npmjs.com/package/gulp-imagemin](https://www.npmjs.com/package/gulp-imagemin)
- [https://www.npmjs.com/package/gulp-rename](https://www.npmjs.com/package/gulp-rename)
- [https://www.npmjs.com/package/gulp-concat](https://www.npmjs.com/package/gulp-concat)
- [https://www.npmjs.com/package/gulp-notify](https://www.npmjs.com/package/gulp-notify)
- [https://www.npmjs.com/package/gulp-cache](https://www.npmjs.com/package/gulp-cache)
- [https://www.npmjs.com/package/gulp-filter](https://www.npmjs.com/package/gulp-filter)
- [https://www.npmjs.com/package/merge-stream](https://www.npmjs.com/package/merge-stream)
- [https://www.npmjs.com/package/gulp-zip](https://www.npmjs.com/package/gulp-zip)
- [https://www.npmjs.com/package/gulp-file-include](https://www.npmjs.com/package/gulp-file-include)
- [https://www.npmjs.com/package/imagemin-svgo](https://www.npmjs.com/package/imagemin-svgo)
- [https://www.npmjs.com/package/gulp-svg2png](https://www.npmjs.com/package/gulp-svg2png)
- [https://www.npmjs.com/package/gulp-svg-spritesheet](https://www.npmjs.com/package/gulp-svg-spritesheet)
- [https://www.npmjs.com/package/gulp-iconfont](https://www.npmjs.com/package/gulp-iconfont)
- [https://www.npmjs.com/package/gulp-axe-webdriver](https://www.npmjs.com/package/gulp-axe-webdriver)

## History
First version

### 1.1.0 ###
Add package.json

### 1.1.1 ###
Modules upgrade

### 1.2.0 ###
Update npm version to use nodejs version 6.9.1
Remove rem breakpoints
Better a11y on skip links and a11y_hidden class

### 1.2.1 ###
Better a11y on main regions (tabindex)
Use gulp-sass instead of gulp-compass
Remove config.rb file-include

### Current version ###
Modules upgrade
Remove useless sourcemap file
Add accessibility check with axe-webdriver
Remove REM calculation for sprites

## Credits
Author: Mylène Chandelier
## License
Copyright © 2016 Mylène Chandelier <chandelier.mylene@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
