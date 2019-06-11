---
title: Hexo的next下添加看板娘
categories:
- Hexo
top: true
---
{% cq %} 无需设置配置文件 {% endcq %}

{% fi /images/77.jpg, alt, title %}



{% note class_name info %} Content (md partial supported) {% endnote %}
**1.下载项目**
将主题保存到主题下的目录中
```
 git clone "https://github.com/stevenjoezhang/live2d-widget" themes/next/source/live2d-widget

```
**2.修改 autoload.js 文件**

修改  themes/next/source/live2d-widget 下的  autoload.js文件
将

```
 const live2d_path = "https://cdn.jsdelivr.net/gh/stevenjoezhang/live2d-widget/";
```
改为
```
const live2d_path = "/live2d-widget/";
```

**3.修改 _layout.swing 文件**

在  /themes/next/layout/_layout.swing 中,新增如下内容：

```
<script src="https://cdn.jsdelivr.net/npm/jquery/dist/jquery.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/font-awesome/css/font-awesome.min.css"/>
<script src="/live2d-widget/autoload.js"></script>
```

**4.个性化设置**

想修改看板娘大小、位置、格式、文本内容等，可查看并修改 waifu-tips.js 、 waifu-tips.json 、waifu.css文件。