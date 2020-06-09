我看到Jake VanderPlas写的Github文章《[Understanding Data Types in Python](https://jakevdp.github.io/PythonDataScienceHandbook/02.01-understanding-data-types.html)》，如此优美，且有comment栏。

我尝试github.io，得到https://pages.github.com。按照指示可以申请自己的github.io的博客。这个博客的特点是：书写markdown文档，上传，就可以发布为blog。那么，需要建设一个基础repo。

1）新建一个repository，名字叫username.github.io。我的是dersu-git.github.io。

2）点击repository setting，选择一个theme。这样在浏览器输入username.github.io，可以得到博客网页。

3）替换整个repo。
在Terminal中pull 整个repository。
```
git pull origin master
```
可以在本地得到dersu-git.github.io文件夹，这是本地repo，清空文件。
```
cd dersu-git.github.io
```

我喜欢Paul Le先生的Lagrange模板，在[这个地址](https://github.com/LeNPaul/Lagrange/)download所有文件。

并将所有文件拷贝至本地repo。可以看到blog如同demo site。

4）个人化：
- _post中的md文档删除，替换成自己的blog md文档。
- 修改menu中的文档。
- 修改_config.yml。
- 修改_data中的setting.yml。需要申请disqus账号，获得short name。
- 修改favicon.ico。需要申请favicon。

