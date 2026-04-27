# Entry 5
##### 4/20/26

* Aframe is a very cool open-source web framework for building virtual reality and augmented reality experiences. I added aframe to my project, and I read more about aframe on this [Guide](https://aframe.io/docs/1.5.0/introduction/) and learned that A-Frame is optimized from the ground up for WebVR. While A-Frame uses the DOM, its elements don’t touch the browser layout engine. A-Frame is a powerful three.js framework, providing a declarative, composable, reusable entity-component
structure.

* While building my aframe scene, i ran into many challanges. The physics, and particle system wasnt working because i forgot to include the `<script src>`. I also had elements outside of the `<a-scene>` which broke some things like the sky wasnt working.

* The [Geometry](https://aframe.io/docs/1.7.0/components/geometry.html) component provides a basic shape for an entity, which is provided by the geometry component. The general shape is defined by the primitive attribute. In computer graphics, geometric primitives are the simplest shapes that cannot be broken down further. To build a complete mesh, a material component is usually paired with the shape to give it an appearance. Common 2D primitives include points, lines, and polygons (rectangles, circles), while 3D primitives (volumetric) include boxes/bricks, spheres, cylinders, cones, and tori.

## Entity list:
<img src="https://github.com/aframevr/aframe/assets/57718207/38e649bb-23c3-4a16-b0a2-cc34c33c1cca" alt="Geometry" width="auto" height="300" />

## Components

* You can add textures by using images with the ```<src>``` tag, you can specify how big the object will be with ```radius```
```bash
  <a-sphere src="https://raw.githubusercontent.com/aframevr/sample-assets/master/assets/images/space/earth_atmos_4096.jpg" radius="4"
            segments-height="84">
```

* You can add particles by using the ```particle-system``` property, you can change the amount of it by using the ```particleCount``` property to specify how much Rain, Snow, Fire, or Dust should appear, you can change the color of the particle with the ```Color``` tag by using the hex codes.
```bash

 Rain
<a-entity particle-system="preset: rain; color: #24CAFF; particleCount: 5000"></a-entity>
```
```bash
 Snow
<a-entity particle-system="preset: snow; color: #FF0000;  particleCount: 500"></a-entity>
```
```bash
 Fire/Dust
<a-entity particle-system="preset: dust; color: #FF4400; particleCount: 1000"></a-entity>
```
* You can create **3D shapes** using built-in primitives, each has its own properties like `width`, `height`, `depth`, `radius`, and `color`
```bash
<a-box color="red" width="2" height="1" depth="1" position="0 1 -3"></a-box>
<a-cylinder color="blue" radius="0.5" height="2" position="0 1 -3"></a-cylinder>
<a-plane color="#3a7d44" width="100" height="100" rotation="-90 0 0"></a-plane>
```

* You can position, rotate, and scale any object using `position`, `rotation`, and `scale` in the `X Y Z` format
```bash
<a-box position="0 2 -5" rotation="45 0 0" scale="2 2 2"></a-box>
```

* You can add animations to any object using the `animation` property, you can animate `position`, `rotation`, `scale`, and even `color`
```bash
<a-box color="red"
  animation="property: rotation; to: 0 360 0; dur: 3000; loop: true; easing: linear">
</a-box>
```

* You can add a sky background using `<a-sky>`, either as a solid color or a 360 degree image
```bash
<a-sky color="#87CEEB"></a-sky>
<a-sky src="https://example.com/sky360.jpg"></a-sky>
```

* You can add lighting to your scene using `<a-light>`, with types like `ambient`, `directional`, and `point`
```bash
<a-light type="ambient" color="#fff" intensity="0.5"></a-light>
<a-light type="point" color="#FF4500" intensity="2" position="0 3 -3"></a-light>
```

* You can add a full environment in one line using the `environment` component which include `forest`, `starry`, `volcano`, `japan` and more
```bash
<a-entity environment="preset: forest"></a-entity>
<a-entity environment="preset: starry"></a-entity>
<a-entity environment="preset: volcano"></a-entity>
```
To run A-Frame you need the core script, and for extra features like particles, physics, and environment you need additional ```<script src>``` tags to load them in your ```<head>```
```bash
<script src="https://aframe.io/releases/1.7.1/aframe.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/c-frame/aframe-particle-system-component@1.2.x/dist/aframe-particle-system-component.min.js"></script>
<script src="https://unpkg.com/aframe-environment-component/dist/aframe-environment-component.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/n5ro/aframe-physics-system@v4.0.1/dist/aframe-physics-system.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/c-frame/aframe-extras@7.6.1/dist/aframe-extras.min.js"></script>
```


[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
