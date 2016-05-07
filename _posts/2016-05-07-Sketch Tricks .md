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

![](/content/images/SketchTricks/Click_through.gif)


#### 如何移动一个元素而不影响到其他内容？ (command + option)

当选中一个元素后，按住**command+option**就可以将鼠标放在任意位置移动该元素，而不影响到其他的元素。

![](/content/images/SketchTricks/Command+Option.gif)



#### 如何选中一个元素而不影响到其他内容？ (Option + 选择) 

通常我们要选择许多元素的时候，只需要将光标移到外面然后拉扯就能选中了，但往往这个时候会选中许多我们不需要的内容，因此为了更精准的选择可以按住**option**的同时进行选择，这样只有当选择的区域被全覆盖的时候，该层组才会被选中。 

![](/content/images/SketchTricks/Option_select.gif)



#### 如何选中被遮住的元素？ (Option + Click)

当画布上有许多图层的时候，有些元素会被覆盖，这时候可以按住**option**点击选择被覆盖的元素。

![](/content/images/SketchTricks/Option+click.gif)

#### 如何选中所有画布 (Command + Shif + a)

选择所有图层方式很简单就是**Command + a**,但若是想要选中所有画布，可以直接按**Command + Shif + a**。


## 重命名( Command + r )
重命名的方式通常我们会双击选中的层，或者也可以直接在选中元素的时候，按**Command + r**，这样就不用将鼠标来回移动，直接可以在选中的时候更改。 

当要批量更改层组的名字的时候，可以先**command+r**,完成后，按**tab**键切换选中的层组，这样就能自动快速的往下命名了。 


## 操控图形

#### 旋转图标(Command + click)

在选择一个图形的时候四周会出现边框供你调整图形大小，当需要图形方向的时候，可以按住**command**键将鼠标移动到右上角就能按到旋转图标。 

![](/content/images/SketchTricks/roate.gif)


#### 调整图形初始点 （space) 

在我们按住r,o,或者u来绘制基本图形的时候，我们会发现很多时候起始点并不是我们理想的，当然你可以放掉后再移动图形位置。

当然，如果你在画图形的时候发现起始点不理想你也可以按住**space**直接改变图形的位置。 

![](/content/images/SketchTricks/Space.gif)



#### 如何将文字变为图形（Shift + Command + O）

这个可以在菜单栏里找到，当然为了省时间，可以直接**Shift + Command + O**（字母O)


#### 放大局部 (command + 2) 

#### 改变corner值

通常我们在讲尖锐的边角变成圆形的时候，会用到corner，这时候用鼠标点击一下下增大corner数值有点累人，为了使数值更快的变化，我们可以按住**shift**键。 

![](/content/images/SketchTricks/Corner.gif)

## 把控图形风格

#### 复制style

当我们将一个图形很好的填色之后，比如用了多重渐变色，我们想要让另外一个元素也使用同样的style，我们可以复制黏贴该元素的style:

* option + Command + C  （复制style）
* option + Command + V  （黏贴style）


#### 如何绘制只有一条边的表格？ 

边框我们可以直接按快捷键b，但是如果我们只需要一边有边线呢， 这种情况下我们可以用**inner shadow（内阴影）**,记得将blur值设为0。


# Symbol的使用

Symbol在Sketch 3.7.2.上有了重大的改变。好吧我已经忘了之前的了。 

#### Nested Symbols 


今天介绍的一种Symbol的使用方式叫做nested Symbol. 也就是说你可以创建一个主symbol,主symbol下还可以有n个附属的symbols，这些附属的symbols的变化得依着主symbol。

**制作方式:**

1. 设置一个Symbol后，
2. 在Symbol页面再插入此symbol(可多次插入多个）
3. 比如你需要将这个Symbol的底色做一个小改变，但是里面的元素还是同主Symbol一致，可以加入一个不同的元素，将此元素同插入的Symbol选中后创建一个新的Symbol，此时这个Symbol依然依附于住Symbol，主Symbol上的元素大小改变也会影响到这个次元素。


![](/content/images/SketchTricks/Symbol.gif)

#### Symbol 分组

有时候在设计一款Button的时候有两种状态，选中和非选中或者鼠标悬停。 
在Symbol的页面我们可以设计两个Symbol，使用同一个主命名比如button，然后在后面用**"/"**来分割命名，说明Symbol的状态： 

![](/content/images/SketchTricks/Button.png)

参考文章： 

# 完美插件


### [Runner](http://sketchrunner.com)

通常我们会在sketch上安装许许多多的插件，而光是Sketch的快捷键就够我们记了(当然嘛，快捷键无非就command,option, shift, control这几个，随便按~按按就懂了），而插件的快捷键。。。算了，我扛不住。 

于是Runner出现了，Runner大法好啊，从此以后，我只要记得runner的快捷键**command+'**就能迅速的找到sketch上的任意功能。 

简而言之，runner就是sketch上的Spotlight,or Alfred~ 


### [Craft](https://www.invisionapp.com/craft)

我还是得表扬一下invision的，Craft将一些机械劳动简化的很好，比如我要复制一组卡片，Craft能很好的将内容有条理的复制，还能自动将图片或者文字按照类型改变。（但是吐槽一下，Splash上的people的图片都好不people啊）



