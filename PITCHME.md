How to get simple blog up and running using
# Jekyll


---

### Content
1. Github
free and powerfull hosting
2. Jekyll
flat stack and focus on content
3. Gulp
enjoy smooth development workflow

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
2. Ruby version 2.0 or above, including all development headers
3. RubyGems
4. GCC and Make (in case your system doesn’t have them installed, which you can check by running gcc -v and make -v in your system’s command line interface)


Detailed instruction from [Jekyll](https://jekyllrb.com/docs/quickstart/)

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

###### 2.2 Conclusion - What the hell happend?

1. Jekyll site is installed - where it is?

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

+++

clone only nessessary files in new destination

my directory structure

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

---


---

### 3. Gulp

Implement Gulp

Detailed instruction from [Aaron Lasseigne](https://aaronlasseigne.com/2016/02/03/using-gulp-with-jekyll/)

---

### Go for it.
### Just add <span style="color: #e49436; text-transform: none">PITCHME.md</span> ;)
