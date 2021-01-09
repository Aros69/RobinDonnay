---
layout: post
title: "Week 1 2021 Devlog"
excerpt: "The begining of a great adventure"
tags: [Devlog, Shader, VR, Projects]
category: presentation
---

One of my resolution this year is to make more personnal dev projects. To complete this goal, I will do weekly devlog to keep track of my work.  
It's time to do some personal projects to improve myself in my passion, computer graphics and video games.  
I got my master degree and a job as tool developer at 8SEC.  
No more job search (for now) or school projects to do until 3 A.M because you have to present it tomorrow at 8 in the morning.    
As my boss said : "2020 was a warm up... 2021 is GAME TIME".  
I got two main project in my head at the moment, a VR Game and shaders. I also got side projects like another VR game, ps vita homebrew (I want to play nds game on it even if it's impossible), I also got a small robot that I want to improve in python and many other idea (AI, Robotics, personnal life style app...).  
  
I don't know where all those things will bring me but "One is better than Zero". I don't care how far I'll go.   
It doesn"t matter if I can't finnish a project, I will win experience with it.   

Now let's talk about those projects a little bit.  
You can find my shader project on this [page](https://aros69.github.io/RobinDonnay/blog/ShadersEverywhere/) and on [github](https://github.com/Aros69/ShadersEverywhere).  
This week I've done one simple shader and take ideas of other one I will do later.  
Heres my week 1 shader, computed trichromatic circles, nothing great but it's honest work.

<script type="text/javascript" src="https://rawgit.com/patriciogonzalezvivo/glslCanvas/master/dist/GlslCanvas.js"></script>
<canvas class="glslCanvas" data-fragment="// Author: Robin Donnay
// Title: Trichromatic Circle

#ifdef GL_ES
precision mediump float;
#endif

uniform vec2 u_resolution;
uniform vec2 u_mouse;
uniform float u_time;

bool IsInCircle(vec2 centerNormalized, vec2 coordNormalized, float radius){
    return sqrt(pow(centerNormalized.x-coordNormalized.x,2.)+pow(centerNormalized.y-coordNormalized.y,2.))<radius;
}

vec3 Circle(vec2 centerNormalized, vec2 coordNormalized, float radius){
	vec3 color = vec3(0.);
    if(IsInCircle(coordNormalized, centerNormalized, radius)){
        color = vec3(1.);        
    }
    return color;
}

vec3 ColoredCircle(vec2 centerNormalized, vec2 coordNormalized, float radius, vec3 circleColor){
	return Circle(centerNormalized, coordNormalized, radius)*circleColor;
}

vec3 RedCircle(vec2 centerNormalized, vec2 coordNormalized, float radius){
	return ColoredCircle(centerNormalized, coordNormalized, radius, vec3(1.,0., 0.));
}

vec3 GreenCircle(vec2 centerNormalized, vec2 coordNormalized, float radius){
	return ColoredCircle(centerNormalized, coordNormalized, radius, vec3(0.,1., 0.));
}

vec3 BlueCircle(vec2 centerNormalized, vec2 coordNormalized, float radius){
    	return ColoredCircle(centerNormalized, coordNormalized, radius, vec3(0.,0., 1.));
}

vec3 TrichromaticCircle(vec2 coordNormalized){
    float radius = 0.3;
    return RedCircle(vec2(0.5, 0.65), coordNormalized, radius) +
        GreenCircle(vec2(0.35, 0.35), coordNormalized, radius) +
        BlueCircle(vec2(0.65, 0.35), coordNormalized, radius);
}

void main() {
    vec2 fragCoordNormalized = gl_FragCoord.xy/u_resolution.xy;
    //st.x *= u_resolution.x/u_resolution.y;

    vec3 color = TrichromaticCircle(fragCoordNormalized);
    // vec3 color = vec3(0.);
    // color = RedCircle(vec2(0.2,0.2), fragCoordNormalized, 0.2);
    // color += BlueCircle(vec2(0.2,0.2), fragCoordNormalized, 0.2);
    // color += GreenCircle(vec2(0.2,0.2), fragCoordNormalized, 0.2);

    //color = vec3(st.x,st.y,abs(sin(u_time)));

    gl_FragColor = vec4(color,1.0);
}

" width="250" height="250"></canvas>

In fact, my biggest struggle this week was scaling and starting the game project.  
I've made a trello to keep my tasks in mind but I can't start anything.  
I've scale down at the maximum and I hope I'll have the smallest and dirtiest POC next week so I can upload it on itch.  
I got too many ideas for that game, I can't focus.  
Anyway, here's my two main inspiration for the game :
- [This app](https://apps.apple.com/in/app/giant-punch/id1541849472) gave me the global idea of the game 
<img src="/RobinDonnay/images/Devlog/GiantPunch.png" alt="App Inspiration" width="200" />
- The music below is another inspiration... I don't know if I can and will polish the project to have the art style of it but that's another far far away goal   
<iframe width="560" height="315" src="https://www.youtube.com/embed/fBGSJ3sbivI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
