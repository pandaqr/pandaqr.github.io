---     
layout: post     
title:  "关于github不记录contribuions"     
date:   2014-10-16 00:18:00     
categories: Git     
---     

用了好几个月的Github，也经常往上面push代码，可是contirbution却一直不见有涨。时间长了心理一直很郁闷，今天终于下决心解决这个问题。    

答案是：    
**本地git设置的用户名/邮箱与Github设置的不一致**    

####解决方案：     
1. 设置本地git（参考链接：<a href="https://help.github.com/articles/set-up-git/" style="color: blue;">--我是链接--</a>）     
```     
git config --global user.name "yourName"     
git config --global user.email "yourEmail"     
//不写具体名字和邮箱的话，可以查看目前的设置值     
```     
2. 对照Github中设置的邮箱一致：<a href="https://github.com/settings/emails" style="color: blue;">--我是链接--</a>     
