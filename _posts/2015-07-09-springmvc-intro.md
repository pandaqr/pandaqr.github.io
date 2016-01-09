---
title: SpringMVC 入门笔记
layout: post
---

<p>SpringMCV笔记分成两部分，第一部分描述应用启动时针对SpringMVC框架所进行的准备工作；第二部分描述SpringMVC框架完成一次用户请求到响应请求的逻辑处理过程。</p>

<h3>第一部分</h3>

<p>SpringMVC的本质原理是通过Servlet拦截所有url的请求来达到控制的目的，我们不妨从一个web应用的描述符文件(web.xml)入手一探究竟（这里补充说一句，Servlet技术对于web开发者来说多多少少都有接触过，结合SpringMVC的本质原理，我们是否可以推测出Spring框架的核心：通过层层封装底层相关技术，如Servlet，从而达到高效开发WEB应用的目的，当然这中间包含了作者呕心沥血的构思和设计）。在描述符文件中包含了应用的资源名称，路径，启动项，监听器和拦截器等等，常常看起来像下面这样：</p>
<span><img src="/assets/images/2015/07/springmvc.png" alt=""></span>


<p>在web.xml中分别标注出了各部分，对重要项进行解释：</p>

<p>1、在Part II中我们配置了一个SpringMVC核心的处理请求类<code>DispatcherServlet</code>，它继承自HttpServlet，继承关系如下所示：</p>
<pre>
public class DispatcherServlet extends FrameworkServlet
public abstract class FrameworkServlet extends HttpServletBean
public abstract class HttpServletBean extends HttpServlet
</pre>

<p>1.1、Servlet框架技术由两个Java包组成：<code>javax.servlet 和 javax.servlet.http</code></p>
<p>前者定义了所有servelt类都必须实现或扩展的通用接口和类；后者定义了基于HTTP协议的HttpServlet类。在HttpServlet类中包含了</p>
<pre>
public void init() throws ServletException
</pre>
<p>方法，该方法在应用程序启动时执行初始化操作，SpringMVC框架重载了这个方法，用于在启动时针对特定应用需求做初始化工作，比如读取描述符文件中的配置信息。</p>

<p>1.2、当DispatcherServlet载入后，将从XML文件中加载配置信息，在默认情况下，该XML文件的文件名取决于，但也可以支持自定义，在该例子中SpringMVC框架将从<code>/WEB-INF/config/springmvc-config.xml</code>处加载配置项。</p>

<p>1.3、通过配置/拦截所有的用户请求，转向DispatcherServlet作进一步的处理，该请求处理过程可以认为是SpringMVC的核心处理逻辑，留在下一部分进行说明。</p>

<p>1.4、关于<load-on-startup>1</load-on-startup>该配置项表明应用程序启动时，则加载Servlet类，执行其init方法，在正式接受用户请求之前，完成初始化工作，当然也可以不加这个配置项，在第一次接受用户请求时进行资源初始化的操作，但在通常情况下，预先加载资源进行初始化工作会带来节省用户请求时间的好处，数值代表加载的优先级，数值越小，优先级越高。</p>

<p>2、在Part III配置了<code>ContextLoaderListener</code>上下文环境监听器，现在我们就大致来了解下这个ContextLoaderListener具备哪些功能？</p>

<p>2.1、当硬编码的时候，我们可以在代码中直接把Spring的配置信息读入Spring容器，比如通过以下方式：</p>
<pre>
ApplicationContest ac = new ClassPathXmlApplicationContext("ApplicationContext.xml");
</pre>
<p>但在通常情况下，在开发web应用时，考虑到配置的灵活性以及程序的正交性，通常将Spring配置文件的路径以的形式进行注册，并用ContextLoaderListener进行监听，好，交待完小小的背景，现在我们来看看ContextLoaderListener到底给我带来了什么样的功能，先查看其继承关系，如下：</p>
<pre>
public class ContextLoaderListener extends ContextLoader implements ServletContextListener
</pre>
<p>而查看ServletContextListener接口发现其包含了两个需要子类实现的方法：</p>
<pre>
public abstract void contextInitialized(ServletContextEvent servletcontextevent);
public abstract void contextDestroyed(ServletContextEvent servletcontextevent);
</pre>
<p>而web容器在启动时，会自动执行contextInitialized方法，所以我们便可以了解ContextLoaderListener的功能：在web容器启动时，就会默认执行其实现的方法contextInitialized，自动加载ApplicationContext的配置信息，开发者能够在为客户端提供服务之前向ServletContext中添加任意的对象。</p>

</p>2.2、每一个Web应用都有一个ServletContext与之相关联，它类似与一个全局变量，在应用启动时被创建，在应用关闭时被销毁。</p>

<h3>Reference</h3>
<pre>
1、http://www.cnblogs.com/xing901022/p/4178963.html
</pre>