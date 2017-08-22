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

Customers often ask me how much **time** would it take me to **build** a CI/CD **pipeline**. When I answer that I could set something up in a day customers react surprised. 

The right answer is of course: **_it depends_**. For example what capabilities should the pipeline have: test automation, auto-scaling, dashboards, authentication, etc. In this post, I will explain how I set up a **simple pipeline** for this **website**. It only took me a couple of minutes. You will have your HTML and javascript files (source code) and a place where to store and host the files and maybe a domain name. 

So people who are still running their blog on WordPress website should read on and take a step into the **future** of building and running a **fast** and **modern** website. My next blog will cover a more elaborate pipeline with more capabilities.

# Components
I am using the awesome static website generator **_Hexo_** for the Prospire website. Hexo is javascript based static website **generator** inspired on _Hugo_, the Golang variant of a static website generator. My source code I will store on Github. 

Created a new organization on Github and a repository that will be the **new home** of the source code for www.prospire.nl:

<img src="prospire-github-account.jpg" alt="prospire org on github" style="width: 100%;">

Now create your own website locally and push the first result to Github and **publish** the static website. First, have a look Hexo website for [installing Hexo](https://hexo.io/) on your computer and push your website to Github:


``` bash bash
hexo init my-new-website
cd  my-new-website
git init
git add .
git remote add origin git@github.com:[username]]/my-new-website.git
git push
```

# Static Website Hosting
Now you need a platform to host your website. There are a couple of options. You can roll your own (S3 for example) or easily use GitHub pages, but I was wondering if there would be something better out there. After some googling, I stumbled upon [github pages vs netlify](https://www.netlify.com/github-pages-vs-netlify/) and immediately I was curious about specific **features** like _**split testing**_ and _**form handling**_. So I went for Netlify.

Using Netlify is super **easy**. Just connect Netlify to your repo and make sure to add the correct build command: ```hexo deploy``` and publish directory: ```public```. Now optionally configure Netlify DNS and use the [branches as subdomain](https://www.netlify.com/docs/custom-domains/#branch-subdomains) feature or [configure the DNS](https://www.netlify.com/docs/custom-domains/#dns-configuration) at your domain name hoster. Now when I push **changes** to my git repo, Netlify **triggers** a **deploy**. If successful in a couple of seconds later, the changes are **live**.

c'est tout
