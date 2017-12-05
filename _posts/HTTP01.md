---
title: HTTP协议
date: 2017-10-02 11:06:35
tags: [HTTP,javaee]
categories: javaWeb
---
<h2>什么是HTTP协议</h2>
&nbsp;&nbsp;&nbsp;&nbsp;HTTP协议是浏览器和服务器之间的通话所定义的一种规则，是TCP/IP集中的一个应用层协议，它是用来定义数据传输的过程以及数据本身格式；也就是我们通过浏览器访问web服务器就通过HTTP协议完成的；
  
<!--more-->
<h2>HTTP1.0协议的会话方式</h2>
&nbsp;&nbsp;&nbsp;&nbsp;HTTP协议的会话是基于客户端浏览器和web服务器端的；<br/>(客户端)建立连接—>(客户端)发送请求—>回送响应(服务器)—>关闭连接(服务器)
  ![HTTP会话图示](http://ox8t0ws1t.bkt.clouddn.com/http01.jpg)
 <hr/>在客户机和服务器之间还可以添加一个或者多个代理服务器
  ![代理服务器](http://ox8t0ws1t.bkt.clouddn.com/http02.jpg)
&nbsp;&nbsp;&nbsp;&nbsp;代理服务器对于客户机浏览器来说相当于服务器，对于服务器来说又相当于普通的客户机；浏览器在访问网页时首先通过代理服务器获取缓存，如果没有则代理服务器又给服务器发送请求，然后对该资源缓存，等浏览器下次访问同样的资源时则直接给缓存。<br/>&nbsp;&nbsp;&nbsp;&nbsp;通过多个代理服务器可以减少web服务器的访问负载，但同时要保证代理服务器的缓存资源与服务器资源的同步。
<h2>HTTP1.0与HTTP1.1的区别</h2>
<h6>HTTP1.0:</h6>
&nbsp;&nbsp;&nbsp;&nbsp;浏览器与服务器的链接是短暂性的，每一个请求之间都是没有关联的，浏览器每进行一个请求，服务器在响应请求之后会立即关闭连接，对于访问一个还有CSS样式，或着img标签，就得进行多个连接与响应，这样会严重的影响客户机与服务器的性能；<br/>不支持Host请求字段，即无法通过主机名访问指定的web资源
<h6>HTTP1.1:</h6>
&nbsp;&nbsp;&nbsp;&nbsp;相对于HTTP1.0协议，HTTP1.1协议提供了浏览器和服务器之间一次性可发送多个请求和响应，大大的降低了建立和关闭连接的耗时；同时客户端可以在服务器未回送响应时一次发送多个请求，然后服务器再依次按顺序回送响应；同时也支持通过主机名访问指定web资源；
<h2>HTTP通用信息、请求消息、响应消息、实体消息</h2>
<h6>通用信息</h6>
&nbsp;&nbsp;&nbsp;&nbsp;存在于请求消息和响应消息中的，与实体消息没有联系，主要有通用信息头Date和pragma，Cache—control等字段；
<h6>请求消息</h6>
主要包括：一个请求行，若干消息头，实体内容<br/>
请求头：只存在于请求消息中，用于向服务器传送附加信息,如：客户机可接受的压缩方式、数据类型。。。<br/>
请求行：包括请求方式，资源路径，使用的HTTP协议版本<br/>

<h6>响应消息</h6>
主要包括：一个状态行，若干消息头，实体内容<br/>
响应头：只存在于响应消息中，用于客户机传送附加信息，如：服务器程序名称，所需认证方式。。。<br/>
状态行：包括HTTP协议版本号，状态码，造成状态的原因
<h6>实体消息</h6>
包括实体头和实体内容<br/>
实体头：用于做实体内容的元信息，即包括实体内容属性，数据类型，长度，编码类型。。。 
<h2>GET和POST传递参数的区别</h2>
在URL地址后面是可以传递参数过去的，这些参数可以保证一定的数据唯一性；传递的参数是通过参数名称和内容指定的；每个参数之间用&符号分隔开；
<h6>GET</h6>
通过GET方式传递的参数直接更在资源路径后面，而且还限制在1kb以下；
<h6>POST</h6>
通过POST传递的参数，浏览器会将数据以HTTP中的实体内容的方式发送给服务器，传递数据量也大；
<hr/>
以上就是鄙人对HTTP协议的了解，如有不当请众君批评指正；