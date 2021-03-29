---
layout: mypost
title: 利用Stylus插件让Chrome有macOS的字体渲染效果
categories: [插件,chrome]
---
# 利用Stylus插件让Chrome有macOS的字体渲染效果

> Stylish是一个让你可以在每个网站自订CSS的工具，我们可以利用CSS达成类似Mac的字体渲染效果

## 安装所需字体和Stylus插件

> 思源黑体：[https://github.com/adobe-fonts/source-han-serif/tree/release](https://link.zhihu.com/?target=https%3A//github.com/adobe-fonts/source-han-serif/tree/release)
> 思源黑体直接下载链接：[Simplified Chinese (简体中文)](https://link.zhihu.com/?target=https%3A//github.com/adobe-fonts/source-han-sans/raw/release/OTF/SourceHanSansSC.zip)
> 思源宋体：[https://github.com/adobe-fonts/source-han-serif](https://link.zhihu.com/?target=https%3A//github.com/adobe-fonts/source-han-serif)
> 思源宋体直接下载链接：Simplified Chinese (简体中文):[ExtraLight + Light + Regular + Medium](https://link.zhihu.com/?target=https%3A//github.com/adobe-fonts/source-han-serif/raw/release/OTF/SourceHanSerifSC_EL-M.zip)&[SemiBold + Bold + Heavy](https://link.zhihu.com/?target=https%3A//github.com/adobe-fonts/source-han-serif/raw/release/OTF/SourceHanSerifSC_SB-H.zip)
> Stylus：[https://chrome.google.com/webst](https://link.zhihu.com/?target=https%3A//chrome.google.com/webstore/detail/stylus/clngdbkpkpeebahjckkjfobafhncgmne)

因为Mac原版苹方体据说在低分屏上表现不佳，而且下载麻烦，故采用Adobe版的免费开源字体思源黑体。思源黑体和思源宋体可以选择简繁日韩任何一种下载，汉字部分是一样的，差别在标点符号的优先度，简体版优先显示大陆样式标点符号。以上给出简体版链接。

![](https://i.loli.net/2021/02/22/mIx2uiDY9zZrV4J.jpg)



## 设置Chrome字体

进入外观→自定义字体

![](https://i.loli.net/2021/02/22/rPh9xco2478DyXg.png)

Source Han Sans TC就是思源黑体繁体版，如果安装简体版应该会显示思源黑体。等寬字体没设也没关系，不影响。

设置完后你会发现有些网站的字体改变了，但是大部分没变，而且也没有渲染效果。因为大部分网站在CSS里面指定了要用的字体，我们需要用Stylish强制那些网站改用我们的字体并且帮我们渲染



## 配置Stylus

点Stylus图标，新建三个样式，名字自己取

![](https://i.loli.net/2021/02/22/aQGnfd4KJU6O8pT.jpg)

**全局样式**

```
* { -webkit-text-stroke-width:0.16px;}
* { text-shadow: 0.01em 0.01em 0.02em #707070; }
@font-face {font-family: "Arial"; src: local("Source Han Sans SC Regular")}
@font-face {font-family: "Roboto"; src: local("Source Han Sans SC Regular")}
@font-face {font-family:  "Helvetica"; src: local("Source Han Sans SC Regular")}
@font-face{font-family: "Microsoft YaHei"; src: local("Source Han Sans SC Regular")}
@font-face {font-family: "微軟正黑體"; src: local("Source Han Sans SC Regular")}
@font-face {font-family: "Microsoft JhengHei"; src: local("Source Han Sans SC Regular")}
@font-face {font-family: "Microsoft JhengHei UI"; src: local("Source Han Sans SC Regular")}
@font-face {font-family: "Times New Roman"; src: local("Source Han Serif SC Regular")}
@font-face {font-family: "Georgia"; src: local("Source Han Serif SC Regular")}
@font-face {font-family: "Times"; src: local("Source Han Serif SC Regular")}
```

字重：ExtraLight(250)、Light(300)、Normal(350)、Regular(400)、Medium(500)、Bold(700)、Heavy(900)

数字越大字越粗，如果不喜欢Regular的效果可以自己调整。Mac的字体是偏粗的，但在低分屏上，太粗的字体会糊成一块，可以考虑改细一点。

**加粗样式**

```
* { -webkit-text-stroke-width: 0.16px;}
* { text-shadow: 0.01em 0.01em 0.02em #707070; }
@font-face {font-family: "Arial"; src: local("Source Han Sans SC Bold")}
@font-face {font-family: "Roboto"; src: local("Source Han Sans SC Bold")}
@font-face {font-family:  "Helvetica"; src: local("Source Han Sans SC Bold")}
@font-face{font-family: "Microsoft YaHei"; src: local("Source Han Sans SC Bold")}
@font-face {font-family: "Times New Roman"; src: local("Source Han Serif SC Bold")}
@font-face {font-family: "Georgia"; src: local("Source Han Serif SC Bold")}
@font-face {font-family: "Times"; src: local("Source Han Serif SC Bold")}
```

![](https://i.loli.net/2021/02/22/Qv8TslUKyFr9Djb.jpg)



**宋体样式（非必需）**

```
* { -webkit-text-stroke-width:0.16px;}
* { text-shadow: 0.01em 0.01em 0.02em #707070; }
* { font-family: "Source Han Serif SC Medium"!important;}
```

