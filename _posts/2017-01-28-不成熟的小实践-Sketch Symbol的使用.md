---
layout: "post"
---

不成熟的小实践-Sketch Symbol的使用

前两天把Sketch 的Symbol功能给由内而外的研究了一番。光看不练假把式。于是就拿来这个月做的Shopbop redesign来练手。 在之前写的[Sketch使用小技巧](http://pandaqr.github.io/2016/05/07/Sketch-Tricks.html)里，提到了Symbol的三种使用方式：命名，Nested symbols,overides,其实这几种方式在真正使用的时候都是要混合起来一起用上的，而在整理Shopbop Redesign 的时候，也走过不少坑。 在这里做个记录。 

# 为什么要用Symbols 

## 利于文档管理

使用Symbols不仅利人也利己。即便之后自己不接受这个项目了，项目源文档给到别人的时候，其他人用起来也会很顺手， 或者在一个团队里，很好的使用Symbol也利于理解和编辑。 

右图是我用了Symbol之后的对比，很显然，左边虽然我已经整理过了，但是还是没有右边看起来啦么爽~
![artbords](http://ob49cesbh.bkt.clouddn.com/2017-02-09-artbords.jpg)


这是整个界面整理出来的Symbols,在整理的时候，可以再把自己的设计从头到脚捋一遍。 

![屏幕快照 2017-01-31 下午12.51.59](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午12.51.59.png)

## 轻松改变视觉效果

常常我们在设计的时候都会有想说如果换一个颜色，或者换一个线条的粗细，整个App看上去会是怎样的？ 会不会好一些，但是我们总不见得一个个去调试每个元素吧，这样会很麻烦。举个例子: 


![屏幕快照 2017-01-31 上午11.56.34](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 上午11.56.34.png)

上图的黑框的border我都用了2px,但是我在纠结到底是细一点还是就保持这样的粗度好呢？ 光想是想不出来的，而如果支取改变一个页面的话也看不出大效果。于是笨办法就是去一个个的调试，这太麻烦了，万一不满意害得一个个弄回来，当然我们可以利用Sketch的版本控制功能立刻回去之前的版本，但总而言之还是很麻烦。 

但要是有了Symbol，整个世界就不一样了，可以看到所有的分类项目基本都是用了同一种形式，因此只要为他们创建同一个Symbol就行了。 如下图。 

![屏幕快照 2017-01-31 下午12.01.37](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午12.01.37.png)

但同时我们可以看到“我喜欢的品牌”和“全部”也是采用黑框的样式，只是文字排布的位置不同，因此我们可以让这三个元素分享同一个Container，也就就是黑色边框： 

![屏幕快照 2017-01-31 下午12.06.46](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午12.06.46.png)

![屏幕快照 2017-01-31 下午12.07.25](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午12.07.25.png)

可以看到这三个边框的symbol都又包含了Container/border/normal这个symbol，于是我们就可以做到千钧一发的效果了~

![symbols1](http://ob49cesbh.bkt.clouddn.com/2017-02-09-symbols1.gif)



轻轻松松完成对所有边框的粗细控制： 
![屏幕快照 2017-01-31 下午12.10.17](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午12.10.17.png)



# 使用Symbols爬过的坑

## 文本设置

当我们设置一个Symbol的时候，文字的设置，也会影响到整个symbol的可用范围。 

还是拿之前的品种分类来举例，我拿运动装这个来制作Symbol： 
![symbols2](http://ob49cesbh.bkt.clouddn.com/2017-02-09-symbols2.gif)

 很显然，当我想要输入较长的文字段的时候，文字没有居中：
 
![屏幕快照 2017-01-31 下午1.19.54](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午1.19.54.png)

这个问题要解决很容易，我们回到Symbols查看一下文字的inspector，发现对齐是左对齐，我们只要改成居中就行了。
![屏幕快照 2017-01-31 下午1.21.30](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午1.21.30.png)

改完居中后，回到页面一看，“外套”两字自动换行了。。。
![屏幕快照 2017-01-31 下午1.22.49](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午1.22.49.png)

这个问题的解决方式就是，将文本框放大： 

![屏幕快照 2017-01-31 下午1.24.24](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午1.24.24.png)

恩，就是这么二的办法，解决了自动换行的问题。。。

完美，因此，建议**将长字段作为Symbol**

当然还有一种解决方式就是将"Fixed"改成"Auto",长字段就能自动调试了。 但是建议使用Fixed，原因是，当Symbol缩放的时候，可以保持其原本的位置和留白。

![屏幕快照 2017-01-31 下午1.25.21](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午1.25.21.png)

## 相同样式内容排布位置不同

在我所有的symbol里面，最强大的Symbol当属下面这个。 

![屏幕快照 2017-01-31 下午3.27.50](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午3.27.50.png)

他可以有下面几种变体： 

![](http://ob49cesbh.bkt.clouddn.com/2017-02-09-14858482651130.jpg)

变化比较大的就是主页上的“热门推荐”和设置里的条目了。设置里的字体比较大，只要将不同的字体覆盖就行，其他条目里没有电子邮件地址和名字那在overrides里取消就行了。 
![symbols3](http://ob49cesbh.bkt.clouddn.com/2017-02-09-symbols3.gif)


”热门推荐“整个尺寸和原本的Symbol就不大一样，因此，我们要注意调试Symbol的Resize，热门推荐里只用到了20号的字体，和一个”更多“的icon， 而icon固定右边距16px,那就可以将其Resize设置为：pin to corner (不能设置为Float in place的原因是，当边框宽度变化的时候，icon的右边距也会随之变化. ）”通知二字“如果设置为默认的Stretch,可能会导致字体变形，因此设置为Float in place较为合适，会随着container的变化和调整大小。 

![屏幕快照 2017-01-31 下午3.46.43](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午3.46.43.png)



更多关于Resize的功能，请细读[Sketch 39 Resizing: Cheat Sheet](https://medium.com/sketch-app-sources/sketch-39-resizing-cheat-sheet-feec0450e7e2#.m6kcqcjty)


## 看有好多啊Container啊

之前写Sketch 使用技巧的时候有提到，每一个即便是文字也要给它加上一个看不见的bounding box，这样做的好处很多，其中之一就是可以很方便的利用bounding box添加分割线。 

纵观整个界面，Container大致分为以下几种： 

![屏幕快照 2017-01-31 下午1.58.25](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午1.58.25.png)

好处很显然，就是我在Overrides的地方可以随意切换container~

举个例子，我不喜欢“评论”这行的container有分割线，那我只需要在右边overrides里将Container切换成Container/normal就可以啦。
![屏幕快照 2017-01-31 下午2.45.57](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午2.45.57-1.png)


![屏幕快照 2017-01-31 下午2.47.15](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午2.47.15.png)


## 原来你还是根据Symbol画布大小分类的Sketch啊~

在完成上面这个Container切换的时候有一个坑，那就是我在将所有的的contrainer归类的时候，发现在切换的时候，另外两个毫不相关的Symbol乱入了，如下图： 

![](http://ob49cesbh.bkt.clouddn.com/2017-02-09-14858458856700.jpg)


无论如何都去不掉，从做symbol也去不掉，后来我试着找了下这两个symbol的共同点，原来他们的大小尺寸相当，于是Sketch就把他们放一起了。。。

因此只要把所有的container大小换成其他的一致的尺寸就可以解决这个问题了：

![屏幕快照 2017-01-31 下午2.59.31](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午2.59.31.png)


但是我们可以借用这个特点来控制icon的颜色变化： 

1. 建立几个色块并将他们设置为Symbol
2. 用色块Symbol来填充图标（将图标设为mask)
3. 插入该icon的时候就可以在overrides里自由切换颜色。 

![屏幕快照 2017-01-31 下午3.23.04](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午3.23.04.png)


![屏幕快照 2017-01-31 下午3.23.24](http://ob49cesbh.bkt.clouddn.com/2017-02-09-屏幕快照 2017-01-31 下午3.23.24.png)


# 小贴士

## Symbol 的图层排列顺序会影响到想对应的overrides排布顺序。

![](http://ob49cesbh.bkt.clouddn.com/2017-02-09-14858684603629.jpg)

![](http://ob49cesbh.bkt.clouddn.com/2017-02-09-14858684114271.jpg)

## Symbol替换

我们可以将一个Symbol A 替换成另一个Symbol B，但要是两个symbol的大小不一，那替换后的Symbol B的大小会同SymbolA一样。

举个例子，我把下图的发现图标改成VISA 图标，由于VISA图标比发现图标要大，在替换的时候，Sketch会自动的将visa图标变小。 如果要恢复成VISA图标本身的大小，只需右键选择**set to original** 就可以了。

这个方法当然可以用在当你自己把symbol调变形了，要恢复原状的时候。 

![symbols4](http://ob49cesbh.bkt.clouddn.com/2017-02-09-symbols4.gif)




 
# 学习如何使用symbols的文章： 

以下的三篇文章都得反反复复的看，实践，自己动一动就会做啦~。

[Sketch symbol best practices (now that nested overrides are a thing)](https://medium.com/@lloyd/sketch-symbols-best-practices-now-that-nested-overrides-are-a-thing-9b651d3fe1a4#.i3xy8r7ww
)

[Sketch: Tint icons using nested symbols](https://medium.com/@FreeAndWilling/sketch-tint-icons-using-nested-symbols-2d52867e0d29#.41l14i4qw)

[This is, without a doubt, the coolest Sketch technique you’ll see all day.](https://medium.com/ux-power-tools/this-is-without-a-doubt-the-coolest-sketch-technique-youll-see-all-day-ddefa65ea959?source=bookmarks---------0----------)


以上都是我不成熟的小实践，个人感觉还需要在图层命名等方面改进，Symbols的归类也是个技术活，需要注意观察，合理提取公因式，合并同类项。







