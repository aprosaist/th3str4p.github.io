---
title: "A Better Calendly Embed"
categories:
  - productivity
tags:
  - calendly
  - embed
  - html
excerpt: "Calendly is an awesome scheduling app.  This post examines a better way to embed it in your website."
header:
  overlay_image: /assets/images/a-better-calendly-embed.jpg
  overlay_filter: 0.5
  caption: "Photo credit: [**rawpixel on Unsplash**](https://unsplash.com/photos/Ps9JJ0dpcko)"
---

## Introduction
If you work in a field that requires a lot of scheduling -- sales, consulting, professional services, etc. -- you know it's a massive pain in the backside.  Sometimes you might send three or four emails back and forth with someone to try and nail down a time that works for both of you.  And then if something comes up that requires you to reschedule... not a fun prospect.  [**Calendly**](https://calendly.com/) was created to solve that problem.  It's not the only game in town, but it's clean, fast and simple.  Its free version is enough for many people, and its Premium and Pro versions are reasonably priced.

## Embedding
If you've noticed on my [**Free Consultation**](/free-consultation/) page, I personally use Calendly.  You might also notice that it's right there on the page.  You don't have to click on anything to get to it.  This is what's known as an **embed**.  I'm literally embedding the Calendly interface into my page.

This has a few benefits.  It makes it that much faster and easier for people to schedule with me.  That should (in theory) have a secondary effect of increasing my conversion rate.  So far so good; so what's the big deal?

By default, Calendly offers three methods to embed their interface into your site:
1.  **Inline**
2.  **Popup Widget**
3.  **Popup Text**

**Inline** is what I'm using on the [**Free Consultation**](/free-consultation/) page.  As you can see, it puts the Calendly interface inline with the rest of the content on the page.  In other words, there's no button to click.  It's just there.

**Popup Widget** puts a button in the bottom-right corner of your site.  When a visitor clicks the button, it will cause a popup to open that contains the Calendly interface.  In my circumstance, this is no good.  I use the Facebook Customer Chat code which puts a little Messenger icon in the bottom-right corner of my site, so the two would conflict with each other.

**Popup Text** allows you to put a link anywhere on your site.  When a visitor clicks the link, a popup will open containing the Calendly interface.  I was using this, but something in the code conflicts with the [**Jekyll**](https://jekyllrb.com/) renderer my site is built on.  This causes the footer to show up in the middle of the page rather than the bottom.  It looks ugly and breaks the functionality of the site.

## The Problem
Granted, I could probably work with Calendly to fix whatever is going on, but right now I just don't have the time.  So, I switched to the inline embed method... which brought its own challenges.

The code Calendly gives you to copy and paste for the inline embed looks like this:

```
<!-- Calendly inline widget begin -->
<div class="calendly-inline-widget" data-url="https://calendly.com/username" style="min-width:320px;height:580px;"></div>
<script type="text/javascript" src="https://assets.calendly.com/assets/external/widget.js"></script>
<!-- Calendly inline widget end -->
```

The only problem with this is that it causes a second scroll bar to show up on the page.  Basically you can scroll the Calendly interface independently of the page itself.  In my opinion, it's confusing (especially on mobile) and ugly.

## The Solution
After some trial and error with a sprinkle of Google-fu, I came up with the following snippet of code:

```
<iframe src="https://calendly.com/username" width="100%" height="950" scrolling="no" frameborder="0"></iframe>
```

This embeds the Calendly interface with no extra scroll bar and makes it tall enough to see a full week of dates without anything being cut off on either desktop or mobile.

## Conclusion
Calendly is an awesome scheduling app.  If you want to embed it in your website but don't like the extra scroll bar it creates, give the code above a try.

<p class="notice--info"><b>Need help?</b>  <a href="/free-consultation/">Click here</a> to schedule a free consultation with me to discuss your web design, graphic design or digital marketing needs.</p>

<!-- Begin MailChimp Signup Form -->
<link href="//cdn-images.mailchimp.com/embedcode/slim-10_7.css" rel="stylesheet" type="text/css">
<style type="text/css">
	#mc_embed_signup{background:#fff; clear:left; font:14px Helvetica,Arial,sans-serif; }
	/* Add your own MailChimp form style overrides in your site stylesheet or in this style block.
	   We recommend moving this block and the preceding CSS link to the HEAD of your HTML file. */
</style>
<div id="mc_embed_signup">
<form action="https://bengilstrap.us19.list-manage.com/subscribe/post?u=f631cb726a5c965a7c24c5eea&amp;id=6bcdb2ecde" method="post" id="mc-embedded-subscribe-form" name="mc-embedded-subscribe-form" class="validate" target="_blank" novalidate>
    <div id="mc_embed_signup_scroll">
	<label for="mce-EMAIL">Like what you see?  Subscribe to my newsletter for more great content.</label>
	<input type="email" value="" name="EMAIL" class="email" id="mce-EMAIL" placeholder="email address" required>
    <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
    <div style="position: absolute; left: -5000px;" aria-hidden="true"><input type="text" name="b_f631cb726a5c965a7c24c5eea_6bcdb2ecde" tabindex="-1" value=""></div>
    <div class="clear"><input type="submit" value="Subscribe Now" name="subscribe" id="mc-embedded-subscribe" class="button"></div>
    </div>
</form>
</div>

<!--End mc_embed_signup-->
