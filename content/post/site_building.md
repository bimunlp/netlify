---
title: "如何在Github上免费开通一个Github Page作为个人主页"
date: 2021-09-20T20:39:46+08:00
image: "https://qiniu.csit.fun/free_website.png"
---

为什么要选择在Github上建站，原因很简单，它是免费的．

只要你按照下面的六步走，就可以轻轻松松发布自己的网站，你不需要有任何关于编程或者网站建设的基础知识．所有的前提只是，你要有一个github账号．


当你下定决心要建站的时候，你就开始面临一系列的选择．我在上个文章中就已经提到了大家会面临的第一个分叉路口．对于一个想要搭建**个人博客**系统的新手，我坚定地建议你采用Github托管的方式，原因很简单，它是免费的．

假定大家都知道Github是个什么东西，并且对它有着一种类似信仰的原始崇拜．

![](http://cdn.yiyouls.com/codeape.gif)



你可以在Github上免费开通[Github Page](https://pages.github.com)，为你个人或者你的项目建立一个网站．[Github Page](https://pages.github.com)官方网站上有详细的介绍和操作流程．让我们开始操作吧．

> 第一步．创建存储库 (repository)

转到[GitHub](https://github.com/)并[创建一个](https://github.com/new)名为*username* .github.io [的新存储库](https://github.com/new)，其中*username*是你在GitHub上的用户名（或组织名称）。

![](http://cdn.yiyouls.com/step1.png)

如果存储库的第一部分与您的用户名不完全匹配，则无法正常工作，因此请务必正确使用。

{% hl_text danger %}

*需要注意的是*

{% endhl_text %}

1. 在实际操作中你会发现，如果你有自己的独立域名，对新储存库的命名不需要遵循这么严格的规则．以我自己为例，我的Github用户名是yiyouls,　我给自己用来建立Github Page的新仓库命名为blog.　同样是可行的．
2. 仓库属性也可以选择Public



> 第二步，进入储存库，转到设置(settings)

在设置页面你可以对你的新储存库进行相关设置，你可以在这里设置你的GIthub Page特性，包括功能的开启与关闭，是否绑定定制域名(custom domain).

![](http://cdn.yiyouls.com/pagedomain.png)



> 第三步，下载使用Github桌面客户端(Github Desktop)

GitHub Desktop是在macOS和Windows上使用Git和GitHub的好方法。（如果你不想使用Github客户端，你也可以直接在终端里通过`git`命令进行操作[^1]，我会把terminal的操作方法一并列出）

[下载GitHub桌面](https://desktop.github.com/)

![](http://cdn.yiyouls.com/githubdesk.png)

> 第四步，将储存库克隆到本地，用Github桌面客户端打开

客户端完成安装后，返回我们刚建的储存库主页并刷新页面。单击“Set up in Desktop”按钮。当GitHub桌面应用程序打开时，保存项目。这样我们就把该储存库克隆到了本地．

{% hl_text danger %}

注意

{% endhl_text %}

1. 如果Github桌面客户端未能打开，你可以从电脑应用程序库找到它并启动，用户登录后，你可以看到你名下的所有储存库，找到我们新建的那个，手动克隆它．

2. 如果你使用terminal操作，你首先需要`cd`到你准备存放你的项目的文件夹（一定要记得你存放的路径），通过下面的操作克隆你的刚建的储存库：

   ```
   git clone https://github.com/username/username.github.io
   ```

   

![](http://cdn.yiyouls.com/clone.png)

> 第五步，创建索引文件

到这里，你的储存库尚未添加任何文件，你的网站也相应地空空如也．你需要添加索引文件

{% tabbed_codeblock index.html https://pages.github.com %}

​    <!-- tab html -->

​    <!DOCTYPE html>
    <html>
    <body>
    <h1>Hello World</h1>
    <p>I'm hosted with GitHub Pages.</p>
    </body>
    </html>

​    <!-- endtab -->

{% endtabbed_codeblock %}

这样，你就在你的网站上添加了一行"hello world"

{% hl_text danger %}

注意

{% endhl_text %}

如果是使用terminal操作，你需要`cd`进入克隆出的文件，然后向文件夹里添加内容：

```
cd username.github.io

echo "Hello World" > index.html
```



> 第六步，提交和发布

输入存储库，提交更改，然后按发布按钮。

{% hl_text danger %}

注意

{% endhl_text %}

1. 你克隆下来的储存库在本地，你可以通过Finder或者资源管理器找到它，把新文件放进去，Github客户端就能够读取到这些改变啦．

2. 如果你使用terminal终端，可以用`push`推送操作进行发布：

   ```
   git add --all
   
   git commit -m "Initial commit"
   
   git push -u origin master
   ```

   

![](http://cdn.yiyouls.com/desktop-demo.gif)



到这里，你的网站就已经发布在了*username* .github.io这个网址．教程到此结束．

{% alert success %}

you made it!

{% endalert %}

![](http://cdn.yiyouls.com/really.gif)

网站这么丑，能用它来干嘛

![](http://cdn.yiyouls.com/ugly.gif)

的确是这样，我们的网站虽然已经发布，但它基本还是个没用的废物，因为到目前为止我们只给它添加了一个索引文件．如果想要实现更多丰富的功能（可能是一些必备的功能），你必须添加很多代码和文件进去．

![](http://cdn.yiyouls.com/busy.gif)

那么问题来了，真的忍心让你一点点把所有功能实现的代码都敲进去吗？那么建站所耗费的时间成本也太大了．事实上，我们大可不必这样．我们的开源社区已经有了很多可爱的工具和框架供我们使用，免去我们许多许多繁杂的工作．

![](http://cdn.yiyouls.com/foryou.gif)

那么下篇博文，我会跟大家介绍一些可以让你的网站瞬间高大上起来的那些可爱的开源工具．so stay tuned.

[^1]: 之所以要使用Githbub客户端，是因为它是一个非常便捷的git储存库管理工具，当我们开始使用jekyll这样的建站工具对网站进行功能升级的时候，单单通过终端显然是很麻烦的．
