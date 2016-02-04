#Modern Web Summit - Feb 4, 2016, Bangalore :: Organized by Flipkart

##Anatomy of Service Workers - Alex Russel

- WinJS, Electron
- W3C Widgets
- AppCache

SW:
- event driven
- shut down b/w events
- install --> activate --> idle ---> fetch <---> stop
- Progressive enhancement for the network calls


##Push Notifications in Progressive Web Apps - @owencm

####What?
App Engagement:
- Home screen icon
- Push notifications
- self selection

####Why?
Reach + Engagement:
- Add to home screen btn
- Web Push

####How?

Service worker:
- Client side proxy written in js
- Background event handler
- Background processes

- Ref: [bit.ly/webpushguide](bit.ly/webpushguide)
- [chrome://serviceworker-internals](chrome://serviceworker-internals)

####UX
- Urgent vs Important chart
- Don't request permission on page load ("would u like notify?")
- De duplicate with native
  - dont send notification if device looks the same
  - fire a n intest into thenatice app as part of the opt 
- Ref: paul kinlan's article

- Payload
- Silent Push
- Background sync
- Ref: Emojoy by Jake


##Real World PWAs (Building Flipkart Lite) - Abhinav Rastogi
- SW
- push notifications
- add to home screen
- splash screen
- Smooth animations - RAIL, FLIP
- security (HTTPS, CSP (Content Security Policy))

####SPA
- complete client side
- Implement a kill switch (and versioning)
	- invalidate SW/cache
	- skip waiting
- Ref: sw-toolbox - a wrapper lib to SW
	- Express-style routes - help SEO
	- "Read though cache" - always stay up-to-date
- 301s redirect is not followed when using fetch api

####Learnings
- Cache busting (one version behind)
- Avoid dynamic content in shells
- skipWaiting so that new SW can override existing SW immediately
```
	
	self.addEventListener('install', event => {
		event.waitUntil(self.skipWaiting());
	});
	self.addEventListener('activate', event => {
		event.waitUntil(self.clients.claim());
	});
```
- 301s are currently dangerous

####Tracking/Analytics
- important for performance consideration
- be wary of automatic UI hooks
- tracking library file size
- queue events before library loads?
- CSP can cause havoc with beacons! 

####CORS
- API might be on diff domain/hostname
- especially on dev/staging env
- API server needs to understand OPTIONS request
- respond with correct access-control headers
- browser plugins for debugging on dev machines

####Splash screen
- 2 splash screen combined

####Performance
- Treat performance as a feature
- RAIL
	- 16ms/frame = 60fps
- Animate right properties: stick to transform & opacity (GPU rasterizations)
- Chrome trace - devtools
- trace on the device

####Next?
- HTTP2
- HTML streaming
- link prefetch
- script type module


##The stack behind Flipkart Lite - Boopathi Rajaa

React/jsx
####HTML Page SHells

- Loading state (pre state: SHELL) - Loaded state (post state: SHELL + content)
- percieved perf > Actual
- Shells + SW
- React.renderToString() - done during build time instead of runtime
- componentDidMount
- ReactRouter

Inject Params:

| Route Defined 		| Route to render 	| Shell    |
|-------------------|-------------------|----------|
| `/:slug/p/:itemid`| /slug/p/itemId 	| product  |
|`/(.*)/pr` 			| /splat/pr			| browsers |
| `/search`			| /search				| search   |
| `/accounts/(.*)`	| /accounts/splat	| accounts |

- Bundle to static assets: webpack
- Two level templating
	- 1hbs to multiple files
	- bundle to new SW file
- CSS Modules
	- postcss
	- .header{} --> .02jei{}
- Babel
- Phrontend: github.com/flipkart-incubator/phrontend
- Monorepo vs Repo per feature
	- logical group
	- master slave apps 

##E-commerce with react - Sunil Pai

####e-commerce site 5 steps:
- landing page
- product list
- product details
- cart
- checkout

components are first class entities

`view = ƒ(props)`

`APP = ƒ(ALL YOUR DATA)`

- why does react scale [https://www.youtube.com/watch?v=D-ioDiacTm8](https://www.youtube.com/watch?v=D-ioDiacTm8)
- compete via iteration
- npm - code reuse & reviews
- urls - router
	- dynamic code loading?
- layouts - css (react native css layouts)
- polish/ui
- deploys - npm

- 2 end points for bundles:
	
	`/packages/iosapp/version`
	
	`/packages/iosapp/${version}`

- rollouts - A/B tests - more npm
- basically a DIY browser

problems:
- its young
- weak ecosystem
- memory intense if not careful

bringing it back:
- 0 blinks
- 60fps
- 'engagement'
- url transitions

demo: 
biro
unity

[https://rnplay.org/](https://rnplay.org/)

##Live Profiling Web Apps - Alex Russel

*(Live profiling done for few websites)*







