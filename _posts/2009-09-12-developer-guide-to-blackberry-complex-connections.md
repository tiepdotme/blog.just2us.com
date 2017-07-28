---
id: 161
title: Developer Guide to BlackBerry Connection Problems
date: 2009-09-12T13:19:15+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2009/09/developer-guide-to-blackberry-complex-connections/
permalink: /2009/09/developer-guide-to-blackberry-complex-connections/
dsq_thread_id:
  - 65765124
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400222201
categories:
  - Development
tags:
  - blackberry tutorials
---
If you develop mobile applications on other platforms such as Java ME, iPhone, Winmos or others, making a HTTP/TCP/UDP connection to the Internet is straightforward. The underlying network used is either Wifi or Cellular (aka GPRS/3G).

But for BlackBerry, it is many times more complex.

The BlackBerry platform provides a multitude of different transports for network access &#8211; Wifi, MDS, BIS, WAP 1.X, WAP 2.0 or Direct TCP. Refer to the diagram below.

Unfortunately, the platform does not provide a simple API that use whichever network that is working. Developers have to add extra parameters to the URL that they want to connect to. That is tolerable, but the problem that comes with each network is not. 

Lets look at each network and their problems.

  * Most users have BIS (BlackBerry Internet Service plan). But for developers to use BIS, they have to join the <a href="http://na.blackberry.com/eng/partners/software.jsp" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://na.blackberry.com/eng/partners/software.jsp', 'Alliance program');">Alliance program</a>. At a fee of course. 
      * Enterprise users have BlackBerry MDS (Mobile Data Service plan), and it is up to the enterprise admin to regulate the traffic. If they block with firewall, you will hit the wall. 
          * If you use WAP 1.X or WAP 2.0, you are using the service provider network and it could be subjected to some <a href="http://supportforums.blackberry.com/rim/board/message?board.id=java_dev&message.id=18343" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://supportforums.blackberry.com/rim/board/message?board.id=java_dev&message.id=18343', 'ridiculous transcoding');">ridiculous transcoding</a>. 
              * If you want to use direct TCP, you have to either know the carrier&#8217;s APN or have a user that configure the APN under Settings > Advanced Settings > TCP. Very unlikely for either. 
                  * Wifi is good, but not all phones come with it.</ul> 
                To conclude, RIM has got us a complex network problem to deal with.
                
                <a href="http://blog.just2us.com/wp-content/uploads/2009/09/BlackBerry-Network-Diagram.png" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://blog.just2us.com/wp-content/uploads/2009/09/BlackBerry-Network-Diagram.png', '');"><img style="border-top-width: 0px; border-left-width: 0px; border-bottom-width: 0px; border-right-width: 0px" height="335" alt="BlackBerry Network Diagram" src="http://blog.just2us.com/wp-content/uploads/2009/09/BlackBerry-Network-Diagram_thumb.png" width="644" border="0" /></a>
                
                &nbsp;
                
                ## Solution
                
                A suggested solution is as such. 
                
                  * Join the Alliance program and use BIS. Then for each application, apply for an application code to use the BIS transport. 
                      * In your connection code, connect in the order **Wifi > BIS > MDS > TCP > WAP**</ul> 
                    <a href="http://www.versatilemonkey.com/blog/index.php/2009/06/24/networking-helper-class/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.versatilemonkey.com/blog/index.php/2009/06/24/networking-helper-class/', 'Versatilemonkey');">Versatilemonkey</a> has a good Helper class that helps to encapsulate the extra parameters needed for the different connections. It is helpful code. There is also an interesting article from versatilemonkey on his <a href="http://www.versatilemonkey.com/story.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.versatilemonkey.com/story.html', 'BlackBerry development story');">BlackBerry development story</a>. Worth reading.
                    
                    &nbsp;
                    
                    ## References
                    
                      1. <a href="http://supportforums.blackberry.com/rim/board/message?board.id=java_dev&message.id=29103#M29103" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://supportforums.blackberry.com/rim/board/message?board.id=java_dev&message.id=29103#M29103', 'Breakdown of the problem and FAQ');">Breakdown of the problem and FAQ</a> 
                          * <a href="http://supportforums.blackberry.com/rim/board/message?board.id=java_dev&message.id=29106#M29106" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://supportforums.blackberry.com/rim/board/message?board.id=java_dev&message.id=29106#M29106', 'The one discussion thread on the matter');">The one discussion thread on the matter</a> 
                              * <a href="http://www.blackberry.com/DevMediaLibrary/view.do?name=NetworkingTransports" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.blackberry.com/DevMediaLibrary/view.do?name=NetworkingTransports', 'Even have a video on Network!');">Even have a video on Network!</a> 
                                  * <a href="http://www.blackberry.com/developers/docs/5.0.0api/net/rim/device/api/io/transport/package-summary.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.blackberry.com/developers/docs/5.0.0api/net/rim/device/api/io/transport/package-summary.html', 'Hope its better in 5.0..');">Hope its better in 5.0..</a> 
                                      * <a href="http://www.versatilemonkey.com/blog/index.php/2009/06/24/networking-helper-class/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.versatilemonkey.com/blog/index.php/2009/06/24/networking-helper-class/', 'Versatilemonkey has a good Helper class');">Versatilemonkey has a good Helper class</a> 
                                          * <a href="http://www.blackberry.com/knowledgecenterpublic/livelink.exe/fetch/2000/348583/800451/800563/What_Is_-_Different_ways_to_make_an_HTTP_or_socket_connection.html?nodeid=826935&vernum=0" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.blackberry.com/knowledgecenterpublic/livelink.exe/fetch/2000/348583/800451/800563/What_Is_-_Different_ways_to_make_an_HTTP_or_socket_connection.html?nodeid=826935&vernum=0', 'Different ways to making a HTTP Connection');">Different ways to making a HTTP Connection</a> 
                                              * <a href="http://mobilephonedevelopment.com/archives/883" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://mobilephonedevelopment.com/archives/883', 'Network Diagnostic Tool');">Network Diagnostic Tool</a></ol> 
                                            <div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
                                            </div>