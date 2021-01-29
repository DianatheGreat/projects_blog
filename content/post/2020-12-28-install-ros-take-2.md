---
title: Install ROS take 2
date: 2021-01-28
hero: "/images/noetic.jpg"
excerpt: Due to unforeseen issues with Melodic causing massive issues with a variety of packages - I have opted to start from scratch with the more updated ROS Noetic Ninjemys.
timeToRead: 10
draft: true
authors:
  - Diana Simpson

---

Well, as I was running through the ROS tutorials learning how it worked and where things went and how to use it ... I suddenly got hit upside the head with an odd python package missing. Well, it turns out that when I thought I had configured Melodic to utilise Python3, versus the default 2.7, it completely reversed all of that when I had to reinstall the desktop packages.

Went back to the Ubuntu Mate [website](https://ubuntu-mate.org/download/arm64/) to select the updated version that will support ROS Noetic. The first download I received ended up being corrupted, thank goodness for the checksum verification. Got the OS image flashed onto the Raspberry Pi's SD card, and loaded it into the Raspberry Pi. The initial setup ended up being conducted in the living room, since ssh is not going to be set up yet.

I installed the ssh-server with `sudo apt-get install ssh-server` and set up as a service at boot with `sudo systemctl enable ssh`. So, that I don't have to worry about not being able to connect to the Pi each time. I restarted the Pi and ssh was still active when I checked, so the boot service worked.

I started experiencing issues with the performance of the Raspberry Pi. It is a model 3 B+, so it is stretching a little bit to be able to work with the latest version of Ubuntu Mate, which is part of the reason I had attempted to use the earlier versions of the software. I used [this blog](https://www.digitalocean.com/community/tutorials/how-to-add-swap-space-on-ubuntu-16-04) to activate the memory swap state to allow some of the SD card to be utilised as a back-up for the 1GB RAM available on the 3B+. There was an instant improvement in performance. It would, at least, prevent the Pi from locking up.

Then I followed the link mentioned in the [previous post](https:www.roboticsbydiana.com) regarding getting vnc installed and running on the Raspberry Pi. So that I could stop sitting point-blank in front of my television in the living room, since the HDMI cable forces me to sit far too close to the screen to be an enjoyable experience.


