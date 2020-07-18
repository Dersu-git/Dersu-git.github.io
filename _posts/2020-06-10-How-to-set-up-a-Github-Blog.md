---
layout: post
title: "How to set up a Github blog?"
author: "Dersu"
categories: journal
tags: [documentation,sample]
image: mountains.jpg
---


There is Github Pages, so one may set up an elegant Github blog.

Github enables markdown files uploaded to be published as blogs. So if one builds a basic repo as a structure, he may "blog like a geek" later by uploading .md files.

In fact, Mr. Paul Le said so:
> The beauty of hosting your website on GitHub is that you don’t have to actually have Jekyll installed on your computer. 

I decided to use Mr. Paul Le's theme, it's tidy and gentle. Let me adjust it to be my basic repo. 

The key task is to copy all the files in his repo to my repo in master branch. Here are the steps:

1. New a repository with the name "username.github.io". In my case, dersu-git.github.io.
2. In the setting of the repository (repo), choose a theme. Then browse https://username.github.io, one might see the blog.
3. Replace the whole repo. Talk later.
4. Personalization. Reading each file, one might know which part need to be modified.


Back to Step 3, there are two ways to build the basic repo, by Git command or by Github webpage functions to upload files one by one. 

Let's introduce the git command solution: build, copy rudely indeed, the basic repo in a local folder, modify the files locally and synchronize all the data to the Github repo.
```
git pull origin master
``` 
There will be a folder as a local copy of the Github repo, delete the few files inside, and switch (cd) to that folder.

Download the theme [Lagrange](https://github.com/LeNPaul/Lagrange/). Copy all the files to the folder, and "synchronize" to Github. 

```
git add .
git commit -m "Copy a basic repo"
git push origin master
```
BTW, it is also Ok to do "4. Personalization" before synchronization, if one is not that eager to see what will happen.

One may see the blog is like the demo site.

Later one can new a Github blog this way: write a markdown file, save it following the naming rule, for example 2020-06-10-how-to-set-up-a-github-blog.md, copy it to _posts folder and "synchronize" with a specific message in place of "Copy a basic repo".


Acknowledgement: @DWJWendy shared the experience in [a blog](https://www.jianshu.com/p/d7c6e59931f0) which inspired me a lot, and the blog also links to more themes: [Themes](https://hexo.io/themes/), [Jekyll Themes](http://jekyllthemes.org).


