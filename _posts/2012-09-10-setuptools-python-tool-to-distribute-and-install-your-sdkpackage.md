---
id: 854
title: 'setuptools &#8211; Python tool to distribute and install your SDK/package'
date: 2012-09-10T09:39:10+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=854
permalink: /2012/09/setuptools-python-tool-to-distribute-and-install-your-sdkpackage/
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
  - 1400232930
dsq_thread_id:
  - 839315596
categories:
  - Development
---
<a href="http://peak.telecommunity.com/DevCenter/setuptools#developer-s-guide" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://peak.telecommunity.com/DevCenter/setuptools#developer-s-guide', 'setuptools');">setuptools</a> is a tool to download, build, install, upgrade, and uninstall Python packages &#8212; easily!

If you _just_ need to install other people&#8217;s packages, this is NOT for you. All you need is pypi and knowing the command

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="bash" style="font-family:monospace;">pip <span style="color: #c20cb9; font-weight: bold;">install</span> some-package</pre>
      </td>
    </tr>
  </table>
</div>

setuptools is for the other way round. It is for developers who want to distribute their SDK/library/packages to those &#8220;pip install&#8221; developers. There are 2 steps.

&nbsp;

## Step 1) setup.py

<a href="http://pypi.python.org/pypi/setuptools" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://pypi.python.org/pypi/setuptools', 'Install setuptools');">Install setuptools</a>. For Mac, it basically downloading and running the egg.

Afterwhich, create a setup.py in the root of your Python project.  A basic template looks like this:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="python" style="font-family:monospace;"><span style="color: #ff7700;font-weight:bold;">import</span> <span style="color: #dc143c;">os</span>
<span style="color: #ff7700;font-weight:bold;">from</span> setuptools <span style="color: #ff7700;font-weight:bold;">import</span> setup<span style="color: #66cc66;">,</span> find_packages
&nbsp;
setup<span style="color: black;">&#40;</span>
    name <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"just2us"</span><span style="color: #66cc66;">,</span>
    version <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"0.0.1"</span><span style="color: #66cc66;">,</span>
    author <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"Junda Ong"</span><span style="color: #66cc66;">,</span>
    author_email <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"junda@just2us.com"</span><span style="color: #66cc66;">,</span>
    description <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"Python SDK for Just2us"</span><span style="color: #66cc66;">,</span>
    license <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"MIT"</span><span style="color: #66cc66;">,</span>
    keywords <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"awesome stuff"</span><span style="color: #66cc66;">,</span>
    url <span style="color: #66cc66;">=</span> <span style="color: #483d8b;">"http://www.just2us.com"</span><span style="color: #66cc66;">,</span>
    install_requires <span style="color: #66cc66;">=</span> <span style="color: black;">&#91;</span><span style="color: #483d8b;">"requests"</span><span style="color: black;">&#93;</span><span style="color: #66cc66;">,</span>
    packages <span style="color: #66cc66;">=</span> find_packages<span style="color: black;">&#40;</span><span style="color: black;">&#41;</span><span style="color: #66cc66;">,</span>
    classifiers <span style="color: #66cc66;">=</span> <span style="color: black;">&#91;</span>
        <span style="color: #483d8b;">"Intended Audience :: Developers"</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">"License :: OSI Approved :: MIT License"</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">"Programming Language :: Python"</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">"Programming Language :: Python :: 2.7"</span><span style="color: #66cc66;">,</span>
        <span style="color: #483d8b;">"Topic :: Software Development :: Libraries :: Python Modules"</span><span style="color: #66cc66;">,</span>
    <span style="color: black;">&#93;</span><span style="color: #66cc66;">,</span>
<span style="color: black;">&#41;</span></pre>
      </td>
    </tr>
  </table>
</div>

As you can see, setup() basically describes various things about your package, such as:

  * meta eg. author email
  * required dependencies
  * <a href="http://pypi.python.org/pypi?%3Aaction=list_classifiers" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://pypi.python.org/pypi?%3Aaction=list_classifiers', 'classifiers');">classifiers</a>

<div>
  <p>
    With that, you can install your Python package. This is usually what you do when you manually install from source.
  </p>
  
  <div class="wp_syntax">
    <table>
      <tr>
        <td class="code">
          <pre class="bash" style="font-family:monospace;">python setup.py <span style="color: #c20cb9; font-weight: bold;">install</span></pre>
        </td>
      </tr>
    </table>
  </div>
  
  <p>
    &nbsp;
  </p>
</div>

## **Step 2) Upload to Python CheeseShop**

But instead of setting up manually, you could make use of Python CheeseShop (pipy) to distribute and setup your package for the Python community. This is the part which connects to pip install.

Firstly, register an account. (Take note: I failed registration a few times, without receiving the validation email. I think that is because of password too short/weak.) The registration is command line based:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="bash" style="font-family:monospace;">python setup.py register</pre>
      </td>
    </tr>
  </table>
</div>

<div>
  <p>
    The Python Cheese Shop provides an <a href="http://pypi.python.org/pypi/an_example_pypi_project" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://pypi.python.org/pypi/an_example_pypi_project', 'example');">example</a> of a pypi project to be uploaded.
  </p>
</div>

<div>
  <div class="wp_syntax">
    <table>
      <tr>
        <td class="code">
          <pre class="bash" style="font-family:monospace;">bdist_egg upload <span style="color: #660033;">--identity</span>=<span style="color: #ff0000;">"Andrew Carter"</span> <span style="color: #660033;">--sign</span> <span style="color: #660033;">--quiet</span>
bdist_wininst <span style="color: #660033;">--target-version</span>=<span style="color: #000000;">2.4</span> register upload <span style="color: #660033;">--identity</span>=<span style="color: #ff0000;">"Andrew Carter"</span> <span style="color: #660033;">--sign</span> <span style="color: #660033;">--quiet</span>
sdist upload <span style="color: #660033;">--identity</span>=<span style="color: #ff0000;">"Andrew Carter"</span> <span style="color: #660033;">--sign</span></pre>
        </td>
      </tr>
    </table>
  </div>
  
  <p>
    &nbsp;
  </p>
</div>

## Versioning

As a bonus, you might want to understand the difference on prerelease and postrelease versions:

  * prerelease 
      * 1.2rc1 (same as 1.2c1)
      * 1.2rc < 1.2
  * postrelease 
      * 1.2-r2943 (as in revision 2943)
      * 1.2-r2943 > 1.2

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>