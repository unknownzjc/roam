---
category: "[[Clippings]]"
author: "[[Steph Ango]]"
title: "Obsidian Web Clipper"
source: https://stephango.com/obsidian-web-clipper
clipped: 2024-08-12
published: 
topics: 
tags: [clippings]
---

Web Clipper是我为[Obsidian](https://stephango.com/obsidian)制作的一个书签工具,可以将网页上的文章和页面保存为Markdown文件到Obsidian中。它兼容Safari、Chrome、Firefox和移动浏览器。

## 演示

## 安装

只需将下面的"Clip in Obsidian"链接拖到您的书签栏中。然后点击该书签即可剪藏页面。这将把页面剪藏到您当前打开的保管库中,并插入有关文章的元数据。

Clip in Obsidian

## 使用方法

默认情况下,点击书签工具会从文章的主体部分创建一个新的Obsidian文件,类似于阅读视图。或者,您可以选择从选定内容创建文件,方法是全选(`CMD+A`)或只选择页面的一部分。

## 下载图片以供离线使用

内容中的任何图片都将作为外部引用嵌入。这减少了您保管库中的存储空间,但有两个缺点:首先,您需要在线才能看到图片;其次,如果网站上的图片被删除,这些图片将无法再显示。

如果您想在本地下载图片,可以使用[Local Images插件](https://github.com/aleksey-rezvov/obsidian-local-images),它会下载图片并保存到您的保管库中,以便随时访问。

## 自定义

如果您想自定义剪藏的文件路径和模板,您需要编辑[源代码](https://gist.github.com/kepano/90c05f162c37cf730abb8ff027987ca3)。

可选变量可以在代码顶部找到,模板在底部。如果您进行了更改,我建议使用[Bookmarklet Maker](https://caiorss.github.io/bookmarklet-maker/)来最小化和URI编码书签工具。

## 故障排除

这个书签工具可能不适用于所有网站和浏览器。您可以通过在浏览器中打开开发者控制台,并在点击书签工具时检查是否出现任何错误来排除故障。

最常见的错误是网站或浏览器本身阻止了第三方代码执行。这通常是由于某些网站使用的`connect-src`内容安全策略(CSP)造成的。

- **Aseel-Naji**[分享了一个分支](https://gist.github.com/kepano/90c05f162c37cf730abb8ff027987ca3?permalink_comment_id=3905251#gistcomment-3905251),提示用户输入文件夹和额外标签
- **ganesshkumar**创建了一个[基于浏览器的书签工具制作器](https://gist.github.com/kepano/90c05f162c37cf730abb8ff027987ca3?permalink_comment_id=4064082#gistcomment-4064082),帮助您自定义输出
- **pioneerskies**将其转变为[一个可以在Heroku上运行的网络服务](https://github.com/pioneerskies/downmark),以绕过CSP限制

- [Tidy Reader](https://stephango.com/tidy) 我的书签工具,用于使网页更易读。
- [Tidy URL](https://stephango.com/tidyurl) 我的书签工具,用于清理URL以使其更易于分享。