---
title: Getting Raspberry Pi loaded with Ubuntu & ROS
date: 2020-10-24
hero: "/images/melodic.jpg"
excerpt: Taking my first swing at using a non-official OS on the Raspberry Pi for optimal functionality with ROS.
timeToRead: 4
authors:
  - Diana Simpson

---

This initial project is to develop a line following robot utilising a home-made setup along with a Raspberry Pi for the brain and integrating ROS for extended functionality and gaining familiarity with the robotic operating system.

## Integrating ROS with Raspberry Pi

I initially headed to the [ROS.org site](https://wiki.ros.org/ROSberryPi) to gain information about loading ROS onto the Pi. It gives instructions on installing ROS Melodic on Raspbian Buster. Since this tutorial was published, Raspbian has been renamed to Raspberry Pi OS. (Raspberry Pi OS)[https://www.raspberrypi.org/downloads/] is currently on version 1.4. But, the tutorial does recommend installing and using Ubuntu Mate with the standard ARM installation instructions for ROS. So, I investigated the latest versions available for the Raspberry Pi.

### Initial attempt

The tutorial was last updated in April, 2020. A newer version of Ubuntu Mate has also been released - Focal Fossa 20.04. So, the newer version of ROS will also need to be installed for compatibility - [ROS Noetic](https://wiki.ros.org/noetic/Installation/Ubuntu).

Unfortunately, when attempting to install any ROS versions of Noetic Ninjemys onto the Raspberry Pi, an issue kept popping up that the files for arm64 were not available. Upon further scrutiny amd64 files were available in the repository, but not arm64 versions. So, this version of ROS is not currently supported for use on Raspberry Pi. So, back to the drawing board with the prior releases of Ubuntu Mate -> Bionic Beaver and ROS -> [Melodic Morenia] (https://wiki.ros.org/ROSberryPi/Installing%20ROS%20Melodic%20on%20the%20Raspberry%20Pi).

### Getting Ubuntu Mate onto Raspberry Pi

The [Ubuntu Mate website](https://ubuntu-mate.org/ports/raspberry-pi/) for the Raspberry Pi version gives a lot of information about the product itself and some additional features and fixes. They do recommend utilising the latest Raspberry Pi 4 Model B 2GB or more for the best experience, but it is still compatible with the 3B+ and the 3B model as well.

####Step 1:
Choose your version -- I selected the previous Ubuntu Mate version for a 64-bit Raspberry Pi system (which is no longer listed as **_experimental_**), which was 18.04.1 Bionic Beaver. _*This version has since been removed from the website._

####Step 2:
Download the compressed disk image. The download did not automatically start for me, so I had to manually get it going.

####Step 3:
Flash to the SD card. I went into my computer programs and no longer had the etcher program I had previously used. So, I found multiple recommendations for [Balena Etcher](https://www.balena.io/etcher/). I got that downloaded and installed pretty quickly. Then, used the program to flash the compressed file onto my SD card.

####Step 4:
I popped the SD card into the Raspberry Pi. I already had my screen, keyboard, and mouse attached. I plugged the power supply in and the disk image did all of the setup work itself. Once the OS was launched, it had me create my login details. Easy peasy!

If you require more detail or visuals for getting the OS onto your SD card, [this](https://itsfoss.com/ubuntu-mate-raspberry-pi/) was a decent guide that was found. Most of the other tutorials and how-tos were even more out-of-date.

### Installing ROS onto Ubuntu Mate loaded Raspberry Pi

Going through the [recommended instructions](https://wiki.ros.org/melodic/Installation/Ubuntu) for the Melodic installation on Ubuntu Bionic Beaver, breaks down the process pretty clearly. So, I am not going to do a step-by-step where other wheels have already been made.

If you are not familiar with Linux or Ubuntu repositories, definitely follow the [recommended guide](https://help.ubuntu.com/community/Repositories/Ubuntu) from the ARM installation instructions.

**Also**, make sure that you read through the steps completely before executing one or all of the options listed. This could cause issues with your installation.

### Completed check-box
I now have the check box marked off for installing ROS on my Raspberry Pi. Now, onto learning ROS.
