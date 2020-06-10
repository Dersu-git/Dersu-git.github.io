There is Github Pages, so one may set up an elegant Github blog.

Github enables markdown files uploaded to be published as blogs. So if one builds a basic repo, he may "blog like a geeker" later by uploading .md files.

In fact, Mr. Paul Le said so:
> The beauty of hosting your website on GitHub is that you don’t have to actually have Jekyll installed on your computer. Everything can be done through the GitHub code editor, with minimal knowledge of how to use Jekyll or the command line. All you have to do is add your posts to the _posts directory and edit the _config.yml file to change the site settings. With some rudimentary knowledge of HTML and CSS, you can even modify the site to your liking. This can all be done through the GitHub code editor, which acts like a content management system (CMS).

I decided to use Mr. Paul Le's theme, it's tidy and gentle. 

The key task is to copy all the file in his repo to my repo in master branch. Here are the steps:

1. New a repository with the name "username.github.io". In my case, dersu-git.github.io.
2. In the setting of the repository, choose a theme. Then browse https://username.github.io, one might see the blog.
3. Replace the whole repo. Talk later.
4. Personalization. Reading each file, one might know which part need to be modified.


Back to Step 3, There are two ways to build the basic repo, by Git command or by Github webpage functions to upload files one by one. 

Let's introduce the git command solution:
```
git pull orgin master
```
There will be a folder, delete all the files, and switch (cd) to that folder.

Download the theme [Lagrange](https://github.com/LeNPaul/Lagrange/). Copy all the files to the folder, and synchronize to the Github repo. BTW, it is good to do "4. Personalization" before synchronization, if one is not that eager to see what will happen.


```
git add .
git commit -m "Copy a demo repo."
git push origin master
```

One may see the blog is like the demo site.

Then how to new a Github blog later? Write a markdown file, copy it to _posts folder and "synchronize".



