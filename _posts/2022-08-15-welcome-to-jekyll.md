---
layout: post
title: 'Jekyll Tips and Tricks'
descripton: 'This blog is built with Jekyll; here are some insights into how the content is built.'
date: 2022-08-15 21:02:56 -0500
author: maker
#image: assets/images/fikry-anshor-X2bDNWh7gMU-unsplash750.jpg
image: 'https://images.unsplash.com/photo-1619793292381-25d2f7315532?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=750&q=80'
categories: [tech]
#tags: [red, blue]
featured: true
hidden: true
#rating: 4.25

---

## Getting Started

The command `jekyll new <PATH>` installs a new Jekyll site at the path specified (relative to current directory).

- To install the Jekyll site into the directory you're currently in, run `jekyll new`. If the existing directory isn't empty, you can pass the --force option with `jekyll new . --force`.
- `jekyll new` automatically initiates `bundle install` to install the dependencies required. (If you don't want Bundler to install the gems, use `jekyll new myblog --skip-bundle`.)
- By default, the Jekyll site installed by `jekyll new` uses a gem-based theme called Minima. With gem-based themes, some of the directories and files are stored in the theme-gem, hidden from your immediate view.
- We recommend setting up Jekyll with a gem-based theme but if you want to start with a blank slate, use `jekyll new myblog --blank`
- To learn about other parameters you can include with `jekyll new`, type `jekyll new --help`.

## About Bundler

Bundler packages ruby gems needed for your project. `gem install bundler` installs the bundler gem through RubyGems. You only need to install it once - not every time you create a new Jekyll project.

The `Gemfile` and `Gemfile.lock` files inform Bundler about the gem requirements in your site. If your site doesn’t have these Gemfiles, you can omit `bundle exec` and just `run jekyll serve`.

When you run `bundle exec jekyll serve`, `Bundler` uses the gems and versions as specified in `Gemfile.lock` to ensure your Jekyll site builds with no compatibility or dependency conflicts. In some environments you may need to install WebBrick to serve to your local environment by using this commend: `bundle add webrick`.

## Blog Posts

Blog posts are stored in the `_posts` folder inside your [Jekyll](https://jekyllrb.com) project. The project layout should look something like this:

```txt
├── assets      # images and other fixed assets go here
├── _includes
├── _layouts
├── _pages
└── _posts      # blog posts go here
```

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

* `YEAR` is a four-digit number
* `MONTH` and `DAY` are both two-digit numbers, and
* `MARKUP` is the file extension representing the format used in the file, e.g. html or markdown.

Each post should have the necessary front matter, e.g.

```html
---
layout: post
title: 'Unicorns Make Great Hobby Horses'
descripton: 'This post is made of unicorn flatulence.'
date: 2022-08-15 21:02:56 -0500
author: abigail
image: assets/images/unicorn.jpg
categories: [hobbies, unicorns]
tags: [pink, shiny]
featured: false
hidden: false
rating: 4.75
---
```

After the front matter, you can begin your post in your markup language of choice.

## About Markdown

Documentation for markdown can be found at [daringfireball.com](https://daringfireball.net/projects/markdown/).

### Adding Images

It's pretty easy to add pictures too.

```
![walking]({{ site.baseurl }}/assets/images/8.jpg)
```

![walking]({{ site.baseurl }}/assets/images/8.jpg)

### Full HTML

Perhaps the best part of Markdown is that you're never limited to just Markdown. You can write HTML directly in the Markdown editor and it will just work as HTML usually does. No limits! Here's a standard YouTube embed code as an example:

<p><iframe style="width:100%;" height="315" src="https://www.youtube.com/embed/Cniqsc9QfDo?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></p>

<!--
### Code Snippets

Jekyll also offers powerful support for code snippets:

There are two types of code elements which can be inserted in Markdown, the first is inline, and the other is block. Inline code is formatted by wrapping any word or words in back-ticks, `like this`. Larger snippets of code can be displayed across multiple lines using triple back ticks:

<pre>
```
triple backticks like these
```
</pre>

```
triple backticks like these
```

#### HTML

```html
<li class="ml-1 mr-1">
    <a target="_blank" href="#">
    <i class="fab fa-twitter"></i>
    </a>
</li>
```

#### CSS

```css
.highlight .c {
    color: #999988;
    font-style: italic; 
}
.highlight .err {
    color: #a61717;
    background-color: #e3d2d2; 
}
```

#### JS

```js
// alertbar later
$(document).scroll(function () {
    var y = $(this).scrollTop();
    if (y > 280) {
        $('.alertbar').fadeIn();
    } else {
        $('.alertbar').fadeOut();
    }
});
```

#### Python

```python
print("Hello World")
```

#### Ruby

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

#### C

```c
printf("Hello World");
```
-->

## Spoiler Warnings

You might not want your readers to know something that might spoil their experience later. <span class="spoiler">For this, you can use a css class to hide the details.</span>

```html
<span class="spoiler">My hidden sentence or paragraph here.</span>
```

## Reference Lists

Another way to insert links in markdown is using reference lists. You might want to use this style of linking to cite reference material in a Wikipedia-style. All of the links are listed at the end of the document, so you can maintain full separation between content and its source or reference.

```markdown
- [RStudio Devtools][1]
- [testthat][2]
- [More unit test examples][3]

[1]: https://stackoverflow.com/users/214446/mb21
[2]: https://github.com/hadley/testthat
[3]: http://r-pkgs.had.co.nz/tests.html
```

- [RStudio Devtools][1]
- [testthat][2]
- [More unit test examples][3]

[1]: https://stackoverflow.com/users/214446/mb21
[2]: https://github.com/hadley/testthat
[3]: http://r-pkgs.had.co.nz/tests.html

## More Helpful Documents

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
