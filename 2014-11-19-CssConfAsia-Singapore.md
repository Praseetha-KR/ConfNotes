##CSSConf Asia 2014
####19 Nov 2014 Amara Sanctury Resort, Singapore

####Build Scalable, Automated CSS Both You and Your ’Back-End’ Coders Can Love
######Challenge #1 Use layouts that makes sense
- stop fighting with floats.
- instead use inline-block
- 0-sized fonts for white space

######Challenge #2 Make CSS code maintainable
- “maintainability” == Optimize first for the processor inside your skull
- Precompilers - mixin, vars, ...
- define theme with different style sheet & @import


1. Automate (responsive & identifiable mixins)
2. Name all the things clearly
	- instead of #nav-list li a, use of #navheader_list_links
	- classes shouldn’t contaminate html
	- BEM, OOCSS, Suit
	- Namespacing
3. use element selectors only for rests
	- not too much namespacing 
	- specificity algorithm
	- reset global styles
	- no !important
	- Use @extend or @include to create a narrower class, rather than fight the existing one	
4. stop over nesting
	- descendant selectors performance
	- `#very-specific-id .semi-specific-class li a`

5. Avoid unnecessary complexity
	- pseudo sectors are too expensive

------

####Inside the Airbnb brand evolution

1. Sane CSS Achitecture (Airbnb CSS framework)
2. Testable and Measurable components
3. Scaling the rebrand

------
####Commandments for efficient CSS architecture

1. Keep file sizes small
2. use vars
3. Component abstraction (@extend)
4. Keep selector strengths low (div.tab —> .tab)
5. Naming convention (BEM):
	```
	
	Block - .component
	Element - .component__sub-part
	Modifier - .component—variation
	```
6. z-index Management
7. @extend - avoid selector hell

------
####What are we doing anyway?

[`<x-gif>`](http://geelen.github.io/x-gif/#/http://i.imgur.com/iKXH4E2.gif)

------
####Performant UIs using Magic of CSS

1. bounce.js
2. pseudo base physics
3. performant scrolling library
4. reusable list items recorded on scroll
5. use of flex box order property

######Performance:
cost of CSS property change
csstriggers.com
order property cause reflow & paint
always use transform, opacity
everything else is detrimental

######Paint v/s Reflow:
- paint - non geometric change
- reflow: geometric chnage

	```javascript

	body.style.visibility = “hidden” // no reflow/paint
	body.style.fontSize // both reflow & paint
	```

######Batching:
- reads & writes
- Layout & paint only happen once per tick
- requestAnimationFrame 60fps

######Control & Minimise:
- DOM Abstractions
- React
- Embers HTMLBArs

######Measure UI performance:
- devtools Chrome, safari, IE11, ffx


- Safari debug
- show composing properties

Flooding the GPU:
- uploading way too many textures
- GPU bus can’t handle it
- white out problem
- order property isn’t performant

*high performmant UI is hard*

- Native performance on the web?
- possible through abstraction layer
- Famous.io
- Flat DOM + rAF + GPU + PhysicsEngine = Awesome
- renderer can be DOM, SVG or even WebGL

*Performance is fragile*

- web platform needs low level controls:
- controlling paints & reflows
- isolation of components
- iframe solves the issue

---------

####Cascading Perspectives with THREE.CSS3DRenderer

1. ######Three.js basics
	- Scene
	- Objs (Meshes with materials, lights, groups)
	- Camera(perspective, orthographic)
	- Renderer(canvas | WebGL | SVG | Software renderer)

2. CSS3D renderer
3. CSS3DObjects, CSS3DSprites
4. transform: matrix()
5. bugs:
	- ie preserve-3d
	- css3drendererIE

*“making layers considered dangerous” - Paul lewis (will-change)*

--------

####Building a modern mobile UI web
```css
flex: grow, shrink, basis
justify-contents: space-around
align-items: center
```
[http://ricostacruz.com/#!/article/1](http://ricostacruz.com/#!/article/1)
