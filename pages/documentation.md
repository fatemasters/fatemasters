---
layout: page
title: "Theme Documentation"
subheadline: "How to use Responsive One"
teaser: "<em>Responsive One</em> features lots of possibilities to make blogging easy and fun while having various options to style your content to your needs."
permalink: "/documentation/"
header: no
---
[Jump to Table of Contents](#toc)
{: .button.radius }


## Different Page/Posts Formats   {#formats}

*Responsive One* was inspired by the tumblr blogging format with post formats for different kinds of posts. These are the available formats. Click on a format to see an example and the according variable to use it via front matter:

{% include list-posts tag='post-format' %}



## Use or disable metadata for Page/Post 

If you want to show metadata like categories, tags and date at the bottom of an entry, just enter `show_meta: true`. It's on by default. You can change it via `config.yml`. To turn of metadata just enter – *yes, you guessed right* – `show_meta: false`.



### Frontpage

This template is special. It allows you to define three *widgets* which are displayed with a headline, image, description and a link to the content. It's used for the [homepage]({{ site.url }}) of this website.

use in front matter via: `layout: frontpage`



## Style your content with   {#styling}

*Responsive One* offers lots of possibilities to style your articles. You can style your content in different ways. There are elements like subheadlines, feature images, header images, homepage images, meta data like categories and tags and many more.



### Subheadlines

If you need a subheadline for an article, just define a subheadline in front matter like this:

`subheadline:  "Subheadline"`



### Quotes

Quotes mix it up a little bit, if you write long articles. So use quotes:

> Age is an issue of mind over matter. If you don't mind, it doesn't matter.
<cite>Mark Twain</cite>



## Comments

You can use comments with **Responsive One** by the way of Disqus. If you want to use Disqus-Comments just open `config.yml` and add your `disqus_shortname`. [More on how to use Disqus ›](https://disqus.com/websites/)

By default comments are turned off. You can customize the default behaviour in `config.yml`. To **turn on comments** just add `comments: true` to front matter using the page layout `layout: page`. 



## Responsive Videos

With foundation responsive videos are easy. [More ›](http://foundation.zurb.com/docs/components/flex_video.html)

<div class="flex-video">
        <iframe width="1280" height="720" src="//www.youtube.com/embed/WoHxoz_0ykI" frameborder="0" allowfullscreen></iframe>
</div>

### Code to use for flexible videos

{% highlight html %}
<div class="flex-video">
  <iframe with video />
</div>
{% endhighlight %}



## Images: Title, Thumbnails, Homepage   {#images}

There are several types of images you can define via front matter. If you want to change the images used in the header have a look at [Style your Header]({{ site.url }}//category-headers/). 


### Title Images

~~~
image:
    title: image.jpg
~~~


### Thumbnails

Thumbnails are used on archive pages like the [blog index][2]. They have a size of 128x128 pixels. Define them in front matter like this:

~~~
image:
    thumb: thumbnail_image.jpg
~~~



### Captions with URL

Sometimes you want to give credit to the creator of your images, maybe with a link. Especially when you use Creative Commons-images like I do for this website. Just add the following front matter and **Responsive One** does the rest:

~~~
image:
    title: header_image.jpg
    caption: Image by Phlow
    caption_url: "http://phlow.de/"
~~~

### Define all images for an article

~~~
image:
    title: title_image.jpg
    thumb: thumbnail_image.jpg
    homepage: header_homepage_13.jpg
    caption: Image by Phlow
    caption_url: "http://phlow.de/"
~~~





## Create a Table of Content
{: .t60}

With the Kramdown parser for Markdown you can render a table of contents for your documents. Just insert the following HTML in your post before the actual content. More information on [»Automatic ›Table of Contents‹ Generation«][1].

### Bare Bones Version
{% highlight html %}
### Table of Contents
*  Auto generated table of contents
{:toc}
{% endhighlight %}

### Foundation panel version

{% highlight html %}
<div class="panel radius" markdown="1">
**Table of Contents**
{: #toc }
*  TOC
{:toc}
</div>
{% endhighlight %}


## Breadcrumbs

To turn on breadcrumbs, just use...

{% highlight html %}
breadcrumb: true
{% endhighlight %}


## Includes
{: .t60}

Includes can be very helpful to spice up your content. You can use includes in your Markdown-files with ease: Just call them with some Liquid code.

### list-posts

The `list-posts`-include is a loop to list posts. It's a helper to add some additional content fast and easy. You can use it in individual posts for example. Which parameters you use, depends on you.

Possible parameter for the loop:

- entries › define the number of entries to show
- offset › define the offset (number of entries to skip before displaying the first one)
- category › define **only one** category to display according entries

The loop looks when you use all parameters. Single parameters are possible of course.

~~~
{% raw %}{% include list-posts entries='3' offset='1' category='design' %}{% endraw %}
~~~

### next-previous-post-in-category

This include creates a next/previous link to a post of the same category using the first categories-variable in front matter.

~~~
{% raw %}{% include next-previous-post-in-category %}{% endraw %}
~~~


### improve_content

If your content is on Jekyll you can use this include to automatically generate a »Edit on GitHub Link« to give people a possibility to improve your content. Got the idea from [Ben Balters Blog](http://ben.balter.com/).

~~~
{% raw %}{% include improve_content %}{% endraw %}
~~~


### list-collection

This include lets you loop through a collection to list all entries in that collection. If you set »published: false« in front matter of a collection page the page gots filtered out via unless. The following example loops through a collection called *wordpress*.

~~~
{% raw %}{% include list-collection collection='wordpress' %}{% endraw %}
~~~


### alert – Embed an alert in your content

This include lets you easily display an alert. To use the include no `.html` ending is necessary. You can use five different kinds of alerts: `warning`, `info`, `success`, `alert` and `text`. 

~~~
{% raw %}{% include alert warning='This is a warning.' %}
{% include alert info='An info box.' %}
{% include alert success='Yeah, you made it!' %}
{% include alert alert='Danger!' %}
{% include alert terminal='jekyll -serve' %}
{% include alert text='Just a note!' %}{% endraw %}
~~~

{% include alert warning='This is a warning.' %}
{% include alert info='An info box.' %}
{% include alert success='Yeah, you made it!' %}
{% include alert alert='Danger!' %}
{% include alert terminal='jekyll -serve' %}
{% include alert text='Just a note!' %}

You can even use `<html>`-tags inside the alert. Beware: Use `"` and `'` properly.


#### Example

~~~
{% raw %}{% include alert info='<em>*Responsive One*</em> is listed on <a href="http://jekyllthemes.org/">http://jekyllthemes.org</a>' %}{% endraw %}
~~~

#### Result

{% include alert info='<em>*Responsive One*</em> is listed on <a href="http://jekyllthemes.org/">http://jekyllthemes.org</a>' %}




## Javascript/Foundation modules

**Responsive One** uses the foundation framework and some of its javascript components. I reduced the modules, to decrease page load and make the theme faster.

I only added one other javascript-module: [`backstretch`][3] by Scott Robbin. These modules are currently used by the theme and included in `javascript.min.js`. There is also a non-minified version, if you want to take a closer look: `javascript.js`.

~~~
/foundation/bower_components/foundation/js/vendor/jquery.js'
/foundation/bower_components/foundation/js/vendor/fastclick.js'
/foundation/bower_components/foundation/js/foundation.accordion.js'
/foundation/bower_components/foundation/js/foundation.clearing.js'
/foundation/bower_components/foundation/js/foundation.dropdown.js'
/foundation/bower_components/foundation/js/foundation.equalizer.js'
/foundation/bower_components/foundation/js/foundation.magellan.js'
/foundation/bower_components/foundation/js/foundation.topbar.js'
/foundation/js/jquery.backstretch.js'
~~~

{% include improve_content %}



<div id="toc" class="panel radius" markdown="1">
Table of Content
{: #toc }
*  TOC
{:toc}
</div>




 [1]: http://kramdown.gettalong.org/converter/html.html#toc
 [2]: {{ site.url }}
 [3]: http://srobbin.com/jquery-plugins/backstretch/
 [4]: #
 [5]: #
 [6]: #
 [7]: #
 [8]: #
 [9]: #
 [10]: #