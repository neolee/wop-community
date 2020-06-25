# 进入编程世界 - 问与答

我们鼓励大家提问，在学习过程中遇到问题就及时提出来，及时解决。

万事开头难，一开始快速清障前进，后面就会越来越顺。

有任何问题，请访问：

> [https://github.com/neolee/wop-community/issues](https://github.com/neolee/wop-community/issues)

在这里可以通过关键字和问题状态来搜索，很多时候可以直接找到自己所遇到问题的答案；如果没找到，点击右上的 *`New issue`* 绿色按钮即可提出问题。

这个系统基本上就像一个问答论坛，并集成了和编程有关的功能，下面有一些常用的小技巧，完整的用法可以自行探索。

## 如何正确地提问

提问是有一些技巧的，经过思考和仔细编写的问题更容易得到靠谱答案。

关于这个问题，有个近乎事实标准的指南在网上已存在很久，那就是大牛 Eric S. Raymond 2001 年发表在 BBS 上的 [How To Ask Questions The Smart Way](http://www.catb.org/~esr/faqs/smart-questions.html)，这篇文章从发表之后一直在不断更新修订，内容清晰详实，附有丰富的“好问题”和“蠢问题”样例，一看就明白；另有质量很不错的 [中文译文](https://github.com/ryanhanwu/How-To-Ask-Questions-The-Smart-Way/blob/master/README-zh_CN.md)（也是开源的）。请务必仔细阅读，尽量按照里面的建议来思考和组织你的问题。

## 如何高效使用 GitHub Issues 系统

问答基于 GitHub 为代码仓库托管提供的 Issues 功能，这个功能主要面向程序员用户，是优秀程序员常用的系统。

下面有一些常见小技巧供参考。

### 一般性建议

* 问题的标题不要太长，要简明扼要，具体描述在问题正文中展开说明；
* 问题的标题和正文都可以反复修改，点击问题标题后面的 `Edit` 按钮可以修改标题，点击问题正文右上角的 `...` 可以修改正文；
* 问题可以随时关闭和打开，无论是误操作还是有了新的想法或发现，随时可以重新打开已经关闭的问题；如果问题已经解决，提问者最好主动关闭问题，否则一段时间不活跃也会被关闭；
* 同一个问题不要重复发问，有新的发现或者想法在原问题后面追加回复就可以了；
* 这个系统最大的优势是内容支持 Markdown 格式，如果还不熟悉这个语言可以先学习相关的支线课程（课程资源列表中有），非常简单同时非常有用。

### 如何贴图

拷贝图片，然后直接在输入框中粘贴，或者直接将图片文件拖到输入框中。

操作之后输入框中会显示 `Uploading pic...`，注意一定要等这句话变成 `<img src=...>` 这样的一串之后再提交，否则上传和贴图会失败，切记。

### 如何贴代码

关于程序的问题，最好把你的代码完整贴出来，贴的时候使用 Markdown 语法：

<pre>
```python
# 把你的代码放在这里
```
</pre>

“\`” 这个字符叫重音符（*grave accent*），也叫 *back quote* 或者 *backquote*，对应按键通常在键盘左上角。

用三个“\`”开始和结束，框起来的部分会被显示为代码样式。

在开始的三个“\`”后面可以用一个编程语言标签来指定其下代码是什么语言，系统会根据语言特性进行语法着色显示。

比如 `python` `javascript` `shell` 等等都支持。

### 如何引用其他问题

在输入框内输入 `#` 后面紧跟问题（*issue*）编号即可，系统会自动创建链接连到对应的问题。

### 如何搜索

在搜索框输入搜索关键字即可，通常关键字是你碰到的出错信息里的关键内容，或者你要问的主题等等。

可以使用多个关键字，用空格隔开就好。

还可以输入一些特殊条件，比如：
* `is:issue` 指定在问题中搜索，否则是对整个仓库的搜索；
* `is:open` 是搜索未关闭的问题，类似的还有 `is:closed` 搜索已关闭的问题，去掉这类条件则搜索所有问题；
* `label:xxxx` 在带有 `xxxx` 标签的问题中搜索，管理员会给问题打上不同的标签，具体可用标签及其含义可以点击搜索框右边的 `Labels` 按钮来查看。

## 附：解决访问 GitHub 的一些问题

由于某些原因，访问 GitHub 有时会碰到一些问题，比如头像显示不出来，或者访问 `raw.githubusercontent.com` 这个域名下的资源出错——这个问题还会影响安装 Scoop 和 Homebrew……这些问题都是因为没有正确进行域名解析导致的，这类问题可以通过修改操作系统的一个叫做 `hosts` 的配置文件来（临时）解决。下面是具体方法。

* 访问 [ipaddress.com](https://www.ipaddress.com/)，查询 `github.com` 域名对应的 IP
    * 比如在我的系统里查出来是 `140.82.113.4`
	* 可以用命令行下的 `ping` 命令做测试：`ping 140.82.113.4`，如果正常你可以看到访问这个 IP 的时间

* 准备一个名为 `hosts` 的空文本文件（文件名就叫 `hosts` 没有任何后缀），将我们查到的域名和对应 IP 写进去
    * 下面是我测试可用的，但在你的网络环境下不一定好用，你可以先用这些配置测试，如果访问某个域名出现问题，就用上面的方法自己去查和测试
```
# GitHub
140.82.113.4 github.com
140.82.113.3 gist.github.com
185.199.108.153 assets-cdn.github.com
199.232.68.133 raw.githubusercontent.com
199.232.68.133 gist.githubusercontent.com
199.232.68.133 cloud.githubusercontent.com
199.232.68.133 camo.githubusercontent.com
199.232.68.133 avatars0.githubusercontent.com
199.232.68.133 avatars1.githubusercontent.com
199.232.68.133 avatars2.githubusercontent.com
199.232.68.133 avatars3.githubusercontent.com
199.232.68.133 avatars4.githubusercontent.com
199.232.68.133 avatars5.githubusercontent.com
199.232.68.133 avatars6.githubusercontent.com
199.232.68.133 avatars7.githubusercontent.com
199.232.68.133 avatars8.githubusercontent.com
140.82.113.5 api.github.com
```

* 将上述 hosts 文件拷贝到系统位置
	* Windows：`C:\Windows\System32\drivers\etc\hosts`
	* macOS：`/etc/hosts`
	* 注意：**如果拷贝时说文件已存在的话，不要覆盖掉，而应该打开上述位置已存在的系统配置文件，将上面列出的内容追加到已存在配置文件的最后才对**
	* 上述拷贝或编辑修改操作均需要系统管理员权限

* 在命令行执行下面的命令，以更新 DNS 缓存令上述修改生效：
	* Windows：`ipconfig /flushdns`
	* macOS：`sudo killall -HUP mDNSResponder`

* 重新打开浏览器，应该可以正常访问 GitHub 的各项服务
	* 或者重新执行命令行的命令，例如 Scoop 和 Homebrew 的安装都需要访问 raw.githubusercontent.com 域名