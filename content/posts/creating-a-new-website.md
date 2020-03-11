---
author:
  name: "Keivan Shah"
date: 2019-11-08
linktitle: Creating your Static Website
type:
- post
- posts
title: Creating your Static Website
weight: 10
series:
- Hugo 101
---


## Introduction

Creating and hosting a website is something that many of us wondered if not tried to do. While hosting a dynamic website is comparatively challenging, it's quite easy to host a simple [static website](https://techterms.com/definition/staticwebsite) with something like [Github Pages](https://pages.github.com/). So in this post, I try to help people setup up what could potentially be your first website :D

**Note:** Being a developer I just assume that people know the basics of computer programming and can get by with using a little bit of command-line. While I do assume the above, I know that it is not obvious to everyone so don't get discouraged if you do not get things!

### Setting Up Github Pages

First of all, you need a [Github Account](https://github.com/) which I am assuming you have. From here on wherever you find `{YOUR_USERNAME}` replace that with your actual GitHub username.

Github Pages allows you to host **free** static websites for users, your organization and your projects. Ever wondered why many open-source libraries and tools generally have a `*.github.io` website? This is the reason!

So let's get started!

Head over to [GitHub](https://github.com/) and create a new repository named `{YOUR_USERNAME}.github.io`. Ensure that the username matches exactly or else it won't work!

```bash
git clone https://github.com/{YOUR_USERNAME}/{YOUR_USERNAME}.github.io

cd {YOUR_USERNAME}.github.io

# Lets create an intial homepage
echo "Hello World!" > index.html

# Push this website to Github!
git add -A
git commit -m "Initial commit"
git push -u origin master
```

Now fire up a browser and go to https://{YOUR_USERNAME}.github.io. You should be greeted by a `Hello World!`. That's it! You have hosted your first website!

While it might not be much but you can do a lot of things with static websites like the one we created. If you know a bit of `HTML` and `Javascript` you can create some amazing static websites. If you are looking for inspiration, people come up with some amazing creations at [Codepen.io](https://codepen.io/popular/pens/).
Not only that hosting your blogs or documentation for your projects is also not out of the question using static webpages. For example, this website that you are visiting right now is a static website hosted via Github Pages!

So go ahead! Try modifying the `index.html` with some actual `HTML` and `Javascript` to host your first Blog or your Resume maybe. 

But before you start that, it may be better that you also consider working with a static website generator. You can host your blog website by modifying the `index.html` file with links to other `.html` files and `.js` and `.css` files giving it multiple pages and structure. But as the size of your website will increase it will get more difficult to maintain! So that's where a static website generator like [Jekyll](https://jekyllrb.com/) or [Hugo](https://gohugo.io/) comes into the picture! Also, [Jekyll](https://jekyllrb.com/) is integrated into Github Pages itself so it might be worth taking a look into. I might discuss more on this in a later post. 

This is my first post so I decided to keep it simple. I hope that this post was helpful! Thanks for reading! Hoping to see your websites soon! 