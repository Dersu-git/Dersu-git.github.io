---
layout: post
title: "How to set up a Github blog?"
author: "Dersu"
categories: journal
tags: [documentation,sample]
image: mountains.jpg
---


There is Github Pages, so one may set up an elegant Github blog.

Github enables markdown files uploaded to be published as blogs. So if one builds a basic repository (=repo) as a structure, he may "blog like a geek" later by uploading .md files.

In fact, Mr. Paul Le [said so](https://lenpaul.github.io/Lagrange/journal/getting-started.html):
> The beauty of hosting your website on GitHub is that you don’t have to actually have Jekyll installed on your computer. 

I decided to use Mr. Paul Le's theme [Lagrange](https://github.com/LeNPaul/Lagrange/). It's tidy and gentle. Let it be a model blog repo and I tailor it to be a basic blog repo. 

The key task is to copy all the files in his repo to my repo in **master** branch. 

(So we can't do it by "Clone" or "Fork" because the data won't be copied in the master branch. We can take the concept of master branch this way: a Github repo is invisibly organized as a tree for the convenience of team work. Team members work in sub-branches independently and a manager may converge the changes into master branch[1][2][3].)

Here are the steps:

1. New a repository with the name "username.github.io". In my case, dersu-git.github.io.
2. In the setting of the repository (repo), choose a theme. Then browse https://username.github.io, one might see the blog after a tiny while like 30 seconds.
3. Replace the whole repo. Talk later.
4. Personalization. Traversing each file, one might know which part need to be modified. Like _config.yml, _data/setting.yml, _post, menu, favicon.ico. For setting.yml, a disqus account is needed for comments.

Back to Step 3, Build the basic repo by Git command. 

My plan is to build the basic repo in a local folder, modify the files locally and synchronize all the data to the online Github repo. Here are the operations:

1)In the command window, for me MacOS Terminal, input:
```
git --version 
git config --global user.name "myusername"
git config --global user.email "myemailaddress"
```
These commands are optional if one uses git before.

```
git remote set-url origin https://github.com/Dersu-git/dersu-git.github.io
git pull origin master
``` 
(The url is one's own github blog repo link.)

I see a folder named "Dersu-git.github.io". This is the local copy of the online Github repo, my focus.

2)Back to Finder, delete the few files inside the folder.

3)Download the theme [Lagrange](https://github.com/LeNPaul/Lagrange/). Copy all the files to the folder. Now I have plagiarized a basic blog repo locally.

4)In the command window, switch (cd) to the folder, and "synchronize" all the data to the online Github repo by **a git command sequence**. 

```
git add .
git commit -m "Copy a basic blog repo"
git push origin master
```
One may see the blog is like the demo site.

(Let's look at **the git command sequence**. Git is basically a version management protocol[4][5][6]. There is a local invisible folder recording all the modifications and storing files of the newest version. The work flow of git is to modify visible files and 1)add some of the changed files to staging area (by command "git add"). Then 2)commit the changes to the final version by command "git commit". So far all the operations are local and personal. Github is a server hosting the final version and the history for one or for a team. Hence 3)finally push the changes to Github (by command "git push").

<div style="text-align:left;"><img src="{{ site.github.url }}/assets/img/gitcommand.jpg" style="margin-bottom:0px; max-width:80%;" alt=""><p style="font-size:12px">Fig: Git work flow</p></div>

BTW, it is also Ok to do "4. Personalization" before synchronization, but I was eager to see what would happen.

The work flow of setting up the Github blog is demostrated in Fig. Git work flow.

Later one can new a Github blog this way: write a markdown file locally, save it following the naming rule, for example: 2020-06-10-how-to-set-up-a-github-blog.md, copy it to _posts folder and copy the images to assets/img folder, "synchronize" with a specific message in place of "Copy a basic repo". 

(The message means what kind of modification is done, it is a visual hint in Github version management.)

I add a picture to a markdown file using HTML code:
```
<div style="text-align:left;"><img src="{{ site.github.url }}/assets/img/gitcommand.jpg" style="margin-bottom:0px; max-width:80%;" alt=""><p style="font-size:12px">Fig: Git work flow</p></div>
```


Acknowledgement: @DWJWendy shared the experience in [a blog](https://www.jianshu.com/p/d7c6e59931f0) which inspired me a lot, and the blog also links to more themes: [Themes](https://hexo.io/themes/), [Jekyll Themes](http://jekyllthemes.org).



Ref:  
[1] The Net Ninja, [Git & GitHub Tutorial for Beginners #8 - Branches](https://www.youtube.com/watch?v=QV0kVNvkMxc)  
[2] The Net Ninja, [Git & GitHub Tutorial for Beginners #9 - Merging Branches (& conflicts)](https://www.youtube.com/watch?v=XX-Kct0PfFc)  
[3] The Net Ninja, [Git & GitHub Tutorial for Beginners #11 - Collaborating on GitHub](https://www.youtube.com/watch?v=MnUd31TvBoU&list=PL4cUxeGkcC9goXbgTDQ0n_4TBzOO0ocPR&index=11)  
[4] Brad Schiff(Youtube ID: LearnWebCode), [Git Tutorial Part 1: What is Version Control?](https://www.youtube.com/watch?v=9GKpbI1siow)  
[5] Brad Schiff(Youtube ID: LearnWebCode), [Git Tutorial Part 2: Vocab (Repo, Staging, Commit, Push, Pull)](https://www.youtube.com/watch?v=n-p1RUmdl9M&list=RDCMUCHRp19HU7Y2LwfI0Ai6WAGQ&index=2)  
[6] Brad Schiff(Youtube ID: LearnWebCode), [Git Tutorial Part 4: GitHub (Pushing to a Server)](https://www.cnblogs.com/dersu/p/13045555.html)