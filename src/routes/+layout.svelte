<script>
  import "../app.css";

</script>

<svelte:head>
	<script>
		///rudderstack below, customer io above
		setTimeout(() => {
     
  !function(){var i="analytics",analytics=window[i]=window[i]||[];if(!analytics.initialize)if(analytics.invoked)window.console&&console.error&&console.error("Segment snippet included twice.");else{analytics.invoked=!0;analytics.methods=["trackSubmit","trackClick","trackLink","trackForm","pageview","identify","reset","group","track","ready","alias","debug","page","screen","once","off","on","addSourceMiddleware","addIntegrationMiddleware","setAnonymousId","addDestinationMiddleware","register"];analytics.factory=function(e){return function(){if(window[i].initialized)return window[i][e].apply(window[i],arguments);var n=Array.prototype.slice.call(arguments);if(["track","screen","alias","group","page","identify"].indexOf(e)>-1){var c=document.querySelector("link[rel='canonical']");n.push({__t:"bpc",c:c&&c.getAttribute("href")||void 0,p:location.pathname,u:location.href,s:location.search,t:document.title,r:document.referrer})}n.unshift(e);analytics.push(n);return analytics}};for(var n=0;n<analytics.methods.length;n++){var key=analytics.methods[n];analytics[key]=analytics.factory(key)}analytics.load=function(key,n){var t=document.createElement("script");t.type="text/javascript";t.async=!0;t.setAttribute("data-global-segment-analytics-key",i);t.src="https://cdn.segment.com/analytics.js/v1/" + key + "/analytics.min.js";var r=document.getElementsByTagName("script")[0];r.parentNode.insertBefore(t,r);analytics._loadOptions=n};analytics._writeKey="wpim2I8dtSIRCo7AlltyWyCvob14baF9";;analytics.SNIPPET_VERSION="5.2.0";
  analytics.load("wpim2I8dtSIRCo7AlltyWyCvob14baF9");
  analytics.page();
  }}();

 
        !function(){"use strict";var sdkBaseUrl="https://cdn.rudderlabs.com/v3";var sdkName="rsa.min.js";var asyncScript=true
        ;window.rudderAnalyticsBuildType="legacy",window.rudderanalytics=[]
        ;var e=["setDefaultInstanceKey","load","ready","page","track","identify","alias","group","reset","setAnonymousId","startSession","endSession"]
        ;for(var t=0;t<e.length;t++){var n=e[t];window.rudderanalytics[n]=function(e){return function(){
        window.rudderanalytics.push([e].concat(Array.prototype.slice.call(arguments)))}}(n)}try{
        new Function('return import("")'),window.rudderAnalyticsBuildType="modern"}catch(a){}
        if(window.rudderAnalyticsMount=function(){
        "undefined"==typeof globalThis&&(Object.defineProperty(Object.prototype,"__globalThis_magic__",{get:function get(){
        return this},configurable:true}),__globalThis_magic__.globalThis=__globalThis_magic__,
        delete Object.prototype.__globalThis_magic__);var e=document.createElement("script")
        ;e.src="".concat(sdkBaseUrl,"/").concat(window.rudderAnalyticsBuildType,"/").concat(sdkName),e.async=asyncScript,
        document.head?document.head.appendChild(e):document.body.appendChild(e)
        },"undefined"==typeof Promise||"undefined"==typeof globalThis){var d=document.createElement("script")
        ;d.src="https://polyfill.io/v3/polyfill.min.js?version=3.111.0&features=Symbol%2CPromise&callback=rudderAnalyticsMount",
        d.async=asyncScript,document.head?document.head.appendChild(d):document.body.appendChild(d)}else{
        window.rudderAnalyticsMount()}window.rudderanalytics.load("2daonypjdAKMmY7iErlfQTx6Wqt","https://gormanmicurxlr.dataplane.rudderstack.com",{})}();    


			
		}, 5000);
	</script>
</svelte:head>


<slot />

