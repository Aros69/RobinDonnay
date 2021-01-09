---
layout: post
title: Shaders Everywhere
excerpt: "A tale in Shader World"
tags: [Shader, GLSL]
category: blog
---

More described post will arrive soon.  
Goal : Have fun and greatly improve shader knowledge.  

You can find my shader project on [github](https://github.com/Aros69/ShadersEverywhere).  

Week 1 shader :  
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