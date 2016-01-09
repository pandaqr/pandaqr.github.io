---
title: 中美日韩四国Github开发者比较
layout: post
---

<h3>Background</h3>
<p>越来越多的开发者开始使用Github工具，在这之前谁都没法预估一个代码托管网站会收到追捧，受由InfoQ推出的2015年<a href="http://www.infoq.com/cn/articles/github-chinese-developers-annual-analysis-report">GitHub中国开发者年度分析报告</a>的启发，想做一份关于中美日韩（为什么选择这四个国家，理由是这几个国家跟中国的关系最微妙，呵呵，瞎扯，其实我是随便选了这四个国家）四国的开发者比较文章。</p>

<h3>四国开发者数量比较</h3>
<p>通过调用Github API来获取每个国家的开发者数量，数据在一定程度上可能会少算导致不够准确，因为API中根据`location`这个属性去定位开发者所属的国家，而`location`这个参数值是可选的，如果开发者未填写此项，那么这部分用户将不会被统计在内。具体发起的HTTP GET请求如下：</p>
<pre>https://api.github.com/search/users?q=location:china</pre>
<p>分别获取了这四个国家的开发者数量，虽然数据在某种程度上并不能保证准确，但不影响其参考意义，四国开发者数量对比图如下所示：</p>
<span><img src="/assets/images/2015/10/cukj.png" alt=""></span>

<p>从上图可以得知，国内开发者数量已经超越美国，处在排头兵的位置，Github在国内开发者社区中的受欢迎程度可见一斑。</p>

<h3>四国开发者使用语言分布情况</h3>
<p>通过有针对性的选择当前比较主流的开发语言：Javascript,Java,Php,CSS,Swift,Python,Ruby,Perl,Shell,C，了解四国开发者的语言使用情况。</p>
<span><img src="/assets/images/2015/10/language-china.png" alt=""></span>
<span><img src="/assets/images/2015/10/language-usa.png" alt=""></span>
<span><img src="/assets/images/2015/10/language-japan.png" alt=""></span>
<span><img src="/assets/images/2015/10/language-korea.png" alt=""></span>

<p>以上四图分别展示了中美日韩四国开发者的语言使用情况（备注：开发语言所对应的扇区面积越大，表示对应的开发者数量越多），我们似乎能够比较确信的获知以下几点信息：</p>

<p>纵观统计图可以发现，前台语言Javascript稳固开发语言第一，Js和Java开发者数量占据所有开发者数量的50%以上，尤其是中韩，两者呈现着势均力敌的效果，而美日两国虽然Js和Java开发者占比很大，但Js明显比Java更受开发者喜爱。</p>
<p>排在Js和Java语言之后的Python，PHP和Ruby不相上下，PHP一直保留着大块江山，目前已推出PHP7；Python和Ruby作为后起之秀，具备动态快速开发的优势，越来越成为开发者的心头之好。</p>
<p>样式语言CSS的出现有点出乎意料之外，在老旧的思维习惯里，似乎有点轻视它；但细细想来，在如今把用户体验当尚方宝剑的产品设计里面，样式不重要才见的奇怪呢，不知从哪年起，UX方面的人才突然变得非常受欢迎，同时轻框架，重设计的提倡也带来用户体验的变革，这对用户来说必然是一件好事，同时也傲娇到再也不需要去迎合老旧，土鳖的设计习惯，因为当下应用产品正在经历着从匮乏到丰富到五彩缤纷到争雄逐鹿到你死我活的变革，真是虐死一堆产品汪的节奏。好了，有点跑题，只是想说UX被越来越重视着。</p>
<h3>Github中国开发者区域分布图</h3>
<p>这似乎是一个已知的事实，用下面的这幅图说话吧。</p>
<span><img src="/assets/images/2015/10/china-fenbu.png" alt=""></span>

<p>没有歧视其他省份开发者的意思，只是有针对性的选择了这几个我认为开发者相对集中的区域（见着色区域，颜色越深，代表开发者数量越多），这幅图不过是在确认一个事实：北上广深依然有绝对优势的开发者，这些一线城市凭借其综合因素仍然吸引着大批开发者前往，但不可否认的是杭州作为一座时尚美丽干净的城市，尤其是近几年互联网的火热让杭州有赶超一线城市开发者的趋势。</p>

<h3>Ending</h3>
<p>这只是作为我业余时间产生的一个衍生品，数据来自官方（All Data From Github），但不代表任何人，任何组织，我只是觉得好玩而已，并且这篇文章也只是从量上进行一个横向比较，没多少有价值的东西，业余有精力再多挖掘一点有意思的东西分享给大家，就这样。</p>

<h3>Reference</h3>
<pre>
1、http://ecomfe.github.io/echarts/index-en.html
2、https://developer.github.com/v3/search/
</pre>