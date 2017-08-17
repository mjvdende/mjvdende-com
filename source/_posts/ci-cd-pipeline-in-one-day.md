---
title: CI/CD Pipeline In 1 Day
tags:
  - ci
  - cd
  - tools
subtitle: 'How to build, test and deploy in less than a day'
cover_index: /assets/covers/pipeline.jpg
cover_detail: pipeline-detail.jpg
date: 2017-07-31 13:46:45
---

Last week I have had an interview with a recruiter for a role as DevOps lead and he asked me how much time would it take me to build a CI/CD pipeline for a customer. When I answered that I could set something up for a customer in a day he reacted surprised. 

# It Depends
The right answer was of course: _it depends_. This post I will explain how I set up a simple pipeline for this website. It took me only a couple of minutes. You will have your html en javascript files (source code) and a place where to store and host the files and maybe a domain name. 

# Components
I am using the awesome static website generator _Hexo_ for the Prospire website. Hexo is javascript based static website generator inspired on _Hugo_, the Golang variant of a static website generator. 

So you will need a place to keep your code save. I choose Github because lately Gitlab had issues with uptime. Maybe I will move it to gitlab an other time because it has private repo's for free.

<img src="prospire-github-account.jpg" alt="prospire org on github" style="width: 100%;">

_Created a new organization on Github and the repository that will be the new home of the source code for www.prospire.nl._

Now create your own website locally and start build and push first result to Github and publish static website. Have a look hexo website for [installing Hexo](https://hexo.io/) on your computer and push your website to Github

``` bash bash
hexo init my-new-website
cd  my-new-website
git init
git add .
git remote add origin git@github.com:[username]]/my-new-website.git
git push
```

That's it! Well almost...

# Static Website Hosting
Now you need platform to host your website. There are a couple of options. You can roll your own (S3 for example) or easily use GitHub or Gitlab pages, but I was wondering if there would be something better out there. After some googling, I stumbled upon [github pages vs netlify](https://www.netlify.com/github-pages-vs-netlify/) and immediately I was curious about specific features like _split testing_ and _form handling_. So I went for Netlify.

