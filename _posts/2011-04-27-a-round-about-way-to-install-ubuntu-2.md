---
title: A Round About Way to Install Ubuntu
author: chris
layout: post
permalink: /2011/04/27/a-round-about-way-to-install-ubuntu-2/
blogger_author:
  - Chris Laughlin
blogger_permalink:
  - /2011/04/round-about-way-to-install-ubuntu.html
blogger_blog:
  - limitedconnection.blogspot.com
categories:
  - Uncategorized
---
Ok so the reason behind this blog post is celebrate my success, for sometime now I have been trying to install a full install of Ubuntu into an old Toshiba Tablet PC. The main issue that I was presented with was that lack of a CD-ROM drive, however the solution to this is to boot of a USB. After a number of different USB sticks and applications that can build a bootable USB stick I was still unable to boot the tablet from the USB and install the OS from it. 

After doing some research I discovered that Toshiba have made it very tricky for there tablet PC ranges to boot from external devices and only a hand full of USB drives external CR-ROM drives will work with the tablet. So my next step was to install Ubuntu from the ISO on the machine with the help of Wubi, Wubi allows you to install a Linux distro on a machine without setting up partitions and working with the boot loader. however the main drawback for me choosing this option is that the OS isn&#8217;t fully installed and has a slower disk access speed that can cause the OS to run sluggish. It also means that if you don&#8217;t want to use the old OS Windows XP in my case its wasted space on your machine. 

So I was almost about to give up and just install with Wubi and leave it at that, until I thought if I have a running version of Ubuntu I should be able to merge this into a full OS install across the machine. I installed the Wubi install of Ubuntu and then was able to find a script that would preform the full install. however to do this I needed to format the partition that was holding the windows install. Luckily the disk utility in Ubuntu let me un-mount the partition and then I was able to format its and swap the Linux partition with this thus overwriting the existing Windows OS and leaving the Ubuntu install as the main OS.