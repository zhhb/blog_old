---
layout: post
title:  "NVM，The node.js/io.js version manager"
date:   2015-05-15 10:49:48
categories: Nodejs
---

>要在 Mac 上建立一个 node.js 的开发有很多方法. 你可以直接下载源码自己编译安装, 或者是用管理工具来帮你解决这些琐碎的問題，比如 homebrew、nvm、n. 因为 node.js 还是很年轻的一个东西, 常常会有版本的更新. 手动安装及更新实在是非常的累人. 若是使用管理工具来帮你处理这些问题可以让你把时间花在思考和编码而不是设定开发环境上面.

# 常规安装方式

## Windows 系统

[Windows安装包下载][Node.js]

## Linxu 系统

[使用 Linux 包管理器来安装][Node.js packagers]


## OS X 系统

### 首先你需要安装 Xcode

>什么？我只是想安装一个 server side javascript 运行环境而已，为神马要安装一个好几个G的 Xcode?   
>嗯……，因为你需要使用gcc来编译 node.js 或 其他的组件，所以你还是乖乖的安装吧   
>如果你用的是windows 那么需要微软的 Microsoft Visual Studio C++   
>如果你用的是linux 那么你需要安装 gcc

### 安装 Homebrew

>[Homebrew][Homebrew] 是 OSX 不可或缺的套件管理器，真的，我会骗你么！！   
>它就像是 Ubuntu 上的 apt-get. 我們需要它来帮我们安裝 node.js 以及 mongoDB。   

{% highlight ruby %}
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
{% endhighlight %}

### 安装 node.js
{% highlight bash %}
brew update 
brew install node
{% endhighlight %}

>没错用 homebrew 安装 node.js 就是这么简单

# 另外你可以单独安装 npm 来管理 node.js 的套件

>npm 是 node.js 最受欢迎的套件管理系统. 就像是 ruby 的 gem 以及 php 里的 pear. 现在上面已经有成千上万现成的套件了. 包括 ORM, router, 以及第三方 api 的 wrapper 等等. 所以当你在写新功能之前先上 npm 找找是不是已经有现成的可用模块组件吧.

{% highlight bash %}
curl http://npmjs.org/install.sh | sudo sh
{% endhighlight %}   


# 使用 n 来管理 node 版本

>n 是 Node 的一个模块，作者是大神 TJ Holowaychuk（鼎鼎大名的Express框架作者），就像它的名字一样，它的理念就是简单：

安装很简单：

{% highlight bash %}
$ sudo npm install -g n
{% endhighlight %}

安装完成之后，直接输入 n 后输出当前已经安装的 node 版本以及正在使用的版本（前面有一个o），你可以通过移动上下方向键来选择要使用的版本，最后按回车生效。

{% highlight bash %}
$ n
    0.10.1 
    0.10.15 
o   0.10.21 
    0.11.8
{% endhighlight %}

如果你要安装其他的版本（比如 0.11.12 ），那么如下：

{% highlight bash %}
$ n 0.11.12
install : 0.11.12
   mkdir : /usr/local/n/versions/0.11.12
   fetch : http://nodejs.org/dist/v0.11.12/node-v0.11.12-darwin-x64.tar.gz
####                                                     5.9%
{% endhighlight %}

n 的详细文档请移步[这里][npmjs-n] OR [这里][gh-n]

# 使用 [nvm][Nvm] 来安装 node.js (今天讲的就是这个)

>nvm 全称 Node Version Manager，它与 n 的实现方式不同，其是通过shell脚本实现的。

为什么我要用 nvm 呢？ 主要还是 nvm 使用起来真的很方便，而且其实大多数情况下，不会发生权限问题

安装方式有三种：

{% highlight bash %}
$ curl https://raw.github.com/creationix/nvm/v0.25.2/install.sh | sh
{% endhighlight %}

或者

{% highlight bash %}
$ wget -qO- https://raw.github.com/creationix/nvm/v0.25.2/install.sh | sh
{% endhighlight %}

或者直接使用 Git

{% highlight bash %}
# clone repo
git clone https://github.com/creationix/nvm.git ~/.nvm && cd ~/.nvm
# checkout the latest tag
git checkout `git describe --abbrev=0 --tags`
# enable on terminal open
$ echo ". ~/.nvm/nvm.sh" >> ~/.bashrc
# reopen your terminal or run source ~/.bashrc and do the following
$ nvm install -s v0.10.36
# set default node
$ nvm alias default v0.10.36
{% endhighlight %}

前两种方式会把nvm库clone到~/.nvm，然后会在~/.bash_profile, ~/.zshrc或`~/.profile末尾添加source，安装完成之后，你可以用方式三中的命令来安装node

使用指定的版本
{% highlight bash %}
$ nvm use v0.10.36
{% endhighlight %}

查看当前已经安装的版本
{% highlight bash %}
$ nvm ls
{% endhighlight %}

查看正在使用的版本
{% highlight bash %}
$ nvm current
{% endhighlight %}

以指定版本执行脚本
{% highlight bash %}
$ nvm run 0.10.36 yourApp.js
{% endhighlight %}

卸载nvm
{% highlight bash %}
$ rm -rf ~/.nvm
{% endhighlight %}

>PS1: homebrew 中有 nvm ，可以使用 brew install nvm 来安装，不过好像还是要自己添加 nvm.sh 的路径到 ~/.bashrc，个人还是倾向于前三种方式   
>PS2: Windows 下有 [nvmw][nvmw]、[nvm-windows][nvm-windows]

然后？然后你就能开开心心的玩 node.js 了

[nvm-windows]:https://github.com/coreybutler/nvm-windows
[nvmw]:https://github.com/hakobera/nvmw
[gh-n]:https://github.com/tj/n
[npmjs-n]:https://www.npmjs.com/package/n
[Node.js]: https://nodejs.org/
[Node.js packagers]: https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager
[Nvm]:https://github.com/creationix/nvm
[Homebrew]:http://brew.sh/