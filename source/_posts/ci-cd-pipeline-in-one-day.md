---
title: CI/CD Pipeline In 1 Day
tags:
  - ci
  - cd
  - tools
subtitle: 'How to build, test and deploy in less than a day'
cover_index: /assets/covers/pipeline.jpg
date: 2017-07-31 13:46:45
---

Last week I have had an interview with a recruiter for a role as DevOps lead and he asked me how much time would it take me to build a CI/CD pipeline for a customer. When I answered that I could set something up for a customer in a day he reacted surprised. 

# It Depends
The right answer was of course: _it depends_. This post I will explain how I set up the simple pipeline for this website. It took me only a couple of minutes. 

I am using the awesome static website generator _Hexo_ for my prospire. Hexo is javascript based static website generator inspired on _Hugo_, the Golang variant of a static website generator. 

# Components
So you will need source code, online source code repository and a platform to host your website. The first two are obvious but for the latter, there are a couple of options. You can roll your own or easily use GitHub or Gitlab pages, but I was wondering if there would be something better out there. After some googling, I stumbled upon [github pages vs netlify](https://www.netlify.com/github-pages-vs-netlify/) and immediately I was curious about specific features like _split testing_ and _form handling_. So I went for Netlify.

