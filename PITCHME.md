How to get simple blog up and running using
# Jekyll


---

### Content
1. Github
free and powerfull hosting
2. Jekyll
flat stack and focus on content
3. Node.js
Use node modules and expad project features
3. Gulp
enjoy smooth development workflow
5. Run and modify
how to start development

---

### 1. Github

Just create new repository and name it:
<span style="color:red">your_user_name</span>.github.io

detailed instruction from [Github](https://pages.github.com/)


---

### 2. Jekyll

You’ll need Ruby as a development enviroment
<br>
1. GNU/Linux, Unix, or macOS
2. Ruby version 2.0 or above
3. RubyGems
4. GCC and Make

+++

Install Ruby
```
brew install ruby
```

+++

Install RubyGems
Read notes from [Rubygems.org](https://rubygems.org/pages/download#formats)

+++

Install Jekyll and Bunlder trought RubyGems
```
gem install jekyll bundler
```

+++

Check that you have [GCC](https://gcc.gnu.org/install/) and [Make](https://www.gnu.org/software/make/)
```
$ gcc -v
$ make -v
```

---

###### 2.1 Jekyll

Getting started:

```

# Create a new Jekyll site at ./myblog
~ $ jekyll new myblog

# Change into your new directory
~ $ cd myblog

# Build the site on the preview server
~/myblog $ bundle exec jekyll serve

# Now browse to http://localhost:4000
```

+++

![Vanilla blog](/img/vanilla-site.png)


---

###### 2.2 What the hell happend?

Jekyll site is build - where it is?

```
bundle show minima
```


+++

Minima directory structure

```
.
├── _config.yml
├── _data
|   └── members.yml
├── _drafts
|   ├── begin-with-the-crazy-ideas.md
|   └── on-simplicity-in-technology.md
├── _includes
|   ├── footer.html
|   └── header.html
├── _layouts
|   ├── default.html
|   └── post.html
├── _posts
|   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
|   └── 2009-04-26-barcamp-boston-4-roundup.md
├── _sass
|   ├── _base.scss
|   └── _layout.scss
├── _site
├── .jekyll-metadata
└── index.html # can also be an 'index.md' with valid YAML Frontmatter
```

clone only necessary files in new destination

---

### 3. Node.js

Start using Node.js

```
$ npm init
```

it creates package.json

+++

Add some Node modules for this project

```
$ npm install --save-dev gulp
$ npm install --save-dev gulp-concat
$ npm install --save-dev gulp-sass
$ npm install --save-dev gulp-util
$ npm install --save-dev browser-sync
```

---

### 4. Gulp

Create gulpfile.js

Detailed instruction from [Aaron Lasseigne](https://aaronlasseigne.com/2016/02/03/using-gulp-with-jekyll/)

+++

```
const child = require('child_process');
const browserSync = require('browser-sync').create();

const gulp = require('gulp');
const concat = require('gulp-concat');
const gutil = require('gulp-util');
const sass = require('gulp-sass');

const siteRoot = '_site';
const cssFiles = '_css/**/*.?(s)css';

gulp.task('css', () => {
  gulp.src(cssFiles)
    .pipe(sass())
    .pipe(concat('all.css'))
    .pipe(gulp.dest('assets'));
});

gulp.task('jekyll', () => {
  const jekyll = child.spawn('jekyll', ['build',
    '--watch',
    '--incremental',
    '--drafts'
  ]);

  const jekyllLogger = (buffer) => {
    buffer.toString()
      .split(/\n/)
      .forEach((message) => gutil.log('Jekyll: ' + message));
  };

  jekyll.stdout.on('data', jekyllLogger);
  jekyll.stderr.on('data', jekyllLogger);
});

gulp.task('serve', () => {
  browserSync.init({
    files: [siteRoot + '/**'],
    port: 4000,
    server: {
      baseDir: siteRoot
    }
  });

  gulp.watch(cssFiles, ['css']);
});

gulp.task('default', ['css', 'jekyll', 'serve']);
```

---

### 5. Run project

```
gulp
```

runs Gulp default task and Jekyll as a subprocess

---
