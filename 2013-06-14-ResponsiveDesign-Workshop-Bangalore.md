##Responsive Design Workshop 2013
####*By* Arpan CJ
####14 June 2013 TERI, Bangalore

1. [http://koala-app.com/](http://koala-app.com/)
2. scout
3. [http://susy.oddbird.net/](http://susy.oddbird.net/)
4. display: inline    - for IE
5. Mobile-first e.g.: flickr
6. device independent pixels introduced by apple
7. "Not everyone is in a hurry" mobile design is important
8. "Don't dump everything in mobile"
9. slow n/w speeds
10. optimizing mobile design
11. 75% thumb use: 44px or 0.7mm minimum for apple
12. content first (homepage & content page nag shouldn't be same)
13. be aware of performance - youtube, slow connection,
14. [http://caniuse.com/css3-boxsizing](http://caniuse.com/css3-boxsizing)
15. border-box
16. browser statistics
17. worry about performance for js, css3 animations etc, not css3
18. site starts at 1/10th of a sec
19. eg: img takes 1sec, gradient 0.01sec - rendered by GPU
20. @include box-sizing(border-box);
21. absolute positioned elements don't take full width by default
22. [http://hellohappy.org/css3-buttons/](http://hellohappy.org/css3-buttons/)
23. [http://compass-style.org/reference/compass/css3/pie/](http://compass-style.org/reference/compass/css3/pie/)
24. [http://www.techrepublic.com/blog/webmaster/css3-layering-multiple](http://www.techrepublic.com/blog/webmaster/css3-layering-multiple)
25. shadows-creates-lightweight-pages/757
26. [http://designingfortheweb.co.uk/](http://designingfortheweb.co.uk/)
27. [http://www.abookapart.com/](http://www.abookapart.com/)
28. [http://smacss.com/](http://smacss.com/)
29. Native app support for iOS:
	```html

	<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=0" />
	<meta name="apple-mobile-web-app-capable" content="yes" />
	```
30. for accessibility, don't do display: 0, ins tread use height: 0, or hide from viewport
31. Forms: [http://diveintohtml5.info/forms.html](http://diveintohtml5.info/forms.html)
32. formalize.me: [http://formalize.me/jquery_demo.html](http://formalize.me/jquery_demo.html)
33. html5 is completely non-versional, instead modules
34. Avoid using ids, use class
35. compass
36. media breakpoints don't depend on specific device width, instead based on design
37. image - content/layout
	- content images : html
	- layout images : css
38. customize drag and drop for touch devices with moderniser [http://modernizr.com/download/](http://modernizr.com/download/)

```
/images
/js
/style
	/base
		base.sass
		colors.sass
		typography.sass
	/layout
		grid.sass
		modules.sass/core.sass //common modules across all devices
		typography.sass
		forms.sass
		header.sass
		components.sass //common elements    
app.sass
```
 
