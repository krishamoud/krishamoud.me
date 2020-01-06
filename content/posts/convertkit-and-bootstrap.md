---
title: "ConvertKit forms and Twitter Bootstrap"
date: 2020-01-02T01:48:12-05:00
draft: false
thumbnail: "/images/design.jpg"
---

## Overview
I have been working for [ConvertKit](https://convertkit.com) for over a year now, and I haven't written a blog post in over two years.  I'm an infrastructure engineer at ConvertKit, which means I spend my working days looking at Linux terminals, and I'm not to be trusted to do frontend work.  Despite my lack of design skills, I've been wanting to write more and publish articles on my own website.  Since working at ConvertKit, I've learned the importance of an email list, so I decided to challenge myself to rebuild my blog, integrate [ConvertKit forms](https://convertkit.com/features/forms) with it, and make it look good.

I might not be a designer, but I do know how to twitter some bootstrap.  I spent the weekend redesigning my blog using the [blog post](https://startbootstrap.com/templates/blog-post/), and [blog home](https://startbootstrap.com/templates/blog-home/) templates provided by [Start Bootstrap](https://startbootstrap.com/).  The goal of this post is to show you how you can seamlessly integrate ConvertKit forms with twitter bootstrap for your own site.

### Picking the right display for the element

ConvertKit offers four display formats for forms.  They are:
1. Inline
2. Modal
3. Slide in
4. Sticky bar

Because all the forms on this site are currently inline, I'll only be going over the **Inline** format.  If I ever add any of the other three, I'll update this post.  Within the **Inline** form format, there are _*six*_ templates from which to choose.  In my opinion, Bootstrap Cards and Sections are the two best components to use in conjunction with ConvertKit forms.  They offer great flexibility and ease of use.

#### Bootstrap Cards
I like these the most, and they are currently the only way I show my forms on this site, but they can be used in multiple different ways.

##### Charlotte Form

```html
<div class="card my-4">
  <script async data-uid="5f9183d72c" src="https://kris.ck.page/5f9183d72c/index.js"></script>
</div>
```
{{< rawhtml >}}
<div class="card my-4">
  <script async data-uid="5f9183d72c" src="https://kris.ck.page/5f9183d72c/index.js"></script>
</div>
{{< /rawhtml >}}

___
##### Clare Form
```html
<div class="card my-4">
  <div class="card-body">
    <script async data-uid="b6e72799f4" src="https://kris.ck.page/b6e72799f4/index.js"></script>
  </div>
</div>
```

{{< rawhtml >}}
<div class="card my-4">
  <div class="card-body">
    <script async data-uid="b6e72799f4" src="https://kris.ck.page/b6e72799f4/index.js"></script>
  </div>
</div>
{{< /rawhtml >}}

___

##### Mills Form

```html
<div class="card my-4">
  <script async data-uid="0b8223d1cb" src="https://kris.ck.page/0b8223d1cb/index.js"></script>
</div>
```
{{< rawhtml >}}
<div class="card my-4">
  <script async data-uid="0b8223d1cb" src="https://kris.ck.page/0b8223d1cb/index.js"></script>
</div>
{{< /rawhtml >}}

---

##### Pine Form
```html
<div class="card my-4">
  <script async data-uid="2fefbfa3f3" src="https://kris.ck.page/2fefbfa3f3/index.js"></script>
</div>
```
{{< rawhtml >}}
<div class="card my-4">
  <script async data-uid="2fefbfa3f3" src="https://kris.ck.page/2fefbfa3f3/index.js"></script>
</div>
{{< /rawhtml >}}

---

##### Powell Form
```html
<div class="card my-4">
  <script async data-uid="ce1b6394aa" src="https://kris.ck.page/ce1b6394aa/index.js"></script>
</div>
```
{{< rawhtml >}}
<div class="card my-4">
  <script async data-uid="ce1b6394aa" src="https://kris.ck.page/ce1b6394aa/index.js"></script>
</div>
{{< /rawhtml >}}

---

##### Rainier Form
```html
<div class="card my-4">
  <script async data-uid="753637692a" src="https://kris.ck.page/753637692a/index.js"></script>
</div>
```
{{< rawhtml >}}
<div class="card my-4">
  <script async data-uid="753637692a" src="https://kris.ck.page/753637692a/index.js"></script>
</div>
{{< /rawhtml >}}

##### Bootstrapping the Cards
They don't look any different than when we created them in the ConvertKit form builder, but when we combine them with the other elements of twitter bootstrap, we can do some cool stuff, and because it's bootstrap it's mobile responsive.

**Real life example:**
```html
<div class="col-md-6">
  <div class="card profile" >
    <img class="card-img-top" src="/profile.png" alt="Card image cap">
      <div class="card-body">
        <h5 class="card-title">Kris Hamoud</h5>
        <p class="card-text">Traveler. Guy on the internet. Infrastructure engineer <a href="https://convertkit.com" target="_blank" rel="noopener noreferrer">@ConvertKit</a></p>

          <a href="https://github.com/krishamoud" class="card-link" target="_blank" rel="noopener noreferrer"><i class="fab fa-github-alt fa-fw"></i></a>

          <a href="https://linkedin.com/in/kristopher-hamoud-17b34665" class="card-link" target="_blank" rel="noopener noreferrer"><i class="fab fa-linkedin-in fa-fw"></i></a>

          <a href="https://twitter.com/krishamoud" class="card-link" target="_blank" rel="noopener noreferrer"><i class="fab fa-twitter fa-fw"></i></a>
          <hr>
      <h5 class="card-title">Newsletter</h5>
      <p class="card-text">Subscribe to get my latest content by email.</p>
      <script async data-uid="d2bb073bb7" src="https://kris.ck.page/d2bb073bb7/index.js"></script>
    </div>
  </div>
</div>
```

{{< rawhtml >}}
<div class="col-md-6">
  <div class="card profile" >
    <img class="card-img-top" src="/profile.png" alt="Card image cap">
      <div class="card-body">
        <h5 class="card-title">Kris Hamoud</h5>
        <p class="card-text">Traveler. Guy on the internet. Infrastructure engineer <a href="https://convertkit.com" target="_blank"_ rel="noopener noreferrer">@ConvertKit</a></p>

          <a href="https://github.com/krishamoud" class="card-link" target="_blank"_ rel="noopener noreferrer"><i class="fab fa-github-alt fa-fw"></i></a>

          <a href="https://linkedin.com/in/kristopher-hamoud-17b34665" class="card-link" target="_blank"_ rel="noopener noreferrer"><i class="fab fa-linkedin-in fa-fw"></i></a>

          <a href="https://twitter.com/krishamoud" class="card-link" target="_blank"_ rel="noopener noreferrer"><i class="fab fa-twitter fa-fw"></i></a>
          <hr>
      <h5 class="card-title">Newsletter</h5>
      <p class="card-text">Subscribe to get my latest content by email.</p>
      <script async data-uid="d2bb073bb7" src="https://kris.ck.page/d2bb073bb7/index.js"></script>
    </div>
  </div>
</div>
{{< /rawhtml >}}

---



#### Bootstrap Section
These can be used as call-to-actions and are useful to get visitors' attention to do something.  I think this one looks best with the Clare form.  Because of the styling on this page, I'm going to put it in an `iframe` and also link to the page.

##### Clare Section

[Check out the page](/examples/clare-example-section/)
```html
<section class="py-5 bg-light py-5">
  <div class="container text-center">
    <h2 class="heading">Example Blog </h2>
    <div class="intro">Welcome to my blog. Subscribe and get my latest content.</div>
    <script async data-uid="b6e72799f4" src="https://kris.ck.page/b6e72799f4/index.js"></script>
  </div><!--//container-->
</section>
<div class="main-wrapper d-flex flex-column sticky-footer-wrapper">
  <div class="flex-fill">
  <div class="container">
    <h1> The rest of your content goes here</h1>
  </div>
  </div>
</div>
<footer class="footer py-2 bg-dark">
  <div class="container text-center text-white">
    <small class="copyright">Made with <i class="fas fa-heart" style="color: #fb866a;"></i> by <a href="https://github.com/krishamoud" target="_blank">Kris Hamoud</a></small>
  </div>
</footer>
```
{{< rawhtml >}}
<iframe src="/examples/clare-example-section/" width="100%" height="500"></iframe>
{{< /rawhtml >}}

---

### Conclusion
ConvertKit forms are easily embedded into HTML.  Using bootstrap makes it even easier to format your forms, so they match the look and feel of your site.  Alternatively, you don't have to build your own website at all and can use [ConvertKit Free Landing Pages](https://convertkit.com/features/landing-pages).  They are easy to set up and get started, and they were crafted from the ground up by the incredibly talented designers at ConvertKit.  You can visit mine at https://kris.ck.page.

If you enjoyed reading this, please consider signing up for my email list using _any_ of the forms above, and I'll continue pushing out content.

**NEXT:** I'll be taking this post one step further and integrating the twitter bootstrap cards and sections above with [Hugo](https://gohugo.io/), which is the static site generator powering this site.
