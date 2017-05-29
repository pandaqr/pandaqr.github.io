---
layout: "post"
image: upbeing community.jpg
---


终于，今年的Google I/O 前阵子结束了，对于Google，和Apple的发布会上关于设计的话题都是我必看的内容。 


今天抓来[Creating UX that “Just Feels Right” with Progressive Web Apps](https://www.youtube.com/watch?v=mmq-KVeO-uU&list=PLRDt1-VhUOFrzO0zvL9dG9jkFJKrzzD9X)啃了一下， 感觉是，很多的问题不是UI的问题， 是技术上的问题， 


基于UX设计出 Just feels right 的网页应用。

* Reactive 
* Predicable
* In Control 

# Reactive : 

## perceive performance 

> Human perception of time is fluid, and can be manipulated purposeful and productive ways 


如果要话费5秒去Loading 一个页面可以是ok但是， 如果能让用户感到只花了1秒钟，那就更好了。 
在跳转到下一页面的时候保留住前一个页面的图片和文字， 再Loading其他的内容， 立刻的跳转， 从而减缓等待感。 

## Infinite lists 

列表下拉时，过长的列表会导致记忆量过大， 有时候下拉的时候就会变得卡顿， 并且会出现空白等待显示情况， 解决这个问题的方法：virtualized lists, 不在屏幕上显示的列表内容其实就是从DOM中移除了 。只记忆page中需要显示的内容就行了。 

## Fonts

* 尽量使用系统默认字体
* 如果字体对你来说非常重要， 那就用SVG
* 当下载完设定字体之后再把原本默认字体换掉。 

**好用的tool**

* Lighthouse 帮助检测网站用户体验，
* Pagespeed insights 
* Webpage test 帮助你体验在较为落后地区的网络状况。 

# Predictable

## 考虑使用底部导航栏。 

汉堡包导航栏的问题是，不容易发现，拉出来后，拉回去的表现不佳
顶部滑动Tab栏的问题是， 用户期望是可以左右滑动切换界面的，但有的Tab栏不支持这一点。 

## Blue Flash 

最初由于技术问题， web app的反应比较慢，点击按钮的时候，会出现透明蓝色区块，给到用户点击反馈。 
但现在速度快了， 可以考虑将蓝色区块去掉，提高用户体验。 


# In Control 

## Stable Load

在内容页面下载之前，将layout设置好。 

## 推送通知
在用户用到相关的情形下， 再询问用户是否开通推送通知。 （全屏询问，不要用底部一部分，因为页面上还有CTA 之类的信息） 



*****
## Smart lock 
当app跳转到网页的时候， 自动登陆，不要让用户再去登陆。。


## payment  request API 

结账的表单，利用已有信息自动帮用户填写。 

##  Service workers 

当用户在不佳的网络环境甚至是离线的情况下， 依然保留用户之前查看的页面， 




P.S : 题图是最近画的一个地图。。。

