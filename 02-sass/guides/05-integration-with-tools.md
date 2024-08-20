# Sass와 다른 도구의 통합

Sass를 다른 빌드 도구(Gulp, Webpack, Grunt 등)와 통합하는 방법을 다룹니다. 이 문서에서는 Gulp를 사용한 Sass 컴파일 자동화, Webpack에서 Sass 로더 설정, Grunt를 사용한 Sass 작업 관리 등을 설명합니다.

## 1. Gulp를 사용한 Sass 컴파일 자동화

### 1.1. Gulp 설치
Gulp는 Sass 파일을 자동으로 컴파일하는 데 매우 유용한 도구입니다. 먼저 Gulp를 설치합니다.

```
npm install --save-dev gulp
npm install --save-dev gulp-sass
```

### 1.2. Gulp 설정
`gulpfile.js` 파일을 생성하고, Sass 파일을 컴파일하는 작업을 설정합니다.

```
const gulp = require('gulp');
const sass = require('gulp-sass')(require('sass'));

gulp.task('sass', function() {
  return gulp.src('src/sass/**/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('dist/css'));
});

gulp.task('watch', function() {
  gulp.watch('src/sass/**/*.scss', gulp.series('sass'));
});

gulp.task('default', gulp.series('sass', 'watch'));
```

### 1.3. Gulp 사용
이제 `gulp` 명령어를 실행하여 Sass 파일을 자동으로 컴파일할 수 있습니다.

```
gulp
```

## 2. Webpack에서 Sass 로더 설정

### 2.1. Webpack 설치
Webpack은 모듈 번들러로, Sass 파일을 로드하고 번들링하는 데 사용됩니다.

```
npm install --save-dev webpack webpack-cli style-loader css-loader sass-loader
```

### 2.2. Webpack 설정
`webpack.config.js` 파일을 생성하고, Sass 로더를 설정합니다.

```
module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: __dirname + '/dist'
  },
  module: {
    rules: [
      {
        test: /\.scss$/,
        use: ['style-loader', 'css-loader', 'sass-loader']
      }
    ]
  }
};
```

### 2.3. Webpack 사용
이제 `webpack` 명령어를 실행하여 Sass 파일을 번들링할 수 있습니다.

```
webpack --mode development
```

## 3. Grunt를 사용한 Sass 작업 관리

### 3.1. Grunt 설치
Grunt는 자동화된 작업을 수행하는 도구로, Sass 파일을 관리하는 데 사용됩니다.

```
npm install --save-dev grunt grunt-sass
```

### 3.2. Grunt 설정
`Gruntfile.js` 파일을 생성하고, Sass 작업을 설정합니다.

```
module.exports = function(grunt) {
  grunt.initConfig({
    sass: {
      dist: {
        files: {
          'dist/css/main.css': 'src/sass/main.scss'
        }
      }
    },
    watch: {
      css: {
        files: 'src/sass/**/*.scss',
        tasks: ['sass']
      }
    }
  });

  grunt.loadNpmTasks('grunt-sass');
  grunt.loadNpmTasks('grunt-contrib-watch');

  grunt.registerTask('default', ['sass', 'watch']);
};
```

### 3.3. Grunt 사용
이제 `grunt` 명령어를 실행하여 Sass 파일을 자동으로 컴파일하고, 변경사항을 감시할 수 있습니다.

```
grunt
```

## 4. 결론

Sass는 Gulp, Webpack, Grunt와 같은 도구와 통합하여 더욱 강력하게 사용할 수 있습니다. 이 문서에서 설명한 통합 방법을 활용하여, 프로젝트의 효율성을 극대화하고, 개발 워크플로우를 자동화하세요.
