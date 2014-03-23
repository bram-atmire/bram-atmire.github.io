---
layout: post
title:  "Can't find files in Spring MVC"
date:   2014-03-23 20:32:58
categories: Spring MVC
---

I am currently building a new webapp from scratch using Spring Web MVC. Spring, Spring Web MVC and a few Java concepts
like annotations are new to me.

The fact that my app's codebase is currently based on [a non-standard example I plucked from the web](https://technicalkeeda.com/bootstrap/twitter-bootstrap-with-spring-mvc)
is not making it any easier.

Right now the app deploys and runs correctly on a Tomcat 7 fired up from within IDEA, the JSPs can't be found after deploying to
Openshift.

It's very likely related to following strange web.xml and servlet definitions:

web.xml

{% highlight xml %}
    ...

    <servlet>
        <servlet-name>analyzer</servlet-name>
        <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
        <load-on-startup>1</load-on-startup>
    </servlet>

    <welcome-file-list>
        <welcome-file>index.jsp</welcome-file>
    </welcome-file-list>

    <servlet-mapping>
        <servlet-name>analyzer</servlet-name>
        <url-pattern>*.htm</url-pattern>
    </servlet-mapping>

    ...
{% endhighlight %}

analyzer.xml

{% highlight xml %}
...
<mvc:resources mapping="/css/**" location="/css/"/>
<mvc:resources mapping="/fonts/**" location="/fonts/"/>
<mvc:resources mapping="/js/**" location="/js/"/>
<mvc:resources mapping="/static/**" location="/static/" />
<mvc:resources mapping="/images/**" location="/images/" />

<!-- Use @MVC annotations -->
<mvc:annotation-driven />

<!-- Read configuration properties -->
<context:property-placeholder location="classpath:configuration.properties"/>

<context:component-scan base-package="atmire.siteChecker.controller" />

<bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
    <property name="prefix" value="/WEB-INF/jsp/" />
    <property name="suffix" value=".jsp" />
</bean>
...
{% endhighlight %}