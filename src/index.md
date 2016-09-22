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

<p class="media-container auto fill-w" style="width:65%">![Popeye](images/popeye.jpg)</p>
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

<p class="media-container fill-w">![Gartner Hype Cycle](images/gartner-hype-cycle.svg)</p>

--

# Maximising reach.

--

# Minimising friction.

<!-- The best of web and native -->

--

<p class="media-container fill-h">![Facebook web app](images/facebook.png)</p>
<p class="caption"><a href="http://wtfmobileweb.com">By Jules Jamison via http://wtfmobileweb.com</a></p>

--

<p class="media-container centre auto fill-w" style="width:80%">![LinkedIn app](images/linkedin-tweets.png)</p>

<!-- TODO if time: Use Reflector, record video of LinkedIn problem -->

--

<p class="media-container centre auto fill-w" style="width:80%">![Medium app](images/medium-peter.png)</p>

<!-- TODO if time: Use Reflector, record video of Medium problem -->

<!-- I'ts not just the Web... -->
<!--<p class="media-container fill-w" style="width:80%">![EasyJet app](images/easyjet-patrick.png)</p>-->

--

<blockquote>“Delays to loading web pages &amp; videos increase our heart rate and produce stress levels equivalent to watching a horror film.”</blockquote>
<p class="caption"><a href="http://www.telegraph.co.uk/technology/2016/03/17/stressed-out-it-could-be-your-slow-internet/">The Telegraph</a></p>

<!-- And according to other studies, stress can cause early death. So basically without service workers, we're killing people! -->

--

<!-- TODO maybe for next time: logos of companies using SWs in prod already - Guardian, FT?, WaPo... -->

<p class="media-container fill-w">![Rio Run](images/riorun-guardian.jpg)</p>
<p class="caption"><a href="http://riorun.theguardian.com">Rio Run by Guardian US Interactive Team - riorun.theguardian.com</a></p>

--

<p class="media-container fill-h">![AliExpress](images/aliexpress.gif)</p>
<p class="caption"><a href="https://developers.google.com/web/showcase/2016/aliexpress">AliExpress PWA increased conversions by over 100%</a></p>

<!-- TODO image of InspireHub -->

--

<p class="media-container auto fill-w" style="width:85%">![Google Web Showcase](images/google-web-showcase.png)</p>
### [developers.google.com/web/showcase/](https://developers.google.com/web/showcase/)

--

<p class="media-container fill-w">![Is Service Worker Ready?](images/isserviceworkerready.png)</p>
<p class="caption"><a href="https://jakearchibald.github.io/isserviceworkerready/">jakearchibald.github.io/isserviceworkerready/</a></p>

--

<!-- For Android, based on Chromium, available on Play Store for Samsung Galaxy devices -->

## Samsung Internet
<p class="no-margin"><img src="images/samsunginternet.png" alt="Samsung Internet" style="width:40%"></p>
<p class="caption"><a href="http://bit.ly/what-is-samsung-internet">bit.ly/what-is-samsung-internet</a></p>

--

<p class="media-container centre fill-w">![Samsung Internet browser share](images/statcounter-mobile-europe-sep2016.png)</p>

<!-- http://gs.statcounter.com/#mobile_browser-eu-monthly-201609-201609-bar -->

--

<!-- Why do we have our own browser? To provide the best experience for our users -->

* Optimised for hardware
* Integration with e.g. Gear VR, iris scanner
* Content blockers

--

<!-- Based on open standards and we contribute to them -->

<p class="media-container centre fill-h">![Service workers spec](images/service-workers-spec.png)</p>

<!-- Message is: we're here, we want to help, we're doing some cool stuff with PWAs, WebVR... -->
<!-- We're planning some cool stuff. And please get in touch if you need us. -->

--

<p class="media-container">![caniuse.com show all button](images/caniuse-showall.png)</p>
<p class="caption"><a href="http://caniuse.com">caniuse.com</a></p>

--

<p class="media-container fill-w auto" style="width:80%"><img src="images/remote-debugging.png" alt="Remote Debugging"></p>

## [bit.ly/debug-samsung-internet](https://medium.com/samsung-internet-dev/introducing-samsung-internet-for-developers-6c3a3be42f72#8f13)

-- 

<p class="media-container fill-w auto" style="width:80%"><img src="images/remotetestlab.png" alt="Samsung Remote Test Lab"></p>

## [developer.samsung.com/remotetestlab/](http://developer.samsung.com/remotetestlab/rtlDeviceList.action)

--

<p class="media-container fill-h">![Snapwat](images/snapwat.png)</p>
<p class="caption">[github.com/SamsungInternet/snapwat](https://github.com/SamsungInternet/snapwat)</p>

<!-- I wanted to develop a PWA myself... -->
<!--* HTTPS (Cloudflare)-->
<!--* Service worker-->
<!--* Web App Manifest-->
<!--* WebRTC-->

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

<!-- TODO add one on URLs not files -->
<!-- And one on sw-toolbox -->

--

## Client-side image downloads? There be dragons!

<p class="media-container auto fill-w" style="width:45%">![Dragon](images/dragon-donstewart.jpg)</p>
<p class="caption">By <a href="https://www.flickr.com/photos/don-stewart/2369281599">Don Stewart</a></p>

### [bit.ly/wicg-save-image](https://discourse.wicg.io/t/save-image-feature-on-mobile-platforms/1676)

--

## I still have work to do...

<p class="media-container auto fill-w" style="width: 70%">![getUserMedia caniuse.com](images/caniuse-getusermedia.png)</p>

--

## WebVR

<p class="media-container auto fill-w" style="width:70%">![Samsung Gear VR](images/samsung-gear-vr.jpg)</p>

### [developer.samsung.com/internet#gearvr-overview](http://developer.samsung.com/internet#gearvr-overview)

--

<p class="media-container auto fill-w" style="width:85%">![A-Frame Racer demo by Ada](images/aframe-racer-ada.png)</p>
### [https://github.com/SamsungInternet/a-frame-demos](github.com/SamsungInternet/a-frame-demos)

--

<p class="media-container fill-h">![Payment Request UI](images/payment-request-ui-chrome.png)</p>
<p class="caption"><a href="https://developers.google.com/web/fundamentals/primers/payment-request/">developers.google.com/web/fundamentals/primers/payment-request/</a></p>

<!-- Samsung Internet are also working on this - W3C Web Pay with credit card (first) and Samsung Pay (later) -->
<!-- and we're involved in the standard.. joined the W3C WG and contribute..-->

--

# PWAs <br> *&nbsp;*

--

# PWAs <br> *Pretty Wrecking Awesome*

--

<h1 class="no-margin">We'd like to help</h1> 

<p class="media-container fill-w auto" style="width: 30%">![Hello](images/hand-raised.png)</p>

--

<h1>Thanks!</h1>

<div class="contact">
  <p>[@poshaughnessy](https://twitter.com/poshaughnessy)</p>
  <p>[@sbrowserdevrel](https://twitter.com/sbrowserdevrel)</p>
  <p>[medium.com/samsung-internet-dev](https://medium.com/samsung-internet-dev)</p>
</div>
