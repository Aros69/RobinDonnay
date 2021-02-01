---
layout: post
title: "Week 4 2021 Devlog"
excerpt: "Search & Learn"
tags: [Devlog, Shader, Unity, IK]
category: presentation
---

<!-- Shaders canvas
<script type="text/javascript" src="https://rawgit.com/patriciogonzalezvivo/glslCanvas/master/dist/GlslCanvas.js"></script>
<canvas class="glslCanvas" data-fragment="" width="250" height="250"></canvas>
     Youtube Video
<iframe width="560" height="315" src="https://www.youtube.com/embed/fBGSJ3sbivI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
-->

As mention in the last devlog, I dedicated this week on research and learning.  
I work on two things. First, I start to search the best IK method for realtime in VR.  
As far as I searched, FABRIK is still the best method as it's fast, customizable (with constraints) and easy to understand.  
I read that VR IK from Final IK unitypackage is also based on FABRIK so I guess it's the best choice at the moment.  
I start reading those two research papers : [First research paper about FABRIK](/RobinDonnay/pdf/FABRIK.pdf) and [Extension of FABRIK to add constraints](/RobinDonnay/pdf/Extending_FABRIK_with_Model_Cοnstraints.pdf).  
I want to make things nicely so I will take my time to understand those papers as this part will highly increase the immersion in the game.
  

As this take some times and I wanted to have something to show this week I started another of my goals, do rendering and shaders in Unity.  
Thanks to [Cat Like Coding Course](https://catlikecoding.com/unity/tutorials/rendering/), I started coding quickly and already adapted one my last shader.  

<img src="/RobinDonnay/images/Devlog/ChessFloorUnity.gif" alt="Chess Floor Shader" width="400" />
  
I still update the game on [itchio.io](https://arosthegame.itch.io/rock-it-for-me), as I promise. Here's the update video :
<iframe width="560" height="315" src="https://www.youtube.com/embed/1jn3U8yXMTs" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

At the moment I feel more hyped about developing cool code features than doing the game.  
I guess that's because I'm not a game designer or a real game developer. I'm more attracted by engine, graphic or tool programming (a good thing as this is my real life work).