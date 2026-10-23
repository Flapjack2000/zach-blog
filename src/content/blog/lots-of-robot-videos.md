---
title: "Lots of Robot Videos"
description: "My second post."
pubDate: "Oct 22 2026"
heroImage: "../../assets/blog-placeholder-4.jpg"
tags: ["Fellowship Research"]
---

During my work with Dr. Hans in Summer 2025, I used ABB's RobotStudio for the robot simulations. ABB was very kind and let us use a free license for a year. Here's a screen recording of the robot sanding the propeller blades on the sander in RobotStudio (please appreciate the high art that is the sander model).

<video controls width="100%">
  <source src="/videos/robotstudio-propeller-on-sander.mp4" type="video/mp4" />
  Something went wrong loading this video.
</video>

Throughout the video, you'll notice the front of the propeller clips through the sander. Collision detection and avoidance are what we're going to focus on in this research project. We're also going to try and generalize our processes for different objects and tools (so not just sanding boat propellers).

We were considering using RobotStudio again, and though we could probably get another free license, I decided to shop around and look at other options. This time around we are doing research instead of working with a client company, meaning we don't necessarily have to do our work specifically for ABB robots anymore.

CoppeliaSim Edu (I'm going to call it CSE for short) is the most promising candidate for our research so far. It has quite a lot going for it. One of the hard parts about RobotStudio was that it required the use of RAPID, which is ABB's proprietary robot controller programming language. I spent a lot of time reading through dozens of dense technical manuals on RAPID. On the other hand, CSE supports both Lua and Python. While I don't know Lua myself, I've been able to get Claude to generate scripts fairly easily.

And, conveniently, the educational version is completely free (just can't use it for commercial purposes). Here's a screen recording of a robot in CSE drawing "hello world". I had Claude generate the script that's being run in this video.

<video controls width="100%">
  <source src="/videos/coppelia-hello-world.mp4" type="video/mp4" />
  Something went wrong loading this video.
</video>

There is one hiccup involving not being able to import .igs files, which is what the propeller's CAD file type is. That's kind of fine because .igs files can be converted to .obj or .stl files to be displayed in CSE. But quality .igs files are impossible to find for free online, meaning if we want to work with CAD models we find on the internet, then we need to change the original code to do that. .obj and .stl files are really easy to find, however, they only store triangle meshes and reverse engineering the B-spline/NURBS surface data from these types of models would be a hassle. From what I understand, STEP files might be the way to go. .igs files hold B-spline/NURBS surface information, and so do STEP files. The original code relies on the file type of the model being .igs, but maybe I can get STEP files working. STEP files hold the kind of information we need, can be converted into .obj or .stl for visuals, and are far more abundant online than .igs files.

Here's a screen recording of a cool demo that came with the software. It's the [Fanta Can Challenge](https://youtu.be/SOESSCXGhFo?si=xlzt1J4DNjRCu2JC) that ABB did back in 2009.

<video controls width="100%">
  <source src="/videos/fanta-challenge-demo.mp4" type="video/mp4" />
  Something went wrong loading this video.
</video>
