---
title: Install ROS take 2
date: 2021-01-28
hero: "/images/noetic.jpg"
excerpt: Due to unforeseen issues with Melodic causing massive issues with a variety of packages - I have opted to start from scratch with the more updated ROS Noetic Ninjemys.
timeToRead: 10
authors:
  - Diana Simpson

---

## Take 2 ...

Well, as I started running through the ROS tutorials to learn how it works, where things go, and how to use them ... I suddenly got hit upside the head with an odd python package missing error. After a bit of research and assistance from a friend familiar with ROS, we learned that when I thought I had configured Melodic to utilise Python3, versus the default 2.7, it had been completely reversed when I had to reinstall the desktop packages (after all of the previously installed ROS packages were mysteriously uninstalled). So, it was back to the drawing board, since there were no real solutions found that actually worked. And it seems that Noetic has fixed its problems with the arm64 version ... or so I am hoping.

### Installing Ubuntu Mate ... again

I went back to the Ubuntu Mate [website](https://ubuntu-mate.org/download/arm64/) to select the updated version that will support ROS Noetic - which is Focal Fossa. The first download I received ended up being corrupted, thank goodness for the checksum verification proving this. Another download was initiated, and then verified. I got the OS image flashed onto the Raspberry Pi's SD card, and loaded it into the Raspberry Pi. The initial setup ended up being conducted on my living room TV, since ssh won't set up any longer.

### Setting up remote control & visual access to Pi

The initial setup up was pretty smooth and straightforward. I performed the standard `sudo apt update`. Then, I installed the ssh-server with `sudo apt install ssh-server`. I ran into a problem with the setup in my previous version where my ssh did not activate automatically, so I had to get the Pi back on the TV to activate ssh again before I could remotely port into it from my desktop. So, this time I initiated with setting it up to be a service at boot with `sudo systemctl enable ssh`. This command should automatically activate ssh any time the Pi boots. I restarted the Pi and ssh was still active when I checked using `sudo systemctl status sshd`, so adding ssh to the boot service was successful. There are countless blogs that can assist with additional details to setup ssh in Ubuntu if you do an internet search. My choices came from a handful of the conglomerated results, which is why I only included the commands I used.

#### Minor issues ... again

Shortly after verifying the ssh status, I started experiencing issues with the performance of the Raspberry Pi. The green light was going solid and it was completely locking up or locking up to the point that nothing could be accomplished. It is a model 3B+, so it is stretching a little bit to be able to work with the latest version of Ubuntu Mate. This is also part of the reason I had attempted to use the earlier versions of the software.

A friend recognised the issue after we did some investigation and directed me to [this blog](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04) to activate the memory swap state. This allows some of the SD card to be sectioned off as a back-up for the 1GB RAM to park some of the lower priority items until it can get back to them. There was an instant improvement in performance and the swap prevented the Pi from locking up again.

I was then able to get back on track with the progress of installation. I followed the link mentioned in the [previous post](https://www.roboticsbydiana.com/post/2020-10-24-installing-ros-on-rasppi/) regarding getting vnc installed and running on the Raspberry Pi. So that I could stop sitting point-blank in front of my television in the living room, since the combination of the HDMI cable and hardwired keyboard force me to sit far too close to the screen to be an enjoyable experience.

### Installing ROS ... again

Next step, installing ROS Noetic Ninjemys. I went back to the ROS website and followed the [instructions](https://wiki.ros.org/noetic/Installation) for installing this version of ROS. I selected the appropriate platform and followed the instructions, as before, but this time things went extremely smoothly and I experienced no real errors or oddities. Other than a timing out issue, I blamed the wifi connection. This resulted in me finding an ethernet cable long enough to go from the router to the Raspberry Pi, and the timing out issues ceased.

Now, back to the tutorials and learning about ROS.
