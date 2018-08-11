---
layout: post
title:  "Build A Blog With Github Pages and Jekyll"
date:   2018-08-11 23:30:22 +1000
categories: jekyll
author: eth4io
---

I always think maybe I should have my own dev blog to record my developing stories, new ideas or just write down some mysterious bugs.

This idea rooted in my mind for 5 years before I actually took action, well I built this site in just **30 minutes** including solve some dependency issues for Ruby.


If you have interest to try what I just did, let's do it together.


Why Github Pages + Jekyll is good
----
* **Simple** and **convenient**, your blog will be easily controlled by your git repository, that means you don't even need a management system, it just works.
* **Markdown**! Github Pages supports [kramdown](https://kramdown.gettalong.org/) as the Markdown processor.
* No database needed, no host needed.

What You Will Get
----
* A static blog like **[eth4io's Dev Blog](https://eth4io.github.io/)**
* which is powered by **[Jekill](https://jekyllrb.com/)**, a simple, blog-aware, static site generator.
* and hosted on **[Github Page](https://github.com/)**, a website hosted directly from your GitHub repository

Get Started
----
[Create a new GitHub repository](https://github.com/new) and name it as `<your-github-username>.github.io`.
mine is `eth4io.github.io`, you can check it out [here](https://github.com/eth4io/eth4io.github.io)

check your Ruby version `ruby --version`, Ryby 2.1.0 or higher is required by Jekyll.

install Bundler: `gem install bundler`


create a new directory on your local machine, name it whatever you like, 
```
mkdir my_blog
cd my_blog
```

make a Gemfile to help you install Jekyll
```
echo "source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins" > Gemfile
```

run `bundle install`

just in case you are a Mac user and have issue with a dependency called `nokogiri`, try run `brew unlink xz; bundle install; brew link xz` first before your `bundle install`.

build your local Jekyll site <br/>
`bundle exec jekyll _3.3.0_ new <your-repo-name>`, <br/>
for me, it's `bundle exec jekyll _3.3.0_ new eth4io.github.io`

push your blog to your repository and let everyone see it!
```
cd <your-repo-name>
git init
git add .
git commit -m 'Init commit for my blog'
git remote add origin git@github.com:<your-github-username>/<your-github-username>.github.io.git
git push -u origin master
```

visit <https://your-github-username.github.io> and here we go.

Test Your Site Locally
----
run `bundle exec jekyll serve` to setup a local server at port 4000.

visit <http://127.0.0.1:4000> to view it locally without actually push it to your repository.

Once you are happy with the new changes

make your new commit, push to your repository
```
git add the-file-you-changed
git commit -m 'Publish new post'
git push
```

Review
----
By this stage we've successfully created a static blog using Jekyll hosted by Github Pages.

The structure of a basic Jekyll site usually looks like

(Retrieved from <https://jekyllrb.com/docs/structure/>):
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

The first step might be edit `_config.yml` to customize your site with your own title, name, etc.

Then create a new post in `_posts` directory to test how it works.

Further reading
----
Configure your sites, <https://help.github.com/articles/configuring-jekyll/>

Find a cool theme for your site, <http://http://jekyllthemes.org/>

You can almost find all FAQs here, <https://help.github.com/categories/customizing-github-pages/>

References
----
* Official Jekyll website, <https://jekyllrb.com/>, accessed Aug 11, 2018.
* Official Github Pages website, <https://pages.github.com/>, accessed Aug 11, 2018.
* Updating your Markdown processor to kramdown, <https://help.github.com/articles/updating-your-markdown-processor-to-kramdown/>, accessed Aug 11, 2018.
* Offical Kramdown website, <https://kramdown.gettalong.org/>, accessed Aug 11, 2018.
* Setting up your GitHub Pages site locally with Jekyll, <https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/>, accessed Aug 11, 2018.
* How to install Nokogiri on Mac OS Sierra 10.12, <https://stackoverflow.com/questions/40038953/how-to-install-nokogiri-on-mac-os-sierra-10-12>, accessed Aug 11, 2018.
* Configuring Jekyll, <https://help.github.com/articles/configuring-jekyll/>, accessed Aug 11, 2018.
* Directory structure of Jekyll, <https://jekyllrb.com/docs/structure/>, accessed Aug 11, 2018.
* Jekyll Themes, <http://http://jekyllthemes.org/>, accessed Aug 11, 2018.
* Github Help, Customizing Github Pages, <https://help.github.com/categories/customizing-github-pages/>, accessed Aug 11, 2018.