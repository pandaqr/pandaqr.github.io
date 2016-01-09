---
title: React’s diff algorithm(中文版)
layout: post
---

<h3>Something go First</h3>
<p>这是一篇介绍diff算法的翻译文章，原文来自FB工程师 Christopher Chedeau所写的《React’s diff algorithm》，特此说明，Ok，Here we go.</p>

<h3>Background</h3>
<p>React是由Facebook所发起的一个用于构建UI的Js库，创始初衷在于提高Js性能。在这篇文章中，我将使用图文的方式来呈现Diff算法和渲染是如何在React中工作的，并基于此原理，读者可以根据实际情况优化你的应用。</p>

<h3>Diff Algorithm</h3>
<p>首先，在正式开始了解React的实现细节之前，让我们从大体上来看下它是如何工作的：</p>
<span><img src="/assets/images/2015/10/workcode.png" alt=""></span>
<p>在任何时候，你都能通过代码来描述你想要的UI效果。但是请记住，如果你使用了React库来描述你的UI，那么你并不是真正得到了真实页面上的DOM，得到的只是保存在内存中的一些轻量的Js对象，我们把这些对象称之为虚拟DOM。</p>
<p>React之所以能够大大提高网站性能，是因为React仅仅执行前一页面渲染成后一页面时所需要执行的最少差异动作，省去很多DOM属性值中间变换的渲染过程。</p>

<h3>逐层比较(Level By Level)</h3>
<p>在一般情况下，计算任意两棵二叉树之间的最少差异是一个O(n^3)的问题，你可以想象，在React实现中采用这种算法是不可取的，因此React设计了一种时间性能接近O(n)的启发式算法。</p>
<p>算法原理是<font color="orange">React对任意两棵二叉树进行逐层比较，以此来确定这两棵二叉树之间的最少差异数。利用该方法大大降低了比较复杂度，按照通常来理解，这种比较方法是缺乏准确性的，但是在实际应用中观察发现：在DOM树中移动上下级节点的情况是非常少见的，通常只是在同一层的兄弟节点之间移动，</font>如下图所示：</p>
<span><img src="/assets/images/2015/10/level.png" alt=""></span>

<h3>列表(List)</h3>
<p>假设我们现在有一个组件，在一次迭代循环中，渲染出五个组件，接下去在该组件列表中插入一个新的组件，在信息如此匮乏的情况下，实现两个组件列表之间的映射是一件非常困难的事情。</p>
<p>在默认情况下，React会把前一个列表中的第一个组件与后一个列表中的第一个组件进行配对，以此类推，当然，你可以为每个组件提供一个Key属性来解决映射问题。在实际应用中，我们能够很容易的在孩子节点中找出唯一的Key，如下图所示：</p>
<span><img src="/assets/images/2015/10/list.png" alt=""></span>

<h3>组件(Components)</h3>
<p>一个React应用通常是由许多用户自定义的组件组成，这些组件最终转化成一棵主要由div(s)组成的DOM树。这一辅助信息被diff算法所很好的利用，因为React通常只比对那些具有相同类的组件。
举例，假设现在Header被一个ExampleBlock所代替，React将会简单粗暴的把Header标签移除，然后创建ExampleBlock，而不会浪费时间去比对这两个毫无相似之处的组件，如下图所示：</p>
<span><img src="/assets/images/2015/10/companet.png" alt=""></span>

<h3>事件代理(Event Delegation)</h3>
<p>为DOM节点设置事件监听器是一件非常耗时和消耗内存的痛苦事。不过，React实现了一项更为流行的技术，叫做"事件代理”，更进一步的是，React还重新实现了一套遵循W3C标准的事件系统，这意味着IE8中原有的事件处理的Bug已成往事，事件名称在各个浏览器之间得以保持一致。</p>
<p>让我来解释一下这是如何实现的：单事件监听器与文档根节点进行绑定，当触发某一事件时，浏览器给了我们想要的DOM节点。因此，React为了在DOM层级间传播事件，并没有在虚拟DOM层级间迭代循环。</p>
<p>取而代之的是我们巧妙地利用了每个React组件都有一个编码层级的唯一标示符ID这样一个事实。通过简单的字符串操作我们能很容易的获取到所有父节点的ID。同时把事件监听器放在一个Hashmap中，我们发现这样做的性能远高于把事件监听器与虚拟DOM节点进行绑定。下面的代码展示了事件是如何在虚拟DOM间进行分发的：</p>
<pre>
// dispatchEvent('click', 'a.b.c', event) 
clickCaptureListeners['a'](event); 
clickCaptureListeners['a.b'](event); 
clickCaptureListeners['a.b.c'](event); 
clickBubbleListeners['a.b.c'](event); 
clickBubbleListeners['a.b'](event); 
clickBubbleListeners['a'](event);
</pre>
<p>浏览器为每个事件和每个监听器都创建一个新的事件对象，这样看起来很好，因为我们能追踪到每个事件对象甚至修改它，然而这也意味着需要许多次的内存分配操作。而React会在应用启动时在内存中分配一个对象池，无论何时需要事件对象，都可以从这个对象池中获取一个可用的事件对象进行复用，这一举措大大降低了垃圾回收的复杂度。</p>

<h3>渲染(Rendering)</h3>
<h3>批处理(Batching)</h3>
<p>无论何时在组件上触发setState方法，React都会把这个组件标记为dirty，等到结束事件循环时，React会对所有标记为dirty的组件进行批处理，重新渲染它们。
该批处理意味着在一个事件循环期间，无论某个DOM元素的属性值被更新过几次，最终在循环结束之后，该属性值只会被渲染一次，这对于构建一款高性能的应用至关重要，而在原生的JS中要实现这个功能却是一项非常困难的工作，而在React应用中，该功能与生俱来，如下图所示：</p>
<span><img src="/assets/images/2015/10/batching.png" alt=""></span>

<h3>子树渲染(Sub-tree Rendering)</h3>
<p>当触发某个组件的setState时，该组件将会为其孩子节点重新构建虚拟DOM。如果你不幸调用了根元素的setState方法，那么整个React应用都将重新渲染，所有组件的render方法都将会被调用，即使这些节点根本就没有发生改变，这听起来很吓人，然而在实际应用中，并不如此，因为我们仅仅只操作了保存在内存中的虚拟DOM，而并没有碰真实的DOM。</p>
<p>首先，我们正在讨论的是展示用户界面。因为屏幕大小是有限制的，而你通常需要一次性的有顺序的展示上百甚至上千个元素。</p>
<p>另一个关键点是当你在写React代码时，你并不会常常调用根节点的setState方法。你只对那些受到事件触发的组件进行setState的调用，这意味setState方法的调用常常局限在与用户交互的组件上，很少会调用根节点的setState方法。</p>
<span><img src="/assets/images/2015/10/sub-tree.png" alt=""></span>


<h3>选择性的子树渲染(Selective Sub-tree Rendering)</h3>
<p>最后，你也可以通过在组件上实现下面的方法来防止其子树进行渲染。</p>
<pre>
boolean shouldComponentUpdate(object nextProps, object nextState)
</pre>
<p>基于组件的前后状态，你可以告诉React该组件并没有发生变化，所以无需重新渲染。如果你能够正确使用这项功能，那么这对你应用的性能是一个极大的提升。
为了能够使用该功能，你必须能够比较JS对象，但是这会带来很多问题，比如我们应该进行何种程度的比较，深还是浅，如果进行深层次的比较，那我们也许应该使用不可变的数据结构或者进行深度拷贝。</p>
<p>并且你还要去考量，如果使用此项了功能，那么我们要确保比较JS对象所带来的计算时间要少于未使用此项功能而需要进行渲染的时间。</p>

<h3>Reference</h3>
1、<a href="http://calendar.perfplanet.com/2013/diff/">http://calendar.perfplanet.com/2013/diff/</a>

2、<a href="http://blog.vjeux.com/">http://blog.vjeux.com/</a>