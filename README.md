## gulp-resource-release

a plugin for gulp.js to replace file's name by adding content hash

## Installation

npm install gulp-resource-release

## Usage

var gulp = require('gulp');
var assetRev = require('gulp-resource-release');

gulp.task('rev',['revCss'],function() {
    gulp.src("./src/index.html")
        .pipe(assetRev())
        .pipe(gulp.dest('./dest'));
});
 
gulp.task('revCss',function () {
    return gulp.src('./src/assets/styles/test.css')
        .pipe(assetRev())
        .pipe(gulp.dest('./dest/styles/'))
});

gulp.task('src',function(){
	gulp.watch(['./src/**/*.css'],['rev']).on('change',function (event) {
		console.log('css发生了改变....:更新版本号');
	});
});




