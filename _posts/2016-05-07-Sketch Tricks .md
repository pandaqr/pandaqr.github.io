---
layout: "post"
---

不大写干货，今天准备来写一些关于Sketch的干货~ 算是个人笔记吧~ 

# 善用快捷键

a,r,o,u,v这种常用的快捷键就不叨叨了。

## 如何有效的选择


#### 如和选中组内的特定元素？(Command + Click)

当我们的一个画布上有许多的图层的时候，选中一些特定的元素就显得有点麻烦， 比如说当我们已经**Group+g**将10个元素放在一组里面的时候，通常选中的时候都是整个组在那边移动，但是常常我们只想选择里面的某一个元素，通常我们可以选择双击，这个方法很便利，但是有时候为了求快多按了几下也会造成一定的麻烦，因此，可以在**点击的时候按着Command**。 

当然如果你可以预见在接下去的一段时间内你都不会选中整个组，可以将控制面板左边的**click-through when selecting**给勾选掉，这样你在选则组的元素时候 Sketch就不会自动帮你选中整个组了。


![Click_through](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Click_through.gif)


#### 如何移动一个元素而不影响到其他内容？ (command + option)

当选中一个元素后，按住**command+option**就可以将鼠标放在任意位置移动该元素，而不影响到其他的元素。


![Command+Option](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Command+Option-1.gif)


#### 如何选中一个元素而不影响到其他内容？ (Option + 选择) 

通常我们要选择许多元素的时候，只需要将光标移到外面然后拉扯就能选中了，但往往这个时候会选中许多我们不需要的内容，因此为了更精准的选择可以按住**option**的同时进行选择，这样只有当选择的区域被全覆盖的时候，该层组才会被选中。 

![Option_select](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Option_select.gif)

#### 如何选中被遮住的元素？ (Option + Click)

当画布上有许多图层的时候，有些元素会被覆盖，这时候可以按住**option**点击选择被覆盖的元素。


![Option+click](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Option+click.gif)


#### 如何选中所有画布 (Command + Shif + a)

选择所有图层方式很简单就是**Command + a**,但若是想要选中所有画布，可以直接按**Command + Shif + a**。

#### 如何将所有的画布都收起来（Collapse artboards and Groups)

该功能隐藏的有点深，藏在**View > Layer list > Collapse artboards and Groups**
照理来说这应该是个听常用的功能，但是可能会有点麻烦每次都要点击好几次才能完成，如何加速，两个方案： 

1. 自定义快捷键
2. 使用[Runner](http://sketchrunner.com)插件（等下会讲到），快速查找运行。

#### 如何将某一组下的所有元素展开(alt+click)

通常一个组下面可能还有好几组，因此想要将一个组下的所有元素展开，就可以按着Alt然后点击组前面的小三角

## 重命名( Command + r )
重命名的方式通常我们会双击选中的层，或者也可以直接在选中元素的时候，按**Command + r**，这样就不用将鼠标来回移动，直接可以在选中的时候更改。 

当要批量更改层组的名字的时候，可以先**command+r**,完成后，按**tab**键切换选中的层组，这样就能自动快速的往下命名了。 

#### 批量命名

有时候批量命名真是个体力活，用上[RenameIt](https://github.com/rodi01/RenameIt)插件就可以帮你解决一些相似的文件的命名啦~ 

几个参数： 

* “%N”数字

* “ * ”原本的命名

* "%a" or "%A"用字母命名

* "%w" or "%h" 高度宽度

## 操控图形

#### 旋转图标(Command + click)

在选择一个图形的时候四周会出现边框供你调整图形大小，当需要图形方向的时候，可以按住**command**键将鼠标移动到右上角就能按到旋转图标。 

![roate](http://ob49cesbh.bkt.clouddn.com/2017-01-22-roate.gif)


#### 调整图形初始点 （space) 

在我们按住r,o,或者u来绘制基本图形的时候，我们会发现很多时候起始点并不是我们理想的，当然你可以放掉后再移动图形位置。

当然，如果你在画图形的时候发现起始点不理想你也可以按住**space**直接改变图形的位置。 

![Space](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Space.gif)

#### 重设图形边框（Flattern)
假设你在画一个五角星，当你旋转的时候，肯定有点晕乎，通常不知道哪里是顶端，这时候你就可以用Flatten键，一键将五角星的边框（bounding box)恢复到正常矩形。

![flattern](http://ob49cesbh.bkt.clouddn.com/2017-01-22-flattern.gif)

#### 如何将文字变为图形（Shift + Command + O）

这个可以在菜单栏里找到，当然为了省时间，可以直接**Shift + Command + O**（字母O)

#### 如何在Vector编辑模式下选中线条的重点(command) 

在双击进入某个图形的编辑状态的时候，如果想要找到两点一线的重点的时候，可以按着Command键点击


#### 放大局部 (command + 2) 

#### 快速改变数值大小

比如，通常我们在讲尖锐的边角变成圆形的时候，会用到corner，这时候用鼠标点击一下下增大corner数值有点累人，为了使数值更快的变化，我们可以按住**shift**键，一次增加10px。 


![Corne](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Corner.gif)


如果想要让数值有小数点的话，可以按着**alt+up/down**

由于系统默认的按住Shift后增加或减少的值是10px,而每个设计师的通常心里都有个基准数，比如8px,因此，我们可以用[nudg.it](http://nudg.it)这款app来调节默认值~

#### 

## 把控图形风格

#### 复制style

当我们将一个图形很好的填色之后，比如用了多重渐变色，我们想要让另外一个元素也使用同样的style，我们可以复制黏贴该元素的style:

* option + Command + C  （复制style）
* option + Command + V  （黏贴style）


#### 如何绘制只有一条边的表格？ 

边框我们可以直接按快捷键b，但是如果我们只需要一边有边线呢， 这种情况下我们可以用**inner shadow（内阴影）**,记得将blur值设为0。比如这样： 

![gird](http://ob49cesbh.bkt.clouddn.com/2017-01-22-gird.png)
像上图这样的按键，建议使用Bounding box,也就是隐形的长方形，用它来包裹内容，这样做的好处是，隐形的边可以直接合在一起，不用去算距离，bounding box也可以代表点击范围，另外也可以用inner shadow来画边线。
![屏幕快照 2017-01-22 下午4.50.57](http://ob49cesbh.bkt.clouddn.com/2017-01-22-屏幕快照 2017-01-22 下午4.50.57.png)

同时我们还可以用这个办法来绘制分割线，我们可能会用Line来绘制分割线，但这样做你每次要去点击它就很麻烦. 因此使用内阴影是个很好的解决方案。 
![iPhone 7](http://ob49cesbh.bkt.clouddn.com/2017-01-22-iPhone 7.png)



#### 如何画出一致性的按钮

Material design有规定按钮的内容距离都为8dp， 但是我们无法把控的是按钮的内容长度，如果多了两个文字，我们又要重新调节距离，就很麻烦。

我们可以使用 [Relabel button](https://github.com/kenmoore/sketch-relabel-button)来很好的解决这个问题.

![Relabel button](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Relabel button.gif)


# Symbol的使用

Symbol在Sketch 3.7.2.上有了重大的改变。好吧我已经忘了之前的了。 

#### Symbol 分组

有时候在设计一款Button的时候有两种状态，选中和非选中或者鼠标悬停。 
在Symbol的页面我们可以设计两个Symbol，使用同一个主命名比如button，然后在后面用**"/"**来分割命名，说明Symbol的状态： 

![Button](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Button.png)


同样的道理，在你想要命名某一些图层的时候可以在前面加上想要将元素放入的Folder名字，比如Project/icon1，输出的时候，就会自动生成一个Project的文件。icon1就会自动放在里面了。 


#### Nested Symbols 


今天介绍的一种Symbol的使用方式叫做nested Symbol. 也就是说你可以创建一个主symbol,主symbol下还可以有n个附属的symbols，这些附属的symbols的变化得依着主symbol。

**制作方式:**

1. 设置一个Symbol后，
2. 在Symbol页面再插入此symbol(可多次插入多个）
3. 比如你需要将这个Symbol的底色做一个小改变，但是里面的元素还是同主Symbol一致，可以加入一个不同的元素，将此元素同插入的Symbol选中后组合然后创建成一个新的Symbol，此时这个Symbol依然依附于主Symbol，主Symbol上的元素大小改变也会影响到这个次元素。这个方法非常适用于有颜色的底部导航栏。


![Symbo](http://ob49cesbh.bkt.clouddn.com/2017-01-22-Symbol.gif)



#### 用Symbol做导航状态

通常一个导航的按键有选中和未选两种状态，通常来说复制黏贴一下的确很方便，但是万一我们要对导航栏有大幅度的改动，那么把他设置成Symbol是最好不过的。让我们看一下如果用Symbol来自动在选中不同状态的tab间切换：

1. 将所有的状态叠加。像我这里的三个标签只有两种状态，选中和未选中。因此我只要叠加一个全选中的状态就好。

![屏幕快照 2017-01-22 下午8.01.48](http://ob49cesbh.bkt.clouddn.com/2017-01-22-屏幕快照 2017-01-22 下午8.01.48.png)

![屏幕快照 2017-01-22 下午8.00.55](http://ob49cesbh.bkt.clouddn.com/2017-01-22-屏幕快照 2017-01-22 下午8.00.55-1.png)

2. 插入Symbol之后，比如我只需要主页是高亮的，表示用户在主页面，那我只要把选中状态的发现，和设置给去掉就好了（按空格键）： 

![symbols](http://ob49cesbh.bkt.clouddn.com/2017-01-22-symbols.gif)

但是这个方法有个缺点，就是不适用于图标。通常移动端的导航栏都有图标，因此可能更加适用于网页端。

那么问题就来了，一般移动端底部导航栏都会是图标+文字的组合，上面这个技能解决的文字切换的问题，那图标是否可以切换呢？ 这就要用到之前提到的nested symbols啦：

举个例子，我们要做的如下这个导航栏： 

![屏幕快照 2017-01-23 下午10.38.56](media/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202017-01-23%20%E4%B8%8B%E5%8D%8810.38.56.png)

我们可以用一个symbol来控制上面的所有的图标:

1.将各个状态的图标都设置成symbol.
![屏幕快照 2017-01-23 下午10.42.09](media/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202017-01-23%20%E4%B8%8B%E5%8D%8810.42.09.png)

2.用nested symbol的方式将所有的图标symbol和底部背景结合起来创造出一个新的symbol，你可以叫它navi:
![屏幕快照 2017-01-23 下午10.41.37](media/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202017-01-23%20%E4%B8%8B%E5%8D%8810.41.37.png)

3.完成上面两步后我们就可以愉快的玩耍啦，将navi插入各个页面的底部，在右边的overides切换图标symbol,就可以轻轻松松搞定所有底部导航栏。 
 ![屏幕快照 2017-01-23 下午10.45.58](media/%E5%B1%8F%E5%B9%95%E5%BF%AB%E7%85%A7%202017-01-23%20%E4%B8%8B%E5%8D%8810.45.58.png)

GIF演示： 
![symbo](media/symbol.gif)


那现在要做的底部栏是既有文字又有图标的也不怕啦~

# 完美插件

### [Runner](http://sketchrunner.com)

通常我们会在sketch上安装许许多多的插件，而光是Sketch的快捷键就够我们记了(当然嘛，快捷键无非就command,option, shift, control这几个，随便按~按按就懂了），而插件的快捷键。。。算了，我扛不住。 

于是Runner出现了，Runner大法好啊，从此以后，我只要记得runner的快捷键**command+'**就能迅速的找到sketch上的任意功能。 

简而言之，runner就是sketch上的Spotlight,or Alfred~ 


### [Craft](https://www.invisionapp.com/craft)

我还是得表扬一下invision的，Craft将一些机械劳动简化的很好，比如我要复制一组卡片，Craft能很好的将内容有条理的复制，还能自动将图片或者文字按照类型改变。（但是吐槽一下，Splash上的people的图片都好不people啊）







