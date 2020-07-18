---
layout: post
title: "How to set up a Github blog?"
author: "Zhi"
categories: journal
tags: [documentation,sample]
image: mountains.jpg
---


There is Github Pages, so one may set up an elegant Github blog.

Github enables markdown files uploaded to be published as blogs. So if one builds a basic repository (=repo） as a structure, he may "blog like a geek" later by uploading .md files.

In fact, Mr. Paul Le [said so](https://lenpaul.github.io/Lagrange/journal/getting-started.html):
> The beauty of hosting your website on GitHub is that you don’t have to actually have Jekyll installed on your computer. 

I decided to use Mr. Paul Le's theme [Lagrange](https://github.com/LeNPaul/Lagrange/), it's tidy and gentle. Let me tailor it to be my basic repo. 

The key task is to copy all the files in his repo to my repo in **master** branch. 

(So we can't do it by "Clone" or "Fork" because the data won't be copied in the master branch. We can take the concept of master branch this way: a Github repo is invisibly organized as a tree for the convenience of team work. Team members work in sub-branches independently and a manager may accept the changes into master branch.)

Here are the steps:

1. New a repository with the name "username.github.io". In my case, dersu-git.github.io.
2. In the setting of the repository (repo), choose a theme. Then browse https://username.github.io, one might see the blog.
3. Replace the whole repo. Talk later.
4. Personalization. Traverse each file, one might know which part need to be modified.


Back to Step 3, there are two ways to build the basic repo, i)by Git command or ii)by Github webpage functions to upload files one by one -- theoretically, I didn't try it. 

Let me introduce the git command solution. My plan is to build the basic repo in a local folder, modify the files locally and synchronize all the data to the online Github repo. Here are the operations:

1)In the command window, for me MacOS Terminal, input:
```
git pull origin master
``` 
I see a folder named "Dersu-git.github.io". This is the local copy of the online Github repo. 

2)Back to normal MacOS, delete the few files inside.

3)Download the theme [Lagrange](https://github.com/LeNPaul/Lagrange/). Copy all the files to the folder. Now I have plagiarized a basic repo.

4)In the command window, switch (cd) to this folder, and "synchronize" all the data to Github by a git command sequence. 

```
git add .
git commit -m "Copy a basic repo"
git push origin master
```
One may see the blog is like the demo site.

BTW, it is also Ok to do "4. Personalization" before synchronization, but I was eager to see what will happen.

Later one can new a Github blog this way: write a markdown file, save it following the naming rule, for example: 2020-06-10-how-to-set-up-a-github-blog.md, copy it to _posts folder and "synchronize" with a specific message in place of "Copy a basic repo".


Acknowledgement: @DWJWendy shared the experience in [a blog](https://www.jianshu.com/p/d7c6e59931f0) which inspired me a lot, and the blog also links to more themes: [Themes](https://hexo.io/themes/), [Jekyll Themes](http://jekyllthemes.org).