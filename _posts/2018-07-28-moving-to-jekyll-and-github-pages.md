---
layout: post
title:  "Moving to Jekyll and GitHub Pages (while Bidding Wordpress Adieu)"
date:   2018-07-28
categories:
permalink: blog/jekyll-github-pages-from-wordpress
---


I did it! I finally made the move to the faster, simpler, more secure, and cheaper alternative, [Jekyll](http://jekyllrb.com/). I'm not particularly technical, but I was able to switch things over relatively painlessly – all it took was a little patience and elbow grease.

After years of hosting my Wordpress site on a Bluehost server, I started to look at Static Site Generator alternatives. Why? A few reasons:
* Simplicity – My personal website doesn't need a dynamic [CMS](https://en.wikipedia.org/wiki/Content_management_system) like Wordpress and Drupal since I'm only using it to share some basic personal information and blog posts. Armed with pretty basic web knowledge, I can make all the changes I want very quickly. Using [Front Matter](https://jekyllrb.com/docs/frontmatter/) and [Markdown](https://daringfireball.net/projects/markdown/) have made my life much easier.
* Speed – My website is somewhere between 10x and 20x faster than it was before.
* Security – While most CMSs can be very powerful, there are plenty of potential security issues, from admin login exploits to plugin vulnerabilities that I'm not well-equipped to navigate. Also, static sites require no database.
* Savings – Hosting a static site can be much, much cheaper than other alternatives. In this case, I'm only paying for my domain name.

For some more good reading on the advantages (and disadvantages) of Static Site Generators, take a look at David Walsh's [An Introduction to Static Site Generators](https://davidwalsh.name/introduction-static-site-generators) and Smashing Magazine's [Why Static Site Generators Are The Next Big Thing](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/).

After deciding to use a static Site Generator, I opted for Jekyll since I've heard good things about it from developer friends, it has a big community, I wanted to learn a bit more about Ruby (the programming language it's built on top of), and it plays [very nicely](https://help.github.com/articles/about-github-pages-and-jekyll/) with [GitHub Pages](https://pages.github.com/) (free and easy hosting).

A quick note that GitHub recently announced [support for HTTPS on GitHub Pages using a custom domain](https://blog.github.com/2018-05-01-github-pages-custom-domains-https/), which was a must for me. I needed to have my own domain name, and ever since I learned [why HTTPS matters](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/why-https) and [that Google announced it would mark HTTP pages as "not secure" in Chrome](https://www.blog.google/products/chrome/milestone-chrome-security-marking-http-not-secure/), I've had my mind set.

## Getting Started

Before diving in too deep, a quick note that this was a fun project for me since I had the available time and interest. I also used knowledge from the following basic web courses that I've taken over the past few years:
* [Command Line Crash Course – To learn how to use my terminal](https://learnpythonthehardway.org/book/appendixa.html)
* [Git Immersion – To learn about Git, an open source distributed version control system](http://gitimmersion.com/)
* [HTML & CSS by Codecademy – For web fundamentals](https://www.codecademy.com/catalog/language/html-css)

After choosing Jekyll, I followed the [installation tutorial](https://jekyllrb.com/docs/installation/) on Jekyll's website without any issue. I also stuck with the default [Minima theme](https://github.com/jekyll/minima), which kept things simple. A couple of video tutorial series that I found helpful to watch throughout the process:

* [Jekyll - Static Site Generator Tutorial by Giraffe Academy](https://www.youtube.com/playlist?list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB)
* [Getting Started With Jekyll by Codecourse](https://www.youtube.com/watch?v=iWowJBRMtpc&list=PLfdtiltiRHWGGdT5j9cF-OHt23wSBGHJe)

## Configuring my GitHub Repo

Setting my GitHub repo was pretty simple. First, I needed to create a new project in GitHub. **It's necessary to name your new repo `username.github.io`.** If you don't do that, GitHub won't know that you're setting up a project for GitHub Pages. Also note the [guidelines/limits of GitHub Pages](https://help.github.com/articles/what-is-github-pages/#guidelines-for-using-github-pages) and the [dependency versions](https://pages.github.com/versions/).

I tried to set up the [Jekyll GitHub Pages Gem](https://github.com/github/pages-gem) but ran into a few issues, realized I didn't really need it, and moved on.

Once my base site was set up locally, I pushed it to my new GitHub project, and saw it live on [btrav.github.io](btrav.github.io), which was pretty neat. I noticed a small discrepancy (I assume because of the difference in dependency versions across my local setup and GitHub) initially – I encountered a strange situation where the page was taking an H2 tag as a page title, which then made itself into the nav somehow – but giving each page a `title` fixed it right away.

Jonathan McGlone has a great [beginner guide on creating a personal website and blog using Jekyll with GitHub pages](http://jmcglone.com/guides/github-pages/) that covers this in more detail.

Keep in mind that GitHub Pages takes your repo and builds a site from your files instead of just taking the static files.

## Configuring DNS for a Custom Domain and Getting HTTPS to Work

[Namecheap](https://www.namecheap.com/) is my domain registrar, and I've been happy with them since I began using them a few years – plus they add WhoisGuard for free – but Cloudflare works best for my new site setup. [Cloudflare](https://www.cloudflare.com/) is an industry-leading company that offers robust DNS services (along with a ton of others) and has a great free plan.

Since I'd hosted my Wordpress website on Bluehost for the past half dozen years, I needed to redirect my nameservers to Cloudflare's instead of Bluehost's. Most registrars have an easy tutorial on how to do that – [here's Namecheap's](https://www.namecheap.com/support/knowledgebase/article.aspx/9607/2210/how-to-set-up-dns-records-for-your-domain-in-cloudflare-account).

Then, I followed [GitHub's tutorial on setting up an apex domain for GitHub Pages](https://help.github.com/articles/setting-up-an-apex-domain/). GitHub requires you to configure `A` records that point to [its IP addresses](https://help.github.com/articles/setting-up-an-apex-domain/#configuring-a-records-with-your-dns-provider). After that, I set up a CNAME record in Cloudflare that points the `www` hostname to the GitHub Pages domain.

I also added CNAME file in my repo (literally just a file named `CNAME` with `benjamintravis.com` as its contents), as required by GitHub pages.

OK, here's where things got a little tricky and I had to reach out to GitHub for support. Everything seemed to be going as expected, but I was unable to `Enforce HTTPS` in my repo settings, and typing in my domain automatically served me an HTTP version of the site. Even stranger, I could access access the HTTPS version directly, but it wasn't the default for some reason.

It turns out that Cloudflare automatically sets up an SSL certificate for you, which is normally great. However, I wanted to use GitHub's certificate [detailed in the recent Github blog post](https://blog.github.com/2018-05-01-github-pages-custom-domains-https/) and force all information over HTTPS.

The GitHub team was really helpful and told me how to disable CloudFlare's DNS/HTTP proxy so that GitHub Pages could do its thing magically on the back end. After logging into my Cloudflare account, I went to my DNS settings and clicked on the orange cloud icons next to any DNS records related to my GitHub Pages domain. I also disabled the default Cloudflare HTTPS certificate. Finally, I went into my GitHub repo settings under GitHub Pages, removed, then added back my custom domain to reset things.

After about a half hour, my new certificate was provisioned, and I was able to enforce HTTPS by checking the `Enforce HTTPS` checkbox.

Note that GitHub encrypts pages through [Let's Encrypt](https://letsencrypt.org/), which is [officially trusted by all major certificate authorities](https://www.bleepingcomputer.com/news/security/lets-encrypt-is-now-officially-trusted-by-all-major-certificate-authorities/). Also, anything related to DNS setup can take up to 48 hours (though it's usually far quicker), so be patient!

## Migrating Blog Content

Since I was previously using Wordpress, I needed to migrate blog content over to my new site. Tomomi Imura has an [easy-to-follow guide on migrating from Wordpress to Jekyll](https://girliemac.com/blog/2013/12/27/wordpress-to-jekyll/) that I'd recommend following if you have a lot of content you'd like to switch over.

Since I only had a few posts to move over and had to make a few changes anyway, I used [Mark It Down](http://markitdown.medusis.com/) to convert my posts to markdown format. If you're unfamiliar with Markdown, I'd recommend reading through [Ghost's resource on it](https://blog.ghost.org/markdown/).

A quick note that while Jekyll is built as a "blog-aware" solution, the default URLs can look kind of ugly (e.g. `.../2018/07/28/this-is-the-name-of-my-article` vs `.../blog/article-name`). Adding [permalinks](https://jekyllrb.com/docs/permalinks/) is a great solution for this.

## Adding Comments

Similar to the blog content, I used Wordpress for comments. During this migration to Jekyll, I wanted to make the switch to [Disqus](https://disqus.com/), a free global comment system that's widely used across the Internet. Fortunately, the Jekyll theme I'm using, Minima, adds that functionality pretty much out of the box.

After registering my website with Disqus, I added my shortname to the `config.yml` file. I had to go through a bit of troubleshooting to figure out that I also [needed to set the url property in `config.yml`](https://github.com/jekyll/minima/issues/104).

## Deciding on Asset Storage

I initially thought I'd keep my assets (any videos, images, etc.) stored in [Amazon S3 buckets](https://aws.amazon.com/s3/), but after talking with a couple of developers, that seemed like far too heavy a solution for what I needed. I ended up [optimizing images](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization) (e.g. no images greater than 1MB, even infographics) and adding them directly to my [GitHub repo](https://help.github.com/articles/about-repositories/).

For my site [favicon](https://en.wikipedia.org/wiki/Favicon), I created a simple vector file and used [Favicon Generator](https://realfavicongenerator.net/) to create favicons for all browsers and platforms.

## Adding Analytics

Adding analytics is also very easy to do with Jekyll. You can add your [Google Analytics](https://marketingplatform.google.com/about/analytics/) ID in the `config.yml` file, though I opted to add my code directly to the `<head>` of my site.

## Handling Redirects

After moving over my site and setting up new [permalinks](https://jekyllrb.com/docs/permalinks/), I realized I needed to add some redirects. Fortunately, there's a Gem for that, and GitHub Pages supports it! The [jekyll-redirect-from](https://github.com/jekyll/jekyll-redirect-from) Gem is easy to implement and saved me a bunch of headaches. Now, any SEO authority I had on my old site can be passed through to my new or updated pages.

## Looking Forward

After writing a couple of new posts already, I've enjoyed my switch over to Jekyll, and I'm impressed by how fast it is. I'd love to experiment with some other Static Site Generators like [Middleman](https://middlemanapp.com/), but I don't think I'll be moving to another solution anytime soon.

I hope this guide was helpful! Feel free to contact me with any questions.
