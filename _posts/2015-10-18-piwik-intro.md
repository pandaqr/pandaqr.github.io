---
title: Piwik实践入门介绍
layout: post
---

<h3>Background</h3>
最近团队内部想利用piwik作为网站流量分析工具，刚好借此机会接触之，用过之后才发现，piwik强大又精细，强大之处表现在其功能性完全可以媲美主流的商用流量分析工具，如Google Analystics，百度流量统计等；精细之处表现在给用户很强的惊喜感，体验到很多意想不到的细节，用户接触之后自有体会。可以在线体验：<a href="http://demo.piwik.org/index.php?module=CoreHome&action=index&idSite=7&period=day&date=yesterday#/module=Dashboard&action=embeddedIndex&idSite=7&period=day&date=yesterday&idDashboard=1">ONLINE DEMO</a>，写这篇文章的目的在于总结这几天的学习心得，算是一个回顾，也把在学习研究过程中遇到的困惑进行记录。


<h3>Install</h3>

安装分『安装需要满足的条件』和『安装过程』，同时官网还提供了安装视频，这一切尽在：<a href="http://piwik.org/faq/#installation">Installation</a>


<h3>New to piwik</h3>

官网上该板块的主要目的是带新用户进入piwik的世界，了解piwik的工作机制甚至会涉及到与同类型的流量统计工具的横向比较，是新用户了解piwik的最好实践：<a href="http://piwik.org/faq/new-to-piwik">New to Piwik</a>


<h3>How to</h3>

该板块主要介绍如何玩转piwik，包括如何定制个性化变量，如何提高piwik运行的性能等等一系列让你更深入玩转piwik的相关建议和最佳实践：<a href="http://piwik.org/faq/how-to">How to</a>


<h3>Troubleshooting</h3>

不管你是新用户还是历史悠久的老用户，这里一定是会来逛逛的，可以说该板块是问题集，遇到问题是不可避免的，不妨来这里看看，或许前人已经给出了很好的解答：<a href="http://piwik.org/faq/troubleshooting/">Troubleshooting</a>


<h3>一些思考的问题（Q&A）</h3>
<p>
1、访问次数，访客数（独立），浏览次数如何确定？
1）浏览次数基于追踪的js代码有没有被加载，加载则+1，建议把追踪代码放在公共页面；
2）访问次数表示访问被监测网站的用户数（用户不去重）；基于first party uuid和ip，session过期之后，重新生成uuid，访问次数+1；
3）访客数指独立访客数，在访问次数的基础上去掉重复的用户；基于ip地址的启发式算法；
</p>
<p>
2、PIWIK页面打开速度很慢？
官网提到的可能原因是：在默认情况下，piwik实时处理用户发出的请求（页面点击操作）生成报表进行展示，所以后台计算以及页面渲染展示的时间会比较长。
解决方案是：在crontab中设置定时任务，定时进行报表的归档。理论上可以提高访问速度，设置定时任务。
</p>
<p>
3、访客数如果想汇总体现，如何在页面提现？
开启相关标志位即可：
</p>

<pre>
enable_processing_unique_visitors_day = 1
enable_processing_unique_visitors_week = 1
enable_processing_unique_visitors_month = 1
enable_processing_unique_visitors_year = 0
enable_processing_unique_visitors_range = 0
</pre>

<p>
在默认情况下，出于性能的考虑，piwik关闭了按年和按指定的时间段进行访客数统计的功能，因为按年和按指定时间段进行访客数统计时，需要实时去扫描piwik的log，所以耗时很长，对高流量的网站来说，可能需要长达几分钟的处理时间。
</p>

<h3>Reference</h3>
http://piwik.org/