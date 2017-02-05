# PHPoole recipe: Service Worker

This repository should help to implement a [service worker](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers#what_is_a_service_worker) to run a [PHPoole](http://phpoole.org/) static website as a [Progressive Web App](https://developers.google.com/web/progressive-web-apps/).

## Prerequisites
* A [PHPoole](http://phpoole.org/) website
* A [supported browser](https://developer.microsoft.com/en-us/microsoft-edge/platform/status/serviceworker/)
* HTTPS

## Recipe

1. Add `manifest.webmanifest`
  * Add a [template file](/layouts/manifest.twig)
  * Add a [content file](/content/manifest.md)
2. Add `<link>` to manifest in head:  
`<link rel="manifest" href="{{ url('manifest.webmanifest') }}">`
3. Add `sw.js`
  * Add a [template file](/layouts/sw.js.twig)
  * Add a [content file](/content/sw.md)
4. [Register the service worker](/layouts/includes/regsw.js.twig) in the main template file:  
`{% if site.serviceworker is defined and site.serviceworker.enabled %}
{% include 'includes/regsw.js.twig' %}
{% endif %}`
5. Enable the service worker and define pre-cached files list in [config file](/phpoole.yml)!
