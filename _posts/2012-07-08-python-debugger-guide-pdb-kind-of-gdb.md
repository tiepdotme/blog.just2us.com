---
id: 811
title: 'Python Debugger Guide (pdb) &#8211; Kind of like gdb'
date: 2012-07-08T15:54:17+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=811
permalink: /2012/07/python-debugger-guide-pdb-kind-of-gdb/
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
  - 1400179693
dsq_thread_id:
  - 755990323
categories:
  - Development
  - How-to
tags:
  - python
---
A lot of programmers starting with Python use just a plain vanilla text editor, and command line.

Although fancier IDE such as <a href="http://wingware.com/doc/debug" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://wingware.com/doc/debug', 'WingIDE');" target="_blank">WingIDE</a> comes with a built-in debugger, the IDE-less way of programming is still very awesome. Moreover, my  favorite IDE &#8211; Sublime Text 2 &#8211; does not support a built-in debugger..

When I first read the <a href="http://docs.python.org/library/pdb.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://docs.python.org/library/pdb.html', 'Python PDB');" target="_blank">Python PDB</a> from the official doc, somehow I have no patient to read it.. then I read a <a href="http://pythonconquerstheuniverse.wordpress.com/category/python-debugger/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://pythonconquerstheuniverse.wordpress.com/category/python-debugger/', 'narrated version');" target="_blank">narrated version</a>.

It is actually very simple to use PDB. Here&#8217;s how.

&nbsp;

## Step 1 &#8211; Add this code to your script

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">import</span> <span style="color: #dc143c;">pdb</span><span style="color: #66cc66;">;</span> <span style="color: #dc143c;">pdb</span>.<span style="color: black;">set_trace</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span></pre>
      </td>
    </tr>
  </table>
</div>

This one line of code will break into the debugger from your running program.

If you are using the interactive prompt, you can also start the debugger in another way.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #dc143c;">pdb</span>.<span style="color: black;">run</span><span style="color: black;">&#40;</span><span style="color: #483d8b;">'mymodule.test()'</span><span style="color: black;">&#41;</span></pre>
      </td>
    </tr>
  </table>
</div>

&nbsp;

## Step 2 &#8211; Debug it!

This is in fact the last step :) For this, it is better to refer to this <a href="http://nblock.org/2011/11/15/pdb-cheatsheet/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://nblock.org/2011/11/15/pdb-cheatsheet/', 'handy cheatsheet');" target="_blank">handy cheatsheet</a>.

<img class=" alignnone" style="border: 2px solid black;" title="Python PDB Cheatsheet" src="http://nblock.org/static/files/pdb-cheatsheet.png" alt="Python PDB Cheatsheet" width="500" height="350" />

&nbsp;

Nonetheless, I like to highlight a few common commands:

  * n(ext) &#8211; Step over next line of code
  * Enter &#8211; Repeat the last command
  * p(rint) some_variable &#8211; Print the variable
  * l(ist) &#8211; Show the code + and &#8211; 5 lines around the current line
  * b(reak) &#8211; Show list of breakpoints 
      * b 99 &#8211; Creates a breakpoint on line 99
      * clear 1 &#8211; Remove the breakpoint 1 in list (use b to see list of breakpoints)
  * !stmt &#8211; A python statement. You may change a variable value or call a function!!
  * local() &#8211; This is not a pdb command, but it can use to print out all the local variables.

&nbsp;

## Post-mortem &#8211; pdb.pm()

There is another pdb method that is really cool.

When you are running in interactive mode and runs into an Exception, how you wish you can stop right at that piece of culprit code, and debug.

You can! Simply run the following command, and you can can trackback to that code.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">import</span> <span style="color: #dc143c;">pdb</span><span style="color: #66cc66;">;</span> <span style="color: #dc143c;">pdb</span>.<span style="color: black;">pm</span><span style="color: black;">&#40;</span><span style="color: black;">&#41;</span></pre>
      </td>
    </tr>
  </table>
</div>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>