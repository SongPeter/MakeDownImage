<center style="font-size: 35px">**Sublime Text3环境配置**</center>

---
<div align="right">2017年7月4日</div>

<center style="font-size: 25px">**目录**</center>

[TOC]

###<p style="color: black">一、 Sublime Text 3 安装</p>
####<p style="color: black">1. Sublime安装</p>
&emsp;&emsp;[下载链接](http://www.sublimetext.com/3)
&emsp;&emsp;sublime Text 3 注册码

```
—– BEGIN LICENSE —–
Michael Barnes
Single User License
EA7E-821385
8A353C41 872A0D5C DF9B2950 AFF6F667
C458EA6D 8EA3C286 98D1D650 131A97AB
AA919AEC EF20E143 B361B1E7 4C8B7F04
B085E65E 2F5F5360 8489D422 FB8FC1AA
93F6323C FD7F7544 3F39C318 D95E6480
FCCC7561 8A4A1741 68FA4223 ADCEDE07
200C25BE DBBC4855 C4CFB774 C5EC138C
0FEC1CEF D9DCECEC D3A5DAD1 01316C36
—— END LICENSE ——
```

```
—– BEGIN LICENSE —–
Alexey Plutalov
Single User License
EA7E-860776
3DC19CC1 134CDF23 504DC871 2DE5CE55
585DC8A6 253BB0D9 637C87A2 D8D0BA85
AAE574AD BA7D6DA9 2B9773F2 324C5DEF
17830A4E FBCF9D1D 182406E9 F883EA87
E585BBA1 2538C270 E2E857C2 194283CA
7234FF9E D0392F93 1D16E021 F1914917
63909E12 203C0169 3F08FFC8 86D06EA8
73DDAEF0 AC559F30 A6A67947 B60104C6
—— END LICENSE ——

```

####<p style="color: black">2. Package Control安装</p>
#####<p style="color: black">2.1 自动安装</p>
&emsp;&emsp;使用 ctrl+` 调出命令行窗口，输入代码：
```
import urllib.request,os,hashlib; h = 'df21e130d211cfc94d9b0905775a7c0f' + '1e3d39e33b79698005270310898eea76'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```
&emsp;&emsp;注：该方法可能由于墙的问题失败，可以在urllib.request.ProxyHandler()中添加代理实现链接的目的，如：
```
urllib.request.ProxyHandler({
    'http':'127.0.0.1:1080',
    'https':'127.0.0.1:1080',
})
```
&emsp;&emsp;在这里可以使用lantern的代理设置，如图2.1所示：

<center>![lantern](https://github.com/SongPeter/MakeDownImage/blob/master/Picture/代理设置.png?raw=true)
</center>
<center style="font-size: 14px">图2.1 lantern代理设置</center>

#####<p style="color: black">2.2 手动安装</p>
1) 点击Preferences > Browse Packages菜单;
2) 进入打开的目录的上层目录，然后再进入Installed Packages/目录;
3) 下载[Package Control.sublime-package](https://sublime.wbond.net/Package%20Control.sublime-package)并复制到Installed Packages/目录;
4) 重启Sublime Text。
&emsp;&emsp;注：观察Preferences菜单最下边是否有Package Settings 和Package Control两个选项，如果有，则代表安装成功了。

#####<p style="color: black">2.3 Package Control配置</p>
&emsp;&emsp;由于Sublime Text 3 插件下载的网站 [packagecontrol.io](https://packagecontrol.io/) 被墙了，使用Shift+Command+P命令无法使用Package Control的insert命令，报错情况如图2.2所示:

<center>![PackageContrelError](https://github.com/SongPeter/MakeDownImage/blob/master/Picture/PackageControl_error.png?raw=true)</center>
<center style="font-size: 14px">图2.2 Package Control Error</center>

&emsp;&emsp;现有解决方法主要有以下两种：

######<p style="color: black">2.3.1 代理</p>
&emsp;&emsp;打开 Menu -> Package Settings -> Package Control -> Settings - User；<sup>[[1]](#quote1)</sup>
>
&emsp;&emsp;设置代理，输入如下：
```
{
    "http_proxy": "127.0.0.1:1080",
    "https_proxy": "127.0.0.1:1080",
}
```
&emsp;&emsp;这样设置完成之后，就能顺利访问 packagecontrol.io ， Ctrl + Shift + P -> Package Control: Install Package 安装插件，具体设置方法详见图2.1。

###<p style="color: black">二、 Sublime Text 3插件环境</p>
####<p style="color: black">1. 插件列表</p>

| Package Name | Description |
|--------------|-------------|
|              |             |


####<p style="color: black">2. 插件配置详解</p>
#####<p style="color: black">2.1 </p>


###<p style="color: black">三、 Sublime Text 3技巧</p>
####<p style="color: black">1. 文章图片插入</p>
&emsp;&emsp;利用github存储图片，在markdown引用图片链接地址，具体步骤如下：<sup>[[X]](#quoteX)</sup>
1) 注册GitHub账号；
2) 在GitHub上建立一个New Progect；
3) mac上建立与[GitHub的连接](http://www.jianshu.com/p/ff1034ed270e)<sup>[[X]](#quoteX1)</sup>；
4) git init；
5) git clone git@github.com:SongPeter/MakeDownImage.git；
6) git add .；
7) git comment --message "test"；
8) **git push -u origin master**；```//需要加上后面的参数否则会报错 ```
9) 访问github仓库，[SongPeter/MakeDownImage](https://github.com/SongPeter/MakeDownImage)；
10)访问图片，如图2.1[lantern代理设置](https://github.com/SongPeter/MakeDownImage/blob/master/Picture/代理设置.png)；
11)获取[图片链接](https://github.com/SongPeter/MakeDownImage/blob/master/Picture/代理设置.png?raw=true)；
12)在makedown中引用链接，[...]\(...\)。






###参考文献
<span id="quote1">[1] [Sublime Text 3 插件下载失败的解决方案. 2016-01-29.](http://www.tuicool.com/articles/uiI3YrY)</span>
<span id="quoteX">[X] [知乎：Markdown中插入图片技巧. 2015-08-27.](https://www.zhihu.com/question/21065229)</span>
<span id="quoteX1">[X1] [在 mac 上使用 Git 和 GitHub 连接. 2015-07-27.](http://www.jianshu.com/p/ff1034ed270e)</span>

