---
layout: post
title: Setting Up GitHub Pages With a Custom Domain
---
I find GitHub Help strange to navigate and can be hard to comprehend sometimes. Here is a short and concise way to handle something I came across the other day that I was having a hard time finding an up-to-date article for: __Linking a Custom Domain with my GitHub Pages site__.

Prerequisites:

- GitHub Pages site set up at `[githubusername].github.io`.
- a custom domain

Let's get started. You can either configure your domain or GitHub first. Order does not matter.

## GitHub

Go to your GitHub repository and click on "Settings." Scroll down to "GitHub Pages" and under "Custom domain" add your domain, e.g. `google.com`, `yahoo.com`, etc. and click "Save." This will automatically create a file named `CNAME` in your repositories root directory.

You can achieve the same effect by pushing or saving a file named `CNAME` with your domain name as the contents of the file, e.g. `google.com`, `yahoo.com`, etc.

You do not have to worry about setting up HTTPS as GitHub Pages naturally enables this functionality. __This will not work at first__ and usually takes 24 hours or so to get set up. You can also enforce it by going to "Settings" within your repository and check "Enforce HTTPS" under "GitHub Pages."

## Your DNS Provider

Add `A` Records that point to the following IP addresses: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` with a Host value of `@` for each.

If you are new to all of this, it is good to know that your site will __not__ automagically point to `http://www.[yourdomain].com`, it will only point to `http://[yourdomain].com`. To get this to work, add a `CNAME` record in your DNS provider with the Host value `www` that points to your `[githubuser].github.io` page. You could also give the Host value something like `blog` to point your `github.io` URL to `blog.[yourdomain].com`.

