---
layout: post
title: "Week 3 2021 Devlog"
excerpt: "Not an artist"
tags: [Devlog, Animation, Blender, VR, Unity]
category: presentation
---

<!-- Shaders canvas
<script type="text/javascript" src="https://rawgit.com/patriciogonzalezvivo/glslCanvas/master/dist/GlslCanvas.js"></script>
<canvas class="glslCanvas" data-fragment="" width="250" height="250"></canvas>
     Youtube Video
-->

This week I was a little bit tired and not productive.  
I read some [tutorials](https://catlikecoding.com/unity/tutorials/) about meshes and rendering.  
It's hard for me to start a task because there are many things to do and I can't decide what to do. I will spend time next week on organization to help me on that.  
I chose to work on my player so I try to use Blender for the first time with no help except [Blender's documentation](https://docs.blender.org/manual/en/2.79/index.html) to create simple robot hands. It's important for me to work on Blender as it will be usefull on many projects and some knowledge on it may help me in my work.  
I soon realize that I'm not an artist and the creation and importation in Unity of the dirtiest hand may take me more than a week.  
As I know the very basics of modeling and I could create a simple cubic pliers for my robot hands but the rigging and animation part is totally unknow for me.  
So after few hours of work on Blender I switch to another task closer to my knowledge.  
Even if I stopped this task here is the left part of my robot hand (with the begining of the armature).  
<img src="/RobinDonnay/images/Devlog/RobotHand.png" alt="Robot Hand Blender Software" width="400" />
  
After discovering that I'm not an artist, I work on something with more algorithms : Invers Kinematic (IK).  
I want to practice and increase my understanding on IK so I won't use available solution like [Final IK](https://assetstore.unity.com/packages/tools/animation/final-ik-14290).  
I re-use a Universty project I done about IK and the FABRIK algorithm (I'll give you more informations about it in the next Devlog).  
As I don't know if it's a good algorithm for VR IK I will make some research on VR IK algorithms next week.  
Anyway, I integrate this IK algorithm in the game really quickly (besides a problem with Unity Primitive creation at runtime on Oculus Quest).  
It's not perfect, there are no constraint on joint rotation and bones does not have a tolerant size which is confusing while playing.  
Here's a video of the result of this week build :   
<iframe width="560" height="315" src="https://www.youtube.com/embed/Nig3QnuBq1c" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  
The new build is available on [itch.io](https://arosthegame.itch.io/rock-it-for-me) for those who want to test the arms.