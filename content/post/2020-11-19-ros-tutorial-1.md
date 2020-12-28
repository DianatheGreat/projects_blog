---
title: ROS Tutorials
date: 2020-11-19
hero: /images/hero-5.jpg
excerpt: Learning about and how to use ROS is a definite advantage for a roboticist, so it is pretty surprising that as an engineering student majoring in mechatronics with a minor in robotics I have not been exposed to ROS in any direct way.
timeToRead: 8
draft: true
authors:
  - Diana Simpson

---

I decided that the easiest, and probably most expeditious, way to learn about ROS is through their own tutorials. I guess this will be a bit of a crash course for me on their tutorials and ROS itself. There are dozens of [tutorials](https://wiki.ros.org/ROS/Tutorials) available on the ROS site. I plan to give my own synopsis of how things go with each tutorial and my impression of its usefulness and efficacy.

## Beginner level

### Tutorial 1: Installing and Configuring Your ROS Environment

Ran into a bit of an odd error with this tutorial. When I went to run the `catkin_make -PYTHON_EXECUTABLE=/usr/bin/python3` command, I received an error that I was missing the `catkin_pkg` and to make sure it was installed. So, I did some searching and digging around and finally stumbled onto [Q&A](https://answers.ros.org/question/337135/catkin_make-no-module-named-catkin_pkg/) on the ROS site that explained why I was having the issue (because the default python package for ROS is 2.7 and that is the version of `catkin_pkg` that is installed). It gave the logical solution to install the appropriate version of the catkin package: `sudo apt install python3-catkin-pkg`.

I ran this command, and it then removed the majority of the ROS packages that I had just installed ... **_Whoa! huh? What just happened?_** I checked with a colleague that is more familiar with ROS1 (uses it on a daily basis at work) and was informed that doing the catkin package install should not have touched my ROS packages at all. Well, that is a bit of a quandary there, because it did.

So, I just tried to do a quick band-aid with a repeat of `sudo apt install ros-melodic-desktop` hoping it would just fix whatever just happened. It seems to have worked. I was then able to run the catkin_make command and finish the tutorial.

### Tutorial 2: Navigating the ROS Filesystem

I attempted to install the tutorial packages, but basically was informed that nothing needed to be installed.

This was pretty plain and straight-forward with the alterations of commands to find `rospack find [package_name]` or change directories `roscd` straight to a specific ROS package. It is nice to have short cuts like that. It also showed the power of utilising tab with under-completed file names, but that is a pretty common trick for anyone that regularly does programming.

The `roscd log` was also an interesting tool, allowing you to see all of the log files that have been stored.

The `rosls [location_name[/subdir]]` seems like it will also be a useful tool in the future. Being able to _remotely_ access the contents of a different folder within the ROS set up would make copying or relocating files much easier.

### Tutorial 3: Creating a ROS Package

Just another tutorial with a lot of explanation and a good walk-through of generating a new ROS package. I have also started working on adopting VIM as my command line file editor, because it seems to have a lot of really good functionality. It can be a little tricky to learn at first - especially if you have never worked with command line file editors before. It has definitely grown on me over the past couple of years though.

### Tutorial 4: Building a ROS Package

This tutorial was super easy and quick. Just had to re-run the catkin_make command to have the directory created in the last tutorial added to the build folder.

### Tutorial 5: Understanding ROS Nodes

Terms to remember:
- **Nodes:** A node is an executable that uses ROS to communicate with other nodes. ROS nodes use a ROS client library to communicate with other nodes. Nodes can publish or subscribe to a Topic. Nodes can also provide or use a Service.
- **Messages:** ROS data type used when subscribing or publishing to a topic.
- **Topics:** Nodes can _publish_ messages to a topic as well as _subscribe_ to a topic to receive messages.
- **Master:** Name service for ROS (i.e. helps nodes find each other)
- **rosout:** ROS equivalent of stdout/stderr
- **roscore:** Master + rosout + parameter server (parameter server will be introduced later)

I ran into no issues with this tutorial. And I had fun using `rosrun` to run the turtlesim node over and over, because you get a different turtle every time!

It was also interesting to learn that using ctrl-C to close out a program will leave a residual program in the `rosnode list`, which needs to go through the cleanup process for the empty node to be purged. So, better to close the window to quit than to use ctrl-C.

### Tutorial 6: Understanding ROS Topics

Well, that was a fun way to explain and demonstrate topics and messages. The `rqt_plot` node was having issues though. The window was either tiny with no graph visible at all or it had to be maximised. I attempted to make it slightly larger and it caused the entire thing to crash.

I ended up with a few terminal windows open, but it was a interesting activity. The visual connections shown with the `rqt_graph` node was nice. I also liked that it could be refreshed with the additional nodes and messages added - including all of the relationships.

### Tutorial 7: Understanding ROS Services and Parameters

This is getting into some more heavy topics that will require more use to really get it into my brain. They break it down to simple explanations in the tutorial, but there is just a lot more going on in these areas than in the prior sections.

Services allow nodes to send requests and receive responses. And the services available will vary depending on the nodes running. I did enjoy spawning a second turtle into the `turtlesim` node.

Parameters are pretty straight forward as well. But, I was a little confused by the fact that the parameters showed a version of `turtlesim` that I had ended earlier, and completely closed the previous terminal window.

### Tutorial 8: Using rqt_console and roslaunch

`rqt_console` is the built-in ROS debugging framework. It is fairly easy to get running and understand with the GUI console and explanations of logger levels. It is also slightly entertaining to get repetitive warnings when your turtle runs into a wall. The program seems very distressed.

`roslaunch` allows multiple nodes to be launched at the same time through a launch file. It is an easy walk-through from generating the launch file, to explaining what each part of the xml code is doing. It also pulls some of the debugging aspects of other `rqt` affiliates into the end as well.

### Tutorial 9: Using rosed to edit files in ROS

This tutorial is short and sweet, and allows you to alter the default editor program used to edit files in ROS with the `rosed` command.

### Tutorial 10: Creating a ROS msg and srv

This tutorial seems fairly straight-forward, as they all have really been. Although, I ran into a snag when it instructed me to copy a `.srv` file from another tutorial folder. Luckily,

### Step 1

During the Bootstrap sequence, which occurs every time you run \$ gatsby develop, there are about 20 events that fire ranging from validating your gatsby-config.js to building the data schemas and pages for your site. For example, the Bootstrap sequence is where Gatsby will create pages. If you want an in depth look of all 20 Bootstrap steps Swyx shared a fantastic Gist that goes into more detail.

### Step 2

The Build sequence is very similar to the Bootstrap sequence, except it’s run with production optimizations and will output static files ready for deployment. Think of it as building your React application in production mode vs development.

### Step 3

And finally, once the generated files are deployed, Gatsby lives in the browser. Gatsby cleverly generates a static website that turns into a web app after initial load, which extends the lifecycle to the browser.

What’s important to remember is that Gatsby’s lifecycle can be aggregated into 3 main sequences:

- Bootstrap
- Build
- Browser
- These three sequences makeup the Gatsby lifecycle.

Parts of the lifecycle are visible when running $ gatsby develop
A peak into the Gatsby lifecycle when running $ gatsby develop
A peak into the Gatsby lifecycle when running \$ gatsby develop
If you’re familiar with React and the component lifecycle, Gatsby’s lifecycle is almost the same concept. Just like React’s lifecycle, Gatsby exposes hooks for developers to build on top of. Those lifecycle hooks are accessed through Gatsby specific files such as gatsby-node.js, gatsby-browser.js and gatsby-ssr.js.

What are the Gatsby specific files for?
gatsby-config.js
A place to put all your site configurations such as plugins, metadata, and polyfills. This file is the blueprint of your application and is where Gatsby really shines with its plugin system. When you run $ gatsby develop or $ gatsby build gatsby-config.js is the first file to be read and validated.

Most of your time spent in gatsby-config.js will likely revolve around source plugins, image plugins, offline support, styling options, and site metadata.

gatsby-node.js
Gatsby runs a Node process when you develop or build your website and uses Webpack under the hood to spin up a development server with hot reloading. During the Node process Gatsby will load plugins, check the cache, bootstrap the website, build the data schema, create pages, and deal with some configuration and data management.

Everything that occurs during the Bootstrap and Build sequences occurs in gatsby-node.js. This means it’s the perfect place to create pages dynamically based off data from a source plugin or modify Gatsby’s Webpack or Babel configs.

For example, if you want to move some files manually, such as a Netlify \_redirects file, a good place to do it is in your gatsby-node.js file at the onPostBuild lifecycle hook.

From experience, most of my time has revolved around handling data and building pages in gatsby-node.js. This file quickly becomes the piping of your entire website.

## Examples of gatsby-node.js hooks:

- createPages
- onCreateBabelConfig
- onCreateWebpackConfig
- onPostBuild
- gatsby-ssr.js

When you think Server Side Rendering you think of a server that takes in requests and dynamically builds pages and sends it to the client. Gatsby doesn’t do that, but it does server side render — it generates all the pages during build time.

Naturally, gatsby-ssr.js allows developers to hook into that lifecycle. In my experience, most use cases revolve around injecting CSS, HTML, or Redux state information into the generated output. For example, if you need to insert third party scripts such as Analytics Tracking or a Pixel it can be done on the onRenderBody gatsby-ssr.js hook.

## Examples of gatsby-ssr.js hooks:

- onPreRenderHTML
- onRenderBody
- replaceRenderer
- gatsby-browser.js

Gatsby is a static site that loads a dynamic application after initial load, which means you get the benefits of a static site in a web application. gatsby-browser.js provides convenient hooks to deal with app loading, route updates, service worker updates, scroll positioning, and more.

Everything that occurs after your static site has loaded can be hooked in gatsby-browser.js. For apps that I’ve built, gatsby-browser.js was mostly used for keeping track of routes, scroll positioning, and sending analytics events.

## Examples of gatsby-browser.js hooks:

- onClientEntry
- onRouteUpdate
- onServiceWorkerInstalled
- registerServiceWorker
- shouldUpdateScroll

## Conclusion

Gatsby is built with React at its core and shares a common API pattern, the lifecycle. This lifecycle gives developers access to key moments in their website’s process through specific hooks. For example, adding analytics can be achieved through the Browser lifecycle hook onClientEntry. Gatsby reserves specific filenames as an entry point to access every lifecycle; these files are named gatsby-node.js, gatsby-ssr.js and gatsby-browser.js.

Without the Gatsby lifecycle, it would be impossible to customize and modify your project beyond the base configuration, leaving developers with a rigid and poor developer experience. This power and flexibility has helped us build amazing web projects for clients like Hopper!

Gatsby is a staple within our engineering process at Narative, helping us help our clients build the products they’ve always dreamed of, and the ones they’re yet to dream up.
