# Table of contents

<!-- TOC -->autoauto1. [Table of contents](#table-of-contents)auto2. [Gauss - Jekyll Template](#gauss---jekyll-template)auto    1. [Acknowledgement](#acknowledgement)auto    2. [Intended users](#intended-users)auto3. [The _best_ way to use this template](#the-_best_-way-to-use-this-template)auto    1. [Preliminaries](#preliminaries)auto    2. [How to use](#how-to-use)auto        1. [Add a new post](#add-a-new-post)auto        2. [Add an image](#add-an-image)auto        3. [Math-typesetting](#math-typesetting)auto        4. [Math proof](#math-proof)auto    3. [Make your website online](#make-your-website-online)auto4. [Customize](#customize)auto5. [Development](#development)auto6. [Copyrighted content](#copyrighted-content)autoauto<!-- /TOC -->

# Gauss - Jekyll Template

It is a website-template designed for people who want to write notes online. It is the convergence of the best three languages: the simplicity of Markdown, the beauty of LaTeX, and the power of HTML.

It is named after the German mathematician, _Carl Friedrich Gauß_, who made significant contribution to many fields of science.

## Acknowledgement

_Gauss template_ originated from the [Leonids template](https://github.com/renyuanz/leonids/tree/gh-pages), which is for some reason terminated by the author, @renyuanz. I am a frequent user of _Leonids_ and I have customized it a lot for my [personal website](https://www.tvhoang.com). I decided to revive this wonderful project with a new name, _Gauss_.

## Intended users

The intended users of this template include **students, scientists, programmers**, who frequently take notes and want to publish them online. It has never been meant for bloggers, hence I eliminated all the web-tracking services like Google Analytics, Google Adsense, Disqus. 

I do like the notion of commenting, but you should know that free services like Disqus came at a cost: you and your readers will be tracked. I want _Gauss_ to be somewhat different and truly your personal space to record your thoughts and knowledge. Of course, you can add these services to your website, but I won't assist you.

# The _best_ way to use this template

## Preliminaries

You should be able to install Jekyll on your operating system. Please refer to [this link](https://jekyllrb.com/docs/installation/) if you run into any problems.

You may want to use [Visual Studio Code](https://code.visualstudio.com/) to write blog. You can use any other editors, but this manual only tells you VSC tips.

Open the folder of this template on your VSC editor. In the editor, open the Terminal window (in the View menu). Type the following command:

```
bundle exec jekyll serve
```

And your website should be live at http://localhost:4000

Note that from the second run onwards, you can use this command:

```
jekyll serve --livereload
```

which helps you save time refreshing your browser to view changes.

Please install the extension **Markdown+Math**, by _goessner_, in your VSC editor. It will significantly improve your writing experience. Moreover, open the Settings menu in VSC, search for the item `mdmath.delimiters` and change to `kramdown`.

## How to use

### Add a new post

Navigate to the folder `_posts`, add a file with `.md` extension. At the beginning of this file, you should have what is so called a _header_.

```
---
layout: post
title: "Title"
categories: ["Category 1", "Category 2"]
excerpt_separator: <!--more-->
image:
  feature: grg/overview.png
sticky: true
---
```

The obligatory fields are `layout` and `title`. For `categories`, you can have as many categories as you want, and they will appear several times in the categories page. The `excerpt_separator` should be left as-is, it is an indicator in your Markdown file to let Jekyll know when to trim off your post and display a preview of the content on the front page. You can also have a featured image as above. Note that all images must be put in the folder `img`. The above example, `grg/overview.png` actually refers to an image whose full path is `img/grg/overview.png`. You also have an option called `sticky` where you can choose to "pin" that post at the beginning of your website.

You can also has `js`, `css`, `ext-js`, `ext-css` fields, though they are rarely used. Currently I don't have time to write document about this.

### Add an image

There are several ways to insert images to your post. _Gauss template_ uses Lightbox2 to enhance the experience.

The fastest way to add an image, for example `img/grg/overview.png`, is to use the `img` tag:

```html
<img src="/img/grg/overview.png">
```

You can also use the class `post-image-left` or `post-image-right`, designed specifically for _Gauss template_:

```html
<div class="post-image-left">
    <a href="/img/grg/overview.png" data-lightbox="setname" data-title="title must be the same everywhere">
        <img src="/img/grg/overview.png">
    </a>
    <p class="post-image-caption">title must be the same everywhere</p>
</div>
```

Notice the attribution `data-lightbox="setname"`. The set name must be the same for all images within one post. When you click on an image, you can navigate through other images of the same set name, and often times you may want to see other images in the same post as a "gallery view".

You can create a _snippet_ in VSC for this bunch of code. Learn more about snippet [here](https://code.visualstudio.com/docs/editor/userdefinedsnippets).

```
"Post_Image": {
    "prefix": "post-image",
    "body": [
        "<div class=\"post-image-${1|left,right|}\">",
        "    <a href=\"${2:link}\" data-lightbox=\"${3:set}\" data-title=\"${4:title}\">",
        "        <img src=\"${2:link}\">",
        "    </a>",
        "    <p class=\"post-image-caption\">${4:title}</p>",
        "</div>$0"
    ]
}
```

You can also use `table` tag to insert multiple images:

```
<table>
    <tr>
        <td>
            <div class="post-image">
                <a href="/img/1.jpg" data-lightbox="setname" data-title="Title 1">
                    <img src="/img/1.jpg">
                </a>
                <p class="post-image-caption">Title 1</p>
            </div>
        </td>
        <td>
            <div class="post-image">
                <a href="/img/2.jpg" data-lightbox="setname" data-title="Title 2">
                    <img src="/img/2.jpg">
                </a>
                <p class="post-image-caption">Title 2</p>
            </div>
        </td>
    </tr>
</table>
```

The piece of code above displays two images side by side. When the class `post-image` is used, the image will span 100% width of the parent element, in this case, the `td` tag. When the class `post-image-left` or `post-image-right` is used, the image will span 30% width of the parent element and float left or right respectively.

### Math-typesetting

Unlike many other templates, _Gauss template_ uses KaTeX as the math renderer. It is significantly faster than MathJax, yet preserves the same functionality. Keep your Math formula inside ``$$`` and `$$` for **both** inline and display mode (display mode means the math formula is displayed in a dedicated line).

In order to use display mode, you have to keep the math equation in a separated line in your Markdown file.

```
paragraph 1

$$ a+b = c $$ text here will be ignored

paragraph 2
```

Note that if a line begins with a display-mode math equation, all other texts of the same line after the equation will be ignored

Sometimes you may want to begin a paragraph with an inline math equation. In this case, you can add a non-breakable space at the beginning of the sentence to let MathJax know that it is dealing with inline math mode.

```
paragraph 1

&nbsp;$$ a+b = c $$ text here will still be shown

paragraph 2
```

It is worth noting how KaTeX works: Jekyll still uses MathJax when it transforms the Markdown file into an HTML file. KaTeX then looks into this file and replace MathJax's parts with its own parts. It may sound redundant, but [reality](https://www.intmath.com/cg5/katex-mathjax-comparison.php) has shown that KaTeX runs at least 10 times faster.

### Math proof

This is a unique feature in _Gauss_ designed specifically for Mathematicians. Whenever you write a theorem and you want to display a proof right after that, you may want it to be hidden for two reasons: the post looks cleaner and the readers can have a moment to think about the proof first. You can add the following snippet to your `markdown.json` file:

```
"Proof": {
    "prefix": "\\proof",
    "body": [
        "<${1|span,h2,h3,h4,h5|} onClick=\"toggleShowHide('$3')\" class=\"toggleButton\" markdown=\"1\"> &#x25B6; Chứng minh$2</$1>",
        "<div id=\"$3\" class=\"toggleContent\" markdown=\"1\">",
        "$4",
        "</div>"
    ]
}
```

A proof will look like this in the Markdown file:

```md
Theorem: blah blah. <span onClick="toggleShowHide('randomidcodejnfkjnk')" class="toggleButton" markdown="1"> &#x25B6; Proof</span>
<div id="randomidcodejnfkjnk" class="toggleContent" markdown="1">

$$\mathbb{R}-S=(-\infty,0)\cup\left(\bigcup_{i\in\mathbb{N}^+}(1/(i+1), 1/i)\right)\cup(1,\infty)$$

is the union of open intervals, hence open. $$\Rightarrow S$$ is closed.

</div>
```

Note that you must leave an empty line after the `div` tag and before the `/div` tag. The users can click on the word "Proof" to show and close the proof. By default, the proof is hidden.

## Make your website online

You can learn how to create a repository on GitHub and deploy a GitHub page [here](https://pages.github.com/). Do remember to change the site name in `_config.yml` and `CNAME`. This is a free service by GitHub and your website will live on `https://username.github.io/`

If you want to use an optional domain, like `https://www.tvhoang.com`. You have to first buy your domain. My experience with [NameCheap](https://www.namecheap.com/) has been fantastic so I would suggest you buy your domain there. You may want to set up HTTPS to get the beautiful green lock in the browser. In that case, you can visit [this blog](https://medium.freecodecamp.org/free-https-c051ca570324) to find out the procedures.

# Customize

The power of HTML/CSS/JS as a whole allows us to customize anything we want. However, my advice is that you should only change the color of the texts. You can look into the file `_variables.scss` and `_typography.scss` if you want to customize. This entirely depends on your creativity and your ability to design.

Of course, you can change your personal information (e.g. your name, email address, etc.) in `_config.yml`.

# Development

There are a lot of features I want to add to this template, but I do not have time to implement.

- Comment section (**not** Disqus): I'm thinking of using some self hosted app on Heroku (which has a free plan). This app plays a role very much like Disqus: record comments from readers and load them into the blog post when requested.
- Page view: Each post should show how many times it has been viewed. Again, I don't want to use commercial or tracking services on the site. If there is an open-source solution, please let me know.
- Documentation: Scientists are usually not familiar with code and commands. They may be able to code in their respected fields, but setting up a website and customizing it without a graphic interface could be very painful and time-wasting. If you can contribute to make this manual clearer even for computer-illiterate, I will be very thankful!

