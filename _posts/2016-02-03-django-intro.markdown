---
layout:     post
title:      "Django: Before you start."
date:       2016-02-02 12:00:00
author:     "new-player"
header-img: "img/python-bg.png"
---

<p><a href="https://en.wikipedia.org/wiki/Django_(web_framework)" target="_blank">Django</a>, a python based web application framework is widely used by many because it is very quick to get started. Well maintained documentation, active commnunity, rapid application development and deployment, loads of built-in packages, dynamic admin interface, MVC architecture are some of pros of using it. <br>Django emphasizes reusability and "pluggability" of components, rapid development, and the principle of <a href="https://en.wikipedia.org/wiki/Don%27t_repeat_yourself" target="_blank">don't repeat yourself</a>.</p>

<h2 class="section-heading">Considerations</h2>

<p>Some of the considerations on using Django are as follows:</p>

<h4>Django ORM vs SQLAlchemy</h4>
<p>Compared to <a href="https://en.wikipedia.org/wiki/SQLAlchemy" target="_blank">SQLAlchemy</a>, Django's ORM is more geared towards direct SQL object manipulation where it exposes a plain and direct mapping between database tables and Python classes. It works well for simple and medium-complexity database operations. Django's ORM provides a lot of built in functionalities extremely useful for web apps, in order to allow it to integrate with Forms, Admin interface, perform pre-validation, etc. When complex database queries, complex joins, subqueries, window aggregates comes to picture, Django ORM fails to deal with anything of that without falling back to Raw SQL.</p>
<p>
SQLAlchemy is a well-regarded Python ORM because it gets the abstraction level "just right" and seems to make complex database queries easier to write than the Django ORM in most cases. It provides "a full suite of well known enterprise-level persistence patterns, designed for efficient and high-performing database access, adapted into a simple and Pythonic domain language". SQLAlchemy is typically used with <a href="https://en.wikipedia.org/wiki/Flask_(web_framework)" target="_blank">Flask</a> as the database ORM.</p>
<p>
If your application is very (SQL) database intensive then you would probably go for SQLAlchemy which is a rare scenario.
<br>Performance wise <strong>SQLAlchemy > Django ORM</strong> (considerable only for complex queries).
</p>

<h4>Realtime Applications</h4>

<p>HTTP is a <a href="https://en.wikipedia.org/wiki/Stateless_protocol" target="_blank">stateless protocol</a>. A stateless protocol does not require the server to retain information or status about each user for the duration of multiple requests. Django is primarily optimized for short-lived HTTP request/response cycles, is not made for handling a large number of concurrent and long-lived connections required to support real-time applications. Django is based on the WSGI specification, which is not geared toward handling long-lived connections. Most WSGI servers handle large concurrency through multithreading, but this approach simply doesn’t scale well to a large number of long lived connections.</p>
<p>
But it doesn't mean realtime functionality cannot be attained using django. Using a separate API server for handling realtime updates can do the trick. With <a href="https://en.wikipedia.org/wiki/WebSocket" target="_blank">WebSockets</a> it is possible to connect with a server from another domain and maintain a bidirectional connection. This separate server (written in Python, Node, Go or Erlang) can push realtime updates to client and can be synced with django securely.
The important part of this is the separation and the well-defined communication between the two servers.
But even if we can achieve realtime capability, it is advicable to use other frameworks that come with websockets support.
</p>
<p>
Some of the other considerations that you might like to know were pointed out by <a href="https://github.com/kennethreitz" target="_blank">Ken Reitz</a>.
<a href="https://speakerdeck.com/kennethreitz/flasky-goodness" target="_blank">Click here</a> to know.
</p>

<!--<p>Links to check out:
http://pythoncentral.io/sqlalchemy-vs-orms/
http://www.fullstackpython.com/object-relational-mappers-orms.html
http://stackoverflow.com/questions/18199053/example-of-what-sqlalchemy-can-do-and-django-orm-cannot
https://www.reddit.com/r/Python/comments/p03yh/sqlalchemy_vs_django_db/
https://news.ycombinator.com/item?id=3525544
https://coffeeonthekeyboard.com/why-django-sucks-except-when-it-doesnt-664/
http://www.skilledup.com/articles/introduction-python-web-frameworks
https://www.reddit.com/r/Python/comments/2g2gjo/what_are_the_advantagesdisadvantages_of_the/
http://nando.oui.com.br/2014/04/04/why_i_sort_of_dislike_django.html
http://stackoverflow.com/questions/9112571/what-are-the-limitations-of-djangos-orm
http://mrjoes.github.io/2013/06/21/python-realtime.html
test driven development python pdf
http://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet
</p>-->
