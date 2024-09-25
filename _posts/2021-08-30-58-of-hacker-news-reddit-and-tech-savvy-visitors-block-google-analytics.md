---
layout: post
title: 58% of Hacker News, Reddit and tech-savvy audiences block Google Analytics
description: Is Google Analytics still useful and how accurate are its stats?
  How much data is missing from Google Analytics due to adblockers and
  privacy-friendly browsers?
slug: /google-analytics-adblockers-missing-data
date: 2021-08-31T07:20:38.038Z
author: marko-saric
image: /uploads/blocking-google-analytics.png
image-alt: 58% of Hacker News, Reddit and tech-savvy visitors block Google Analytics
---
There are several [privacy concerns with running Google Analytics](https://plausible.io/blog/remove-google-analytics) but there are worries about data accuracy too. How much data is missing from Google Analytics due to adblockers and privacy-friendly browsers?

1. Ordered list
{:toc}

## Do adblockers stop Google Analytics?

Several browsers, including Firefox, Brave and Safari, interfere with Google Analytics and Google Tag Manager tracking. Google Analytics and Google Tag Manager calls are blocked by many adblockers too. This makes site owners wonder whether Google Analytics is still useful and whether its stats are accurate.

The level of Google Analytics blockage varies by industry, audience, the device used and the individual website. In [a previous study](https://markosaric.com/google-analytics-blocking/), I've found that less than 10% of visitors block Google Analytics on foodie and lifestyle sites but more than 25% block it on tech-focused sites.

But how about a very tech-heavy website with a tech-savvy audience of hackers, developers and the like? How many visitors do sites that use Google Analytics miss out on from referral sources such as Hacker News or Reddit? Let's find out.

## Google Analytics and Plausible Analytics stats comparison

I looked at analytics of a site that had a post trending on Hacker News and Reddit with more than a thousand upvotes and more than a thousand comments.

I compared stats between [Plausible Analytics](https://plausible.io/) and Google Analytics. Google Analytics was installed using the default method. Plausible was installed [using a proxy](https://plausible.io/docs/proxy/introduction) to get the most accurate data on the level of blockage. Plausible proxy runs as a first-party connection and is only blocked by those visitors who block JavaScript entirely. It is not blocked by any browser or adblocker.

Here's the data Plausible Analytics shows for the three days in late August 2021 when the site got a lot of traffic. Plausible allows you to share your dashboard publicly so you can explore [these stats here](https://plausible.io/markosaric.com?period=custom&from=2021-08-26&to=2021-08-28).

![Plausible Analytics stats](/uploads/plausible-analytics-stats-hn-post.png)

And here's the [Google Analytics](https://plausible.io/vs-google-analytics) data for the same site and the same period.

![Google Analytics stats](/uploads/google-analytics-stats-hn-post.png)

It turns out 58% of Hacker News readers, Reddit users and other techies block Google Analytics. Tech-heavy audiences use adblockers and privacy-friendly browsers much more than the average web user. Let's take a closer look at the numbers.

## 58% of visitors block Google Analytics
 
Here's a look at the overall traffic numbers and the difference between Plausible and Google Analytics. Google Analytics is not showing all traffic. It is missing data from 58.67% of all visitors and 58.38% of all page views. Google Analytics is underreporting the tech-savvy audiences by almost 60%. 

Metric | Plausible | Google Analytics | Difference
| ------ | ------ | ------ | ------
Visitors | 50,947  | 21,054 | 58.67%	
Pageviews | 60,731  | 25,275 | 58.38%

Let's now look at the segments of users that cannot be tracked accurately in Google Analytics.

## 68% of laptop and desktop users block Google Analytics

At the device level, laptop and desktop users (68.2%) block Google Analytics more frequently than mobile and tablet users (49.9%). 

This makes sense especially considering how difficult it is to install an adblocker on Chrome, the most popular browser on mobile devices.

Device | Plausible | Google Analytics | Difference
| ------ | ------ | ------ | ------
Mobile/Tablet | 27,331  | 12,848 | 49.9%	
Laptop/Desktop | 25,725  | 8,181 | 68.2%		

## 88% of Firefox users block Google Analytics

Here's a look at the browsers and which browser users block Google Analytics most frequently. 

Surprisingly, Safari users with [Safari's Intelligent Tracking Protection (ITP)](https://plausible.io/blog/safari-privacy-report) block Google Analytics only in 41.41% of cases while 88.28% of Firefox users block it.

Browser | Plausible | Google Analytics | Difference
| ------ | ------ | ------ | ------
Chrome | 16,405  | 8,133 | 50.42%
Safari | 16,136  | 9,454 | 41.41%
Firefox | 15,192 | 1,780 | 88.28%
Edge | 1,059 | 301 | 71.58%

## 82% of Linux users block Google Analytics

Here's a look at the operating systems and which OS users block Google Analytics most frequently. iOS users block Google Analytics least frequently at 41.5% while 82.3% of Linux users block it.

OS | Plausible | Google Analytics | Difference
| ------ | ------ | ------ | ------
Mac | 13,905  | 5,325 | 61.7%
iOS | 13,631  | 7,978 | 41.5%
Android | 10,684  | 4,914 | 54%
Windows | 6,892  | 1,764 | 74.4%
Linux | 5,680  | 1,006 | 82.3%

## Adblockers or bots or something else?

Could this difference be caused by anything else other than adblockers? Perhaps Google is ignoring bots and other crawlers? Can we verify that Plausible isn’t over-reporting?

Both Plausible Analytics and Google Analytics automatically exclude bots and crawlers. We are both JavaScript-based tools and exclude any known non-human traffic by default. Although, Plausible does a better job by exluding ~32K data center IP ranges (i.e. a lot of bot IP addresses) by default. Google Analytics still requires a lot of manual exclusions. You can check this study between [Plausible and server logs](https://plausible.io/blog/server-log-analysis) to see the number of bots that Plausible excludes.

It’s worth noting that it’s rare for the data from two analytics providers to have complete parity. Plausible and Google Analytics have different measurement methodologies and define specific metrics differently. Even if there were no blockers at all, slight differences in data between Plausible and Google Analytics were likely to be seen.

To track unique visitors, [Google Analytics uses cookies](https://plausible.io/blog/google-analytics-cookies). Plausible is a cookie-free tool and [tracks unique visitors differently](https://plausible.io/data-policy). 

Plausible doesn't use any long term identifiers as we're a [GDPR compliant web analytics](https://plausible.io/blog/google-analytics-gdpr) tool. This means that the same person visiting a site multiple times in one day would be seen as one unique visitor but that same person coming back a few days later would be seen as another unique visitor.

Google's method is not bulletproof either as visitors using incognito mode would be new unique visitors and same would those who block or clear cookies.

For three days, the difference this makes would be minimal. The difference could get larger over a longer period especially on sticky sites where the same people return back daily. The top sources of traffic for this site were Hacker News and Reddit and they are notorious for traffic that bounces quickly and doesn't return.

Because Plausible and Google Analytics measure unique visitors differently, I also looked at the total pageviews. These should be identical but they show pretty much the same difference as unique visitors.

All in all, the difference in stats would mostly come from people blocking the Google Analytics script. Google Analytics is listed on many blocklists while the Plausible proxy runs as a first-party connection and is not.