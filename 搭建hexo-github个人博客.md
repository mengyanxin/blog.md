---
title: 搭建hexo+github个人博客
date: 2017-03-30 14:15:58
tags:
- github
- hexo
- blog
- mengyan
categories:
- utils
---
## 创建GitHub仓库
>### 注册/登陆
>### 创建仓库
仓库名称必须为：*用户名.github.io*

## 安装Git
>### 安装[Git](https://git-scm.com/download/ "download")客户端
>### 安装[Nodejs](https://nodejs.org/en/download/ "download")
>### 安装Hexo
在命令行中输入:
{% codeblock %}npm install hexo-cli -g{% endcodeblock %}

## 创建本地博客
> 1. 打开命令，定位到放置博客的文件夹下
> 2. 输入命令：
{% codeblock %}
hexo init 你的用户名.github.io // 建议和创建仓库时使用同一个
{% endcodeblock %}

## 主题安装
### Next/yilia
> 切换到上面生成的博客本地目录(xxx.github.io)
> 执行命令：
{% codeblock %}
git clone https://github.com/iissnan/hexo-theme-next themes/next
git clone git@github.com:litten/hexo-theme-yilia.git themes/yilia
{% endcodeblock %}
> 想要使用哪种主题，就下载哪一种主题

### 使用主题
> 切换到上面生成的博客本地目录(xxx.github.io)
> 修改_config.yml文件
{% codeblock %}
theme: next //刚刚安装的主题名称
{% endcodeblock %}
>> 注意：该配置文件中的键值之间一定要有空格，否则轻则没有作用，重则报错，无法启动。

### 配置文件基本项修改
> 请参考[Hexo官方文档](https://hexo.io/zh-cn/docs/configuration.html "")
> 我自己的配置为：
{% codeblock %}
# Hexo Configuration
## Docs: https://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site
title: mengyanxin
subtitle: 有情者伤人，无情者自伤
description: 一人吃饱，全家不饿的小码农！
author: mengyanxin
language: zh-Hans
email: 13260695212@163.com
keywords: "java,liunx,html,js"
timezone:

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://yoursite.com
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:

# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: true
  tab_replace:

# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss

# Pagination
## Set per_page to 0 to disable pagination
per_page: 20
pagination_dir: page

# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: yilia
#theme: next
#theme: landscape

# 头像
# 注意：是 xxx.github.io/source 下的开始的相对路径，如果 source 文件夹下面没有 uploads 文件夹，那么新建一个。考虑到会博客中用很多图片，在 uploads 文件夹下请分好类，避免混乱
avatar: uploads/user/images/mengyan.jpg

# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: http://github.com/mengyanxin/mengyanxin.github.io.git


jsonContent:
  meta: false
  pages: false
  posts:
    title: true
    date: true
    path: true
    text: true
    raw: false
    content: false
    slug: false
    updated: false
    comments: false
    link: false
    permalink: false
    excerpt: false
    categories: false
    tags: true
{% endcodeblock %}

### 运行本地服务
> 切换到博客本地目录(xxx.github.io)
> 输入命令：
{% codeblock %}
hexo s -p 5000  //可以直接使用hexo s打开服务
{% endcodeblock %}
> 如果PC已经安装福昕阅读器，会占用hexo的默认端口4000，使用-p 打开另一端口，供hexo使用
> ![运行结果图](/uploads/product/ACC07RO7]2Q}[1(O6UE_(D0.jpg)

## 插件配置
> 切换的博客本地目录(xxx.github.io/themes/yilia)
> 修改_config.yml文件
> 下面是[我的博客](http://mengyanxin.github.io "go")的配置
{% codeblock %}
# Header

menu:
  主页: /
  夢魇: /tags/mengyan
  相册: /photos

# SubNav
subnav:
  github: "https://github.com/mengyanxin"
  #weibo: "http://weibo.com/litten225"
  #rss: /atom.xml
  #zhihu: "#"
  #douban: "#"
  #segmentfault: "#"
  #mail: "mailto:litten225@qq.com"
  #facebook: "#"
  #google: "#"
  #twitter: "#"
  #linkedin: "#"

#rss: /atom.xml

# 是否需要修改 root 路径
# 如果您的网站存放在子目录中，例如 http://yoursite.com/blog，
# 请将您的 url 设为 http://yoursite.com/blog 并把 root 设为 /blog/。
root:

# Content
excerpt_link: 'more'
show_all_link: '展开全文'
fancybox: true
mathjax: false

# 打赏
reward_type: 2
reward_wording: '谢谢你请我吃糖果'
alipay: /assets/img/alipay.jpg
weixin: /assets/img/weixin.jpg

# 是否在新窗口打开链接
open_in_new: true

# Miscellaneous
baidu_analytics: 'a30844fa2bcbce0a9e001fe06cefeddf'
google_analytics: false
favicon: /assets/img/favicon.ico

#你的头像url
avatar: /uploads/user/images/mengyan.jpg

#是否开启分享
share_jia: true

mobile:
  social: true

#是否开启多说评论，填写你在多说申请的项目名称 duoshuo: duoshuo-key
#若使用disqus，请在博客config文件中填写disqus_shortname，并关闭多说评论
#duoshuo: "litten-hexo"

# 样式定制 - 一般不需要修改，除非有很强的定制欲望…
style:
  # 头像上面的背景颜色
  header: '#4d4d4d'
  # 右滑板块背景
  slider: 'linear-gradient(200deg,#a0cfe4,#e8c37e)'

# slider的设置
slider:
  # 是否默认展开tags板块
  showTags: false

# 如不需要，将该项置为false
# 比如
#smart_menu:
#  friends: false

smart_menu:
  innerArchive: '所有文章'
  friends: '友链'
  aboutme: '关于我'

friends:
  alanli7991's Blog: http://alanli7991.github.io
  litten: http://litten.me
  友情链接3: http://localhost:4000/
  友情链接4: http://localhost:4000/
  友情链接5: http://localhost:4000/
  友情链接6: http://localhost:4000/

aboutme: 萌萌哒小菜鸡。。。
{% endcodeblock %}

## hexo常用命令
> 创建分类和标签页面
{% codeblock %}
hexo new page categories      //新建分类
hexo new page tags            //新建标签
{% endcodeblock %}

> 编辑新建页面文件夹下面的index.md
{%codeblock%}
---
title: All tags
date: 2017-03-23 14:12:52
type: "categories"
comments: false
---
{%endcodeblock%}
{%codeblock%}
---
title: All tags
date: 2017-03-23 14:12:52
type: "tags"
comments: false
---
{%endcodeblock%}

## 安装自动部署工具
> 切换到本地博客目录
> 运行命令：
{%codeblock%}
npm install hexo-deployer-git --save
{%endcodeblock%}

## 部署到GitHubPages
> {%codeblock%}
hexo clean #清除缓存 网页正常情况下可以忽略此条命令
hexo g #生成静态网页
hexo d #开始部署

#也可以一次性执行
hexo clean && hexo g && hexo d
{%endcodeblock%}
