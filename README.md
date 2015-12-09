# To get this project setup:
```sh
git clone https://github.com/skplunkerin/gulp_scss_example.git
cd gulp_scss_example/
npm install
```

To run the gulp task once:

```sh
gulp sass
```

To run it and have it re-run when changes are made to scss

```sh
gulp sass:watch
```

-------

# For (not so helpful) directions on how to get the gulpfile.js setup (from scratch)
## First

```sh
cd directory-youre-working-in/
```

## Second

http://www.codingpedia.org/ama/how-to-use-gulp-to-generate-css-from-sass-scss/

### follow steps 1.1 - 1.2.2

```sh
install nodejs
install gulp
# (you'll need to use sudo)
```

## Third
https://www.npmjs.com/package/gulp-sass

```sh
sudo npm install gulp-sass --save-dev
```

create gulpfile.js with the following content:

```javascript
'use strict';
 
var gulp = require('gulp');
var sass = require('gulp-sass');
 
gulp.task('sass', function () {
  gulp.src('./css/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});
 
gulp.task('sass:watch', function () {
  gulp.watch('./css/*.scss', ['sass']);
});
```

### Finally

To create your initial css files (as well as test if working), run

```sh
gulp sass
```

If all good, let's watch for any saves to the scss file

```sh
gulp sass:watch
```
