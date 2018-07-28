---
layout: post
title:  "Your Guide to Mobile Publishing Formats: AMP, Facebook Instant Articles, and Apple News"
date:   2016-12-13
categories:
permalink: blog/mobile-publishing-formats
---

When’s the last time you gave up on a website because it took too long to load on your phone? Or encountered an ad interstitial on your tablet that mysteriously had no way to close? Slow and poorly-designed pages on mobile devices suck. They gobble up data and kill user experience.  

In response, tech behemoths have created solutions to optimize content on mobile devices, what I’ll refer to as Mobile Publishing Formats. You’ve probably heard of at least one of the three most popular: Accelerated Mobile Pages (AMP), Facebook Instant Articles, and Apple News.

If you’d like to dive into specific information about each right away:

- [Accelerated Mobile Pages (AMP)](https://www.viget.com/articles/your-guide-to-mobile-publishing-formats-amp-facebook-instant-articles-and-apple-news/#amp) 
- [Facebook Instant Articles](https://www.viget.com/articles/your-guide-to-mobile-publishing-formats-amp-facebook-instant-articles-and-apple-news/#fbia) 
- [Apple News](https://www.viget.com/articles/your-guide-to-mobile-publishing-formats-amp-facebook-instant-articles-and-apple-news/#an)

### A Sad State of Mobile Web Affairs

We’ve come a long way in the past few years. Giant pandas are no longer endangered. Self-driving Ubers are already on streets. Apparently your next roof will be made of solar shingles. Great, but why is the mobile web still so frustrating?

Today’s average web page requires users to download [2.5MB of data](http://www.httparchive.org/interesting.php?a=All&l=Nov%2015%202016), and that number is only growing. To put this into perspective, that’s the [same amount of data](https://www.wired.com/2016/04/average-webpage-now-size-original-doom/) it takes to download the original DOOM game or roughly two 3.5in floppy disks. Back in 2010, the average web page was just over 700KB, so how did we get here? Ask a developer, and they’ll likely mention something about bloated javascript libraries, advertising scripts, uncompressed images, and large videos.

This isn’t a small issue, either. Industry reports suggest [mobile traffic is nearing or has surpassed desktop traffic](http://marketingland.com/mobile-top-sites-165725). For some websites, nearly all traffic comes from mobile devices. In fact, [90%](http://thenextweb.com/facebook/2016/01/27/90-of-facebooks-daily-and-monthly-active-users-access-it-via-mobile/) of Facebook's daily active users access it via mobile. For more on the ubiquity of mobile, check out [Mitch](https://www.viget.com/about/team/mdaniels)’s recent [State of the Web presentation](https://www.viget.com/articles/state-of-the-web-2016).

Just as we became accustomed to mobile devices and faster internet, new tools allowed us to add media and integrations more easily than ever before. Unfortunately, that content often isn’t small or compressed. That’s not a big deal if you have a 40Mbps connection on a laptop, but it’s a very big deal if you have a 2Mbps mobile connection or a limited data plan.

Most users expect pages to load [as fast on phones](https://blog.radware.com/applicationdelivery/applicationaccelerationoptimization/2014/10/report-2014-state-of-the-union-for-mobile-ecommerce-performance/) as they do on desktops, so clearly some are being left unsatisfied. During a recent page speed analysis for a large ecommerce site, we found that every additional second a page took to load correlated with a 2.7% increase in exit rate. [Other studies](https://www.soasta.com/blog/mobile-web-performance-monitoring-conversion-rate/) have shown a substantial correlation between conversion rate and page load time.

Alright, so we’ve got these heavy pages, but surely they use that weight to provide a decent mobile user experience once they’re loaded, right? Some do, but many websites don’t have a responsive design or at least a corresponding mobile site. It makes me sad every time I have to pinch, zoom, and drag to read articles.

Even “mobile-friendly” websites play with my emotions by sending me to advertisers when I just wanted to scroll down a page, though admittedly my fingers may be too fat. And some buttons are so close together I feel like I’m defusing a bomb when I try to choose one. How about pages that keep building even once you’ve started reading? [Throw it on the ground!](https://media.giphy.com/media/1306MTkHlXkUZG/giphy.gif)

Most of these issues are rooted in advertising elements, interactive media, someone demanding my seemingly prized email address, or just poor implementation. Other irksome scenarios for mobile users, as [outlined by Google Webmasters](https://developers.google.com/webmasters/mobile-sites/mobile-seo/common-mistakes) include:

- Unplayable Content
- Faulty Mobile Redirects
- [Annoying Interstitials](https://webmasters.googleblog.com/2016/08/helping-users-easily-access-content-on.html)
- Small Font Size

There are billions of web pages full of quality content, but in many cases, that content is difficult to access via mobile. In turn, mobile users are frustrated and driven away. What’s a tech giant to do?

### The Emergence of Mobile Publishing Formats

Google, Facebook, and Apple have created solutions to deliver “instant” content on mobile and keep users on their own platforms. These Mobile Publishing Formats all deliver fast content by using world-class servers and markup that adheres to specific guidelines. Facebook claims their Instant Articles solution is 10 times faster than standard mobile web articles. Google says AMP pages load 4 times faster and use 10 times less data than equivalent non-AMP pages. [Fast](https://bruceleeeowe.files.wordpress.com/2009/11/warp-drive1.gif).

These formats also standardize content design and limit what publishers are able to insert into articles, particularly when it comes to interactive elements and advertising. Remember moving from a chaotic, gif-ridden, tile-background-patterned MySpace page to a clean, structured Facebook profile? It’s kind of like that, but for mobile content.

### But Why?

One important motivation in creating these Mobile Publishing Formats, especially for Facebook and Apple, is to keep users on their own platform. Most of Facebook’s audience uses mobile devices, and many users access the site solely through a mobile device. Some even suggest that Facebook is using Instant Articles [to sidestep Apple’s mobile browser restrictions](https://www.theverge.com/2015/7/20/9002721/the-mobile-web-sucks). Apple, the [largest](https://www.statista.com/statistics/273697/market-share-held-by-the-leading-smartphone-manufacturers-oem-in-the-us/) smartphone manufacturer in the United States and [second-largest](http://www.gadgetsnow.com/slideshows/5-biggest-smartphone-makers-of-the-world/photolist/52375163.cms) worldwide, obviously has a huge stake in their mobile users.

As readers consume mobile content that adheres to Mobile Publishing Formats, they find it easier to discover more by navigating back to either the Newsfeed, Apple News app, or Google results page. This is great for those platforms, but not quite as exciting for content publishers. It’s easier than ever to reach new audiences, yet drawing users further into their other content can prove difficult.

Above all, money is on the line. That’s not to say these organizations can’t make the world a better place while earning a profit, but Google, Facebook, and Apple run the world’s largest digital ad networks. Each commands a huge share of the internet’s audience and are [top referrers](http://fortune.com/2015/08/18/facebook-google/) to news sites.

If these solutions seem less than selfless to you, you’re not alone. Are they evil? No. Are they antithetical to the idea of a free and open internet? Possibly. Some argue that these formats make it [harder to publish content to the internet](https://www.recode.net/2016/10/20/13318746/online-publishing-platform-amp-facebook-instant-articles-apple-news) and easier for [fake news to masquerade as legitimate](https://www.theverge.com/2016/12/6/13850230/fake-news-sites-google-search-facebook-instant-articles). Others have provided alternatives, [such as CPP](https://timkadlec.com/2016/02/a-standardized-alternative-to-amp/). Opponents have called these formats [fake fixes](http://idlewords.com/talks/website_obesity.htm#fixes) and the [saddest refutation of the open web revolution](https://www.theverge.com/2015/7/20/9002721/the-mobile-web-sucks).

Google seems to address this from a more open stance, while Facebook and Apple are actively striving to keep readers on their own platforms where they have more control, consistency, and conveniently don’t have to deal with ad blockers.

Now let's take a closer look at the three main Mobile Publishing Formats:

|                                  | Accelerated Mobile Pages (AMP) | Facebook Instant Articles | Apple News               |
|----------------------------------|--------------------------------|---------------------------|--------------------------|
| Accessible by URL                | Yes                            | No (Facebook App Only)    | No (Apple News App Only) |
| Speedy                           | Yes                            | Yes                       | Yes                      |
| Themes                           | No                             | Yes                       | Yes                      |
| Design Customization             | Yes                            | Yes                       | Yes                      |
| Estimated Implementation Effort  | Medium to High                 | Medium                    | Low                      |
| SEO Benefits                     | Yes                            | No                        | No                       |
| Approval Needed                  |                                | Yes                       | Yes                      |
| Open Source Specification        | Yes                            | No                        | No                       |
| 3rd Party Analytics Integrations | Yes                            | Yes                       | No                       |

### Accelerated Mobile Pages (AMP)

>The Accelerated Mobile Pages (AMP) Project is an open source initiative that makes it easy for publishers to create mobile-friendly content once and have it load instantly everywhere.  
- [AMPProject.org](https://www.ampproject.org/)

In October 2015, [Google announced AMP](https://googleblog.blogspot.com/2015/10/introducing-accelerated-mobile-pages.html), with the aim of improving the performance of the mobile web. Google began rolling out AMP in organic search in February 2016, specifically in the “top stories” module. In September 2016, AMP content [began appearing](http://www.thesempost.com/amp-results-now-live-googles-organic-search-results/) in the main section of Search Engine Results Pages (also known as the “10 blue links”). That gray lightning symbol in Google’s organic search results indicates a page adhering to AMP standards.

At its core, AMP focuses on simplicity and performance. This format highly restricts Javascript usage and unnecessary mobile elements. It also provides SEO benefits. When displaying results on a mobile device, Google will show an AMP page (if available) [instead of the mobile or desktop page that would normally appear](https://moz.com/blog/google-amp-search-results). While AMP is led by Google, it’s an open source project that you can [contribute to](https://github.com/ampproject/amphtml). Other platforms, including Twitter, are also using AMP to cache and render content at very fast speeds.  

In terms of tracking, Google allows integrations with analytics providers, with an [unsurprisingly tight Google Analytics setup](https://developers.google.com/analytics/devguides/collection/amp-analytics/). For more information on AMP analytics solutions, be sure to review [this Google Tag Manager setup](https://www.simoahava.com/analytics/accelerated-mobile-pages-via-google-tag-manager/) by Simo Ahava. Google has also created a new section in [Search Console](https://www.google.com/webmasters/tools/home?hl=en&pli=1) that provides information about a website’s integration with AMP and has recently opened up the format to [A/B testing](http://www.thesempost.com/amp-now-supports-ab-testing/).

However, there are a few caveats. Design can get hairy when retro-fitting content, especially if you have a few thousand pages on a site. Technical implementation is also [trickier](https://www.viget.com/articles/lessons-learned-working-with-googles-amp) than other formats. Luckily there’s quite a bit of documentation from Google, as well as handy resources like [AMP by Example](https://ampbyexample.com/). 

That said, AMP can be used as a substitute for a responsive, mobile-friendly site. According to Paul Bakaus, Open Web Developer Advocate at Google, websites can even use AMP for _all_ content pages (including Desktop). He mentions [AMPProject.org](https://www.ampproject.org/) as a site that is 100% AMP and works across all devices and resolutions.

Before you implement AMP, take a look at [Ben Tinsley](https://www.viget.com/about/team/btinsley)’s article here: [Lessons Learned Working with Google's AMP](https://www.viget.com/articles/lessons-learned-working-with-googles-amp).

AMP CMS Plugins/Modules:  

- [Wordpress AMP Plugin](https://wordpress.org/plugins/accelerated-mobile-pages/)
- [Drupal AMP Module](https://www.drupal.org/project/amp)
- [Craft AMP Plugin](https://straightupcraft.com/craft-plugins/amplify)
- [Accelerated Mobile Pages Project – Getting Started](https://www.ampproject.org/docs/get_started/create)

### Facebook Instant Articles

>Create fast, interactive articles on Facebook. Instant Articles load up to 10 times faster than the mobile web. Powerful creative tools help publishers bring their stories to life in new ways, like tilt-to-pan photos, auto-play video, embedded audio captions, and interactive maps.  
- [InstantArticles.FB.com](https://instantarticles.fb.com/)

The first of the three main Mobile Publishing Formats to be announced, Facebook Instant Articles launched in May 2015. At first, only select publishers (like National Geographic and the New York Times) were allowed to participate, but Instant Articles was [opened to all publishers](https://media.fb.com/2016/04/12/instant-articles-now-open/) in April 2016. [That month](https://media.fb.com/2016/04/12/instant-articles-now-open/), Facebook saw more than one thousand publishers join the program.

Facebook has been particularly concerned with optimizing performance on Android (which has a global market share of nearly [90%](https://www.idc.com/prodserv/smartphone-os-market-share.jsp)), since international readers on slower connections [consume up to 40%](https://media.fb.com/2016/04/12/instant-articles-now-open/) more Instant Articles than mobile web articles. The claim that Instant Articles load 10 times faster than standard mobile web pages and result in more engagement is an enticing offer to publishers. As mentioned earlier, Facebook is also the [top referrer](http://fortune.com/2015/08/18/facebook-google/) for news. In short, if a substantial amount of your traffic comes from Facebook, you should look into Instant Articles.

The ad model for Facebook Instant Articles allows publishers to sell their own inventory and keep all ad revenue, while extra inventory is sold by Facebook, which takes a 30% cut. Built on Facebook’s Audience Network, some say the ad network has allowed them to [monetize content better](http://www.wsj.com/articles/facebooks-instant-articles-advertising-fixes-win-over-publishers-1455218551) than they could have themselves. Still, many are not impressed by the lack of control over content, and other publishers are [more bearish on returns](http://digiday.com/publishers/google-expands-amp-presents-friendly-face-publishers/).

There are a few additional stipulations for submitting content as Instant Articles. Publishers must have a Facebook Page and use Facebook’s Business Manager app. They must also have at least 5 articles that Facebook can review.

An obvious downside is that offering content on Facebook’s own closed ecosystem makes it harder to hook users into additional publisher content. Publishers also have less control over navigation and media. Some worry that their own branding is eroded by using Facebook’s platform, which offers few differentiating design elements. Facebook also has final say on whether or not publishers will be approved.

Facebook does allow for [analytics integrations](https://developers.facebook.com/docs/instant-articles/analytics), though depending on a website’s setup, [dark social](https://www.theatlantic.com/technology/archive/2012/10/dark-social-we-have-the-whole-history-of-the-web-wrong/263523/) traffic could occur as users navigate to other content from the Facebook app.

FBIA CMS Plugins/Modules:

- [Wordpress Instant Articles Plugin](https://wordpress.org/plugins/fb-instant-articles/)
- [Drupal Instant Articles Module](https://www.drupal.org/project/fb_instant_articles)
- [Facebook Instant Articles Publisher Approval](https://developers.facebook.com/docs/instant-articles/get-started/article-review)
- [SDK - Instant Articles - Documentation - Facebook for Developers](https://developers.facebook.com/docs/instant-articles/sdk)

### Apple News

>With Apple News Format, you can create engaging content for Apple News. Elegant layouts, beautiful typography, photo galleries, videos, and animations bring your stories to life. You can author once and News will optimize for all iOS devices, so your readers will have a great experience no matter which device they’re using.  
- [Developer.Apple.com/News-Publisher](https://developer.apple.com/news-publisher/)

Apple News was first launched in September 2015, replacing the old Newsstand app. It lives completely within Apple’s own ecosystem. Fortunately, initial Apple News setup is relatively painless. It hooks into existing RSS feeds, and there are already integrations available for most CMSs. As an audience bonus to publishers, the Apple News app comes preinstalled on all iOS devices in the US, UK, and Australia.

Because Apple News is a closed environment like Facebook Instant Articles, Apple has total control and all publishers must first be approved. Similar to Facebook’s model, Apple’s ad network, iAd Workbench, allows publishers to sell ads and keep that revenue, and any additional inventory can be backfilled from Apple with [70%](https://developer.apple.com/library/content/documentation/General/Conceptual/iAd_News_Advertising/OpportunityInNews.html#//apple_ref/doc/uid/TP40016664-CH2-SW3) of ad revenue sent to the publisher. Apple News allows for little customization in terms of design but displays content beautifully.

While implementation is straightforward, Apple News’ RSS bot has [received criticism](https://www.slightfuture.com/webdev/excessive-applenewsbot-requests) for its poor execution and propensity to overload servers at times, which can create a subpar experience for real visitors. Some publishers have mentioned increased visitations after implementation but [difficulty in monetizing that traffic](http://digiday.com/publishers/apple-news-sending-publishers-traffic-not-revenue/). 

When publishers submit an RSS feed to Apple News, there are a number of [technical requirements](https://newsresources.apple.com/en/faq/RSS_Overview#80591595), and some content may require adjustments in order to comply with Apple's terms of service, like removing certain advertisements for [the Apple News bot](https://www.slightfuture.com/technote/applenews-user-agent). Note that using Apple News format is not technically required to be featured in Apple News since it's possible to provide content solely through an RSS feed. Any user can navigate to an RSS feed in Safari to subscribe to that news source in Apple News, and an edition of that feed will be available for that user.

Unlike other Mobile Publishing Formats, Apple News is [far less inclined](https://www.idropnews.com/how-to/how-publishers-can-track-apple-news-traffic-with-google-analytics/22049/) to share user data with outside analytics software. Instead, Apple’s internal analytics will show the number of readers and some information around sharing.  

Apple News CMS Plugins/Modules:

- [Wordpress Apple News Plugin](https://wordpress.org/plugins/publish-to-apple-news/)
- [Drupal Apple News Module](https://www.drupal.org/project/applenews)
- [Craft Apple News Plugin](https://craftcms.com/apple-news)
- [Apple News Publisher Approval](https://developer.apple.com/news-publisher/)

### The Choice is Yours

How can publishers determine which Mobile Publishing Format is the best fit for their content? For publishers focused on SEO, AMP is likely to be the most important option. Those who operate most heavily in social media should prioritize Facebook Instant Articles. If a target audience is iOS users, Apple News is a smart choice.

As a summary, the benefits can be very real, and Mobile Publishing Formats promise faster loading times, increased social sharing, decreased abandonment, and longer reading time – all amounting to a better user experience. However, each has a very real cost in implementation and upkeep. For each Mobile Publishing Format, publishers also relinquish some content discoverability and design control in the form of image limitations and removed navigation elements. Additionally, publishers may be required to hand over some authority of their content to external parties..

Each Mobile Publishing Format offers a distinct solution to publish optimized and accessible mobile content. Ultimately, it comes down to balancing potential new audiences, different monetization strategies, and control over your own content and audience. [The choice is yours.](https://www.youtube.com/watch?v=sLVawsuhlzY)

--

_For some other great resources on the subject, be sure to review:_

- _[Accelerated Mobile Pages Project](https://www.ampproject.org/) and accompanying [Developer Docs](https://www.ampproject.org/docs/get_started/create) from ampproject.org_
- _[Facebook Instant Articles](https://instantarticles.fb.com/) and accompanying [Developer Docs](https://developers.facebook.com/docs/instant-articles) from developers.facebook.com_
- _[Apple News](https://www.apple.com/news/) and accompanying [Developer Docs](https://developer.apple.com/news-publisher/) from developer.apple.com_
- _[From WordPress to Apple News, Instant Articles, and AMP](http://mediatemple.net/blog/tips/wordpress-apple-news-instant-articles-amp/) by Chris Coyier_
- _[A Technical Review Of Adding Support For Google's AMP Pages](http://blog.robertelder.org/adding-support-for-amp-pages/) by Robert Elder_
- _[Why I prefer Google AMP pages to Facebook Instant Articles](http://venturebeat.com/2016/08/14/google-amp-vs-facebook-instant-articles/) by Jordan Novet_
- _[The mobile web sucks](https://www.theverge.com/2015/7/20/9002721/the-mobile-web-sucks) by Nilay Patel_
- _[How Google's AMP Will Influence Your Online Marketing](https://moz.com/blog/how-googles-amp-will-influence-your-online-marketing) by Chapman Lever_
- _[Facebook Instant Articles: What They Are, How They Work and 5 Things You Need to Know](https://blog.bufferapp.com/facebook-instant-articles) by Ash Read_
- _[Progressive Web AMPs](https://www.smashingmagazine.com/2016/12/progressive-web-amps/) by Paul Bakaus_

--

_Special thanks to [Ben Tinsley](https://www.viget.com/about/team/btinsley), [Mitch Daniels](https://twitter.com/Ditch_Maniels), [Andy Crestodina](https://twitter.com/crestodina), [Paul Bakaus](https://twitter.com/pbakaus), [Daniel Aleksandersen](https://twitter.com/Aeyoun), and others __for sharing feedback on this piece._


_This article was originally published on [Viget](https://www.viget.com/articles/your-guide-to-mobile-publishing-formats-amp-facebook-instant-articles-and-apple-news/)._
