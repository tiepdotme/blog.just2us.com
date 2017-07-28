---
id: 393
title: How to use MapKit
date: 2010-05-23T00:15:52+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/?p=393
permalink: /2010/05/how-to-use-mapkit/
dsq_thread_id:
  - 100135291
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400218237
categories:
  - Development
  - How-to
tags:
  - mapkit
---
Apple seems to lack a MapKit programming guide. I have to look through the MapKit reference, search on the Internet, and read blog articles in order to do a _few simple tasks_ with MapKit.

I thought it would be great if there is a MapKit programming guide, similar to the <a href="http://developer.apple.com/iphone/library/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/Introduction/Introduction.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.apple.com/iphone/library/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/Introduction/Introduction.html', 'Push Notification Service programming guide');">Push Notification Service programming guide</a> provided by Apple. 

But there isn’t. So I am here writing one for developers who are interested to use MapKit for that _few simple tasks_. This post contains 8 code snippets for 8 tasks.

&#160;

#### 1. Adding a map view

If you simply want to add a map to your view, simply create a MKMapView object and insert it. That’s our first big step!</p> 

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #002200;">-</span> <span style="color: #002200;">&#40;</span><span style="color: #a61390;">void</span><span style="color: #002200;">&#41;</span>viewDidLoad <span style="color: #002200;">&#123;</span>
  <span style="color: #002200;">&#91;</span>super viewDidLoad<span style="color: #002200;">&#93;</span>;
  <span style="color: #11740a; font-style: italic;">// Init our map view </span>
 mapView <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span>MKMapView alloc<span style="color: #002200;">&#93;</span> initWithFrame<span style="color: #002200;">:</span>self.view.bounds<span style="color: #002200;">&#93;</span>;
 <span style="color: #002200;">&#91;</span>self.view insertSubview<span style="color: #002200;">:</span>mapView atIndex<span style="color: #002200;">:</span><span style="color: #2400d9;"></span><span style="color: #002200;">&#93;</span>;
<span style="color: #002200;">&#125;</span></pre>
      </td>
    </tr>
  </table>
</div>

&#160;

#### 2. Configuring the map

With a map, you could now configure various aspects by setting the mapView properties. Examples below:

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"> <span style="color: #11740a; font-style: italic;">// Set the map type such as Standard, Satellite, Hybrid</span>
 mapView.mapType <span style="color: #002200;">=</span> MKMapTypeStandard;
&nbsp;
  <span style="color: #11740a; font-style: italic;">// Config user interactions</span>
 mapView.zoomEnabled <span style="color: #002200;">=</span> <span style="color: #a61390;">NO</span>;
 mapView.scrollEnabled <span style="color: #002200;">=</span> <span style="color: #a61390;">YES</span>;
&nbsp;
  <span style="color: #11740a; font-style: italic;">// Set the region and zoom level</span>
  MKCoordinateRegion region;
  MKCoordinateSpan span;
  CLLocationCoordinate2D location;
  location.latitude <span style="color: #002200;">=</span> <span style="color: #2400d9;">1.302851</span>; <span style="color: #11740a; font-style: italic;">// Singapore!</span>
 location.longitude <span style="color: #002200;">=</span> <span style="color: #2400d9;">103.85523</span>;
 span.latitudeDelta <span style="color: #002200;">=</span> <span style="color: #2400d9;">0.02</span>;
  span.longitudeDelta <span style="color: #002200;">=</span> <span style="color: #2400d9;">0.02</span>;
 region.span <span style="color: #002200;">=</span> span;
 region.center <span style="color: #002200;">=</span> location;
 <span style="color: #11740a; font-style: italic;">// Set to that region with an animated effect</span>
 <span style="color: #002200;">&#91;</span>mapView setRegion<span style="color: #002200;">:</span>region animated<span style="color: #002200;">:</span>TRUE<span style="color: #002200;">&#93;</span>;
 <span style="color: #11740a; font-style: italic;">// Lastly, set the MKMapViewDelegate (we will use this later) </span>
  mapView.delegate <span style="color: #002200;">=</span> self;</pre>
      </td>
    </tr>
  </table>
</div>

&#160;

#### 3. Showing the user&#8217;s location

To show the user&#8217;s location on the map, we set this one special property.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"> mapView.showsUserLocation <span style="color: #002200;">=</span> <span style="color: #a61390;">YES</span>;</pre>
      </td>
    </tr>
  </table>
</div></p> 

&#160;

#### 4. Creating custom annotations/landmarks

If you want to display some landmarks, aka annotations, on the map, you will need to create your annotation class that implement the MKAnnotation protocols. 

Say you want to display some shops on the map, this is want you would do. 

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #11740a; font-style: italic;">// ShopAnnotation.h</span>
<span style="color: #a61390;">@interface</span> ShopAnnotation <span style="color: #002200;">:</span> <span style="color: #400080;">NSObject</span> &lt;mkannotation&gt; <span style="color: #002200;">&#123;</span>
 Shop <span style="color: #002200;">*</span>shop; <span style="color: #11740a; font-style: italic;">// Assuming this class contains info about a shop</span>
<span style="color: #002200;">&#125;</span></pre>
      </td>
    </tr>
  </table>
</div>

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #11740a; font-style: italic;">// ShopAnnotation.m  </span>
<span style="color: #11740a; font-style: italic;">// Required to implement</span>
<span style="color: #002200;">-</span> <span style="color: #002200;">&#40;</span>CLLocationCoordinate2D<span style="color: #002200;">&#41;</span>coordinate <span style="color: #002200;">&#123;</span>
  CLLocationCoordinate2D theCoordinate;
 theCoordinate.latitude <span style="color: #002200;">=</span> shop.latitude;
 theCoordinate.longitude <span style="color: #002200;">=</span> shop.longitude;
 <span style="color: #a61390;">return</span> theCoordinate; 
<span style="color: #002200;">&#125;</span>
&nbsp;
<span style="color: #11740a; font-style: italic;">// Optional</span>
<span style="color: #002200;">-</span> <span style="color: #002200;">&#40;</span><span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span>title <span style="color: #002200;">&#123;</span>
    <span style="color: #a61390;">return</span> shop.name;
<span style="color: #002200;">&#125;</span>
&nbsp;
<span style="color: #11740a; font-style: italic;">// Optional</span>
<span style="color: #002200;">-</span> <span style="color: #002200;">&#40;</span><span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span>subtitle <span style="color: #002200;">&#123;</span>
    <span style="color: #a61390;">return</span> shop.address;
<span style="color: #002200;">&#125;</span></pre>
      </td>
    </tr>
  </table>
</div>

&#160;

#### 5. Adding annotations to the map

To add the annotations to the map, you would create the ShopAnnotation earlier and add them to mapView.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;">  <span style="color: #a61390;">for</span> <span style="color: #002200;">&#40;</span>Shop <span style="color: #002200;">*</span>shop <span style="color: #a61390;">in</span> allMyShops<span style="color: #002200;">&#41;</span> <span style="color: #002200;">&#123;</span>
    ShopAnnotation <span style="color: #002200;">*</span>shopAnnotation <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span>ShopAnnotation alloc<span style="color: #002200;">&#93;</span> initWithShop<span style="color: #002200;">:</span>shop<span style="color: #002200;">&#93;</span> autorelease<span style="color: #002200;">&#93;</span>;
    <span style="color: #002200;">&#91;</span>mapView addAnnotation<span style="color: #002200;">:*</span>shopAnnotation <span style="color: #002200;">&#93;</span>;
 <span style="color: #002200;">&#125;</span></pre>
      </td>
    </tr>
  </table>
</div>

&#160;

#### 6. Handling the annotation views

Annotations are not views. After you added your annotations to the map, you would still need to provide its views. The mapView delegate methods will be called to ask for your annotations’ VIEWS. You will need to create the view and return it for mapView to display. 

In our example, we create a MKPinAnnotationView, which is a standard pin that you see in Maps app. You could otherwise create your custom view that extends MKAnnotationView.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #002200;">-</span> <span style="color: #002200;">&#40;</span>MKAnnotationView <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span>mapView<span style="color: #002200;">:</span><span style="color: #002200;">&#40;</span>MKMapView <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span>theMapView viewForAnnotation<span style="color: #002200;">:</span><span style="color: #002200;">&#40;</span><span style="color: #a61390;">id</span> &lt;mkannotation&gt;<span style="color: #002200;">&#41;</span>annotation <span style="color: #002200;">&#123;</span>
  <span style="color: #11740a; font-style: italic;">// If it's the user location, just return nil.</span>
 <span style="color: #a61390;">if</span> <span style="color: #002200;">&#40;</span><span style="color: #002200;">&#91;</span>annotation isKindOfClass<span style="color: #002200;">:</span><span style="color: #002200;">&#91;</span>MKUserLocation class<span style="color: #002200;">&#93;</span><span style="color: #002200;">&#93;</span><span style="color: #002200;">&#41;</span>
    <span style="color: #a61390;">return</span> <span style="color: #a61390;">nil</span>;
 <span style="color: #11740a; font-style: italic;">// If it is our ShopAnnotation, we create and return its view</span>
 <span style="color: #a61390;">if</span> <span style="color: #002200;">&#40;</span><span style="color: #002200;">&#91;</span>annotation isKindOfClass<span style="color: #002200;">:</span><span style="color: #002200;">&#91;</span>ShopAnnotation class<span style="color: #002200;">&#93;</span><span style="color: #002200;">&#93;</span><span style="color: #002200;">&#41;</span> <span style="color: #002200;">&#123;</span>
    <span style="color: #11740a; font-style: italic;">// try to dequeue an existing pin view first</span>
    <span style="color: #a61390;">static</span> <span style="color: #400080;">NSString</span><span style="color: #002200;">*</span> shopAnnotationIdentifier <span style="color: #002200;">=</span> <span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"ShopAnnotationIdentifier"</span>;
    MKPinAnnotationView<span style="color: #002200;">*</span> pinView <span style="color: #002200;">=</span> <span style="color: #002200;">&#40;</span>MKPinAnnotationView <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span><span style="color: #002200;">&#91;</span>mapView dequeueReusableAnnotationViewWithIdentifier<span style="color: #002200;">:</span>shopAnnotationIdentifier <span style="color: #002200;">&#93;</span>;
    <span style="color: #a61390;">if</span> <span style="color: #002200;">&#40;</span><span style="color: #002200;">!</span>pinView<span style="color: #002200;">&#41;</span> <span style="color: #002200;">&#123;</span>
     <span style="color: #11740a; font-style: italic;">// If an existing pin view was not available, create one</span>
      MKPinAnnotationView<span style="color: #002200;">*</span> customPinView <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span>MKPinAnnotationView alloc<span style="color: #002200;">&#93;</span> initWithAnnotation<span style="color: #002200;">:</span>annotation reuseIdentifier<span style="color: #002200;">:</span>shopAnnotationIdentifier<span style="color: #002200;">&#93;</span> autorelease<span style="color: #002200;">&#93;</span>;
      customPinView.pinColor <span style="color: #002200;">=</span> MKPinAnnotationColorRed;
     customPinView.animatesDrop <span style="color: #002200;">=</span> <span style="color: #a61390;">YES</span>;
     customPinView.canShowCallout <span style="color: #002200;">=</span> <span style="color: #a61390;">YES</span>;
&nbsp;
      <span style="color: #11740a; font-style: italic;">// add a detail disclosure button to the callout which will open a new view controller page</span>
     UIButton<span style="color: #002200;">*</span> rightButton <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span>UIButton buttonWithType<span style="color: #002200;">:</span>UIButtonTypeDetailDisclosure<span style="color: #002200;">&#93;</span>;
     customPinView.rightCalloutAccessoryView <span style="color: #002200;">=</span> rightButton;
&nbsp;
      <span style="color: #a61390;">return</span> customPinView;
   <span style="color: #002200;">&#125;</span> <span style="color: #a61390;">else</span> <span style="color: #002200;">&#123;</span>
      pinView.annotation <span style="color: #002200;">=</span> annotation;
    <span style="color: #002200;">&#125;</span>&lt;strike&gt;&lt;<span style="color: #002200;">/</span>strike&gt;&lt;strike&gt;&lt;<span style="color: #002200;">/</span>strike&gt;
   <span style="color: #a61390;">return</span> pinView;
 <span style="color: #002200;">&#125;</span>
<span style="color: #002200;">&#125;</span></pre>
      </td>
    </tr>
  </table>
</div>

&#160; 

#### 7. Selecting a pin

When a user selects a pin and press the UIButtonTypeDetailDisclosure button within the callout, we can present more details about the annotation. Implement another MKMapViewDelegate to handle this.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"><span style="color: #002200;">-</span> <span style="color: #002200;">&#40;</span><span style="color: #a61390;">void</span><span style="color: #002200;">&#41;</span>mapView<span style="color: #002200;">:</span><span style="color: #002200;">&#40;</span>MKMapView <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span>_mapView annotationView<span style="color: #002200;">:</span><span style="color: #002200;">&#40;</span>MKAnnotationView <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span>view calloutAccessoryControlTapped<span style="color: #002200;">:</span><span style="color: #002200;">&#40;</span>UIControl <span style="color: #002200;">*</span><span style="color: #002200;">&#41;</span>control <span style="color: #002200;">&#123;</span>
  <span style="color: #11740a; font-style: italic;">// Handle it, such as showing another view controller</span>
<span style="color: #002200;">&#125;</span></pre>
      </td>
    </tr>
  </table>
</div>

&#160;

#### 8. Open Maps app

If want to provide a route from the user location to the selected annotation, you would need the help of iPhone’s Maps app. This means that your app will exit and Maps app will be opened, with you telling Maps the source and destination to route.

You can open Maps with the schema as such.

<div class="wp_syntax">
  <table>
    <tr>
      <td class="code">
        <pre class="objc" style="font-family:monospace;"> <span style="color: #400080;">NSString</span> <span style="color: #002200;">*</span>url <span style="color: #002200;">=</span> <span style="color: #002200;">&#91;</span><span style="color: #400080;">NSString</span> stringWithFormat<span style="color: #002200;">:</span><span style="color: #bf1d1a;">@</span><span style="color: #bf1d1a;">"http://maps.google.com/maps?saddr=%f,%f&amp;daddr=%f,%f"</span>;, userLatitude, userLongitude, <span style="color: #002200;">&#91;</span>shop.latitude floatValue<span style="color: #002200;">&#93;</span>, <span style="color: #002200;">&#91;</span>shop.longitude floatValue<span style="color: #002200;">&#93;</span><span style="color: #002200;">&#93;</span>;
  <span style="color: #002200;">&#91;</span><span style="color: #002200;">&#91;</span>UIApplication sharedApplication<span style="color: #002200;">&#93;</span> openURL<span style="color: #002200;">:</span><span style="color: #002200;">&#91;</span><span style="color: #400080;">NSURL</span> URLWithString<span style="color: #002200;">:</span>url<span style="color: #002200;">&#93;</span><span style="color: #002200;">&#93;</span>;</pre>
      </td>
    </tr>
  </table>
</div>

&#160;

With that, we have come to the end of _a few simple tasks_ with MapKit!

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>