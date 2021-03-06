---
title: C/S与B/S系统架构
date: 2017-10-14 17:14:50
tags: [javaee, C/S, B/S]
categories: javaWeb
---
<h3>C/S</h3>
&nbsp;&nbsp;&nbsp;&nbsp;<b>C/S</b>：Client(客户端)/Server(服务器),它是基于应用程序与服务器之间的交互式连接，即多个用户通过swing界面的GUI应用程序端对服务器端数据库的一系列操作。

<!--more-->
<br/>
![C/S系统架构图](http://ox8t0ws1t.bkt.clouddn.com/image/%E7%B3%BB%E7%BB%9F%E6%9E%B6%E6%9E%84/CS%E6%9E%B6%E6%9E%84.PNG)<br/>
缺点：
	<ol>
		<li>如果客户机与服务器保持持久连接，但是服务器端数据库所支持的并发连接数又是有限个，那么无法实现多个客户机对服务器端数据库的操作；如果将客户端程序设计成需要与数据库连接的时候再进行连接，虽然这样会增加客户机的数量，但是会对事务数理带来很大的难度，而且客户机与服务器的链接是一个比较耗时的过程，所以这种架构模式不适合与服务器频繁链接的客户端程序</li>
		<li>这种模式是将业务逻辑(处理数据的逻辑)和界面显示都设计在客户端程序上，当二者要改变其一的时候，就必须要将另一个也要改变，不利于程序的维护</li>
		<li>客户端程序是安装在每一台客户机上的，当客户端程序发生改变的时候，就需要系统维护人员对每个客户机进行重新安装，工作量大，效率低</li>
	</ol>
优点：<br/>&nbsp;&nbsp;&nbsp;&nbsp;客户端应用程序的功能可以很强大，在服务器瘫痪时还可以独立运行，可以将事务记录临时保存在本地数据库中，然后再统一交给服务器。
	
<h3>B/S</h3>
&nbsp;&nbsp;&nbsp;&nbsp;<b>B/S:</b>Browser(浏览器)/Server(服务器)，B/S架构就是将C/S架构中的客户端应用程序用web浏览器进行了替换，直接通过浏览器的URL地址直接与web服务器进行交互然后web服务器可以实现与数据库服务器之间的连接<br/>![BS系统架构图](http://ox8t0ws1t.bkt.clouddn.com/image/%E7%B3%BB%E7%BB%9F%E6%9E%B6%E6%9E%84/BS%E6%9E%B6%E6%9E%84.PNG)<br/>
优点：
<ol>
	<li>客户端不需要安装应用程序，直接可以在浏览器页面进行操作</li>
	<li>程序内容的改变只需要在web服务器端的网页文档中进行操作，直接可以实现浏览器端的同步</li>
	<li>客户端不直接与数据库服务器端进行连接，解决了高并发问题</li>
</ol>
<hr/>
综上所述，B/S架构就是C/S架构的一个演变，B/S架构优势更强于C/S架构，所以现在的开发我们都是基于B/S架构的。
