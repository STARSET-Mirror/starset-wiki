---
title: 2.3.1 插入音频
description: 
published: true
date: 2022-02-02T14:20:05.323Z
tags: 
editor: markdown
dateCreated: 2022-02-02T13:28:22.671Z
---

> 目前只有**Markdown编辑器**和**HTML编辑器**支持插入音频。如果你使用可视化编辑器，请先转换为这两个格式中的一个。
{.is-warning}

# 方案一：直接使用音乐平台提供的外链播放器
## 网易云音乐
1. 进入网页版网易云音乐，打开你要插入的单曲/歌单/专辑，就能看到“生成外链播放器”按钮
![生成外链播放器按钮](https://imgs.thestarsetsociety.cn/2022/02/02/40c60159b4925.png)
2. 单击“生成外链播放器”，复制下方的HTML代码（可预先选择样式、调整宽度、高度、是否自动播放）
![配置播放器选项](https://imgs.thestarsetsociety.cn/2022/02/02/d8e4f11c8f3f8.png)
3. 将代码直接粘贴到你要编辑的页面里
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=450 src="//music.163.com/outchain/player?type=1&id=135098711&auto=0&height=430"></iframe><br/><br/>
注意：
1. 一个页面只允许插入一个网易云外链播放器
2. 这种播放器只能播放非VIP歌曲，如果要实现VIP歌曲和版权歌曲的播放，请参考方案二

## 国外音乐平台
Spotify、Amazon Music等国外平台均提供外嵌播放插件，如果您想使用它们的播放组件，只需在“分享”之类的地方查找是否有相关功能即可，使用方法与网易云音乐类似。由于本文档是中文文档，主要面向中国用户，故不展开。

# 方案二：第三方外链播放器
我们目前在所有页面默认载入了第三方播放器APlayer和MeetingJS，您只需参考下面说明配置好代码，粘贴到您编辑的页面即可。
## 最简配置
1. 样式一（正常大小播放器）
```html
<meting-js
	name="歌曲名"
	artist="歌手名"
	url="歌曲音频链接"
	cover="歌曲封面链接">
</meting-js>
```
效果如下：
<meting-js
  name="THE BREACH"
  artist="STARSET"
  url="https://music.163.com/song/media/outer/url?id=1888810383.mp3"
  cover="https://scdn.thestarsetsociety.cn/GeneralMedia/Muscvr/starset/horizons.webp">
</meting-js>
2. 样式二（迷你播放器）
```html
<meting-js
	name="歌曲名"
	artist="歌手名"
	url="歌曲音频链接"
	cover="歌曲封面链接"
  mini="true">
</meting-js>
```
效果如下：
<meting-js
  name="THE BREACH"
  artist="STARSET"
  url="https://music.163.com/song/media/outer/url?id=1888810383.mp3"
  cover="https://scdn.thestarsetsociety.cn/GeneralMedia/Muscvr/starset/horizons.webp"
  mini="true">
</meting-js>
3. 样式三（固定在页面下方的播放器）
```html
<meting-js
	name="歌曲名"
	artist="歌手名"
	url="歌曲音频链接"
	cover="歌曲封面链接"
  fixed="true">
</meting-js>
```
<meting-js
  name="THE BREACH"
  artist="STARSET"
  url="https://music.163.com/song/media/outer/url?id=1888810383.mp3"
  cover="https://scdn.thestarsetsociety.cn/GeneralMedia/Muscvr/starset/horizons.webp"
  fixed="true">
</meting-js>
### 说明
#### 歌曲音频链接
1. 如果该歌曲是网易云音乐的免费歌曲，你可以获得这个歌曲的链接，在浏览器中打开后获得这个歌曲的id，随后把上面的'歌曲id'替换为你得到的歌曲id即可。
示例：`https://music.163.com/song/media/outer/url?id=1888810383.mp3`
2. 如果是VIP歌曲或要自定义歌曲，按照格式填写链接然后联系CDN上传，格式为：`https://scdn.thestarsetsociety.cn/GeneralMedia/Mustrm/歌手名/专辑名/歌曲名.mp3`
其中，歌手名、专辑名、歌曲名的字母全为小写，如果有空格，以下划线代替
示例：`https://scdn.thestarsetsociety.cn/GeneralMedia/Mustrm/starset/horizons/the_breach.mp3`
#### 歌曲封面链接
1. 你可以用浏览器访问相关专辑，然后右键单击歌曲封面，点击“检查”/“检查元素”就能看到图片地址（显示在“img src=”后面的就是）
![如图所示](https://imgs.thestarsetsociety.cn/2022/02/02/22d13a19e20e6.png)
2. 如果获取不到或者要自定义图片，请按照格式填写链接然后联系CDN上传，格式为：
`https://scdn.thestarsetsociety.cn/GeneralMedia/Muscvr/歌手名/专辑名.webp`
其中，歌手名、专辑名、歌曲名的字母全为小写，如果有空格，以下划线代替
示例：`https://scdn.thestarsetsociety.cn/GeneralMedia/Muscvr/starset/horizons.webp`
### 其它说明
> 由于和Wiki页面样式的冲突，目前只有通过上述格式引入的播放器才能正常加载。
{.is-danger}

