---
title: Post with an image gallery
description: This post contains an image gallery in Markdown as well as shortcodes.
tags:
  - eleventy
  - markdown
  - shortcode
  - images
  - gallery
  - lightbox
layout: layouts/post.njk

header:
  teaser: /img/image001.jpg

---

To display a set of images in a gallery, just surround the images (written as Markdown), with the `gallery` shortcode. Clicking the image shows the image in lightbox, with the caption. A little Markdown might in the caption might also work.

```
{% raw %}{% gallery %}
![](/img/image001.jpg)
![**Second** image](/img/image002.jpg)
![`Third` image](/img/image003.jpg)
{% endgallery %}{% endraw %}
```

Produces this:

{% gallery %}
![](/img/image001.jpg)
![**Second** image](/img/image002.jpg)
![`Third` image](/img/image003.jpg)
{% endgallery %}

The images are constrained to a fixed size. The captions don't appear on the page, as they would for standalone images, because it's crowded and can get awkward quickly.


## Using gallery and figure shortcodes together

It's also possible to use the `figure` shortcode inside the `gallery` shortcode.

```
{% raw %}
{% gallery %}
{% figure "/img/image001.jpg", "First **caption**" %}
{% figure "/img/image002.jpg", "Second *caption*" %}
{% figure "/img/image003.jpg", "Third `caption`" %}
{% endgallery %}
{% endraw %}
```

Produces this:

{% gallery %}
{% figure "/img/image001.jpg", "First **caption**" %}
{% figure "/img/image002.jpg", "Second *caption*" %}
{% figure "/img/image003.jpg", "Third `caption`" %}
{% endgallery %}

In this case, the caption appears below the images, but not in the lightbox.  This is because the shortcodes are rendered independently. This can get crowded and awkward, I'm not sure if this is a good idea.