---
layout: "post"
---

事情是这样的， 我研究 Design system 研究到一半发现，这不是我目前所需要的内容，我的目的是更加完善的搭建行动村的一个组件， 毕竟我们公司还没有什么一系列的产品， 不需要一个庞大的 Design system 去沟通。 

我需要的只是目前在使用Figma画交互的时候搭建一个更好的统一组件， 这叫做library.

于是，问题来了， Style Guide, Library , Design System ,这些东西到底有什么区别？ 到底哪些是适合我们的？ 

于是我看到了这个视频👇

https://www.youtube.com/watch?v=rO5dBA-avfw

![ab75a8](https://raw.githubusercontent.com/pandaqr/BlogImageBed/master/img/ab75a8.png)

那我们就一起来扒一下三个东西到底有什么区别吧~

# Style guide

样式指南是公司/品牌的样式，样式，做法和原则的实体或数字文档，并会说明如何使用它

The physical or digital document that represents the styles, patterns, practices, and principles of a company/brand and teaches how to use it

这个在印刷时代就有的古早产物，最典型的代表比如NASA
![1nsUIW](https://raw.githubusercontent.com/pandaqr/BlogImageBed/master/img/1nsUIW.png)

一个完整的Style Guide 里面或包含了如下的内容

* Design Principles
* Best Practices 
* Brand styles 
* Use Cases 
* Writing styles&Tone
* Iconography 
* Imagery 

## 举例🌰
Foursquare Style Guide
https://playfoursquare.s3.amazonaws.c...

Animal PLanet Styles Guide
https://logoblink.com/wp-content/uplo...

Barnes & Noble 
http://portacreativeserver.com/vault/...


使用Style Guide可以让我们的整个产品体系看起来更加的视觉上具有统一性， 比如我们要做一个动物星球的网站，如果我们不使用动物星球的样式指南， 那我们可能设计出来的就是一个新的网站，看起来和原本的动物星球毫无关系感觉是两个产品。 

Style Guide能让我们较为自由的进行创作， 但有一定的模糊性， 可能会导致一些不一致性。 


# Pattern library

组件库指的是一组相关的，可复用的相关组件，通常包含了代码示例，设计准则和用例

An organized set of related, reusable components, often containing code examples, design guidelines, and use cases

较常在交互设计中见到，可能会包含一些列的UI组件，比如卡片， 表单等，整个组件库就像是乐高玩具一样， 有着一个个的模块， 你可以自由的拼搭，但又有一定的局限性。 


一般一个组件库内包含了

* Pattern Names 
* Visual Presentation
* Design Elements 
* Code Samples 
* Use cases 
* Related elements 


做组件库就像洗澡， 洗澡🛀前要鼓起十足的勇气做足心理准备和纠结挣扎， 但洗澡的过程，特别是洗完澡后却又相当爽。

这大抵就是做模式库给人的感觉， 想到要做模式库就感觉好累好麻烦， 做完之后开始搭积木了，就感觉有那么一丢丢的爽 ， 但设计系统还是感觉会有点死板，不能自由的在画布上乱搞...

## 举例🌰
Pattern Library
https://natashahockey.github.io/patte...

MailChimp Pattern Library
http://ux.mailchimp.com/patterns

Bootstrap
http://getbootstrap.com/2.3.2/

# Design system

设计系统指的是值，语义，语法和上下文的全面集合，构成共享设计语言的基础

The comprehensive set of values, semantics, syntax, and context that form the foundation of a shared design language

设计系统被视为解决Style Guide 和pattern library 不足之处的一个整全的解决办法 ，毕竟前两个还是会导致一些inconsistancy 的问题。 我们搭建设计系统是希望整个体系可以是相互呼应，有着一致性的。不只是有一堆的UI组件， 还需要有架构， 含义，场景等。 这可以帮助你在一些列的产品中保持一致性。  

Design System其实就是一个语言（a Shared Language） , 当我们使用同一个语言的时候， 这将不仅仅帮助我们有所连接， 也让我们明白彼此的理想， 愿景。
Design System 对于有着多个直线产品的大公司来说是相当需要的， 毕竟他们有许多的产品人员，从设计师，工程师， 到产品经理，当大家都说同一种语言的时候，可以更快的帮助彼此打成共识， 搭建产品。 比如我们说卡片的时候， 卡片就有成千上万的样式， 但是当我们对话是基于同一套设计系统的时候， 沟通起来就方便多了， 因为我们有着同样的沟通基础。 

一般一个Design System 里面包含了： 

* Pattern Library
* Style Guide
* Shared Conceptual Model 
* Shared Language 
* Design Resources 
* Shared code components 


## 举例🌰

Shopify Polaris
https://polaris.shopify.com/

Lightning Design System
https://www.lightningdesignsystem.com

Carbon Design System
http://carbondesignsystem.com/



因此如果你是一个拥有者众多产品支线的大公司，搭建一个设计系统，是需要的， 但如果你只是要搭建一两个产品，是一个很小的团队，那么pattern library 就足够了。 当然每个公司都最好有一个style guide or brand guide， 毕竟这是公司的脸。。。

这不还是因为行动村要迭代了，先不提什么设计系统，至少不画个 style guide 不行啊。。🤦‍♀️

