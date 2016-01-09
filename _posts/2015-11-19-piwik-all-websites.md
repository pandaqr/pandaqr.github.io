---
title: 自建PIWIK-ALL WEBSITES DASHBOARD页面
layout: post
---

<p>Piwik是一款开源流量监测工具，好用好看好配置，好处自然不用多说。但也有一些小问题，私以为Piwik的可配置参数项还不够多。</p>

<p>前段时间一直在纠结如何在「所有网站」这个页面上加上「访客数」这个指标，一通翻找Piwik源码，发现水有点深，另外考虑到以后的升级，所以在想如果我把它的源码给改了，那以后方便的一键升级是不是玩不转了，或者说升级之后又需要重新再修改一遍，经过重重考虑，决定还是绕道，既然Piwik这么强大，提供的API如此丰富，何不如再写一个自己的「所有网站」页面，展示自己认为比较重要的检测指标，这种灵活性是不是爆棚，所有就自己写了一个「所有网站」的Dashboard页面。</p>

<h3>Installation</h3>
<p>项目源码下载到本地之后，如果需要跑起来，还需要修改这么几个地方：</p>
<p>1、~/js/piwik-tongji.js中的<code>http://www.yourpiwikserver.com</code>替换成你自己Piwik的服务器地址，token_auth请替换成你自己Piwik的授权码；</p>
<p>2、如果想要在本地进行测试，并且你的Piwik并没有安装在本地，那么还涉及到一个跨域的问题，可以在Chrome的浏览器里面装一个插件<code>Allow-Control-Allow-Origin: *</code></p>

<h3>Need to be done</h3>
<p>1、还是有很多值得优化的地方，比如页面布局</p>

<h3>At Last</h3>
<p>最后上一张效果图(好像有点以假乱真)：</p>
<span><img src="/assets/images/2015/11/piwik.png" alt="DASHBOARD页面"></span>