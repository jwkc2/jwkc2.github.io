---
layout: post
title: "Setting up these GitHub Pages with Jekyll"
permalink: /setting-up-jekyll/
date: 2015-12-13 12:51
categories: software-engineering
---

# Introduction

Instructions to create and develop this user GitHub Pages site using Jekyll.

* Platform: MacOS 10.11.1
* IDE: Visual Studio Code
* Version Control: Git

# References

* [https://scotch.io/tutorials/getting-started-with-jekyll-plus-a-free-bootstrap-3-starter-theme](https://scotch.io/tutorials/getting-started-with-jekyll-plus-a-free-bootstrap-3-starter-theme)
* [http://www.aymerick.com/2014/07/22/jekyll-github-pages-bower-bootstrap.html](http://www.aymerick.com/2014/07/22/jekyll-github-pages-bower-bootstrap.html)

# Setup Dev Environment - Visual Studio Code

Install Visual Studio

* [https://code.visualstudio.com](https://code.visualstudio.com)

Configure User Settings

* `"editor.wrappingColumn": 80,`
* `"editor.insertSpaces": true,`

# Setup Dev Environment - Git

Install Git

* [http://git-scm.com/downloads](http://git-scm.com/downloads)

# Create GitHub Pages project

Follow instructions at [https://pages.github.com](https://pages.github.com)

* Use the Terminal
* Create the local repo at `~/jwkc2.github.io`

# Setup Dev Environment - Jekyll

Install Homebrew

* [http://brew.sh](http://brew.sh)
* `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

Install newer Ruby

* [https://www.ruby-lang.org/en/documentation/installation/#homebrew](https://www.ruby-lang.org/en/documentation/installation/#homebrew)
* `brew install ruby`

Install RubyGems

* [https://rubygems.org/pages/download](https://rubygems.org/pages/download)
* Already installed?
`gem —version`
* Get latest
`gem update —system`

Install Bundler

* [https://help.github.com/articles/using-jekyll-with-pages/](https://help.github.com/articles/using-jekyll-with-pages/)
* `gem install bundler`

Install Jekyll

* [http://jekyllrb.com/docs/installation/](http://jekyllrb.com/docs/installation/)
* Install Xcode
* `gem install jekyll`

Install Jekyll dependencies that match GitHub (to ease deployment)

* `cd <local-repo>`
* `nano Gemfile`
* [http://jekyllrb.com/docs/github-pages/](http://jekyllrb.com/docs/github-pages/)
* `bundle install`

# Setup Project

Create Jekyll site scaffolding:

* `cd <local-repo>`
* `jekyll new .`

Create an assets folder:

* `cd <local-repo>`
* `mkdir -p assets/stash`
* `mv _posts/* asset/stash`

# Configure Jekyll Project

Edit _config.yml

* title: Simple Software Engineering
* email: jwkc2@cantab.net
* description: A place to dump some thoughts and ideas I've been developing over time.
* url: “http://jwkc2.github.io”
* Remove line containing “twitter_username: “
* github_username: jwkc2

# Workflow

* Match GitHub dependencies (do this frequently):
`bundle update`
* Build the site (current dir):
`bundle exec jekyll build`
* Write a post:
  * In _posts: `YYYY-MM-DD-Title.md`
  * Include Front Matter:
<pre>
---
title: My Post Title
---
</pre>

Preview in browser:

* Start server
`bundle exec jekyll serve`
* Browse to http://localhost:4000
* Detach the server
`bundle exec jekyll server --detach`
* Kill the process
`kill -9 <pid>`

Deploy to GitHub pages:

* `git add —all`
* `git commit`
* `git push`