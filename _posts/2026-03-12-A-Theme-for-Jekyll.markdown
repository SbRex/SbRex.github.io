---
layout: single
title:  "Theme for Jekyll"
date:   2026-03-12 12:09:00 +0100
categories: jekyll update
toc: true
---
Hi. I did not surrender, I want to change theme for my Jekyll website. I found out there are few "basic" themes, somewhat "default" with Jekyll. 

### Midnight
Midnight is a simple, dark and aesthetically pleasing one, so I'm trying to include it.
Following the install guide from the [Midnight GitHub Page](https://github.com/pages-themes/midnight?tab=readme-ov-file) i added these lines to my _config.yml:
```
remote_theme: pages-themes/midnight@v0.2.0
plugins:
- jekyll-remote-theme # add this line to the plugins list if you already have one
```
and since I want to preview the site(themed) offline locally i also added to the GemFile:
```gem "github-pages", group: :jekyll_plugins```

Looks like you can also add this self descriptive line:
```tagline: [A very short description of your site's purpose, used as subtitle]```
and
```
show_downloads: ["true" or "false" (unquoted) to indicate whether to provide a download URL]
google_analytics: [Your Google Analytics tracking ID]
```
I only added the downloads one, don't know enough about google analytics. 

### Problems
The Midnight GitHub page gives this instructions...

To use the Midnight theme:

1. Add the following to your site's _config.yml:
```
remote_theme: pages-themes/midnight@v0.2.0
plugins:
- jekyll-remote-theme # add this line to the plugins list if you already have one
```
2. Optionally, if you'd like to preview your site on your computer, add the following to your site's Gemfile:
```
gem "github-pages", group: :jekyll_plugins
```

So since I'm hosting on GitHub AND locally, I ASSUMED that I should add all the instructions.

Does not tell you that you need to "bundle install" to install the missing gems so I did that.
But the problem seems to comes up because you give 2 ways to install the theme. The first trough the remote_theme method the second with the gem based one. These 2 seem to collide and fucking nothing works.

After some try I decided to go with the gem method so I can see this both locally and online.

I added the lines to the gemfile but after the ```bundle install``` and the ```bundle exec jekyll serve``` the server starts but the home page is blank.

### Finally a solution

The Midnight theme is a very BASIC theme, though for static single page websites.
There is only 1 layout so I had to manually change it in the ```index.markdown```(old one was "home") and from all of my posts(inside ```_post``` folder)
Since the layout is so simple the default index does not show anything by default, even the posts are not shown until I manually edit the index.markdown with the lines:
```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      (<span>{{ post.date | date: "%b %d, %y" }}</span>)
    </li>
  {% endfor %}
</ul>
```

### Conclusion

Now everything works but I'm not sure this template is right for my use case.
Maybe be better to edit the default theme(minima) to tailor it around my needs.

See you soon for other mishaps
-Sbrex
