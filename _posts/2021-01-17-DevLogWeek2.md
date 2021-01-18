---
layout: post
title: "Week 2 2021 Devlog"
excerpt: "The writer's block"
tags: [Devlog, Shader, VR, Projects, GLSL, Unity]
category: presentation
---

This week I still was fully motivated.  
I found some team mates who will work on their projects and we will cheer each others.  
Even with those supports, I had to fight something I didn't except: the writers blocks.  
I was overwhelmed by the amount of work and the quality of the work I wasn't able to do because I was overwhelmed.  
I should not care, for the moment, about the quality of the game.  
My main goal is to practice myself by working on a project I want to do.  
So I decide to apply one of my favorite quotes when developing something: "First do it, then do it right, then do it better".  
  
  
Thanks to this, I managed to have my very minimalist proof of concept on [itchio.io](https://arosthegame.itch.io/rock-it-for-me) and on the video bellow.  
There is basically nothing but that was my goal of the week. I mainly work on in game scaling this week.  
I don't have much space to play and test so I want the game to be playable without moving or just a bit (stationary position).  
I think it's hard to do nice and clean in game movement (teleportation or sliding in game without moving in reality). I get sick too often.  
My favorite games for now in VR are fast paced with few in game movement (Beat Saber, CrisisVRigade, Tea For God, ...).  
Besides the POC, I tried to define in game scale to match my small play space and to fulfill the giant sensation.  
The physics is fucked up (gravity is to high and my hands aren't powerfull).  
  
<iframe width="560" height="315" src="https://www.youtube.com/embed/VYBl_G_wa-M" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Besides the game, I've made a quick shader that will be used in the game one day I think.  
It's a chess floor customizable (colors and size).  

<script type="text/javascript" src="https://rawgit.com/patriciogonzalezvivo/glslCanvas/master/dist/GlslCanvas.js"></script>
<canvas class="glslCanvas" data-fragment="// Author: Robin Donnay
// Title: Chess Floor

#ifdef GL_ES
precision mediump float;
#endif

uniform vec2 u_resolution;
uniform vec2 u_mouse;
uniform float u_time;

void main() {
    vec2 st = gl_FragCoord.xy/u_resolution.xy;

    vec3 color1 = vec3(0.0, 0.0, 0.0);
    vec3 color2 = vec3(1.);
    float XTilesNumber = 10.;
    float YTilesNumber = 10.;

    bool XStatus = mod(floor(st.x/(1./XTilesNumber)),2.)==1.;
    bool YStatus = mod(floor(st.y/(1./YTilesNumber)),2.)==0.;
    vec3 color = color1;
    if( (XStatus || YStatus) && !(XStatus && YStatus) ){
        color = color2;
    }
    

    gl_FragColor = vec4(color,1.0);
}
" width="250" height="250"></canvas>
  
[You can have fun here](https://www.shadertoy.com/view/3tycDD) and modify the two colors and the number of tiles on this web site.