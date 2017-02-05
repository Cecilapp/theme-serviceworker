# PHPoole recipe: Service Worker

This repository should help you to implement a service worker to run your [PHPoole](http:://phpoole.org) static site as a [Progressive Web App](https://developers.google.com/web/progressive-web-apps/).

* [What is a service worker?](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers#what_is_a_service_worker)
* Prerequisites
  * A [supported browser](https://developer.microsoft.com/en-us/microsoft-edge/platform/status/serviceworker/)
  * HTTPS

## Recipe

1. Create a [manifest file](/static/manifest.json)
2. Add `sw.js`
  * Add a [template file](/layouts/sw.js.twig)
  * Add a [content file](/content/sw.md) (because PHPoole is driven by content ^^)
3. [Register the service worker](/layouts/includes/regsw.js.twig) in your [main template file](/layouts/index.html.twig)
4. Enable the service worker and define pre-cached files list in your [config file](/phpoole.yml)!
