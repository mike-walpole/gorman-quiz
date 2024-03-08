<script>
  import "../app.css";

</script>

<svelte:head>
	<script>
		///rudderstack below, customer io above
		setTimeout(() => {
			!(function () {
				'use strict';
				var sdkBaseUrl = 'https://cdn.rudderlabs.com/v3';
				var sdkName = 'rsa.min.js';
				var asyncScript = true;
				(window.rudderAnalyticsBuildType = 'legacy'), (window.rudderanalytics = []);
				var e = [
					'setDefaultInstanceKey',
					'load',
					'ready',
					'page',
					'track',
					'identify',
					'alias',
					'group',
					'reset',
					'setAnonymousId',
					'startSession',
					'endSession'
				];
				for (var t = 0; t < e.length; t++) {
					var n = e[t];
					window.rudderanalytics[n] = (function (e) {
						return function () {
							window.rudderanalytics.push([e].concat(Array.prototype.slice.call(arguments)));
						};
					})(n);
				}
				try {
					new Function('return import("")'), (window.rudderAnalyticsBuildType = 'modern');
				} catch (a) {}
				if (
					((window.rudderAnalyticsMount = function () {
						'undefined' == typeof globalThis &&
							(Object.defineProperty(Object.prototype, '__globalThis_magic__', {
								get: function get() {
									return this;
								},
								configurable: true
							}),
							(__globalThis_magic__.globalThis = __globalThis_magic__),
							delete Object.prototype.__globalThis_magic__);
						var e = document.createElement('script');
						(e.src = ''
							.concat(sdkBaseUrl, '/')
							.concat(window.rudderAnalyticsBuildType, '/')
							.concat(sdkName)),
							(e.async = asyncScript),
							document.head ? document.head.appendChild(e) : document.body.appendChild(e);
					}),
					'undefined' == typeof Promise || 'undefined' == typeof globalThis)
				) {
					var d = document.createElement('script');
					(d.src =
						'https://polyfill.io/v3/polyfill.min.js?features=Symbol%2CPromise&callback=rudderAnalyticsMount'),
						(d.async = asyncScript),
						document.head ? document.head.appendChild(d) : document.body.appendChild(d);
				} else {
					window.rudderAnalyticsMount();
				}
				window.rudderanalytics.load(
					'2YdILm3JlBuNWtOQaX8gWtqV6G6',
					'https://pctumichavxrvw.dataplane.rudderstack.com',
					{}
				);
			})();
			//segment below
			!(function () {
				var analytics = (window.analytics = window.analytics || []);
				if (!analytics.initialize)
					if (analytics.invoked)
						window.console && console.error && console.error('Segment snippet included twice.');
					else {
						analytics.invoked = !0;
						analytics.methods = [
							'trackSubmit',
							'trackClick',
							'trackLink',
							'trackForm',
							'pageview',
							'identify',
							'reset',
							'group',
							'track',
							'ready',
							'alias',
							'debug',
							'page',
							'once',
							'off',
							'on',
							'addSourceMiddleware',
							'addIntegrationMiddleware',
							'setAnonymousId',
							'addDestinationMiddleware'
						];
						analytics.factory = function (e) {
							return function () {
								if (window.analytics.initialized)
									return window.analytics[e].apply(window.analytics, arguments);
								var i = Array.prototype.slice.call(arguments);
								i.unshift(e);
								analytics.push(i);
								return analytics;
							};
						};
						for (var i = 0; i < analytics.methods.length; i++) {
							var key = analytics.methods[i];
							analytics[key] = analytics.factory(key);
						}
						analytics.load = function (key, i) {
							var t = document.createElement('script');
							t.type = 'text/javascript';
							t.async = !0;
							t.src = 'https://cdn.segment.com/analytics.js/v1/' + key + '/analytics.min.js';
							var n = document.getElementsByTagName('script')[0];
							n.parentNode.insertBefore(t, n);
							analytics._loadOptions = i;
						};
						analytics._writeKey = 'DGDv9h0UCpQ6YLRBgb9VzqMPh9JYX0xg';
						analytics.SNIPPET_VERSION = '4.16.1';
						analytics.load('DGDv9h0UCpQ6YLRBgb9VzqMPh9JYX0xg');
						analytics.page();
					}
			})();
		}, 5000);
	</script>
</svelte:head>


<slot />

<slot />