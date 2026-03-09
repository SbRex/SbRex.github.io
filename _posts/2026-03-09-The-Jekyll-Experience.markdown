---
layout: post
title:  "The Jekyll Experience!"
date:   2026-03-09 12:09:00 +0100
categories: jekyll update
---
Hi, I'm Matteo. Today I installed(?) the Jekyll application on my Fedora system to create a blog-like website thanks to GitHub pages.

### What is Jekyll
Jekyll is an application which enable users to make a blog-like website hosted on GitHub(Github Pages). Jekyll is made with Ruby. Ruby is a programming language.
Apps made in ruby are referred as "Gems" 💎

The first steps to install Jekyll is to install Ruby and its dependancies.
Having installed gems with "sudo" command before I had problems executing the commands.
I started anew using this command:
```sudo dnf install ruby-devel gcc gcc-c++ make redhat-rpm-config```
then:
```
echo '# Ruby Gems Path' >> ~/.bashrc
echo 'export GEM_HOME=$HOME/.gem' >> ~/.bashrc
echo 'export PATH=$HOME/.gem/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
```
to tell the system to install "Gems" inside the system "home" folder
Jekyll is a Gem so then it's possible to install with:
```gem install jekyll bundler```
to check the istallation
```jekyll -v```

After the creation of the repository in github, in my case SbRex.github.io, I cloned the repository with Git.
So cd ~/path/SbRex.github.io
then
```jekyll new . --force```
"--force" is used if there are git files inside(only README.md was present)
Jekyll use a file call Gemfile to know which plugin to load. Using:
```bundle install```
will download the necessary files.
Finally to launch the local server:
```bundle exec jekyll serve```
I receive quite some "Deprecation Warning" during this process but going to http://localhost:4000/ or http://127.0.0.1:4000/ shows me the correct page so everything went trough.

### Hands-on the Jekyll enviroment
it's possible to customize the "website" editing the ```_config.yml``` file (needs to restart the service to update, creating or editing posts does not require to restart the service).
The posts are stored inside the ```_posts/``` folder and they MUST follow the naming system ```AAAA-MM-DD-title.md or .markdown```.
