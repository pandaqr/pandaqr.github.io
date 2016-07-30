---
layout: "post"
---



有大抵一个多月时间没回来码字了，记得三四月的时候捡来Google的Material Design开始看起，但是就好像是每一次看Guide一样，总都有一种看着看着就要掉线的节奏。 还好借着这次新接的项目，所谓实践出真知，把Material Deisgn里里外外的翻了翻。


刷MD的时候，很大一部分的感觉上是这不仅仅是一份规范，是一份很好的学习资料，就好比在使用哪些Terminology的规范上，Google也很贴心的告诉你哪些是好例子哪些是范例，并且将原因也说的很明确。 

项目还在进行中，在这次的项目的进展中，可能更大程度上扮演的是GUI的角色，UX方面也有努力去优化，而产品的设计过程本身有点本末倒置，代码已经写完，才来做UI的确会有很大的限制，这可能更像是带着镣铐跳舞。

而MD的规范看遍后，该遵守的，不该遵守的也要了然于心，只有掌握了规则，才能更好的突破规则。 

今天记录一下MD设计中的一些基本规范。 




## 基本尺寸规范&切图



* 设计尺寸以一倍图为基准（360*640px)
* 切图倍率关系：


| Density Bucket | Scaling factor | Density |
| --- | --- | --- |
| MDPI | 1x | 160dpi |
| HDPI | 1.5x | 240dpi |
| XHDPI | 2x | 320dpi |
| XXHDPI | 3x | 480dpi |
| nexus | 3.5x |   |
| XXXHDPI | 4x | 640dpi |

* 栅格系统的最小单位是8dp，一切距离、尺寸都应该是8dp的整数倍。

以下是一些常见的尺寸与距离：

| 元素 | 尺寸|
| --- | --- | --- |
| **顶部状态栏高度：**  | 24dp |
| **Appbar最小高度：** | 56dp |
| **底部导航栏高度：** | 56dp |
| **底部黑色导航栏：** | 48dp |
| **悬浮按钮尺寸：** | 56x56dp/40x40dp |
| **用户头像尺寸：** | 64x64dp/40x40dp |
| **小图标点击区域：** | 48x48dp |
| **侧边抽屉到屏幕右边的距离：** | 56dp |
| **卡片间距：** | 8dp |
| **分隔线上下留白：** | 8dp |
| **大多元素的留白距离：** | 16dp |
| **屏幕左右对齐基线：** | 16dp |
| **文字左侧对齐基线：** | 72dp |
| **所有可操作元素最小点击区域尺寸：**| 48dp X 48dp |

另外注意56dp这个数字，许多尺寸可变的控件，比如对话框、菜单等，宽度都可以按56的整数倍来设计

* 字体以4dp为基线



## 色彩

* 主色(Primary color)
* 辅助色(Secondary color)
* 强调色(Accent Color)
* 文字和背景颜色(Text and background colors)

通常只需要选取主色和强调色就行了。辅助色非必须，辅助色可以是主色的加深或减淡的变化。 主色应该是App上最广泛使用的色彩。（可以同过加深/减淡主色，扩展色彩配置）

Google建议使用500Colors的作为主色调，其他可选用为强调色。 

强调色使用的场景：

* 文本区域光标
* 文字选择
* 进度条
* 连接
* 按钮，滑块，选择控件。

Appbar背景使用主色，状态栏背景使用深一级的主色或20%透明度的纯黑。
小面积需要高亮显示的地方使用强调色。

[Palette-perfect](https://design.google.com/videos/palette-perfect/)

## 字体

### 字体类型

| 英语 | 中文 |
| --- | --- |
| Roboto | Noto |
| English | Dense |

(其他例如中东地区的文字属于Tall)


### 字体大小


|  | 超大号文字 | 大标题 | App bar文字 | 小标题 | 正文文字/按钮文字 | 小字提示 |
| --- | --- | --- | --- | --- | --- | --- |
| **English** | 112/56/45/34sp Regular | 24sp Regular  | 20sp Medium | 16sp(桌面端15sp) Regular | 14sp(桌面端13sp) Medium | 12sp Regular |
| **Dense** | 112/56/45/34sp Regular | 24sp Regular  | 21sp Medium | 17sp(桌面端16sp) Regular | 15sp(桌面端14sp) Medium | 13sp Regular |

导航栏字体大小： 12dp 
Tab栏字体大小： 14dp

### 字体颜色

| 黑色文字（#000000） | 透明度|
| --- | --- |
| 一级文字 | 87% |
| 二级文字 | 54% |
| 禁用文字，提示文字，图标 | 38% |
| 分隔行 | 12% |


| 白色文字（#ffffff） | 透明度|
| --- | --- |
| 一级文字 | 100% |
| 二级文字 | 70% |
| 禁用文字，提示文字，图标 | 50% |
| 分隔行 | 12% |

### 行高

由于文字是以4dp为基准，因此，**行高为20dp, 24dp, 32dp, 36dp**,以此类推。


## 图标

### 系统图标

#### 系统图标颜色： 

|   | 正常状态 | 禁用状态 |
| --- | --- | --- |
| 黑色图标 | 54% | 26% |
| 白色图标 | 100% | 30% |

#### 系统图标尺寸： 

* 小图标尺寸：24dp X 24dp。图形限制在中央20dp X 20dp区域内。

* 图标圆角：2dp
* 图标线条粗细：2dp (为了达到视觉上的平衡，线条粗细有时候也会是1.5dp)

#### 系统图片绘制注意点：

* 线条粗细要保持一致。 
* 线条终点不要使用圆角
* 图标的设计要是正面的，不要有倾斜等多角度情况
* 用最简单的图形描绘，不要添加复杂元素
* 图标需要图形化，粗线条
* 使用几何图形，具有连贯性
* 讲一个图形嵌入到另外一个图形的时候，要全部嵌入，不要打破外面图形的边界。
* 使用“人”元素的图形，当需要表达某个特定含义的时候。但如果人“图形的添加没有帮助的话，就不要添加。 
* 使用最简单的图形表达人的性格。 

## 图片

### 图片使用的原则： 

* 相关性（personal，relavent)
* 提供信息，将图片与所提供信息的内容相结合更好的传递（informative)
* 愉悦的，有视觉美感的，能很好传递出产品的风格（Delightful）

* 较合适的分辨率
* 使用遮罩确保图片上文字的正常显示


### 图片使用注意点：

* 对于某个特定的话题，寻找合适的照片素材
* 当图片不合适可以用插图来说明，增进理解。 
* 图片需要有叙事性。
* 展示特定物品的图片不要添加其他不相关元素。
* 使用颜色和组合来然图片有一个中心含义。 不要让用户寻找图片的含义。


### 图片在UI中的使用
 

* 使用不同大小的缩略图（thumbnails）来表达内容层次感。 
* 为了让文字能够清晰的在图片上显示，可以使用透明遮罩（scrim）： 
  * 根据背景内容，深色遮罩应该为20-40%透明度，浅色遮罩：40-60%
  * 对于带有文字的大幅图片， 遮罩文字区域，不要遮住整张图片
  * 可以使用半透明的主色调盖住图片。 

#### 图片的四种类型： 

* Avatars
* Thumbnails
* Hero images
* Gallery


Avatars 和Thumbnails通常来说都是可以触发点击的，点击后可能看到更加完整的信息。 Avatar通常显示的是个人的头像，或者品牌的logo，而Thumbnails可以让你看到更多的信息。

Hero images通常是放置在最重要的位置上， 比如屏幕上方的banner,主要用来吸引用户的视线，加强文字内容的表达，或者加强品牌形象。

Gallery是Hero images有序的排列，列表的排序或者单个一张图片。 



## 按钮

MD的button在触发点击的时候，会有波纹的产生。

### 按钮的类别： 

* 扁平按钮（Flat button- 由墨水制成） 
* 凸起按钮 （Raised button) 
* 悬浮按钮 （Floating action button) 

扁平按钮不会抬起，只是以文字形式出现，但是在点击的时候文字会有背景色。 可能会在对话框，工具栏中出现。 

凸起按钮是长方形的纸片，在点击的时候会抬起， 抬起高度为2dp.

至于是使用扁平按钮还是凸起按钮，主要看其使用的地方z-space有多少。不要产生层级太多的情况。 在一屏内容里只能使用一种按钮形式。除非你有很好的其他理由。 


三种按钮的重要性依次为：悬浮按钮 > 凸起按钮 > 扁平按钮

 

### 凸起按钮

凸起按钮给扁平的页面添加的层次感，凸起按钮可以帮助暗示页面内容的划分。

| 高度 | 最小宽度 | 可触发点击范围 | 卡片角度 | 文字大小 | 文字左右边距 |
| --- | --- | --- | --- | --- | --- | 
| 36dp  | 88dp| 48dp | 2dp | 14dp Roboto Medium | 16dp |

按钮与按钮之间的距离： 16dp

### 扁平按钮： 

使用场景：

* 工具栏
* 对话框
* 卡片

| 高度 | 最小宽度 | 可触发点击范围 | 角度 | 文字大小 | 文字左右边距 |
| --- | --- | --- | --- | --- | --- |
| 36dp | 64dp | 48dp | 2dp | 14dp Roboto Medium | 8dp |

按压后外边框外边距：8dp
按钮同按钮之间的距离：8dp


### 悬浮按钮

悬浮按钮是一款App里面最主要的按钮。

* 一个屏幕只使用一个悬浮按钮
* 悬浮按钮应该是触发正向操作，例如创建，添加，分享。
* 不要在悬浮按钮上加其他任何东西，例如数字角标。
* 悬浮按钮可以贴在纸缝边缘或者衔接处，不要贴在对话框、侧边抽屉和菜单的边缘
* 列表滚动的时候，应该隐藏悬浮按钮，避免其挡住列表。
* 悬浮按钮的摆放边距16dp,16dp（贴着左右两边边距）


Fab按键可以触发的形式:
 
* 工具栏(morphs into a toolbar)
* 触发出多个相关按键，例如分享按键点击后可以触发不同平台的logo，展示在小的Fab按键上。 至少触发三个小按键，触发出的新动作必须是一个类型的，比如触发出一系列分享的按键，其中不能包含联系人按键（ flinging out related actions）
* 变成一张卡片（transforming into a single sheet of material）
* 触发容易屏幕中的一个元素（morph into a sheet of material that is part of the app structure.）

## 卡片


卡片可以包含图片，文字，连接。可以包含不同大小的元素。

* 包含用来展现不同的内容：图片，影片，文字
* 卡片不起对比作用
* 支持包含不同长度的内容，如评论
* 包含交互内容，比如按键，评论	，Slider,评分，tab.
* 本该是列表，但文字超过3行
* 本该是网格，但需要展现更多文字

### 卡片布局

所有内容距离卡片边距：16dp
卡片圆角：2dp
卡片与卡片间距离:8dp
屏幕边界与卡片间留白：8 dp

#### 字体
正文：14 sp 或 16 sp
标题：24 sp 或更大
扁平按钮：Roboto Medium, 14 sp, 10 sp 字间距


卡片可以将额外内容隐藏，比如评论内容，点击下拉按钮展示更多内容。



## 底部导航栏

* 底部导航拦可以有三到五个按键
* 需要有直接到达某个界面的作用
* 导航栏里的图标应该固定的，而不是可以滑动的
* 用app的主色调表示点击到的图标
* 如果导航栏是有色的，那么久用黑色或白色来填充图标，避免彩色。
* 图标文字尽量用简短的不要用太长的说明将文字折叠起来。
* 当下拉页面的时候， 导航栏可以自动隐藏。上拉显示。
* 同tab栏不同，当手指左右滑动底部导航栏的时候，页面是不会切换的。
* 高度56dp
* 图标大小：24*24dp


## 顶部标签栏（Tab）

* 固定，可左右滑动 
* 不要在可以左右滑动的内容上面使用Taps，因为Tabs本身就可以左右滑动， 在不同的界面滑动切换， 比如说在地图界面， 就不要使用Tab。
* 标签栏上可以单是图标，或文字， 或图标加文字

* 颜色： 使用主色调，或者对比色
* 标签栏提供了将不同内容组合在一起的示能，比如说，可以用来展示报纸内容的不同恩类。 
	
* 将tabs展现在一行里， 如有需要将文字折叠， 然后省略号显示。 
* 不要在tab里面再加tab
* 注意tab和tab里面所展示的内容的关联性。


### 仅有文字的tab栏

* 高度48dp 
* 字体14sp Roboto Medium， 如有折叠12sp 
* 全大写
* 颜色：#fff或强调色
* 未激活按键颜色:#fff 70% 
* 文字到底部的距离20dp

### 既有文字又有icon的tab栏

* 高度72dp
* 图标24×24dp 
* 图标和文字间间距10dp 
* 文字到底部距离16dp

### 仅有图标的tab栏

* 高度48dp
* 图标24*24dp
* 图标到底部的距离12dp 



## 抽屉式导航栏（Navigation drawer）

* Navigation drawer 从左边划入
* 抽屉应该是在屏幕最上方， 后方所有的东西都由遮罩遮住。

* 悬浮高度16dp

* 当选中抽屉导航栏里的一项的时候，这一项的颜色应该变成应用主色调或者#00000 100%

* 抽屉菜单可以上下滑动。 设置和帮助功能应该放在所有选项的最下面

* 抽屉栏的三种形式，根据每个App不同的结构

	1. Full-height navigation drawer (全高度）
	2. Navigation drawer clipped under the app bar （在app bar下方）
	3. Floating navigation drawer (悬浮式）



**********

以上笔记并不完善，没有插图，主要是为了能够迅速找到需要的一些主要元素的尺寸。 

## 参考资料：

学习MD最好的资料当然还是取之于官网材料，当然要注意的是这绝对不是一个你只打开一次的文档，基本要来来回回的不断翻开，由于翻墙速度堪忧的原因，我个人将几个没有小视频的文档都存成了PDF这样查看起来瞬间就方便了不少。 要注意的是，Google会时不时的去更新MD，比如最近一次最重大的更新就是底部导航栏了，这玩意儿本来只是ios的，MD也弄来了~ 很多人吐槽说，这下好了，屏幕使用率更加堪忧了~但其实在实行过程中你会发现tabs,buttom naviagtion,和drawer并一定需要共存~
[Google Material design guideline](https://material.google.com/#introduction-goals)

不推荐大家直接上手读中文版的guideline,翻译问题不少，也不完善，但是要翻好也不容易，看着中文也感到挺累的，可以作为参照，如果英文觉得啃得有点辛苦，可以参照一下中文版，说不定，就豁然开朗了。 
[Material Design 中文版](http://wiki.jikexueyuan.com/project/material-design/)


Cola Chan的MD学习笔记还是很值得一看的，算是高度浓缩版。
[material design学习笔记](http://www.colachan.com/post/3416)


### 参考视频


建议大家有空去把Google I/O上关于设计的和MD的视频都扫一遍，下面是列出的是一些我觉得值得看，并和MD相关的一些视频~ 

**MD设计规范**

[Google I/O 2014 - Material design principles](https://www.youtube.com/watch?v=isYZXwaP3Q4)

[Google I/O 2014 - Material design: Structure and components](https://www.youtube.com/watch?v=dZqzz5lZFvo)

[Google I/O 2014 - Material design: Visual style and imagery]
(https://www.youtube.com/watch?v=ctzWKRlTYHQ)

[Google I/O 2014 - Material design: Motion](https://www.youtube.com/watch?v=FBD0VlcVS1E)


**MD设计实践**

[Google I/O 2014 - Material design in Google Play](https://www.youtube.com/watch?v=ZlY714W4uww)


**设计师vs工程师** 


这个视频解释了Android的基本尺寸，解释了为什么要用一倍图设计的原因以及好处
[Designer & developer communication - Google I/O 2016](https://www.youtube.com/watch?v=ZFyK1J5NrVk&list=PLJ21zHI2TNh-RpdsZdynAnvn6026Pw7Rr&index=5)

这里主要是给大家提供一个思路，感受一下Google设计师设计流程，以及设计的英文术语
[Learning to speak Designer - Google I/O 2016](https://www.youtube.com/watch?v=80hrknwD74Q&list=PLJ21zHI2TNh-RpdsZdynAnvn6026Pw7Rr&index=1)


### 工具

这个网站可以帮你迅速生成Android设计中所需要的icon尺寸，点九图等。有空我得把点九图的制作方法整理一下~
[Android Asset Studio](http://romannurik.github.io/AndroidAssetStudio/index.html)


如果说写这篇文章只是为了记录MD的最最基本的规范法则的话，那么为了更好的理解Material design,我又写了一篇理解Material design的文章，试图抛开细节，从宏观上来看MD~

