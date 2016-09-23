title: PWAs and the biggest browser you've probably never thought of
output: public/index.html
style: styles.css
script: script.js
controls: true

--

# Progressive web apps

## And the biggest browser you’ve probably never thought of 

<div class="contact">
  <p>Peter O'Shaughnessy</p>
  <p>[@poshaughnessy](https://twitter.com/poshaughnessy)</p>
</div>

--

# PWAs

--

## “Just websites that took all the right vitamins”

<img src="images/popeye.jpg" alt="Popeye" style="max-width:65%; max-height:60vh"/>
<p class="caption">By [Mike Mozart](https://www.flickr.com/photos/jeepersmedia/17144071448)</p>

--

<ul class="long-list">
    <li>Secure</li>
    <li>Offline</li>
    <li>App-like</li>
    <li>Web-like</li>
    <li>Engaging</li>
    <li>Sized to your device</li>
    <li>Up-to-date</li>
    <li>Manifest-ready</li>
</ul>

## &nbsp;

--

<ul class="long-list">
    <li>**S**ecure</li>
    <li>**O**ffline</li>
    <li>**A**pp-like</li>
    <li>**W**eb-like</li>
    <li>**E**ngaging</li>
    <li>**S**ized to your device</li>
    <li>**U**p-to-date</li>
    <li>**M**anifest-ready</li>
</ul>

## “SO AWESUM”

--

<img src="images/gartner-hype-cycle.svg" alt="Gartner Hype Cycle" style="min-width:85%"/>

--

# Maximising reach.

--

# Minimising friction.

--

<blockquote>“Delays to loading web pages &amp; videos increase our heart rate and produce stress levels equivalent to watching a horror film.”</blockquote>

[The Telegraph](http://www.telegraph.co.uk/technology/2016/03/17/stressed-out-it-could-be-your-slow-internet/)

--

<img src="images/facebook.png" alt="Facebook web app" style="min-height:75%; max-height: calc(96vh - 3em); margin-top:4vh"/>
<p class="caption">[By Jules Jamison via http://wtfmobileweb.com](http://wtfmobileweb.com)</p>

--

<img src="images/linkedin-tweets.png" alt="LinkedIn app" style="min-height:80%"/>

--

![Rio Run](images/riorun-guardian.jpg)
<p class="caption">[Rio Run by Guardian US Interactive Team - riorun.theguardian.com](http://riorun.theguardian.com)</p>

--

![AliExpress](images/aliexpress.gif)
<p class="caption">[AliExpress PWA increased conversions by over 100%](https://developers.google.com/web/showcase/2016/aliexpress)</p>

--

![Google Web Showcase](images/google-web-showcase.png)
## [developers.google.com/web/showcase/](https://developers.google.com/web/showcase/)

--
<img src="images/isserviceworkerready.png" style="max-height: calc(96vh - 3em); margin-top:4vh" alt="Is Service Worker Ready?"/>
<p class="caption">[jakearchibald.github.io/isserviceworkerready/](https://jakearchibald.github.io/isserviceworkerready/)</p>

--

## Samsung Internet
<p class="no-margin"><img src="images/samsunginternet.png" alt="Samsung Internet" style="width:40%"></p>
<p class="caption">[bit.ly/what-is-samsung-internet](http://bit.ly/what-is-samsung-internet)</p>

--

![Samsung Internet browser share](images/statcounter-mobile-europe-sep2016.png)

--

* Optimised for hardware
* Integration with e.g. Gear VR, iris scanner
* Content blockers

--

![Service workers spec](images/service-workers-spec.png)

--

<img src="images/caniuse-showall.png" style="max-height: calc(96vh - 3em); margin-top:4vh" alt="caniuse.com show all button"/>
<p class="caption"><a href="http://caniuse.com">caniuse.com</a></p>

--

<img src="images/remote-debugging.png" alt="Remote Debugging" style="max-width:85%"/>

## [bit.ly/debug-samsung-internet](https://medium.com/samsung-internet-dev/introducing-samsung-internet-for-developers-6c3a3be42f72#8f13)

-- 

<img src="images/remotetestlab.png" alt="Samsung Remote Test Lab" style="max-width:85%">

## [developer.samsung.com/remotetestlab/](http://developer.samsung.com/remotetestlab/rtlDeviceList.action)

--

<img src="images/snapwat.png" alt="Snapwat" style="max-height: calc(96vh - 3em); margin-top:4vh"/>
<p class="caption">[github.com/SamsungInternet/snapwat](https://github.com/SamsungInternet/snapwat)</p>

--

```javascript
const RESOURCES = [  
  '/',  
  '/index.html',
  '/css/styles.css',  
  '/build/bundle.js',  
  '/images/emojione/1f354.svg',  
  '/images/emojione/1f369.svg',
  ...
];
// Cache pre-defined assets on installation
self.addEventListener('install', event => {   
  function onInstall () {     
    return caches.open('cache-v1')
      .then(cache => {        
        cache.addAll( RESOURCES );        
      });  
  }   
  event.waitUntil(onInstall(event));
});
```

--

## Automatic cache list generation

* [github.com/GoogleChrome/sw-precache](https://github.com/GoogleChrome/sw-precache)
* [bit.ly/rollup-precache](https://gitlab.com/Rich-Harris/rollup-cache-manifest-example/tree/master)

### *But don't pre-cache too much!*

--

## Client-side image downloads? There be dragons!

<img src="images/dragon-donstewart.jpg" alt="Dragon" style="max-width:45%"/>
<p class="caption">By <a href="https://www.flickr.com/photos/don-stewart/2369281599">Don Stewart</a></p>

### [bit.ly/wicg-save-image](https://discourse.wicg.io/t/save-image-feature-on-mobile-platforms/1676)

--

## I still have work to do...

<img src="images/caniuse-getusermedia.png" alt="getUserMedia caniuse.com" style="max-width: 70%"/>

--

## WebVR

<img src="images/samsung-gear-vr.jpg" alt="Samsung Gear VR" style="max-width:70%"/>

### [developer.samsung.com/internet#gearvr-overview](http://developer.samsung.com/internet#gearvr-overview)

--

<img src="images/aframe-racer-ada.png" alt="A-Frame Racer demo by Ada" style="max-width:85%"/>

### [https://github.com/SamsungInternet/a-frame-demos](github.com/SamsungInternet/a-frame-demos)

--

<img src="images/payment-request-ui-chrome.png" alt="Payment Request UI" style="max-height: calc(96vh - 3em); margin-top:4vh"/>
<p class="caption"><a href="https://developers.google.com/web/fundamentals/primers/payment-request/">developers.google.com/web/fundamentals/primers/payment-request/</a></p>

--

<ul class="pwa">
    <li>Powerful</li>
    <li class="invisible">Wide-Reaching</li>
    <li class="invisible">Awesome</li>
</ul>

--

<ul class="pwa">
    <li>Powerful</li>
    <li>Wide-Reaching</li>
    <li class="invisible">Awesome</li>
</ul> 

--

<ul class="pwa">
    <li>Powerful</li>
    <li>Wide-Reaching</li>
    <li>Awesome</li>
</ul> 

--

<h1>We'd like to help</h1> 

--

<h1>Thanks!</h1>

<div class="contact">
  <p>[@poshaughnessy](https://twitter.com/poshaughnessy)</p>
  <p>[@sbrowserdevrel](https://twitter.com/sbrowserdevrel)</p>
  <p>[medium.com/samsung-internet-dev](https://medium.com/samsung-internet-dev)</p>
</div>
