---
id: 848
title: 'Sphinx &#8211; Documentation for Python'
date: 2012-09-01T19:40:25+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=848
permalink: /2012/09/sphinx-documentation-for-python/
wp_plus_one_redirect:
  - 
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400246349
dsq_thread_id:
  - 826674825
categories:
  - Development
tags:
  - python
---
Python is a wonderful language also because of the awesome tools that are available.

One of which is <a href="http://sphinx.pocoo.org/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://sphinx.pocoo.org/', 'Sphinx');">Sphinx</a>. It is like markdown, but even more powerful, with cross referencing of pages and autogeneration of doc for python code.

Start with installing Sphinx.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="bash" style="font-family:monospace;"><span style="color: #666666;">$ </span><span style="color: #c20cb9; font-weight: bold;">sudo</span> easy_install <span style="color: #660033;">-U</span> Sphinx</pre>
      </td>
    </tr>
  </table>
</div>

Create sphinx docs in your project.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="bash" style="font-family:monospace;">$ <span style="color: #7a0874; font-weight: bold;">cd</span> <span style="color: #000000; font-weight: bold;">/</span>path<span style="color: #000000; font-weight: bold;">/</span>to<span style="color: #000000; font-weight: bold;">/</span>project<span style="color: #000000; font-weight: bold;">/</span>docs<span style="color: #000000; font-weight: bold;">/</span>
$ sphinx-quickstart</pre>
      </td>
    </tr>
  </table>
</div>

Write your documentation (eg. quick start guide) in your index.rst. Sphinx uses reStructured Text (a kind of text formatting).  Refer to this <a href="http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html', 'quick tutorial');">quick tutorial</a> and a <a href="https://github.com/ralsina/rst-cheatsheet" onclick="__gaTracker('send', 'event', 'outbound-article', 'https://github.com/ralsina/rst-cheatsheet', 'handy cheatsheet');">handy cheatsheet</a>.

<a href="http://sphinx.pocoo.org/markup/inline.html#cross-referencing-syntax" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://sphinx.pocoo.org/markup/inline.html#cross-referencing-syntax', 'Cross reference');">Cross reference</a> your documentation. You can across to arbitrary location with :ref:\`my-label-name \` or across files with :doc:\`my-doc-name\`

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="html" style="font-family:monospace;">.. _my-reference-label:
&nbsp;
Section to cross-reference
--------------------------
&nbsp;
This is the text of the section.
&nbsp;
It refers to the section itself, see :ref:`my-reference-label`.</pre>
      </td>
    </tr>
  </table>
</div>

Finally, generate the HTML files.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">make</span> html</pre>
      </td>
    </tr>
  </table>
</div>

Lastly, Sphinx can automatically generate your module and classes, using your docstrings. That way, you can write your documentation in your python files (and not again in Sphinx doc). To do that, you have to edit Sphinx conf.py to add the path to your modules to sys.path.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #808080; font-style: italic;"># Load the source for autodoc</span>
<span style="color: #dc143c;">sys</span>.<span style="color: black;">path</span>.<span style="color: black;">insert</span><span style="color: black;">&#40;</span><span style="color: #ff4500;"></span><span style="color: #66cc66;">,</span> <span style="color: #dc143c;">os</span>.<span style="color: black;">path</span>.<span style="color: black;">abspath</span><span style="color: black;">&#40;</span><span style="color: #dc143c;">os</span>.<span style="color: black;">path</span>.<span style="color: black;">join</span><span style="color: black;">&#40;</span><span style="color: #dc143c;">os</span>.<span style="color: black;">getcwd</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span><span style="color: #66cc66;">,</span> <span style="color: #483d8b;">'..'</span><span style="color: black;">&#41;</span><span style="color: black;">&#41;</span><span style="color: black;">&#41;</span></pre>
      </td>
    </tr>
  </table>
</div>

With that, you can automatically generate doc for a class.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="html" style="font-family:monospace;">.. automodule:: mymodule.something
&nbsp;
.. autoclass:: MyClass
    :members:</pre>
      </td>
    </tr>
  </table>
</div>

This is a short introduction guide to Sphinx. There&#8217;s obviously more, with cases of authors writing books using Sphinx!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>