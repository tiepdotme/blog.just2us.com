---
id: 203
title: How to flash a Hero ROM onto ADP1 (dev phone)
date: 2009-11-05T00:43:10+00:00
author: Junda Ong
layout: post
guid: http://blog.just2us.com/2009/11/how-to-flash-a-hero-rom-onto-adp1-dev-phone/
permalink: /2009/11/how-to-flash-a-hero-rom-onto-adp1-dev-phone/
dsq_thread_id:
  - 65765145
arkayne-cache-post:
  - |
    |
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        <!-- BlogGlue Plugin Error -->
        <!-- This page cannot be linked by BlogGlue. -->
        <!-- Your Account was not found. -->
        <!-- http://www.blogglue.com/contact/ -->
        
        
arkayne-time-post:
  - 1400200584
categories:
  - Android
  - Development
  - How-to
tags:
  - Android
  - ROMs
---
This post describes my experience in flashing a Hero ROM onto a ADP1 Google&#8217;s development phone, also known as a G1 or HTC Dream.

&nbsp;

### I. Downgrading Android to RC29

  1. Format sdcard to FAT 
  2. Download <a href="http://android-roms.googlecode.com/files/DREAIMG-RC29.zip" onclick="__gaTracker('send', 'event', 'download', 'http://android-roms.googlecode.com/files/DREAIMG-RC29.zip');">DREAIMG-RC29</a>
  3. Unzip and copy DREAIMG.nbh to root of sdcard
  4. Power off
  5. Press and hold Camera + Power
  6. Update as per instruction
  7. Finish and reboot

Your phone is now downgraded to G1 build RC29. Wondering why we are downgrading? This is because we need to exploit a security hole that is present in RC29. In RC30+, we can no longer exploit the security hole.

&nbsp;

### II. Replacing Recovery Image

A recovery image allows us to load custom build of Android, and it is what that gives us root access to the device. 

  1. Download <a href="http://n0rp.chemlab.org/android/cm-recovery-1.4.img" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://n0rp.chemlab.org/android/cm-recovery-1.4.img', 'Cyanogen&#8217;s version cm-recovery-1.4.img');">Cyanogen&#8217;s version cm-recovery-1.4.img</a>&nbsp;
  2. Copy cm-recovery-1.4.img to root of sdcard
  3. Reboot
  4. At home screen, press enter > pause for a second > press enter > type &#8220;telnetd&#8221; (if it is doing a contact search, you are correct) > press enter.
  5. Go to Market, search for &#8220;telnet&#8221; and install
  6. Launch telnet and connect
  7. Enter the commands:
> mount -o rw,remount -t yaffs2 /dev/block/mtdblock3 /system  
> cd /sdcard  
> flash_image recovery cm-recovery-1.4.img  
> cat cm-recovery-1.4.img > /system/recovery.img

  8. Power off
  9. Press and hold Home + Power
 10. You should see a Cyanogen system recovery. If you encountered a problem going into the recovery mode, try downgrading to RC29 and repeat again.

In later steps, we will be frequently rebooting the phone and goes into this recovery mode.

&nbsp;

### III. Upgrading Radio Image and SPL

  1. Download <a href="http://sapphire-port-dream.googlecode.com/files/ota-radio-2_22_19_26I.zip" onclick="__gaTracker('send', 'event', 'download', 'http://sapphire-port-dream.googlecode.com/files/ota-radio-2_22_19_26I.zip');" title="http://sapphire-port-dream.googlecode.com/files/ota-radio-2_22_19_26I.zip">ota-radio-2_22_19_26I.zip</a> and copy to root of sdcard
  2. Download <a href="http://sapphire-port-dream.googlecode.com/files/spl-signed.zip" onclick="__gaTracker('send', 'event', 'download', 'http://sapphire-port-dream.googlecode.com/files/spl-signed.zip');" title="http://sapphire-port-dream.googlecode.com/files/spl-signed.zip">spl-signed.zip</a> and copy to root of sdcard
  3. Reboot to recovery mode
  4. Select apply any zip and select the ota-radio-2\_22\_19_26I.zip
  5. When completed, reboot to recovery mode
  6. Select apply any zip and select the spl-signed.zip

Why are we doing this? 

The radio image is the latest radio baseband version. We need the correct version to go with the correct Android build.

SPL is Second Program Loader, which is part of the device&#8217;s bootloader. It is responsible for bootstraping the device, and we are replacing it with a less restrictive one that allows us to apply flash images from any region.

&nbsp;

### IV. Partition SD Card

  1. Download <a href="http://www.4shared.com/file/139646917/5695730f/sdparted.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://www.4shared.com/file/139646917/5695730f/sdparted.html', 'sdparted.txt');">sdparted.txt</a> and copy to root of sdcard
  2. Reboot to recovery
  3. Select console mode (Alt-x)
  4. Enter the commands:
> <font face="mon">mount /sdcard<br />cp /sdcard/sdparted.txt /sbin/sdparted<br />chmod 755 /sbin/sdparted<br />sdparted -efs ext4 -ss 150M</font> 

  5. Continue with execution of the script
  6. Enter the command &#8220;reboot recovery&#8221;
  7. Take out your sdcard

Your sdcard is now correctly partitioned for installing bigger sized ROMs, such as Hero. As you will not be able to boot up your phone to access the sdcard now, you would need to copy the ROMs to the sdcard via a card reader.

&nbsp;

### V. Installing Custom ROMs

The last part is pretty easy &#8211; update a desired custom ROM to the phone. The hardest in this last part would be selecting from the many available ROMs :)

Visit the <a href="http://db.androidspin.com/android_build_information.asp" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://db.androidspin.com/android_build_information.asp', 'Android ROM Build database');">Android ROM Build database</a> to download your desired ROMs. For example, I wanted to try HTC Hero on my ADP1/G1/Dream, I downloaded <a href="http://db.androidspin.com/androidspin_filedownload.asp?release=103&type=1" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://db.androidspin.com/androidspin_filedownload.asp?release=103&type=1', 'KiNgxKxROM Sense Hybrid v2.2');">KiNgxKxROM Sense Hybrid v2.2</a>.

  1. Copy the ROM to root of sdcard (via a cardreader)
  2. Insert sdcard back to phone
  3. Reboot to recovery
  4. Select apply any zip and select the ROM
  5. Reboot when done

That&#8217;s it :)

<p align="center">
  <img alt="hero sense UI" src="http://db.androidspin.com/buildphotos/103-9.jpg" />
</p>

<p align="center">
  &nbsp;
</p>

<p align="left">
  Related:
</p>

  * <a href="http://androidandme.com/2009/08/news/how-to-root-a-t-mobile-g1-and-mytouch-3g-android-phone/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://androidandme.com/2009/08/news/how-to-root-a-t-mobile-g1-and-mytouch-3g-android-phone/', 'How to root a T-Mobile G1');">How to root a T-Mobile G1</a>
  * <a href="http://code.google.com/p/android-roms/" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://code.google.com/p/android-roms/', 'Android ROMs');">Android ROMs</a>
  * <a href="http://db.androidspin.com/android_build_information.asp" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://db.androidspin.com/android_build_information.asp', 'AndroidSpin ROM database');">AndroidSpin ROM database</a>
  * <a href="http://developer.htc.com/adp.html" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://developer.htc.com/adp.html', 'HTC dev phone 1');">HTC dev phone 1</a>
  * <a href="http://forum.xda-developers.com/forumdisplay.php?f=448" onclick="__gaTracker('send', 'event', 'outbound-article', 'http://forum.xda-developers.com/forumdisplay.php?f=448', 'xda-developers');">xda-developers</a>

<div style="font-size:0px;height:0px;line-height:0px;margin:0;padding:0;clear:both">
</div>